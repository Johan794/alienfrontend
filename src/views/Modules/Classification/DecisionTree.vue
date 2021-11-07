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
        <div>
            <h1 class="text-center"> DECISION TREE </h1>
            <h2>What is a Decision Tree ?</h2>
             <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Placeat est ullam distinctio officia aut non libero facilis cumque ab incidunt itaque tempora, magni debitis impedit officiis doloremque. Hic, accusamus deleniti.</p>
            <br>
            <h2> These are its main features</h2>
            <article>
              <ul>
                <li>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad praesentium suscipit consequuntur unde aperiam, soluta odio assumenda asperiores sed sunt optio similique nisi minus consectetur voluptatum molestias. Quia, porro reiciendis?</li>
                <li>Dolor nostrum veritatis, atque in sed vel quod maxime quis sunt natus cupiditate consectetur iure culpa. Dolor officiis nam, vel vero deleniti veritatis temporibus? Ullam explicabo optio dignissimos ducimus quas.</li>
                <li>Asperiores tempora illo reiciendis facilis? Sit dolore omnis maxime laborum debitis repellat esse impedit mollitia deserunt error facilis cum natus rem praesentium voluptate at, sint rerum consequatur, soluta et accusamus?</li>
                <li>Commodi laboriosam ab distinctio illo tempora ullam molestias suscipit quaerat dicta voluptates temporibus facere in rerum, iusto accusantium. Doloribus animi facilis voluptas minima fuga ex eos voluptates odio quia asperiores?</li>
                <li>Minus pariatur ipsa ipsam. Temporibus reprehenderit autem eligendi veritatis veniam dolorum magni delectus commodi suscipit quidem, natus laboriosam. Vero sequi et quae libero voluptates temporibus. Suscipit tempore corporis velit quas.</li>
              </ul>
            </article>
            <br>
            <h2>What kind of trees can we find?</h2>
            <ul>
              <li><h3>Calssfication Tree</h3></li>
              <li><h3>Regression Tree</h3></li>  
            </ul>

            <br>
            
            <h2>What about this implementation?</h2>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Suscipit dicta obcaecati at, earum eius possimus voluptates dolorem incidunt velit illum ad repellat, magnam quisquam aliquid tenetur eaque recusandae modi excepturi.</p>
     
           <br>

           <h2 class="text-center">Classsfication Tree</h2>

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
  </div>
</template>

<script>
import { tree } from 'vued3tree'
import { treeData } from 'src/views/Modules/Classification/Data.json'
export default {

  components: {
    tree,
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

