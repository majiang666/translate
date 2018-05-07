<template>
  <div id="app">
    <h1>翻译</h1>
    <h5>简单 / 快捷 / 小巧</h5>
   <TransForm @transdata="showData"></TransForm>
   <transShow v-text="transRes"></transShow>
  </div>
</template>

<script>
import TransForm from './components/transForm'
import TransShow from './components/transShow'
export default {
  name: 'App',
  data(){
    return {
      transRes:''
    }
  },
  methods:{
    showData(word,select){
      if(word == ''){
        alert('请输入关键词');
        return;
      }else{
        this.$ajax.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180507T013532Z.416c3dd9adf82183.f65cff23c4628135afe0b21ca33cf8497bf069ae&lang='+select+'&text='+word)
        .then((res) => {
          console.log(res);
          this.transRes = res.data.text[0];
        }).catch((err) => {
          console.log(err);
        });
      }
    }
  },
  components: {
    TransForm,
    TransShow
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
