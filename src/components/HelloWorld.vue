<template>
  <div class="hello">
    
  </div>
</template>

<script>
import Qs from 'qs'

export default {
  name: 'HelloWorld',
  props: {

  },
  created(){
    let sdata = new FormData();
    sdata.append('username','test');
    sdata.append('password','test');
    let param = new URLSearchParams()
    param.append('username', 'test')
    param.append('password', 'test')
    let da = Qs.stringify({
      "username":"test",
      "password":"test"
    })
    this.$axios.post("http://localhost/login",da)
    .then(res=>{
      console.log(res)
    })
    .catch(error=>{
      console.log(error);
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
