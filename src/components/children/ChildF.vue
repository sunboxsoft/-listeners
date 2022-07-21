<template>
  <section class="ChildF">
    ChildF
    <!-- <button @click="$listeners.jiaguoqiang('贾国强')">ceshi</button> -->
    <button @click="$emit('jiaguoqiang','测试姓名')">ceshi</button>
    <button @click="$emit('onFun','测试姓名onFun')">ceshi onFun</button>

 <hr/>

 <child-s v-on="$listeners" @fatherF="fatherF"></child-s>

<button @click="printChildren">打印子组件</button>

 </section>
</template>

<script>
import ChildS from './ChildS.vue'
export default {
 name: 'ChildF',
  data() {
    return {

    }
  },
  components: {ChildS},
  watch: {},
  mounted() {
    //  console.log(this.$listeners,'this.$listeners')
  },
  methods: {
    fatherF(){
      console.log(arguments[0],'fatherF')
    },
    printChildren(){
       //children
       for(let child in this.$children){
        console.log(child)
       }
    }
  }
}
</script>

<style>

</style>
