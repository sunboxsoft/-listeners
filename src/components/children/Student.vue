<template>
  <section class="Student">
    Student
    <slot name="default" :age="$attrs.record.age"></slot>
  </section>
</template>

<script>
export default {
 name: 'Student',
  data() {
    return {

    }
  },
  components: {},
  watch: {},
  mounted() {},
  methods: {}
}
</script>

<style>

</style>
