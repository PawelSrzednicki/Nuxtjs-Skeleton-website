<template>
  <section class="section">
    <div class="container">
      <h2 class="title">My Profile</h2>

      <div class="content">
        <p>
          <strong>Email:</strong>
          {{ user.email }}
        </p>
      </div>
    </div>
  </section>
</template>

    <script>
export default {
  middleware: "auth"
};
</script>