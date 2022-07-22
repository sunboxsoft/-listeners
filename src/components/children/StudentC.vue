<template>
  <section class="StudentC">
    <button @click="defineFun" >触发</button>
    
     Child

     <button @click="changeC">改变颜色</button>
     <!-- <p v-color>AAA</p> -->
     <p v-color="colorV">AAA</p> 
  </section>
  
</template>

<script>
export default {
  name: 'StudentC',
  data() {
    return {
      colorV:{
        c:'red',
        bg:'yellow'
      }
    }
  },
  components: {},
  watch: {},
  mounted() { },
  methods: {
    defineFun() {
      this.$listeners.defineFun(this.$attrs.num++)
      // this.$emit('defineFun',this.$attrs.num++)
    },
    changeC(){
      if(this.$attrs.num%2===0){
        this.colorV.c='pink'
      }
      else{
        this.colorV.c='skyblue'
      }
    }
  },
  directives: {
    // 只在首次加载时起作用
    // color:{
    //   bind(el){
    //     el.style.color='red'
    //   }
    // }

    // 首次和改变时都起作用   方法一
    // color:{
    //   bind(el,binding){
    //     console.log(binding)
    //     el.style.color=binding.value
    //   },
    //   改变时起作用
    //   update(el,binding){
    //     console.log(binding)
    //     el.style.color=binding.value
    //   }
    // }
    // 首次和改变时都起作用   方法二
    color(el,binding){
      console.log(binding)
      el.style.color = binding.value.c
      el.style.backgroundColor=binding.value.bg
    }
  }
}
</script>

<style>
</style>
