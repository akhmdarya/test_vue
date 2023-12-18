<template>
  <form  class='form' @submit.prevent>
    <h1>Создание поста</h1>
    <my-input
       v-model="post.title"
            type="text" placeholder="Name"/>
    <my-input
v-model="post.body"
           type="text" placeholder="Description"/>
    <my-button
              style="align-self:flex-end; margin-top: 15px"
@click="createPost"
    >Create post</my-button>
  </form>
</template>

<script>


import MyInput from "@/components/UI/MyInput";
export default {
  components: {MyInput},
  data(){
  return{
    post:{
      title:'',
      body:""
    }
  }
  },
  methods:{
  createPost(){
  this.post.id=Date.now()
this.$emit('create',this.post)
    this.post ={
      title:'',
      body:""
    }

  }
},
  // watch:{
  //   post:{
  //     handler(newVal){
  //       console.log(newVal)
  //     },
  //     deep:true
  //   }
  // }
}
</script>

<style scoped>
.form{
  display: flex;
  flex-direction: column;
}



</style>
