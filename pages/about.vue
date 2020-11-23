<template>
  <div>
    <h3>About</h3>
    <p>{{ name }}</p>
    <button @click="increase">Increase</button>
    <p>count: {{ count }}</p>
    <p>double: {{ double }}</p>
    <button @click="loading">Loading</button>
  </div>
</template>
<script lang="ts">
import { Vue, Component, Watch } from "nuxt-property-decorator";
@Component({})
export default class extends Vue {
  name: string = "pham van lam";
  count: number = 0;

  increase() {
    this.count++;
  }

  // computed
  get double(): number {
    return this.count * 2;
  }

  @Watch("double")
  myFunction(new_val: number, old_val: number) {
    console.log("it was: " + old_val);
    console.log("now it's: " + new_val);
  }

  created(){
    console.log('life cycle created')
  }
  mounted() {
    console.log('lifecycle mounted')
  }
  beforeDestroy() {
    console.log('lifecycle before destroy')
  }
  loading(){
    setTimeout(() => {
      
    }, 3000);
  }
}
</script>