<template>
  <div id="app">
    <input type="text" v-model="gioithieu" style="width: 30%"/>
        <h1>{{ten}}</h1>
        <h1>{{tuoi}}</h1>
    <input type="text" v-model="ten" :disabled="lock">
    <button @click="lock = !lock"> khóa</button>
    <br>
    <div :class="{doimau: color}">
      {{ ten}}
    </div>

    <test></test>
     <button @click="color = !color"> Đổi màu</button>
<!-- v-for -->
<ul id="example-2">
  <li v-for="(item, index) in items1" :key="index">
    {{ parentMessage }} - {{ index }} - {{ item.message }}
  </li>
</ul>
    <!-- an hien -->
    <br><br><br>
    <div v-show="show">
        <div v-bind:style="styleo" ></div>
        <div v-bind:style="styleo" ></div>
        <div v-bind:style="styleo" ></div>
        <div v-bind:style="styleo" ></div>
        <div v-bind:style="styleo" ></div>
        <div v-bind:style="styleo" ></div>
    </div>
    <div>
      <button @click="show = !show"> Ẩn hiện</button>
      <button @click="clickb++">click tăng</button>
      <button @click="clickb--">click giảm</button>
      <div>{{ clickb }}</div>
    </div>
  </div>
  
</template>

<script>
import test from './components/test.vue';

export default {
  name: 'App',
   el: '#example-2',
  data(){
    return {
      ten: 'Luu Quang Huy',
      tuoi: 30,
      ban: "bạn",
      nameage: "Tuổi",
      mes: '',
      lock: true,
      color: true,
      show: true,
      numberA:0,
       clickb: 0,
       styleo:{
          width: '40px',
          height: '40px',
          background: 'blue',
          float: 'left'
    },
    items: [
      { name: 'Cà phê' },
      { name: 'Trà đặc' },
      { name: 'Bò húc' }
    ],
     parentMessage: 'Parent',
    items1: [
      { message: 'Foo' },
      { message: 'Bar' }
    ]
    }
  }, computed:{
    gioithieu: {
            get: function() {
                return this.ban + " "+this.ten + " " + this.tuoi + " " + this.nameage;
            }
        }
  }, watch:{
mes: function(old, newm){
console.log(old);
console.log(newm);
}
  },
  components: {
        "test" : test,
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.doimau{
  background-color: aqua;
}
</style>
