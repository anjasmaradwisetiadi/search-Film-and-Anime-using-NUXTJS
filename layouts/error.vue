<template>
  <div>
    <h1 v-if="error.statusCode === 404">
      <PageNotFound />
    </h1>
    <h1 v-else>An error occurred</h1>
  </div>
</template>

<script>
export default {
  props: {
    error: {
      type: Object,
      default: null,
    },
  },
  layout: 'error', // you can set a custom layout for the error page
};
</script>
