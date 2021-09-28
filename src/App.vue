<template>
  <div>
    <ul>
      <li v-for="email in emailRandomica" :key="email">{{emailRandomica}}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  components: {
   
  },
  data: function(){
        return{
          emailRandomica:[],
        }
    },
   mounted() {
    console.log(axios);

    for(let i = 0; i < 10; i++){
        axios.get('https://flynn.boolean.careers/exercises/api/random/mail')
        .then((resp) => {
          console.log(resp.data.response);
          this.emailRandomica.push (resp.data.response);
        });
      }
  }
}
</script>

<style lang="scss">

</style>
