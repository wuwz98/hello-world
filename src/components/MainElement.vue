<template>
  <div class="MainElemet">

    <el-table stripe border v-if="url" :data="dataList" ref="multipleTable" style="width: 100%">
      <el-table-column v-for="(key) in Object.keys(dataList[0])"
                      :prop="key" :label="key" :key="Math.random(key)"  >
      </el-table-column>
    </el-table>
    
    <el-empty description="点击左侧导航栏显示数据" v-else></el-empty>

  </div>
</template>


<script>
import axios from 'axios';
import mainBus from '@/utils/mainBus';

export default {
  name: "MainElemet",
  data: function () {
    return {
      url: null,
      dataList: null
    }
  },
  mounted() {
    mainBus.$on(
      'url',
      res => {
        this.url = res;
        axios
          .get(this.url)
          .then(response => (
            this.dataList = response.data.data))
      }
    )
  },
}
</script>

<style>
td {
  width: 200px;
  overflow: hidden;
}

.MainElemet {
  padding: 20px;
}
</style>