<template>
  <header class="header">
    <div class="header-logo">Charts Examples</div>
    <div class="header-user">
      <img src="user-avatar.jpg" alt="User Avatar" class="header-user-avatar">
      <span>User Name</span>
    </div>
  </header>
</template>

<script>
export default {
  // Component logic goes here
}
</script>

<style>
/* Add your custom styles for the header in dark mode */
.header {
  background-color: #2b2d31; /* Dark blue background color */
  color: #fff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
}

.header-logo {
  font-size: 24px;
  font-weight: bold;
}

.header-user {
  display: flex;
  align-items: center;
}

.header-user-avatar {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  margin-right: 10px;
}
</style>
