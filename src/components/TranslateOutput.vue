<template>
  <div id="output">
   <p v-text="translated"></p>
   <!-- <p v-text="translatedText"></p> -->
  </div>
</template>

<script>

export default {
  name: 'translateoutput',
  props: ['translated']
  // props: ['translatedText']
}
</script>

<style>
#output {
 
}
</style>
