<template>
<div id="app">
 <trans v-on:formSubmit="textTranslate"></trans>
 <Resutat></Resutat>
</div>
</template>

<script>
import Trans from './components/Trans';
import Resutat from './components/Resutat'
export default {
  name: 'App',
  data:function()
  {
    return{
      resultat:''
    }
  },
  components: {
    Trans,
    Resutat
  },
  methods:{
    textTranslate: function(text)
    {
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20200325T235244Z.af4c3bad2a354ac8.9806b92f63156b9f37d68b12e6890b1fe088b6a1&lang=en&text='+text).then((res)=>
      {
        console.log(res.body['text'][0]);
        this.resultat=res.body['text'][0];
      });
    }
  }
};
</script>
