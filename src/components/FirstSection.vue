<template>
  <div class="firstSection">
    <div class="big-heading">
      <h1>More than just<br>shorter links</h1>
      <p>Build your brand's recognition and get detailed insights on how your links are performing.</p>
      <a href="#">Get Started</a>
    </div>
    <img src="../assets/images/illustration-working.svg" alt="Landing Page Working Image">
  </div>
</template>

<script>
export default {
  name: 'FirstSection'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.firstSection {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 480px;
  font-size: 18px;
}

.big-heading {
  width: 37%;
  color: hsl(0, 0%, 75%);
}

.big-heading h1 {
  font-size: 56px;
  line-height: 60px;
  color: hsl(260, 8%, 14%);
  margin-bottom: 0;
}

.big-heading p {
  margin-bottom: 30px;
}

.big-heading a {
  color: #FFF;
  padding: 10px 25px;
  border-radius: 25px;
  background-color: hsl(180, 66%, 49%);
  text-decoration: none;
  cursor: pointer;
}


.firstSection img {
  position: absolute;
  right: 0;
}


@media screen and (max-width: 1120px) {
      
  .big-heading h1 {
    font-size: 42px;
  line-height: 48px;
  }

  .firstSection img {
    width: 500px;
    height: auto;
  }

  .big-heading {
    width: 45%;
  }
}

@media screen and (max-width: 850px) {   
  .firstSection img {
    width: 400px;
  }
}

@media screen and (max-width: 768px) {
  .firstSection {
    flex-direction: column-reverse;
    justify-content: space-between;
    align-items: center;
    text-align: center;
    height: auto;
  }
  
  .firstSection img {
    position: relative;
    width: 100%;
    top: 0;
    /* margin-top: 70px; */
  }
  
  .big-heading {
    width: 100%;
  }
        
  .big-heading h1 {
    font-size: 32px;
  line-height: 36px;
  }

  .big-heading p {
    font-size: 16px;
    line-height: 21px;
  }



}
</style>
