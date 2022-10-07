<template>
  <div>
    <h1> Hello!</h1>
    <Ref />
    <Reactive />
    <Watch />
    <WatchEffect />
  </div>
  <!-- <div>
    <h1> {{title}}</h1>
    <strong>Import component</strong>
    <div>
      <HelloWorld />
    </div>
    <div>
      <CompositionApi /> -->
  <!-- </div>
  <div>
    <TailwindCss />
  </div>
  </div> -->
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import CompositionApi from "./components/CompositionApi.vue";
import TailwindCss from "./components/TailwindCss.vue";
import Ref from "./components/compositionApi/Ref.vue";
import Reactive from "./components/compositionApi/Reactive.vue";
import Watch from "./components/compositionApi/Watch.vue";
import WatchEffect from "./components/compositionApi/WatchEffect.vue";
import { ref, reactive, watch, watchEffect } from "vue";
export default {
  components: { Ref, Reactive, WatchEffect, Watch },

  setup() {
    const title = " Vue JS";
    return { title }
  }
}
</script>