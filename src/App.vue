 
 <style>
            #cartbtn{
             margin-top: -20px;
            
            }
            .card {
              border: 4px solid rgb(0, 0, 0);
              border-radius: 8px;
              transition: 0.3s;
              width: 30%;
              background-color: rgb(255, 255, 255);
              margin-bottom:30px;
              margin-top: 30px;
              display: inline-block;
              margin-left:25px;
            }
            
            .card:hover {
              box-shadow: 0 8px 16px 0 rgba(33, 39, 2, 0.2);
            }
            body{
                background-color:rgb(255, 196, 0);;


            }
            </style>
<template>

  <div id="app">
           
    <header style="background-color:rgb(0, 0, 0);font-family:monospace;height:100px">
       <img style="height:90px;display: flex;" src="header1.png"><br>
       <img style="height:50px;display:flex;margin-left:110px;margin-top:-80px;" src="header.png">
       <button  style="margin-left:980px;visibility: hidden;height:50px;border:4px solid white;border-radius:20px;width:200px;background-color:rgb(163, 156, 154);color:rgb(0, 0, 0);" id="cartbtn" @click="showCheckout()">
        {{ this.cart.length }}
        Shopping cart
      </button>
    </header>


    <main>
     <div v-if="showlesson">
     <lessons-list  @addlessons="addToCart"></lessons-list>
     </div>
     <div v-else>
      <checkout  :cart="cart"></checkout>
     </div>
    </main>
  </div>
</template>
<script>

import lessonsList from "./components/lessonsList.vue";
import checkout from "./components/Form.vue";
export default {
  name: "App",
  components: {
    lessonsList,
    checkout,
  },

  data() {
    return {
      sitename: "After school Activities",
      cart: [],
       showlesson: true,
    };
  },

  methods: {
    showCheckout() {
       if (  this.showlesson = this.showlesson ? false : true)
                    document.getElementById("lsn").style.display='contents';
                    else 
                    document.getElementById("lsn").style.display='none';
                    document.getElementById("urcart").style.display='contents';
    },
    addToCart(lessons) {
     console.log("addLessons event received by the root component.");
      this.cart.push(lessons);
       document.getElementById("cartbtn").style.visibility='visible';
    },
  },
};
</script>