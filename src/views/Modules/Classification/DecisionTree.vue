<style type="text/css">
#mygraph {
  width: 400;
  height: 500px;
  border: 1px solid lightgray;
  background: #d1d1d1;
}
.tree {
  height: 800px;
}
#container{
   width: 400;
   height: 400px;
   display: flex;
   align-items: center;
}

.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: #fff;
  padding: 20px;
  border-radius: 15px;
  box-shadow: 3px 3px rgba(0, 0, 0, 0.4);
  z-index: 101;
}

</style>
<script
  type="text/javascript"
  src="https://visjs.github.io/vis-network/standalone/umd/vis-network.min.js"
></script>
<template>
<div>
  <div>
    <div class="col-12" align="center">
      <h1> DECISION TREE </h1>
    </div>
    <div class="col-12" align="center">
      <base-button type="primary" v-on:click = "showModal"> About Decision Tree </base-button>
    </div>
    <br>
    <div class="col-lg-12" align="center">
        <div class="text-left">
            <el-tooltip
            content="Upload your own dataset" effect="light" :open-delay="300" placement="top">
            <el-input type="file" class="col-md-5 my-1" outlined id="external"></el-input>
            <base-button type="primary" @click ="showModal = true" style="width:500px;">Submit yours</base-button>
            </el-tooltip>
            <label class="col-sm-2 col-form-label" style="font-size: 0.05 rem" align="right">N# Folds</label>
            <el-tooltip
                  content="Type the number of folds"
                  effect="light"
                  :open-delay="300"
                  placement="top"
                >
              <input v-model="message" placeholder="0">
            </el-tooltip>
            <br />
            <el-tooltip
            content="Upload the given dataset" effect="light" :open-delay="300" placement="top">
            <el-input type="file" class="col-md-5 my-1" outlined id="predefined"></el-input>
            <base-button type="primary" style="width:500px;">Submit predefined</base-button>
            </el-tooltip>
            
        </div>
        </div>
        <br />
        <div class="text-left">
            
        </div>
        <div align="right">
          <div class="col-sm-8">
            
          </div>
        </div>
        <div align="right">
            <div class="col-sm-8">
              <label class="col-sm-2 col-form-label" style="font-size: 0.05 rem" align="right">Max Depth</label>
              <el-tooltip
                  content="Type the max depth"
                  effect="light"
                  :open-delay="300"
                  placement="top"
                >
              <input v-model="m2" placeholder="0">
              </el-tooltip>
            </div>
        </div>
        <div align="right">
          <div class="col-sm-8">
              <label class="col-sm-2 col-form-label" style="font-size: 0.05 rem" align="right">Min size</label>
              <el-tooltip
                  content="Type the minimum size"
                  effect="light"
                  :open-delay="300"
                  placement="top"
                >
              <input v-model="m3" placeholder="0">
            </el-tooltip>
          </div>
        </div>
        <div id="mygraph">
        <input class="col-sm-12 btn btn-outline-danger expand" type="button" v-on:click="nextStep" value="Next">
        <div id="container"> 
         
       <tree :data="treeData"
         node-text="name" 
         duration="750" 
         layoutType="vertical" 
         :marginX = "30" 
         :marginY = "30"
         :radius = "10"
         :type = "tree"
         :nodeTextMargin = "6"
         :leafTextMargin = " 6 "
         :zoomable = "true"
         class="tree"
         >
         </tree>
      </div>
        </div>
    </div>
  </div>
</template>

<script>
import {BaseAlert } from "src/components";
import { tree } from 'vued3tree'
import Data from 'src/views/Modules/Classification/tree.json'
import Vue from "vue"
import Swal from 'sweetalert2'
import VueSimpleAlert from "vue-simple-alert";


Vue.use(VueSimpleAlert);
export default {
  components: {
    tree,
    BaseAlert,
    Data,
    Swal
  },

  data() {
    return {
       treeData: Data,
       showModal: function (event) {
          const Swal = require('sweetalert2')
          Swal.fire({
            title: 'Decision Trees',
            imageUrl: 'https://fhernanb.github.io/libro_mod_pred/images/fit_unfit.png',
            imageAlt: 404,
            imageHeight: 312,
            text: 'A decision tree is a map of the possible outcomes of a series of related decisions. A decision tree usually starts with a single node and then branches into possible outcomes. Each of those outcomes creates additional nodes, which branch into other possibilities. This gives it a tree-like shape.',
            imageAlt: 'A tall image'
          })
       }
      /*
       treeData: {

            name: "Padre",
            children: [
                {
                    name: "Hijo 1",
                     children: [{name: "Nieto"}, {name: "Nieto 2"}]
                },
                {
                    name: "Hijo 2",
                    children: [{name: "Nieto 3"}, {name: "Nieto 4"}]
                }
            ]
        },
        */

        /*modals: {
         notice: false  
         
         sq: false,
         ss: false,
         rs: false
        }
        */
    };
  },

  methods: {
    metodo1() {
    },
  }

  
};
</script>

<style>
button{
  min-width:100px
}
</style>
