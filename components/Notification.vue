<template>
  <v-alert :value="false" type="warning">{{ message }}</v-alert>
</template>

<script>
export default {
  name: "Notification",
  props: ["message"]
};
</script>