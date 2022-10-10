<template>
  <div class="container mx-auto pt-5">
    <h1 class="text-2xl font-bold text-center"> Hello!</h1>
    <div>
      <Ref />
    </div>
    <div>
      <Reactive />
    </div>
    <div>
      <Watch />
    </div>
    <div>
      <Computed />
    </div>
  </div>

</template>
<script>
import Ref from "./components/compositionApi/Ref.vue";
import Reactive from "./components/compositionApi/Reactive.vue";
import Computed from "./components/compositionApi/Computed.vue";
import './assets/main.css';
export default {
  components: { Ref, Reactive, Computed },

  setup() {
    const title = " Vue JS";
    return { title }
  }
}
</script>