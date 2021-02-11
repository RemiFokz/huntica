<template>
  <div class="hello">
    <component
      :is="tasks[active]"
      :phone="phone"
      @inputPhone="phone = $event"
    />
    <div class="btns">
      <button
        @click="active = item - 1"
        v-for="item in tasks.length"
        :key="item"
      >
        {{ item }}
      </button>
    </div>
  </div>
</template>

<script>
import LoginType from "@/components/questions/1/LoginType";
import FormSubmit from "@/components/questions/2/FormSubmit";
import UsersListVFor from "@/components/questions/3/UsersListVFor";
import WrongType from "@/components/questions/4/WrongType";
import CustomInput from "@/components/questions/5/CustomInput";
import InputFocus from "@/components/questions/6/InputFocus";
import PhoneValidation from "@/components/questions/7/PhoneValidation";
import SlotsComponent from "@/components/questions/8/SlotsComponent";
import RefComponent from "@/components/questions/9/RefComponent";
import StepsComponent from "@/components/questions/10/StepsComponent";
import ClickComponent from "@/components/questions/11/ClickComponent";
import ComponentForTest from "@/components/questions/12/ComponentForTest";
import RenderFunction from "@/components/questions/13/RenderFunction";
import ReviewAndRefactor from "@/components/questions/14/ReviewAndRefactor";

export default {
  name: "Playground",

  components: { SlotsComponent },
  props: {
    msg: String,
  },
  data() {
    return {
      active: 0,
      phone: "+79855310868",
    };
  },
  computed: {
    tasks() {
      return [
        LoginType,
        FormSubmit,
        UsersListVFor,
        WrongType,
        CustomInput,
        InputFocus,
        PhoneValidation,
        SlotsComponent,
        RefComponent,
        StepsComponent,
        ClickComponent,
        ComponentForTest,
        RenderFunction,
        ReviewAndRefactor,
      ];
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
.btns {
  display: flex;
  justify-content: center;
  margin-top: 2rem;
}
</style>
