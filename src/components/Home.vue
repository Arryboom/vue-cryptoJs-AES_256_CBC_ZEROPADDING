<template>
  <div class="home">
    <h1>{{ msg }}</h1>
    <textarea rows="5" cols="50" value="" v-model="mingwen"/><input type="button" value="加密" @click="jiami()">
    <br><br>
    <textarea rows="5" cols="50" v-model="miwen"/><input type="button" value="解密" @click="jiemi()">
    <br>

  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      msg: 'AES_256_CBC_ZeroPadding',
      mingwen:"test_text",
      miwen:"",
      key:"wznxlssm"
    }
  },
  methods:{
    jiami:function(){ //加密

      this.miwen=this.getAES(this.mingwen,this.key) 
	  console.log(this.miwen)
    },
    jiemi:function(){ //解密
      alert(this.getDAes(this.miwen,this.key))
	  console.log(this.getDAes(this.miwen,this.key))
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
