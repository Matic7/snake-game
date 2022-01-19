<template>
  <div id="containerAll">
    <div id="game">
      <div id="cobra"></div>
    </div>
  </div>
</template>

<script lang="ts">
// used for typeScript
import { defineComponent } from "vue";

export default defineComponent({
  name: "App",
  components: {},
  data() {
    return {};
  },
  methods: {},
  mounted() {
    let cobra: any = document.getElementById("cobra");
    let move = 5;
    cobra.style.top = 290 + "px";
    cobra.style.left = 290 + "px";
    //cobra.style.right = 290 + "px";
    //cobra.style.bottom = 290 + "px";
    document.addEventListener("keydown", function (event) {
      let keyCode = event.code;
      if (keyCode === "ArrowUp") {
        let t = (cobra.style.top = parseInt(cobra.style.top) - move + "px");
        console.log("top: ", t);
        if (t < "0px") {
          window.alert("game over T");
        }
      } else if (keyCode === "ArrowDown") {
        let b = (cobra.style.top = parseInt(cobra.style.top) + move + "px");
        console.log("bottom: ", b);
        if (b > "575px") {
          window.alert("game over B");
        }
      } else if (keyCode === "ArrowLeft") {
        let l = (cobra.style.left = parseInt(cobra.style.left) - move + "px");
        console.log("left: ", l);
        if (l < "0px") {
          window.alert("game over L");
        }
      } else if (keyCode === "ArrowRight") {
        let r = (cobra.style.left = parseInt(cobra.style.left) + move + "px");
        console.log("right: ", r);
        if (r > "575px") {
          window.alert("game over R");
        }
      }
    });
  },
});
</script>
