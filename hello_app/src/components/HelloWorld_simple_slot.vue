<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
    <hr>
    <div><slot /></div>
  </div>
</template>


<script>
export default {
  name: 'HelloWorld',
  props: {
    title: String, 
  },
  data: function(){
    return {
      message: 'This is message.',
    };
  },
}
</script>


<style>
div {
  margin:0px;
  padding: 0px;
  text-align:left;
}
h1 {
  font-size:72pt;
  font-weight:bold;
  text-align:right;
  letter-spacing:-8px;
  color:#f0f0f0;
  margin:0px;
}
p {
  margin:0px;
  color:#666;
  font-size:16pt;
}
.inner {
  color:red;
  font-size:14pt;
}
</style>