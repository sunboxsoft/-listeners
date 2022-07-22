<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <child-f @jiaguoqiang="HF" @onFun="onFun"></child-f>

    <student v-for="(item, index) in students" :key="item.id" :record="item">

      <template #default="scope">
        <!-- {{ index }}--{{ item.name }}=={{ item.num }} -->
        {{ scope.age }}-{{item.num}}-{{ index }}
        <student-c :num="item.num" @defineFun="defineFun($event, item)"></student-c>
      </template>
    </student>
  </div>
</template>

<script>
import ChildF from './children/ChildF.vue'
import Student from './children/Student.vue'
import StudentC from './children/StudentC.vue'
export default {
  name: 'HelloWorld',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      students: [{
        id: 101,
        name: 'jiaguoqiang',
        age: 40,
        num: 0
      },
      {
        id: 102,
        name: 'jiajindian',
        age: 10,
        num: 3
      }
      ]
    }
  },
  components: {
    ChildF,
    Student,
    StudentC
  },
  created() {
  },
  mounted() {
    console.log(this.$slots, 'this.$slots')
  },

  methods: {
    HF() {
      console.log(arguments, arguments[0], ' HF(){')
    },
    onFun() {
      console.log(arguments[0], 'onFUn')
    },
    defineFun(e, item) {
      item.num = e
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
