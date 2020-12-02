<template>
  <div>
    <input type="text" :placeholder="wrap" v-model="value" />
  </div>
</template>

<script>
export default {
  props: ["wrap"],
  data: function() {
    return {
      value: "",
      format: "",
      regex: "^"
    };
  },
  mounted() {
    let counter = 1;
    this.format = this.wrap.replace(/X+/g, () => "$" + counter++);
    this.wrap.match(/X+/g).forEach(character => {
      this.regex += "(\\d{" + character.length + "})?";
    });
  },

  watch: {
    value() {

      this.value = this.value
        .substr(0, this.wrap.length)
        .replace(/[^0-9]/g, "")
        .replace(new RegExp(this.regex, "g"), this.format);
    }
  }
};
</script>
