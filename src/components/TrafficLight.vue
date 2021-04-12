<template>
<div style="position: relative;
    bottom: 60px;top: -25vw;">
<img src="./wp3638802.jpg" id="demo">
 <div>{{myVal}}</div>
 <div class="author"> Traffic Light Application</div>
 <p class="lwa">Made By : Nolwazi Mlonzi</p>
<span id="red" class="circle" @click="reset" :style="{backgroundColor:red}"></span>
<span id="orange" class="circle" :style="{backgroundColor:orange}" @click="reset"></span>
<br>
<span id="green" class="circle" :style="{backgroundColor:green}" @click="startPause"></span>
<br>
<div class="myDiv" style="">
  <img class="traffic" src="../assets/traffic_light_PNG56243.png">
</div>
</div>
</template>

<script>
export default {
  data : function data()
  {
    var data =
    {
      speed:1000
      ,ctr:0
      ,green:""
      ,orange:""
      ,red:""
      ,ivl:0
    }
    return data;
  }
  ,computed: {
      myVal() {
        if (this.ivl === 0) {
            // start the interval timer
            this.updateTimer()
        }
        return this.ctr
      }
  },
  watch: {
      speed() {
        this.updateTimer()
      }
  }
  ,methods:
  {
     updateTimer() {
       var self = this;
          clearInterval(this.ivl)
          this.ivl = setInterval(()=>{
                console.log('tick...')
                this.ctr = this.ctr + 1
                if (this.ctr <= 5)
                {
                  self.green = "#000";
                  self.red = "red";
                  self.orange = "#000";
                  console.log('tick..we reached 5.')
                }
                else if (this.ctr <= 10)
                {
                  self.green = "#000";
                  self.orange = "gold";
                  self.red = "#000";
                  console.log('tick..we reached 10.')
                }
                else if (this.ctr <= 15)
                {
                  self.green = "green";
                  self.orange = "#000";
                  self.red = "#000";
                  console.log('tick..we reached 15.')
                }
                else if(this.ctr ==16)
                {
                  this.ctr = 0;
                  console.log('tick..reset.')
                }

          }, this.speed)
      }
      ,startPause : function startPause() 
      {
          if (this.running == 0) 
          {
              this.running = 1;
              this.increment();
              document.getElementById('startPause').innerHTML = 'Pause';
          } 
          else 
          {
              this.running = 0;
              document.getElementById('startPause').innerHTML = 'Resume';
          }
      }
      ,reset : function reset()
      {
          this.this.running = 0;
          this.time = 0;
          document.getElementById('output').innerHTML = '00:00:00';
          
          document.getElementById('startPause').innerHTML = 'Start';
    
      }
    }
}
</script>
<style>
.traffic
{
  width:400px;
  height: 600px;
  position: relative;
  z-index: 1;
}
.circle
{

  padding: 30px;
  opacity:  0.98;
  border-radius: 50%;
  position: relative;
  z-index: 3;
}
#green
{
      bottom: 315px;
    left: 0px;
    /* height: 17vh; */
    padding-top: 109px;
    padding-left: 110px;

}
#red
{
   bottom: 674px;
    left: 71px;
    /* height: 17vh; */
    padding-top: 14vh;
    padding-left: 110px;
}
#orange
{
    bottom: 486px;
    right: 67px;
    height: 20vh;
    padding-top: 15vh;
    padding-left: 110px;
}
#demo
{
  position: relative;
  z-index: 1;
}
.myDiv
{
  position: relative;
  z-index: 2;
      bottom: 115vh;
}
.lwa
{
  font-size: 28px;
  font-family: cursive;
  right:60vh;
  bottom: 80vh;
  position: relative;
  z-index: 3;
  color: #ccc;
}
.author
{
  font-size: 50px;
  font-family: cursive;
  right:60vh;
  bottom: 90vh;
  position: relative;
  z-index: 3;
  color: lightblue;
}
body
{
  overflow: hidden;
}
</style>
