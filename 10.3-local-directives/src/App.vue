<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Built-in Directives</h1>
        <p v-text="'some text'"></p>
        <p v-html="'<strong>strong text</strong>'"></p>
      </div>

      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Custom Directives</h1>
        <p v-highlight>Colored text</p>
        <p v-highlight="'red'">Colored text</p>
        <p v-highlight:background.delayed="'red'">Colored text</p>
        <p v-local-highlight:background.delayed="'red'">Color locally</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  directives: {
    "local-highlight": {
      bind(el, binding, vnode) {
        // el.style is a normal JS property of a HTML element.
        // el.style.backgroundColor = "green";
        // el.style.backgroundColor = binding.value;

        let delay = 0;
        if (binding.modifiers["delayed"]) {
          delay = 3000;
        }

        setTimeout(() => {
          if (binding.arg === "background") {
            el.style.backgroundColor = binding.value;
          } else {
            el.style.color = binding.value;
          }
        }, delay);
      },
    },
  },
};
</script>

<style></style>
