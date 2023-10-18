<template>
    <component v-if="name" :is="dynamicComponent" />
  </template>
  
  <script>
  export default {
    props: ['name'],
    data() {
      return {
        dynamicComponent: null,
      };
    },
    created() {
      if (this.name) {
        import(`./icons/${this.name}.vue`)
          .then((module) => {
            this.dynamicComponent = module.default;
          })
          .catch((error) => {
            console.error(`Error loading component: ${error}`);
          });
      }
    },
  };
  </script>