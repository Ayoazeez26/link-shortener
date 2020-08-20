<template>
  <div class="shortenInput">
    <form class="flexInputs">
      <input type="text" name="link" id="link" placeholder="Shorten a link here...">
      <a class="shorten" href="#">Shorten It!</a>
    </form>
  </div>
</template>

<script>
export default {
  name: 'ShortenInput'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.shortenInput {
  background-image: url("../assets/images/bg-shorten-desktop.svg");
  height: 100px;
  border-radius: 10px;
  background-color: hsl(257, 27%, 26%);
}
.flexInputs {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 80%;
  margin: 0 auto;
}
#link {
  border-radius: 10px;
  padding: 15px;
  width: 80%;
}
.shorten {
  color: #FFF;
  padding: 10px 25px;
  border-radius: 10px;
  background-color: hsl(180, 66%, 49%);
  text-decoration: none;
  cursor: pointer;
  width: 15%;
}
</style>
