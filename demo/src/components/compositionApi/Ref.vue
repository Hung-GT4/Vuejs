<script>
import { ref } from "vue";
export default {
      setup() {
            const firstName = ref("Hung Nguyen")

            const onChangeSomething = () => {
                  console.log(firstName.value);
                  firstName.value = "Phạm Hùng"
            };
            // mặc định trả ra giá trị(value) của ns  => unRef
            return { firstName, onChangeSomething }
      },
};
</script>
<template>
      <h1
            class=" mx-auto pt-5 text-center border-y-4 border-red-400 py-5 w-80   hover:bg-yellow-500/50 hover:font-bold my-5 container">
            Vue- Javascript
      </h1>
      <p class="border-black border p-2 w-32"> {{firstName}}</p>
      <button @click="onChangeSomething"
            class="my-5 px-7 py-2 font-bold font-mono border border-slate-300 hover:bg-rose-500/50 hover:border-indigo-300">
            Ref
      </button>
</template>