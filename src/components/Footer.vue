<template>
  <footer class="footer">
    <h4>Shortly</h4>
    <div class="links">
      <ul>
        <li><h5>Features</h5></li>
        <li><a href="#">Link Shortening</a></li>
        <li><a href="#">Branded Links</a></li>
        <li><a href="#">Analytics</a></li>
      </ul>
      <ul>
        <li><h5>Resources</h5></li>
        <li><a href="#">Blog</a></li>
        <li><a href="#">Developers</a></li>
        <li><a href="#">Support</a></li>
      </ul>
      <ul>
        <li><h5>Company</h5></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Our Team</a></li>
        <li><a href="#">Careers</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </div>
    <div class="socials">
      <img src="../assets/images/icon-facebook.svg" alt="Facebook Icon">
      <img src="../assets/images/icon-twitter.svg" alt="Twitter Icon">
      <img src="../assets/images/icon-pinterest.svg" alt="Pinterest Icon">
      <img src="../assets/images/icon-instagram.svg" alt="Instagram Icon">
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style>
footer {
  display: flex;
  justify-content: space-between;
  background-color: #232027;
  color: #FFF;
  padding-top: 50px;
  padding-bottom: 50px;
}
footer h4 {
  flex-grow: 5;
  text-align: center;
  font-size: 24px;
  margin-top: 0;
}
.links {
  display: flex;
  flex-grow: 2;
}
.links ul {
  margin-top: 0;
}
.links h5 {
  font-size: 16px;
  margin-bottom: 20px;
  margin-top: 0;
}
.links a {
  text-decoration: none;
  color: #FFF;
  font-size: 14px;
  font-weight: 300;
}
.links a:hover {
  color: hsl(180, 66%, 49%);
}
.links li {
  list-style-type: none;
}
.links li:not(:first-child) {
  margin-top: 10px;
}
.socials {
  flex-grow: 4;
  display: flex;
  justify-content: space-around;
  height: 24px;
}
@media screen and (max-width: 768px) {
  footer {
    flex-direction: column;
    text-align: center;
  }
  .links {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }
  .links ul {
    padding-left: 0;
    margin-bottom: 35px;
  }
  .socials {
    width: 60%;
    margin: 0 auto;
  }
}
</style>