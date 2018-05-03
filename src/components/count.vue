<template>
    <div class="container">
    <h2>count:<span class="count"> {{ count }}</span></h2>
    Set Number :
    <input type="number" style="width:50px;" v-model="inputNumber"><br/>
    <md-button class="md-dense md-primary"
    @click="actionIncrease(inputNumber)">
     + {{inputNumber}}
    </md-button>
    <md-button class="md-dense md-raised md-primary"
    @click="actionDecrease(inputNumber)">
     - {{inputNumber}}
    </md-button>
    <br/>
    <md-button class="md-raised" @click="actionReset">Reset</md-button>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
export default {
  data() {
    return {
      inputNumber: 1
    };
  },
  computed: {
    ...mapGetters({
      count: "getCount"
    })
  },
  methods: {
    ...mapActions(["actionIncrease", "actionDecrease", "actionReset"])
  }
};
</script>
