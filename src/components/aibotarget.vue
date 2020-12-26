<template>
    <div class="form-group">
        <div class="input" v-for="(argument, index) in arguments"
          :key="index"
          :value="argument.text">
            <p v-if="argument" class="text-left pt-3 mb-1 ml-2"><b>{{argument.text}}</b></p>
            <div v-if="isNaN(argument.input)">
              <select v-if="argument" class="selectpicker form-control mt-2 p-0"
                  v-model="values[index]" @change="argumentSelected">
                  <option v-for="(item, index) in argument.values"
                      :key="index"
                      :value="{arg: argument.name, value: item}">
                      {{item}}
                  </option>
              </select>
            </div>
            <div v-else>
              <input class="m-2 p-1" type="text" :value="argument.input"><i>{{argument.units}}</i>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'aibotarget',
  props: {
    arguments: Array,
  },
  data() {
    return {
      selected: '',
      values: {},
    };
  },
  computed: {
    needsInput() {
      return 0;
    },
  },
  methods: {
    init() {

    },
    argumentSelected() {
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
<style scoped>
.input {
  width: 300px; overflow:hidden;
}

select {
  width: 300px;
}
</style>
