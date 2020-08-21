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
  height: 150px;
  border-radius: 15px;
  background-color: hsl(257, 27%, 26%);
  display: flex;
  justify-content: center;
  align-content: center;
  margin-top: 50px;
}
.flexInputs {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 90%;
}
#link {
  border-radius: 10px;
  padding: 20px 25px;
  width: 75%;
  font-size: 24px;
  border: 1px solid #DDD;
}
.shorten {
  color: #FFF;
  padding: 17px 25px;
  border-radius: 10px;
  background-color: hsl(180, 66%, 49%);
  text-decoration: none;
  cursor: pointer;
  width: 12%;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 1.5em;
}
@media screen and (max-width: 1140px) {
  .flexInputs {
    width: 94%;
  }
  #link {
    width: 70%;
  }
  .shorten {
    width: 15%;
  }
}

@media screen and (max-width: 875px) {
  #link {
    width: 60%;
  }
  .shorten {
    width: 20%;
  }
}

@media screen and (max-width: 768px) {
  .shortenInput {
    margin-top: 70px;
    height: 175px;
  }
  .flexInputs {
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    width: 95%;
  }
  #link {
    width: 80%;
    padding: 10px 15px;
    font-size: 20px;
  }
  .shorten {
    width: 80%;
    padding: 8px 15px;
    font-size: 1.1em;
  }
}
</style>
