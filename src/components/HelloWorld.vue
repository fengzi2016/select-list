
<template>
<!-- eslint-disable  -->
<div class="app" @click="closeList"> 
    <div class = 'app_normal_button' @click.stop="openList">
     <p> 新建 </p>
     </div>
      <div class="sel-wrap" v-if="select_options">
          <ul  class = 'select_options'>
            <li v-for="(item,index) in items" :key="index">
                <img :src="item.src">
                <a href="https://baidu.com">
                <p>
                {{item.word}}
                </p>
                </a>
            </li>
          </ul>
      </div>
   </div>
</template>

<script>
/* eslint-disable */ 
export default {
  name: 'HelloWorld',
  data () {
    return {
      select_options: false,
      items: [{word:'文档',src:'../../static/docs@2x.png'}, {word:'表格',src:'../../static/chart@2x.png'}, {word:'文件夹',src:'../../static/folder@2x.png'},{word:'导入',src:'../../static/upload@2x.png'}],
    }
  },
  methods:{
    openList(e){
    
      this.select_options = true;
    },
    closeList(){
       this.select_options = false;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.app{
  text-align: center;
  margin-left: 50%;

}
.app_normal_button{
  
  color:white;
  text-align: center;
  
  background:#41464b;
  border-radius:2px;
  width:168px;
  height:56px;
  border-radius: 2px;
  cursor: pointer;
}
.app_normal_button p{
  
  display: inline-block;
  vertical-align: middle
  
}
.sel-wrap{
position: relative;
top: 15px;
left: -40px;
/* display: flex; */
background:#ffffff;
border:1px solid #dddddd;
box-shadow:0 4px 12px 0 rgba(0,0,0,0.10);
border-radius:2px;
width:248px;
height:319px;
}
.sel-wrap:before{
  content:"";
  position: relative;
  top: -33px;
  border-bottom: 16px solid #ccc;
  border-left: 16px solid transparent;
  border-right: 16px solid transparent;

}
.sel-wrap:after{
  content:"";
  position: relative;
  top: -294px;
  border-bottom: 16px solid white;
  border-left: 16px solid transparent;
  border-right: 16px solid transparent;
  

}
ul {
  list-style-type: none;
  padding: 0;
  
}

li {
  /* display: inline-block; */
  margin: 0 10px;
  height: 100%;
  
  
}
img{
  vertical-align:text-bottom; 
  float: left;
  margin-left: 5vw;
  height: 100%;
}

.select_icons{
  float: left;
}
a{
  text-decoration: none;
  display: inline-block;
}
</style>
