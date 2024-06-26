<template lang="html">
  <div>
    <h1>Counter -> <span>{{ counter }}</span></h1>
    <button @click="increment()"><span>Increment</span></button>
    <button @click="decrement()"><span>Decrement</span></button>
  </div>
  <img :src="imgUrl">
  <div>
    <!-- Class style binding -->
    <h4 :class="{hello:check}">Conditional rendering</h4>
    <!-- Conditional rendering -->
    <h1 v-if="check">The value is true</h1>
    <h1 v-else>The value is false</h1>
    <button @click="change()"><span>Change state</span></button>
    <h1 v-show="check">This got that v-show</h1>
    <ul>
      <!-- list rendering -->
      <li v-for="(sport, index) in sports" :key="index">{{ sport }}</li>
      <li v-for="object in objects" :key="object.id">{{ object.message }}</li>
    </ul>
    <!-- one way data binding-->
    <h3>{{ oneWayText }}</h3>
    <!-- two way data binding-->
    <h3>{{ twoWayText }}</h3>
    <input type="text" v-model="twoWayText">
  </div>
  <!-- <info-comp first-name="hehe" last-name="hehehehehehe"/>
  <info-comp first-name="hehe1"/>
  <info-comp :object-data='singleObject'/> -->
  <info-comp>
    Hehe I am using slots
  </info-comp>
  <slot-comp>
    <template #slotTitle>
      Card Slot
    </template>
    <template #default>
      <img :src="imgUrl">
    </template>
  </slot-comp>
  </template>

<script>
import InfoComp from '@/components/InfoComp.vue';
import SlotComp from '@/components/SlotComp.vue';
export default {
  data(){
    return{
      counter:0,
      imgUrl: "https://m.media-amazon.com/images/I/61dXTaEXjBL._AC_SL1500_.jpg",
      check: true,
      sports: ['soccer', 'rugby', 'darts'],
      objects: [
        { message: "hello there 1", id: 1 },
        { message: "hello there 2", id: 2 },
        { message: "hello there 3", id: 3 }
      ],
      singleObject: {
        name: 'Zen',
        surname: 'George'
      },
      oneWayText: 'hehe',
      twoWayText: 'hehe2.0',
    }
  },
  components:{
    InfoComp,
    SlotComp
  },
  methods: {
    increment() {
      this.counter++
    },
    decrement() {
      this.counter--
    },
    change() {
      this.check = !this.check
    }
  }
}
</script>

<style scoped>
  h1{
    color: blue;
}    

img{
  width: 200px;
  height: 200px
}

button{
  background-image: linear-gradient(to right, #007bff, #ffce00, #ee4b2b);
  background-size: 200px 100%;
  background-position: 0% 100%;
  animation: bounce 2s ease-in-out infinite;
  color: #fff;
  border: none;
  border-radius: 15%;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  margin: 10px;
  }

  @keyframes bounce {
  0% {
    background-position: 0% 100%;
  }
  50% {
    background-position: 100% 100%;
  }
  100% {
    background-position: 0% 100%;
  }
}

</style>