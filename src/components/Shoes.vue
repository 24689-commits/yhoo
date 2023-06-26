<template>
    <div id="table">
    
        <div>
            <h1>id</h1>
        <ul v-for="shoe in Shoes" :key="shoe.id">
          {{ shoe.id }}
        </ul>
        </div>

        <div>
            <h1>color</h1>
        <ul v-for="shoe in Shoes" :key="shoe.color">
            {{ shoe.color }}
          </ul>
        </div>
        <div>
            <h1>size</h1>
          <ul v-for="shoe in Shoes" :key="shoe.size">
            {{ shoe.size }}
          </ul>
        </div>
       
    </div>
  </template>
  <script>
  export default {
    data() {
      return {
        Shoes: []
      };
    },
    mounted() {
      fetch("https://aphelele2.github.io/jsonExamplee/shoes.json")
        .then((response) => response.json())
        .then((data) => {
          console.log(data);
          this.Shoes = data;
        })
        .catch((error) => {
          console.error(error);
        });
    },
  };
  </script>
  <style scoped>
 
  </style>







