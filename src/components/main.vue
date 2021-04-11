<template>
  <div style="background-color:#000;width: 100%;
    margin-top: -63px;
    height: 100vh;">
    <template v-if="myTime =='day'">
    <div>
       <table style="width:100%;height: 94vh;" border="0">
          <tr>
           <td style="width:30%">
        <div style="padding:5%; height:'86vh'">
        <span style="">Switch LightBulb Application</span>
      <img id="myImage" @click="changeImage" src="../assets/myOff.png" style="width: 49vh;
    margin-left: 10px;
    height: 339px;
    border-radius: 10px;
    position: relative;
    top: 12vh;">
        </div>
            </td><td width="70%">
        <div :style="{backgroundImage:'night.jpeg',height: '86vh'}">
        <img src="./night.jpg" style="position:relative;z-index:1;height:500px;width: 135vh;
    margin-left: 15px;"/>
      <img id="myImage" @click="changeImage" src="../assets/pic_bulboff.gif" style="position:relative;z-index:2;bottom: 52vh;" width="100" height="180">
        </div>
        </td>
        </tr>
        </table>
    </div>
  </template>
  <template v-else-if="myTime =='night'">
    <div>
       <table style=" yellow;width:100%; height: 94vh;" border="0">
          <tr>
           <td style="width:30%">
        <div style="padding:5%;height: 86vh;">
<span style="">Switch LightBulb Application</span>
      <img id="myImage" @click="changeImage" src="../assets/myOn.png" style="width: 49vh;
    margin-left: 10px;
    height: 339px;
    border-radius: 10px;
    position: relative;
    top: 12vh;">
        </div>
            </td><td width="70%">
        <div :style="{backgroundImage:'night.jpeg',    height:'86vh'}">
        <img src="./night.jpg" style="position:relative;z-index:1;height:500px;width: 135vh;
    margin-left: 15px;"/>
      <img id="myImage" @click="changeImage" src="../assets/pic_bulbon.gif" style="position:relative;z-index:2;bottom: 52vh;" width="100" height="180">
        </div>
        </td>
        </tr>
        </table>
    </div>
  </template>
  <h3><i>Made By: Nolwazi Mlonzi</i></h3>
  </div>
</template>

<script>
export default {
  data: function data ()
  {
    var data ={ myTime:"night"}
    return data;
  }
,methods:
{

changeImage:function changeImage() {
  //var image = document.getElementById('myImage');
  if (this.myTime =="day") {
    this.myTime ="night";
  } else {
    this.myTime="day";
  }
}
,interval:function interval ()
{
    var timer ="100";
    return timer;

}
}
 ,mounted:function mounted()
    {
        var self = this;
        setInterval(function()
        {
          console.log("Hello world");
        },self.interval);

    }
}
</script>
<style>
span{
      font-size: 33px;
    line-height: 2;
    font-weight: bold;
    font-family: cursive;

}
</style>