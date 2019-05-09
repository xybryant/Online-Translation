<template>
  <div id="translateform" class="row justify-content-md-center mx-2">
    <div class="">
      <form @submit.prevent="onSubmit" class="form-inline my-5">
        <input type="text" class="form-control" name="content" v-model="content" placeholder="请输入内容...">
        <select v-model="lang" class="form-control mx-2">
          <option value="en">English</option>
          <option value="ja">Japanese</option>
          <option value="ru">Russian</option>
          <option value="ko">Korean</option>
          <option value="fr">French</option>
          <option value="it">Italian</option>
          <option value="zh">Chinese</option>
          <option value="de">German</option>
        </select>
        <button type="submit" class="btn btn-primary btn-sm mr-2">翻译</button>
        <button type="reset" class="btn btn-danger btn-sm">清空</button>
      </form>
    </div>
  </div>
</template>

<script>

export default {
  name: 'translateform',
  data () {
    return {
      content: '',
      lang: 'en'
    }
  },
  methods: {
    onSubmit () {
      if(!this.content){
        alert('请输入要翻译的内容！')
      }else{
        this.$emit('translates', this.content, this.lang)
      }
    }
  }
}
</script>

<style>
#translateform {
 
}
</style>
