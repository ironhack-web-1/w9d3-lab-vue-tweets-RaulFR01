<template>
  <p className="message">{{ mensaje }}</p>
</template>

<script>
export default {
  props: {
    mensaje: {
      type: String,
    },
  },
};
</script>

<style></style>
