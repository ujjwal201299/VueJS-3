<template>
  <div>
    <!-- Options API -->
    <input type="text" placeholder="name" v-model="name" />

    <input type="text" placeholder="First Name" v-model="firstName" />
    <input type="text" placeholder="Last Name" v-model="lastName" />

    <input type="text" placeholder="Reactive First Name" v-model="fName" />
    <input type="text" placeholder="Reactive Last Name" v-model="lName" />

    <input type="text" placeholder="Hero Name" v-model="options.heroName" />
  </div>
</template>

<script>
import { ref, watch, reactive, toRefs } from "vue";
import _ from "lodash";
export default {
  name: "Watch",
  setup() {
    const state = reactive({
      fName: "",
      lName: "",
      options: {
        heroName: "",
      },
    });

    // watch(
    //   () => {
    //     return { ...state };
    //   },
    //   function (newValue, oldValue) {
    //     console.log("fName Old Value: ", oldValue.fName);
    //     console.log("fName New Value: ", newValue.fName);
    //     console.log("lName Old Value: ", oldValue.lName);
    //     console.log("lName New Value: ", newValue.lName);
    //   }
    // );

    watch(
      () => state.fName,
      function (newValue, oldValue) {
        console.log("fName Old Value: ", oldValue);
        console.log("fName New Value: ", newValue);
      }
    );

    watch(
      () => _.cloneDeep(state.options),
      function (newValue, oldValue) {
        console.log("fName Old Value: ", oldValue);
        console.log("fName New Value: ", newValue);
      },
      {
        deep: true,
      }
    );

    const firstName = ref("");
    const lastName = ref("Wayne");

    watch(
      [firstName, lastName],
      (newValues, oldValues) => {
        console.log("firstName Old Value: ", oldValues[0]);
        console.log("firstName New Value: ", newValues[0]);
        console.log("lastName Old Value: ", oldValues[1]);
        console.log("lastName New Value: ", newValues[1]);
      },
      {
        // immediate: true,
      }
    );

    return {
      firstName,
      lastName,
      ...toRefs(state),
    };
  },

  data() {
    return {
      name: "",
    };
  },
  watch: {
    name(newValue, oldValue) {
      console.log("Old Value: ", oldValue);
      console.log("New Value: ", newValue);
    },
  },
};
</script>

<style scoped></style>
