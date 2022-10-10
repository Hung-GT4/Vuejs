<script>
// các thuộc tính thay đổi thì ns sẽ thay đổi nhưng không thể thay thế chính ns 

import { reactive, ref } from "vue";
export default {
      setup() {
            const secondName = ref({
                  title: "Reactive vs Ref",
                  something: "VueJS",
            });
            // reactive sử dụng trong object.
            const car = reactive({
                  title: "Reactive",
                  description: "vuejs",
            });
            const onChangeSomething = () => {
                  console.log(car);
                  console.log(secondName);
                  car.value = {
                        description: "sử dụng trong object",
                  };
                  secondName.value = {
                        title: "ref trong object sử dụng value",
                  };
            };
            return { car, secondName, onChangeSomething }
      },
};
</script>
<template>
      <p class="border-red-500 border-2 p-2 w-96 "> {{car}}</p>
      <p class="border-red-500 border-2 p-2 w-96 "> {{secondName}}</p>
      <button @click="onChangeSomething"
            class="bg-blue-500 my-5 px-5 py-2 rounded text-white hover:bg-blue-700 shadow-black border-0">
            Reactive</button>
</template>