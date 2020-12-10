<template>
  <div>
    <div>BaseNumber: {{baseNumber}}</div>
   <div>RandomNumber: {{randomNumber}}</div>
   <div>BaseNumber + RandomNumber = {{sumNumber}}</div>
   <div>{{sumNumberToPercent}}</div>
    <button @click="handleRandom">submit</button>
    </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: () => ({
    baseNumber: 10,
    randomNumber: undefined,
  }),
  computed: {
    // 计算属性的 getter
    sumNumber: function () {
      // `this` 指向 vm 实例
      return this.randomNumber + this.baseNumber
    }
  },
  watch:  {
    sumNumber: function(oldValue, newValue) {
      this.sumNumberToPercent = `${newValue}%`
    }
  },
  mounted:function() {
    this.randomNumber = parseInt(Math.random() * 100, 10)
  },
  methods: {
    handleRandom: function () {
      this.randomNumber = parseInt(Math.random() * 100, 10)
    }

  }
}
</script>

