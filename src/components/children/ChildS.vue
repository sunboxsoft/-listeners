<template>
  <section class="ChildS">
    ChildS  <button @click="PrintListeners">打印$listeners</button>
  </section>
</template>

<script>
export default {
 name: 'ChildS',
  data() {
    return {

    }
  },
  components: {},
  watch: {},
  mounted() {},
  methods: {
    PrintListeners(){
        // console.log(this.$listeners,'PrintListeners')
        // this.$listeners.fatherF('子组件参数')

        // this.$emit('fatherF','childS emit arguments')
        this.$listeners.jiaguoqiang('ChildS arguments')
    }
  }
}
</script>

<style>

</style>
