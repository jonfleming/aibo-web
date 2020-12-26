<template>
    <div class="container">
        <div class="row text-center">
            <aiboimage/>
        </div>
        <form class="form-horizontal row p-2">
            <div class="form-group col-sm-3">
                <aiboaction/>
            </div>
            <div class="form-group col-sm-2">
              <span></span>
            </div>
            <div class="form-group col-sm-7">
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
import aiboresponse from '@/components/aiboresponse.vue';
import aibolog from '@/components/aibolog.vue';
import { reactive } from 'vue';

export default {
  name: 'App',
  components: {
    aiboimage,
    aiboaction,
    aiboresponse,
    aibolog,
  },
  data: () => ({
    response: {},
  }),
  setup() {
    const state = reactive({
      selectedAction: {},
    });
    return {
      state,
    };
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
