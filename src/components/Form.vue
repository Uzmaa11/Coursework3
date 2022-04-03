<template>
<div>
<div id="urcart">
  <h2 style="margin-left: 30px;font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;font-size:30px;color:rgb(0, 0, 0);">Your Cart</h2>
 <div  class=card v-for='(lessons,index) in cart' :key="index">
       <h2 style="margin-left: 30px;font-family: Brush script MT;font-size:30px;color:rgb(0, 0, 0);" v-text="lessons.subject"></h2>
                 <figure>
                     <img  style="width: 300px;height:300px;margin-left:-20px;" v-bind:src="lessons.image">
                 </figure>
                 <p style="margin-left: 30px;color:rgb(0, 0, 0);;">Location: {{lessons.location}}</p>
                 <p style="margin-left: 30px;color:rgb(0, 0, 0);;">Price: {{lessons.price}}</p>
        <button style="margin-left:160px;margin-bottom:20px;height:50px;width:120px;background-color:rgb(209, 22, 22);color:rgb(255, 196, 0);border:4px solid  rgb(255, 196, 0);border-radius:30px;" @click="RemoveItem(lessons)">Remove</button>
    </div>

  <div id="chkout" style="background-color:rgb(255, 55, 5);border:4px solid black;border-radius:30px;">
    <h2  style="margin-left:530px;font-family:Brush script MT;font-size:40px;color:black;">Checkout</h2>
    <p>
      <strong style="margin-left:300px;color:white;">Name </strong>
      <input v-model="name" />
      <strong style="margin-left:150px;color:white;"> Address </strong>
      <input v-model="address" /><br><br>
      <button style="margin-left:450px;margin-bottom:20px;height:40px;width:250px;background-color:rgb(8, 8, 8);color:rgb(255, 196, 0);border:4px solid rgb(255, 196, 0);border-radius:30px;" v-on:click=submitForm()>Submit</button>
    </p>
  </div>
</div>
</div>
</template>

<script>
export default {
  name: "Form",
  props: ['cart'],
  data() {
    return {
      name: "",
      address: "",
    };
  },
  methods:{
     submitForm() {
                    alert('Order submitted!')
                },
      RemoveItem(lessons) {
                  for( let i=0;this.cart.length;i++){
                      if(this.cart[i].id==lessons.id){
                          this.cart.splice(i,1);
                      }
                  }
                   
                    
                },

  }
};
</script>