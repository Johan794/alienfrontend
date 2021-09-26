<template>
    <div>
        <div>
            <h1 class="text-center"> DECISION TREE </h1>
    </div>
    <div class="col-12" align="left">
        <el-tooltip
        content="Upload your own dataset"
        effect="light"
        :open-delay="300"
        placement="top"
        >
        <base-button type="primary" @click.native="modals.notice = true">Submit yours</base-button>
      </el-tooltip>
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
