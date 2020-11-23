<template>
  <div>
    <h3>About</h3>
    <p>{{ name }}</p>
    <button @click="increase">Increase</button>{{ count }}
  </div>
</template>
<script lang="ts">
import { Vue, Component } from "nuxt-property-decorator";
@Component({

})
export default class extends Vue {
  name: string = "pham van lam";
  count: number = 0;

  increase() {
    this.count++;
  }
}
</script>