<template>
  <div id="app" class="small-container">
    <router-view/>
  </div>
</template>
<style>
/* ##### Common Styles ##### */
body {
  color:black;
  margin:0;
  padding:0;
}

.blogName{
  text-align:left;
  padding: 1ex 1ex 1ex 2ex;
}

.subHeader{
  background-color:rgb(250,250,250);;
}

.subHeader a{
  color:black;
  text-decoration:none;
  padding:1ex;
}

.subHeader a:hover{
  text-decoration:none;
  color:white;
  background-color:rgb(150,150,150);;
  padding:2ex 1ex 2ex 1ex;
}

.wrapper{
  padding:4ex;
  font-size:120%;
  min-height:100%;
  text-align:center;
  align-items:center;
  --indent:16px;
}

.blogPost{
  padding:2ex;
}

.blogPost p{
  text-align:left;
}

.blogPost img{
  vertical-align:center;
  height:300px;
}

#footer {
  position:absolute;
  bottom:0;
  width:100%;
  height:50px;
}

</style>
