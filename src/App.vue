<template>
    <div class="container">
        <div class="row text-center">
            <aiboimage/>
        </div>
        <form class="form-horizontal row p-2">
            <div class="form-group col-sm-6">
                <aiboaction/>
                <aibotarget/>
            </div>
            <div class="form-group col-sm-6">
                <aiboresponse/>
            </div>
            <div class="form-group col-sm-12">
              <aibolog/>
            </div>
        </form>
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
