<template >
    <div>
      <p>Reation time -{{ score }}</p> 
      <p class="speed">{{ speed }}</p> 
    </div>
</template>
<script>
export default {
  props:['score'],
  data(){
      return{
          speed:null
      }
      
  },
  mounted(){
      if (this.score < 250 ) {
          this.speed ="Very Fast"
          
      } else if (this.score < 400 ){
          this.speed ="Relatively Fast"
      }
          
    else{
        this.speed = "Not so Fast Chap"
    }  
  }
}
</script>
<style>
  .speed{
      font-size: 1.4em;
      color:#0faf87;
      font-weight: bold;
  }  
</style>