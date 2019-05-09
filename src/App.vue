<template>
  <div id="app">
    <h1>^_^ 在线翻译 ^_^</h1>
    <h4>简单 / 易用 / 便捷</h4>
    <translate @translates="getTtranslate"/>
    <translate-output :translated="translatedText"/>
    <!-- <translate-output v-text="translatedText"/> -->
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'

export default {
  name: 'App',
  components: {
    'translate': TranslateForm,
    'translate-output': TranslateOutput
  },
  data () {
    return {
      translatedText: ''
    }
  },
  methods: {
    getTtranslate (content, lang) {
      // console.log(content, lang)
      this.$axios.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20190508T081106Z.8315918d315c8689.03d120c8ff77ed764d1e2d75b27693d804af9ec3&lang='+lang+'&text='+content).then(res => {
        //console.log(res.data.text[0])
        this.translatedText = res.data.text[0]
      })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
