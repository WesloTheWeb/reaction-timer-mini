<template>
  <button class="block">click me</button>
</template>

<script>
export default {
  props: {
    delay: Array,
  },
};
</script>

<style>
.block {
  display: block;
  width: 10rem;
  height: 10rem;
  border-radius: 50%;
  border: solid #000 5px;
  color: #fff;
  text-align: center;
  text-transform: uppercase;
  padding: 2rem 0;
  margin: 4rem auto;
}
</style>