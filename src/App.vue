<template>
  <div>
    <aiboimage/>
    <aiboaction/>
    <aibotarget/>
    <aiboresponse/>
    <aibolog/>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import aiboimage from '@/components/aiboimage.vue';
import aiboaction from '@/components/aiboaction.vue';
import aibotarget from '@/components/aibotarget.vue';
import aiboresponse from '@/components/aiboresponse.vue';
import aibolog from '@/components/aibolog.vue';

export default {
  name: 'App',
  components: {
    aiboimage,
    aiboaction,
    aibotarget,
    aiboresponse,
    aibolog,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
