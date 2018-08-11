<template>
  <div>
    <form action="">
      <h2>{{ module }}</h2>
      <input type="text" v-model.number="from">から
      <input type="text" v-model.number="to">までをカンマ区切りで出力
      <br>
      <textarea readonly cols="30" rows="10" v-model="separatedNum"></textarea>
    </form>
  </div>
</template>

<script>
  export default {
    name: "NumSeparator",
    props: {
      module: ''
    },
    data: function() {
      return {
        from: '',
        to: ''
      }
    },
    computed: {
      separatedNum: function() {
        if (this.from !== '' && this.to !== '') {
          let ar = []
          for (let i = this.from; i <= this.to; i++) {
            ar.push(i)
          }
          return ar.join()
        }
      }
    }
  }
</script>

<style scoped>

</style>
