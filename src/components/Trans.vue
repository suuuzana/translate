<template>
  <div id="Trans">
   <form v-on:submit="submitForm">
     <input type="text" v-model="textToTranslate" placeholder="Entrer votre texte" required>
     <select v-model="language">
       <option value="en">English</option>
        <option value="ja">Japenese</option>
         <option value="ko">koran</option>
          <option value="ru">Russian</option>
          <option value="ar">Arab</option>
     </select>
     <input type="submit" value="Traduire">
   </form>
  </div>
</template>

<script>
export default {
  name: 'Trans',
  data: function () {
    return { textToTranslate: '',
    language: 'en' }
  },
  methods: {
    submitForm: function (e) {
      this.$emit('formSubmit', this.textToTranslate, this.language)
      e.preventDefault()
    }
  }
}
</script>

<style>
#Trans {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
