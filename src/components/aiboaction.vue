<template>
  <div>
    <p class="text-left">Action</p>
    <select class="form-control" v-model="selected" @change="actionSelected">
      <option v-for="(item, index) in actions"
        :key="index"
        :value="{action: item.action, arguments: item.arguments}">
        {{item.text}}
      </option>
    </select>
    <div v-for="(argument, index) in arguments" :key="index" :value="argument.text">
    <p v-if="arguments" class="text-left">{{argument.text}}</p>
    <select v-if="arguments" class="form-control" v-model="values[index]" @change="argSelected">
      <option v-for="(item, index) in argument.values"
        :key="index"
        :value="{arg: argument.name, value: item}">
        {{item}}
      </option>
    </select>
    </div>
  </div>
</template>

<script>
const aiboActions = require('./aiboActions');

export default {
  name: 'aiboaction',
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
    argSelected() {
      for (let i = 0; i < this.arguments.length; i += 1) {
        // eslint-disable-next-line
        console.dir(this.arguments[i]); //{ name: "TargetType", text: "Target Type", values: [] }
        // eslint-disable-next-line
        console.dir(this.values[i]); // {arg: "TargetType", value: "aibone"}
      }
    },
  },
};
</script>
