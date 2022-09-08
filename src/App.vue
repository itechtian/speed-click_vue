<template>
  <div>
<!--    <h1>{{ userInfo.name }}</h1>-->
<!--    <h1>{{ userInfo.age }} years</h1>-->
<!--    <h1>{{ userInfo.country }}</h1>-->
<!--    <p>{{homeParagraph}}</p>-->
   {{count}}
    <div class="count-div">
          {{count <= 0 ? count = 0 : count}} km/s
        </div>
    <div>
      <button v-on:click="count++" class="btn">{{buttonValue.increment}}</button>
      <button v-on:click="count--" class="btn">{{buttonValue.decrement}}</button>
      <button v-on:click="count=0" class="btn">{{buttonValue.reset}}</button>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      userInfo:{
            name:'Clark',
            age:40,
            country:'Nigeria'
        },

        homeParagraph:"this is a paragraph, on my page.",
         buttonValue:{
             increment:'Increase',
              decrement:'Decrease',
              reset: 'Reset'
         },
        count:0


    }
  }
}
</script>

<style>
.count-div{
  font-size: 300px !important;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 90vh;
  border: solid red;
}

.btn{
  width: 10%;
  height: 5vh;
  margin: 2%;
}
</style>
