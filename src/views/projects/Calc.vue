<template>
  <div>
    <h1 class="subheading grey--text">Calc</h1>
    <v-container class width="300">
      <v-row>
        <p class="display_calc">{{lastNumber}}</p>
      </v-row>
      <v-row>
        <p class="display_calc">{{expression}}</p>
      </v-row>

      <div class="buttons_wrap">
        <v-btn
          text
          v-for="(singleButton, index) in calcButtons"
          :key="index"
          v-bind:width="singleButton.cellType == 2 ? 128 : 60"
          height="60"
          tile
          fab
          class="blue lighten-4 ma-1 blue-grey--text text--darken-4"
          @click="bntPress(index)"
        >{{singleButton.name}}</v-btn>
      </div>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "home",
  data() {
    return {
      expression: [],
      lastNumber: "0",
      calcButtons: [
        {
          name: "AC",
          type: "func",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "+/-",
          type: "func",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "%",
          type: "func",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "÷",
          type: "func",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "7",
          type: "number",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "8",
          type: "number",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "9",
          type: "number",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "×",
          type: "func",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "4",
          type: "number",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "5",
          type: "number",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "6",
          type: "number",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "-",
          type: "func",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "1",
          type: "number",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "2",
          type: "number",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "3",
          type: "number",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "+",
          type: "func",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "0",
          type: "number",
          cellType: 2,
          color: "#321341"
        },
        {
          name: ",",
          type: "float",
          cellType: 1,
          color: "#321341"
        },
        {
          name: "=",
          type: "func",
          cellType: 1,
          color: "#321341"
        }
      ]
    };
  },
  methods: {
    bntPress: function(index) {
      let operand = this.calcButtons[index].name;
      /* eslint-disable no-console */
      console.log(operand);
      /* eslint-enable no-console */
      switch (this.calcButtons[index].name) {
        case "AC":
          this.expression = '0';
          this.lastNumber = '0';
          operand = "";
          break;
        case "+/-":
          this.lastNumber = Number(this.lastNumber) / -1;
          break;
        case ",":
          operand = ".";
          break;
      }

      if (
        this.calcButtons[index].type === "number" ||
        (this.calcButtons[index].type === "float" &&
          this.lastNumber.indexOf(".") == -1)
      ) {
        if (this.lastNumber === '0' && operand !== ".") {
          this.lastNumber = operand;
        } else {
          this.lastNumber += operand;
        }

        /* this.expression += operand; */
      }
      /* eslint-disable no-console */
      console.log(operand);
      /* eslint-enable no-console */
    }
  }
};
</script>
<style scoped>
.buttons_wrap {
  width: 280px;
  height: 350px;
  background-color: #eee;
}
</style>