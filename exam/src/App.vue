<template>
  <div id="app">
    <div class='container'>
      <img src="../static/logo-main.svg">
      <img src="../static/lemon-bear.png">
    </div>
    <div class='container'>
      <label>排序:</label>
      <select v-model="selected" @change="sortOrder()">
        <option value="reward" >報酬率</option>
        <option value="closePrice">收盤價</option>
      </select>
      <select v-model="order" @change="sortOrder()">
        <option value="desc">高至低</option>
        <option value="asc">低至高</option>
      </select>
      <input type="checkbox" value="specialStock" v-model="specialStock" @change="checkSpecial()">
      <label>只顯示特選商品</label>
      <table class="table" style="width:100%">
        <thead>
          <tr>
            <th>Id</th>
            <th>名稱</th>
            <th>報酬率</th>
            <th>特選商品</th>
            <th>收盤價</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(item, index) in data" :key="index">
            <td>{{item.id}}</td>
            <td>{{item.name}}</td>
            <td>{{item.reward}}</td>
            <td>{{convertedBoolean(item)}}</td>
            <td>{{item.closePrice}}</td>
          </tr> 
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import rdata from "./data/data.json"
export default {
  name: 'app',
  data () {
    return {
      selected: 'reward',
      order:'desc',
      specialStock:false,
      data :rdata,
    }
  },
  methods:{
    convertedBoolean: item => item.specialStock? "是":"否",
    sortOrder(){
      let order = this.order
      let selected = this.selected

      if(order =='asc'){
        this.data.sort((a, b) => (a[selected] - b[selected]))
      }else{
        this.data.sort((a, b) => (b[selected] - a[selected]))
      }
     
    },
    checkSpecial(){
      if(this.specialStock){
        this.data = this.data.filter(item => item.specialStock==true)
      }else{
        this.data = rdata
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 20px;
}
.container img {
  height: 40px;
  width: auto;
  margin-bottom: 20px;
}
</style>
