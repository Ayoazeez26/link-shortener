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
    <div
      class="hamburger"
      @click="toggleNav"
    >
        &#9776;
    </div>
    <div
      class="nav-scroll"
      id="idNav"
      ref="navId"
    >
      <ul class="items">
        <li>Features</li>
        <li>Pricing</li>
        <li>Resources</li>
        <li><hr></li>
        <li><a href="#">Login</a></li>
        <li class="signup-mobile"><a href="#">Sign Up</a></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  methods: {
    toggleNav() {
      let navScroll = document.querySelector('.nav-scroll');
      if (navScroll.style.top === '-500px') {
        navScroll.style.top = '0';
      } else {
        navScroll.style.top = '-500px';
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  width: 100%;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #ffffff;
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

.hamburger {
  display: none;
  font-size: 30px;
  font-weight: 700;
}

.nav-scroll {
  position: absolute;
  top: -500px;
  width: 90%;
  height: 400px;
  margin: 0 auto;
  background-color: hsl(257, 27%, 26%);
  border-radius: 10px;
  text-align: center;
  color: #ffffff;
  font-size: 18px;
  margin-top: 70px;
  transition: all .3s cubic-bezier(.03, .84, .18, 1.01);
  z-index: 99;
}

.items {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  height: 100%;
  margin: 0;
  padding: 0;
}

.items li {
  list-style-type: none;
  width: 90%;

}

.items a {
  text-decoration: none;
  color: #FFF;
  cursor: pointer;
}

.signup-mobile {
  background-color: hsl(180, 66%, 49%);
  padding-top: 15px;
  padding-bottom: 15px;
  border-radius: 40px;
}

@media screen and (max-width: 768px) {
  .nav-el,
  .div-user {
    display: none;
  }

  .hamburger {
    display: block;
  }

  /* .header {
    width: 100%;
  } */
}
</style>
