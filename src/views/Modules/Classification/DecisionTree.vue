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
      <el-tooltip
        content="Know more about decision trees"
        effect="light"
        :open-delay="300"
        placement="top"
      >
        <base-button type="primary" @click.native="modals.notice = true"> About Decision Tree
        </base-button>
      </el-tooltip>
    
      <modal :show.sync="modals.notice">
        <template slot="header">
          <h5 slot="header" class="title">What is a decision tree? </h5>
        </template>
        <div class="instruction">
        <div class="row">
          <strong>
            <i class="tim-icons icon-book-bookmark text-primary"></i>What is it?
          </strong>
          <p class="description">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Suscipit dicta obcaecati at,
            earum eius possimus voluptates dolorem incidunt velit illum ad repellat, magnam quisquam
            aliquid tenetur eaque recusandae modi excepturi.
          </p>
        </div>
        </div>
        <div class="instruction">
        <div class="row">
          <strong>
            <i class="tim-icons icon-notes text-info"></i>These are its main features
          </strong>
          <p class="description">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Suscipit dicta obcaecati at,
            earum eius possimus voluptates dolorem incidunt velit illum ad repellat, magnam quisquam
            aliquid tenetur eaque recusandae modi excepturi.
          </p>
        </div>
        </div>
        <div class="instruction">
        <div class="row">
          <strong>
            <i class="tim-icons icon-paper text-success"></i>What kind of trees can we find?
          </strong>
          <p class="description">
            After you choose the type of system to control the inventory, you will need to fill the information required.
            The program gives the outputs associated to the system selected.
          </p>
        </div>
        </div>
        <div slot="footer" class="justify-content-center">
        <base-button type="primary" round @click.native="modals.notice = false">Finish</base-button>
        </div>
      </modal>
    </div>
    </div>
    <div class="col-lg-12" align="center">
        <div class="text-left">
            <el-tooltip
            content="Upload your own dataset" effect="light" :open-delay="300" placement="top">
            <el-input type="file" class="col-md-5 my-1" outlined id="external"></el-input>
            <base-button type="primary" @click.native="modals.notice = true" style="width:500px;">Submit yours</base-button>
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
            <base-button type="primary" @click.native="modals.notice = true" style="width:500px;">Submit predefined</base-button>
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
         :radius = "8"
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
</template>

<script>
import { Modal, BaseAlert } from "src/components";
import { tree } from 'vued3tree'
import { treeData } from 'src/views/Modules/Classification/Data.json'
export default {

  components: {
    tree,
    Modal
  },

  data() {
    return {
   //  treeData: treeData
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
        
        modals: {
        notice: false,
        sq: false,
        ss: false,
        rs: false
        }
        
        
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

