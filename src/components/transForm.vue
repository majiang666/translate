<template>
  <div class="transForm">
    <input type="text" v-model="keyWord" placeholder="请输入搜索词" class="search-input">
    <select v-model="optionSelect" class="search-select">
      <option value="en">English</option>
      <option value="zh">Chinese</option>
      <option value="ru">Russian</option>
      <option value="ko">Korean</option>
      <option value="ja">Janpenese</option>
    </select>
    <input type="button" value="翻译" @click="transBtn" class="search-btn">
  </div>
</template>

<script>
export default {
  name: 'transForm',
  data () {
    return {
      keyWord: '',
      optionSelect:''
    }
  },
  created(){
      this.optionSelect = 'en'
  },
  methods:{
      transBtn(){
          this.$emit("transdata",this.keyWord,this.optionSelect);
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    input{
        outline: none;
    }
    .search-input{
        width:400px;
        height:45px;
        line-height: 45px;
        border:solid 1px #dedede;
        padding:0 5px;
    }
    .search-select{
        width:100px;
        height:47px;
        border:solid 1px #dedede;
    }
    .search-btn{
        width:100px;
        height:47px;
        background: #f60;
        border:0;
        font-size:18px;
        color:#fff;
        vertical-align: middle;
        margin-top:-1px;
    }
</style>
