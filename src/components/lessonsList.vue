<template>
  <div>
    <div id="lsn">
    <div  class="card" v-for="lessons in lessons" :key="lessons.id">
      <h2 style="margin-left: 30px;font-family: Brush script MT;font-size:30px;color:rgb(0, 0, 0);">{{lessons.subject}}</h2>
      <figure>
        <img  style="width: 300px;height:300px;margin-left:-20px;" v-bind:src="lessons.image" />
      </figure>
      <p style="margin-left: 30px;color:rgb(0, 0, 0);">Location: {{lessons.location}}</p>
      <p style="margin-left: 30px;color:rgb(0, 0, 0);">Price: {{lessons.price}}</p>
      <p style="margin-left: 30px;color:rgb(0, 0, 0);">Available spaces: {{ lessons.availableInventory}}</p>
      
      <button style="margin-left:160px;margin-bottom:20px;height:50px;width:120px;background-color:rgb(8, 8, 8);color:rgb(255, 196, 0);border:4px solid rgb(255, 196, 0);border-radius:30px;" @click="add(lessons)">Add to cart</button>
    </div>
  </div>
  </div>
</template>
 
<script>
export default {
  name: "lessonsList",
  data() {
    return {
      lessons: [
         {
    "id": 1,
    "subject": "Dance",
    "location": "London",
    "price": 7500,
    "image": "dance.png",
    "availableInventory": 5,
  
  },
  {
      "id": 2,
      "subject": "Cooking",
      "location": "Bristol",
      "price": 5000,
      "image": "cooking.png",
      "availableInventory": 5,
    
    }, {
      "id": 3,
      "subject": "Art",
      "location": "England",
      "price": 1300,
      "image": "art.png",
      "availableInventory": 5,
    
    },
    {
      "id": 4,
      "subject": "Swimming",
      "location": "Berlin",
      "price": 7000,
      "image": "swimming.png",
      "availableInventory": 5,
    
    },
    {
      "id": 5,
      "subject": "Robotics",
      "location": "Tokyo",
      "price": 3000,
      "image": "robotics.png",
      "availableInventory": 5,
    
    },
    {
      "id": 6,
      "subject": "Chess",
      "location": "Moscow",
      "price": 1000,
      "image": "chess.png",
      "availableInventory": 5,
    
    },
    {
      "id": 7,
      "subject": "Yoga",
      "location": "Rio",
      "price": 6000,
      "image": "yoga.png",
      "availableInventory": 5,
    
    },
    {
      "id": 8,
      "subject": "Baseball",
      "location": "India",
      "price": 2000,
      "image": "baseball.png",
      "availableInventory": 5,
    
    },
    {
      "id": 9,
      "subject": "Basketball",
      "location": "Ireland",
      "price": 3000,
      "image": "basketball.png",
      "availableInventory": 5,
    
    },
    {
      "id": 10,
      "subject": "Badminton",
      "location": "Denver",
      "price": 4000,
      "image": "badminton.png",
      "availableInventory": 5,
    
    },
    {
      "id": 11,
      "subject": "Music",
      "location": "Atlanta",
      "price": 2050,
      "image": "music.png",
      "availableInventory": 5,
    
    },
    {
      "id": 12,
      "subject": "Gymnastic",
      "location": "Dubai",
      "price": 3050,
      "image": "gymnastic.png",
      "availableInventory": 5,
    }
      ],
    };
  },
  methods: {
    add(lessons) {
      console.log("added lessons", lessons.id);
      this.$emit('addlessons',lessons);
      console.log(lessons.availableInventory--);
    },
     cartCount(id) {
                    let count = 0;
                    for (let i = 0; i < this.cart.length; i++) {
                        if (this.cart[i] === id) {
                            count++;
                        }
                    }
                    return count;
                },
  },
};
</script>