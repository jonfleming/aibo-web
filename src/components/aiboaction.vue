<template>
  <div>
    <p class="text-left"><b>Action</b></p>
    <select class="form-control" v-model="selected" @change="actionSelected">
      <option v-for="(item, index) in actions"
        :key="index"
        :value="{action: item.action, arguments: item.arguments}">
        {{item.text}}
      </option>
    </select>
    <div v-if="selected">
      <aibotarget :arguments="arguments"/>
    </div>
  </div>
</template>

<script>
import aibotarget from '@/components/aibotarget.vue';

const aiboActions = require('./aiboActions');

export default {
  name: 'aiboaction',
  components: {
    aibotarget,
  },
  data() {
    return {
      selected: '',
      arguments: [],
      values: [],
      actions: aiboActions };
  },
  mounted() {
    this.init();
  },
  methods: {
    init() {

    },
    actionSelected() {
      // eslint-disable-next-line
      console.dir(this.selected.arguments);
      // this.selected.arguments[0] = { name: "TargetType", text: "Target Type", values: [] }
      this.arguments = this.selected.arguments;
    },
  },
};
</script>
