<style type="text/css">
        #mygraph {
          width: 300;
          height: 400px;
          border: 1px solid lightgray;
          background:#d1d1d1;
        }
  </style>
   <script type="text/javascript"
   src="https://visjs.github.io/vis-network/standalone/umd/vis-network.min.js"></script>
<template>
    <div>
        <div>
            <h1 class="text-center"> DECISION TREE </h1>
        </div>
        <div class="col-lg-12" align="center">
        <div class="text-left">
            <el-tooltip
            content="Upload your own dataset" effect="light" :open-delay="300" placement="top">
            <el-input type="file" class="col-md-5 my-1" outlined id="external"></el-input>
            <base-button type="primary" @click.native="modals.notice = true">Submit yours</base-button>
            </el-tooltip>
        </div>
        </div>
        <br />
        <div class="text-left">
            <el-tooltip
            content="Upload the given dataset" effect="light" :open-delay="300" placement="top">
            <el-input type="file" class="col-md-5 my-1" outlined id="predefined"></el-input>
            <base-button type="primary" @click.native="modals.notice = true">Submit predefined</base-button>
            </el-tooltip>
        </div>
        <div align="right">
          <div class="col-sm-8">
            <label class="col-sm-2 col-form-label" style="font-size: 0.05 rem" align="right">N# Folds</label>
            <el-tooltip
                  content="Type the max depth"
                  effect="light"
                  :open-delay="300"
                  placement="top"
                >
              <input v-model="message" placeholder="0">
            </el-tooltip>
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
                  content="Type the max depth"
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
        </div>
    </div>
    
</template>
<script>

export default {
    data(){

        return{
            file: '',
        }

    },
    methods: {

        metodo1(){

        }
    }
}

</script>

<style>
</style>
