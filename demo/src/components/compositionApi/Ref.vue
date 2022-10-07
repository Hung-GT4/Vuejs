<script>
import { ref } from "vue";
export default {
      setup() {
            const firstName = ref("Hung Nguyen")

            const onChangeSomething = () => {
                  console.log(firstName.value);
                  firstName.value = "Phạm Hùng"
            };
            return { firstName, onChangeSomething }
      },
};
</script>
<template>
      <h1>Vue - Javascript</h1>
      <p> {{firstName}}</p>
      <button @click="onChangeSomething"> Ref</button>
</template>