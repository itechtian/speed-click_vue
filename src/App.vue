<template>
  <body>
    
 
  <div class="page">
<!--    <h1>{{ userInfo.name }}</h1>-->
<!--    <h1>{{ userInfo.age }} years</h1>-->
<!--    <h1>{{ userInfo.country }}</h1>-->
<!--    <p>{{homeParagraph}}</p>-->

<form v-on:submit.prevent="getUserName">
  <label for="fname">What's your name?</label><br>
  <input type="text" id="name" name="name"><br>
  <button type="submit">Enter</button>
</form>
  <h1>Test your click speed XD</h1>
  <div class="stopwatch">
        <h1>Timer</h1>
        <h1 id="display">00:00:00</h1>
        <button id="handler" v-on:click="startStop">Start</button>
        <button v-on:click="reset">Reset</button>
        </div>
    <div class="count-div">
      
          {{count <= 0 ? count = 0 : count}} clks/s
        </div>
        
    <div class="buttons">
      <button v-on:click="count++" class="btn">{{buttonValue.increment}}</button>
      <button v-on:click="count--" class="btn">{{buttonValue.decrement}}</button>
      <button v-on:click="count=0" class="btn">{{buttonValue.reset}}</button>
      
      
    </div>
    <div>
    <table>
    <tr>
    <th>Highscore</th>
  </tr>
  <tr>
    <td></td>
  </tr>

  
    </table>
    </div>
  </div>
</body>
</template>

<script>
export default {
        data() {
          return{
         buttonValue:{
             increment:'Increase',
              decrement:'Decrease',
              reset: 'Reset'
         },

         count:0
          }

          


        //  highScore:{
        //   highest: 'count'
        //  },
         
        
        },
        methods: {
          getUserName() {
           let userName = document.getElementById('name').value
           console.log(userName)
           alert('Welcome '+ userName + '!')
          },

          startTime() {
           seconds++
        if(seconds/60 === 1) {
              seconds=0
              minutes++

          if(minutes/60 === 1) {
               minutes = 0
               hours++
          }
        }

        if(seconds < 10) {
           displaySeconds = '0' + seconds.toString()
        }
        else {
          displaySeconds = seconds
        }


        if(minutes < 10) {
          displayMinutes = '0' + minutes.toString()
        }
        else {
          displayMinutes = minutes
        }

        if(hours < 10) {
          displayHours = '0' + hours.toString()
        }
        else {
          displayHours = hours
        }

        document.getElementById('display').innerHTML = displayHours + ':' + displayMinutes + ':' + displaySeconds

        
       },
       
       startStop() {
        if(status == 'Stopped')
        {
          interval = window.setInterval(this.startTime,1000)
          document.getElementById('handler').innerHTML = 'Stop'
          status = 'Started'
        }
       
        else if(
          status == 'Started'
        ) {
          window.clearInterval(interval)
          document.getElementById('handler').innerHTML = 'Start'
          status = 'Stopped'
          console.log('hello')

        }

        },

        reset() {
        seconds = 0
        hours = 0
        minutes = 0

        window.clearInterval(interval)
        document.getElementById('display').innerHTML = '00:00:00'
        document.getElementById('handler').innerHTML = 'Start'
        status = 'Stopped'
       }

          
        }
        
        
      } 
      let seconds = 0
       let minutes = 0
       let hours = 0

       let displaySeconds = 0
       let displayMinutes = 0
       let displayHours = 0

       let status = 'Stopped'
       let interval = ''
        
         
       
     
       
</script>

<style>
.count-div{
  font-size: 150px;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50vh;
  border: solid black;
  background: linear-gradient(to right, lightblue, white);
  margin: 0;
}

.stopwatch{
  align-items: left;
  justify-self: left;
}

h1{
font-size: 50px;
text-align: center;
font-family:  verdana;
color: black;
}

.btn{
  align-items: center;
  width: 10%;
  height: 5vh;
  margin: 2%;
  background-color: white;
  border: 2px solid black;
  border-radius: 6px;
}
.buttons > button:hover {
    background-color: lightblue;
}

body{
  background-color: lightblue;
}

input[type=text] {
  border: 2px solid black;
  border-radius: 6px;
  transition: width 0.4s ease-in-out;
  width : 10%;
}

input[type=text]:focus {
  background-color: rgb(224, 220, 220);
  width: 30%;
}

button[type=submit] {
  background-color: rgb(224, 220, 220);
  cursor: pointer;
  width: 3.7cm;
  border: 2px solid black;
  border-radius: 6px;
}

table, th, td{
  border: 1px solid;
}
</style>
