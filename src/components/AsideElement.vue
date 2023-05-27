<template>
  <div class="AsideElement">


    <el-row class="tac">
      <el-col :span="24">
        <el-menu class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose" background-color="#545c64"
          text-color="#fff" active-text-color="#ffd04b">

          <div v-on:click="setUrl(1)"><el-submenu index="1">
              <template slot="title">
                <i class="el-icon-warning"></i>
                <span>disease</span>
              </template>
            </el-submenu>
          </div>

          <div v-on:click="setUrl(2)">
            <el-submenu index="2">
              <template slot="title">
                <i class="el-icon-first-aid-kit"></i>
                <span>medication</span>
              </template>
            </el-submenu>
          </div>

          <div v-on:click="setUrl(3)">
            <el-submenu index="3">
              <template slot="title">
                <i class="el-icon-s-release"></i>
                <span>symptom</span>
              </template>
            </el-submenu>
          </div>

          <div v-on:click="setUrl(4)">
            <el-submenu index="4">
              <template slot="title">
                <i class="el-icon-s-order"></i>
                <span>treatment</span>
              </template>
            </el-submenu>
          </div>

        </el-menu>
      </el-col>
    </el-row>



  </div>
</template>

<style>
.AsideElement {
  padding-top: 20px;
  padding-left: 20px;
}
</style>

<script>
import mainBus from '@/utils/mainBus.js';

export default {
  name: "AsideElement",
  data() {
    return {
      indexToURL: {
        1: "http://localhost:8001/wwz/diseaseController/all",
        2: "http://localhost:8001/wwz/medicationController/all",
        3: "http://localhost:8001/wwz/symptomController/all",
        4: "http://localhost:8001/wwz/treatmentController/all"
      },
      urlInAside: null,
    }
  },
  methods: {
    setUrl(index) {
      console.log(index);
      this.urlInAside = this.indexToURL[index];
      console.log(this.urlInAside)
      mainBus.$emit('url', this.urlInAside)
    }
  }
}
</script>