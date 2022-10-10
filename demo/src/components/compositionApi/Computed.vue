<template>
      <div>
            <h3 class="font-bold uppercase"> Search Computer </h3>
            <p class="text-slate-400"> Comput thuôc dạng tính toán mảng mới</p>
            <input type="Text"
                  class="border border-solid p-3 w-96 placeholder:text-lg hover:border-orange-500 hover:shadow-lg"
                  v-model="searchText" placeholder="search Text" />
            <ul class="border border-black mt-2">
                  <li class="border" v-for="(text,index) in textFiled" :key="index">
                        {{text}}
                  </li>
            </ul>
            <h3 class="pt-3"> Watch theo dõi 1 biến.</h3>
            <h3> WatchEffect giống như computed giá trị thay đổi thì ns thực hiện lại </h3>

      </div>
</template>
<script>
import { computed, reactive, ref, watch, watchEffect } from "vue";
export default {
      setup() {
            const searchText = ref("");
            const texts = reactive(["Computed", "Reactive", "Ref"]);
            const textFiled = computed(() =>
                  texts.map((text) => {
                        text = text.toLowerCase();
                        return text;
                  })
                        .filter((text) => text.includes(searchText.value.toLowerCase()))
            );

            watch(searchText, (newValue, oldValue) => {
                  console.log(newValue, oldValue);
            });
            watchEffect(() => {
                  if (searchText.value) {
                        console.log("Đây là watchEffect");
                  }
            })
            return { textFiled, searchText }
      }
}
</script>