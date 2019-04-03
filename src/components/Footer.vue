<template>
  <footer>
      <ul>
          <router-link v-for="(nav,i) in navList" :to="{name:nav.name,query:loginInfo}" :key="i" class="rli"  tag="li"  activeClass="active">
            {{nav.text}}
          </router-link>
          <li v-on:click="targetIndex">测试传值</li>
      </ul>
  </footer>
</template>
<script>
export default {
	  props : {
      loginInfo : {
          type : Object,
          required : false
      }
  },
  data(){
      return {
          navList : [
              {icon:"icon-menuHome",text:"首页",name:"Home1"},
              {icon:"icon-menuClass",text:"关于我们",name:"Home2"},
              {icon:"icon-menuShop",text:"我的",name:"Home3"},         
          ]
      }
  },
  created(){
     console.log(this.loginInfo) 
  },
  methods : {
      back(){
          this.$router.go(-1);
      },
      targetIndex(){
      	this.$emit('order','传值成功了！')
      }
  }
}
</script>
<style  scoped>
  ul{
  	margin:0px;
  	padding:0px;
  	display:flex;
  	justify-content:space-between;
  	align-items:center;
  	position:fixed;
  	bottom:0px;
  	width:100%;
  	 }
  ul>li{
  		width:33.333%;
  		height:30px;
  		text-align:Center;
  		line-height:30px;
  		list-style:none;
  		border:1px solid red;
  		color:white;
  		background-color: #00aeff;
  		cursor:pointer;
  	}

    
   
</style>

