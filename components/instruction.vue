<template>
  <div>
    <ul>
      <li v-for="(inst, i) in instList" :key="i">
        <arrow
          @theOne="setVal"
          :number="inst"
          :opacity="i + 1 === index ? null : 'opacity50'"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import arrow from "~/components/arrow";
export default {
  components: {
    arrow,
  },
  props: {
    userSelect: {
      default: null,
    },
  },
  data() {
    return {
      level: 2,
      instList: [3, 2],
      index: 1,
      theOne: null,
    };
  },
  methods: {
    calRand() {
      this.instList = Array.from(Array(this.level + 1)).map((x) =>
        Math.floor(Math.random() * 4)
      );
      console.log(this.instList);
    },
    setVal(value) {
      this.theOne = value;
    },
  },
  watch: {
    userSelect(newVal) {
      if (newVal == this.instList[this.index - 1]) {
        console.log("true");
        if (this.index === this.instList.length) {
          this.calRand();
          this.index = 1;
          if (this.level < 8) {
            this.level = this.level + 1;
          }
        } else {
          this.index = this.index + 1;
        }
      } else {
        console.log("wrong");
      }
    },
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  display: flex;
  background-color: #484848;
  border-radius: 2em;
  width: fit-content;
  padding: 0;
  margin: auto;
}
li {
  display: flex;
}
</style>
