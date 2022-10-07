<script>
// các thuộc tính thay đổi thì ns sẽ thay đổi nhưng không thể thay thế chính ns 

import { reactive, ref } from "vue";
export default {
      setup() {
            // reactive sử dụng trong object.
            const car = reactive({
                  title: "Reactive",
                  description: "vuejs",
            });
            let secondName = ref({
                  title: "Reactive vs Ref",
                  something: "VueJS",
            })

            const onChangeSomething = () => {
                  console.log(car);
                  console.log(secondName);
                  car = {
                        description: "sử dụng trong object",
                  };
                  secondName.value = {
                        title: "sử dụng ref trong object sử dụng value",
                  };
            };
            return { car, secondName, onChangeSomething }
      },
};
</script>
<template>
      <p> {{car}}</p>
      <p> {{secondName}}</p>
      <button @click="onChangeSomething"> Reactive</button>
</template>