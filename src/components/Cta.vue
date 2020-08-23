<template>
  <div class="cta">
    <div class="cta-boost">
      <h2>Boost your links today</h2>
      <a href="#">Get Started</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Cta'
}
</script>

<style>
.cta {
  background-image: url("../assets/images/bg-shorten-desktop.svg");
  background-color: hsl(257, 27%, 26%);
  width: 100%;
  height: 150px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.cta-boost {
  width: auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.cta h2 {
  color: #FFF;
  font-size: 36px;
  text-align: center;
  margin-top: 0;
}
.cta a {
  color: #FFF;
  padding: 10px 25px;
  border-radius: 25px;
  background-color: hsl(180, 66%, 49%);
  text-decoration: none;
  cursor: pointer;
}
@media screen and (max-width: 768px) {
  .cta {
    height: 230px;
  }
  .cta h2 {
    font-size: 27px;
  }
}
</style>