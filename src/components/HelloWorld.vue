<template>
  <input type="button" :value=num+n />
</template>

<script>
export default {
  name: "HelloWorld",
  data(){
    return{
      n:'%'
    }
  },
  props: {
    num: {
      type: String,
    },
  },
};
</script>

<style>
</style>