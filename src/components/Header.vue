<template>
  <div class="header">
    <div class="navbar">
      <h4>Shortly</h4>
      <ul class="nav-el">
        <li>Features</li>
        <li>Pricing</li>
        <li>Resources</li>
      </ul>
    </div>
    <div class="div-user">
      <a class="login" href="#">Login</a>
      <a class="signup" href="#">Sign Up</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  border: 1px solid black;
  position: fixed;
  top: 0;
  width: 1280px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #ffffff;
  z-index: 99;
}

.navbar {
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

h4 {
  color: hsl(260, 8%, 14%);
  font-size: 24px;
}

.nav-el {
  display: flex;
  justify-content: flex-start;
  color: hsl(257, 7%, 63%);
  font-size: 16px
}

.nav-el li {
  list-style-type: none;
}

.nav-el li:not(:last-child) {
  margin-right: 15px;
}

.nav-el li:hover {
  color: hsl(260, 8%, 14%);
  cursor: pointer;
}

.div-user {
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

.div-user a {
  text-decoration: none;
  cursor: pointer;
}

.login {
  color: hsl(257, 7%, 63%);
  margin-right: 15px;
}

.signup {
  color: #FFF;
  padding: 10px 25px;
  border-radius: 25px;
  background-color: hsl(180, 66%, 49%);
}

@media screen and (max-width: 768px) {
  .nav-el,
  .div-user {
    display: none;
  }
}
</style>
