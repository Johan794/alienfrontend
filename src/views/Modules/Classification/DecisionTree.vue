<style type="text/css">
        #mygraph {
          width: 300;
          height: 400px;
          border: 1px solid lightgray;
          background:#d1d1d1;
        }
  </style>
   <script type="text/javascript" src="https://visjs.github.io/vis-network/standalone/umd/vis-network.min.js"></script>
<template>
    <div>
        <div>
            <h1 class="text-center"> DECISION TREE </h1>
    </div>
    <div class="col-lg-12" align="center">
        <div class="text-left">
            <el-tooltip
            content="Upload your own dataset" effect="light" :open-delay="300" placement="top">
            <base-button type="primary" @click.native="modals.notice = true">Submit yours</base-button>
            </el-tooltip>
        </div>
        <br />
        <div class="text-left">
            <el-tooltip
            content="Upload the given dataset" effect="light" :open-delay="300" placement="top">
            <base-button type="primary" @click.native="modals.notice = true">Submit predefined</base-button>
            </el-tooltip>
        </div>
      <form>
        <card>
          <div>
            <div class="row" align="right">
              <label class="col-sm-2 col-form-label" style="font-size: 0.05 rem">N# Folds</label>

              <div class="col-sm-8">
                <el-tooltip
                  content="Type the number of folds"
                  effect="light"
                  :open-delay="300"
                  placement="top"
                >
                  <base-input
                    v-model="title"
                    :error="getError('required')"
                  ></base-input>
                </el-tooltip>
              </div>
            </div>
            <div class="row"></div>
          </div>
        </card>
      </form>
    </div>
    <div id="mygraph"></div>
    <input class="col-sm-12 btn btn-outline-danger expand" type="button" v-on:click="nextStep" value="Next">
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
