<template>
  <div id="divFather" >
    <div  >{{message}} </div>
    <Radio v-bind:answer="answer"></Radio>

  </div>
</template>

<script>
import Radio from "@/components/Question/Components/Radio";

export default {
  name: "question",
  props:['answer'],
  data:function() {
    return {
    message:""
  };
},
  components:{
    Radio
  }
}
</script>

<style scoped>
  #divFather{
    display: flex;
    flex-direction:  row;
    margin-left: 42px;
  }
</style>