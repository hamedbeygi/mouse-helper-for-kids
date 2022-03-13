<template>
  <div class="main">
    <div class="top">
      <div class="top-button">
        <Top @select="changeSelected" number="0" />
      </div>
    </div>

    <div class="left">
      <div class="left-button">
        <Top @select="changeSelected" number="3" />
      </div>
    </div>
    <div class="mid">
      <Instruction :userSelect="userSelect" />
    </div>

    <div class="right">
      <div class="right-button">
        <Top @select="changeSelected" number="1" />
      </div>
    </div>

    <div class="bottom">
      <div class="bottom-button">
        <Top @select="changeSelected" number="2" />
      </div>
    </div>
  </div>
</template>

<script>
import Top from "~/components/top";
import Instruction from "~/components/instruction";
export default {
  components: {
    Top,
    Instruction,
  },
  data() {
    return {
      userSelect: null,
    };
  },

  methods: {
    changeSelected(newOne) {
      this.userSelect = newOne;
    },
  },
};
Instruction;
</script>

<style scoped>
.main {
  position: absolute;
  height: 100%;
  width: 100%;
  display: grid;
  grid-template-areas: "top top top top top" "left middle middle middle right" "left middle middle middle right" "left middle middle middle right" "bottom bottom bottom bottom bottom";
  background-color: #088174;
}

.top {
  grid-area: top;
  /* background-color: red; */
  height: fit-content;
}
.top-button {
  display: flex;
  justify-content: center;
  margin-top: 1em;
}
.left {
  grid-area: left;
  /* background-color: yellow; */
}
.left-button {
  display: flex;
  position: absolute;
  left: 0;
  margin-top: 5em;
}
.mid {
  grid-area: middle;
  margin-top: 4em;
  /* background-color: blue; */
}
.right {
  grid-area: right;
  /* background-color: rgb(94, 76, 138); */
}
.right-button {
  display: flex;
  position: absolute;
  right: 0;
  margin-top: 5em;
  /* align-items: center; */
}
.bottom {
  grid-area: bottom;
  /* background-color: green; */
}
.bottom-button {
  display: flex;
  justify-content: center;
  margin-bottom: -4.5em;
}
</style>
