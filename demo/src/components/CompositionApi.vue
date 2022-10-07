<!-- <script>
// reactive sử dụng trong object.
// các thuộc tính thay đổi thì ns sẽ thay đổi nhưng không thể thay thế chính ns 
import { ref, reactive } from "vue";
export default {
  setup() {
    //một biến tạo trong data bất cứ một sự thay đổi biến nào ns sẽ nhận biết đk
    const car = reactive({
      price: 10000,
      name: "Mec",
    });
    const firstName = ref("Hung Nguyen");
    const onChangeSomething = () => {
      console.log("running hee.....");
      console.log(firstName);
      console.log(car);
      car.price = 2000;
      firstName.value = "Phạm Hùng";
    };
    return { firstName, onChangeSomething };
  },
};
</script> -->

<script>
import { ref, reactive, watch, watchEffect } from "vue";
export default {
      setup() {
            const searchClick = ref("");
            const customers = reactive(["Something", "Hung Nguyen", "32"]);
            const customersFilled = computed(() =>
                  customers
                        .map((customer) => {
                              customer = customer.toLowerCase();
                              return customer;
                        })
                        .filter((customer) =>
                              customer.includes(searchClick.value.toLowerCase())
                        )
            );
            watch(searchClick, (newEffect, oldEffect) => {
                  console.log(newEffect, oldEffect);
            });
            watchEffect(() => {
                  if (searchClick.value) console.log("run again...");
            });
            return { searchClick, customersFilled, HelloWorld };
      },

};
</script>
<template>
      <div>
            <input type="text" v-model="searchClick" @input="check" />
            <ul>
                  <li v-for="(customer, index) in customersFilled" :key="index">
                        {{ customer }}
                  </li>
            </ul>
      </div>
</template>
      