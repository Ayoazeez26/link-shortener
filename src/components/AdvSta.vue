<template>
  <div class="container">
    <div class="advSta">
      <div class="desc">
        <h3>Advanced Statistics</h3>
        <p>Track how your links are performing accross the web with our advanced statistics dashboard.</p>
      </div>
      <div class="desc-text">
        <div class="recog">
          <div class="recog-img">
            <img src="../assets/images/icon-brand-recognition.svg" alt="Brand Recognition Image">
          </div>
          <div class="recog-text">
            <h4>Brand Recognition</h4>
            <p>Boost your brand recognition with each click. Generic links don't mean a thing. Branded links help instill confidence in your content.</p>
          </div>
        </div>
        <div class="link one"></div>
        <div class="record">
          <div class="recog-img">
            <img src="../assets/images/icon-detailed-records.svg" alt="Brand Recognition Image">
          </div>
          <div class="recog-text">
            <h4>Detailed Records</h4>
            <p>Gain insights into who is clicking your links. Knowing when and where people engage with your content helps informs better decisions.</p>
          </div>
        </div>
        <div class="link two"></div>
        <div class="custom">
          <div class="recog-img">
            <img src="../assets/images/icon-fully-customizable.svg" alt="Brand Recognition Image">
          </div>
          <div class="recog-text">
            <h4>Fully Customizable</h4>
            <p>Improve brand awareness and content discoverability through customizable links, supercharging audience engagement.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AdvSta'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  width: 100%;
  background-color: #F0F1F6;
  padding-bottom: 70px;
}
.advSta {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  width: 1280px;
  margin-left: auto;
  margin-right: auto;
}
.desc {
  width: 38%;
  text-align: center;
}
.desc h3 {
  font-size: 36px;
  color: hsl(260, 8%, 14%);
  margin-bottom: 0;
  margin-top: 70px;
}
.desc p {
  line-height: 24px;
  color: hsl(0, 0%, 75%);
}
.desc-text {
  display: flex;
  justify-content: space-between;
  width: 100%;
}
.recog,
.record,
.custom {
  width: 26%;
  background-color: #FFF;
  height: 250px;
  padding-left: 25px;
  padding-right: 25px;
  position: relative;
  border-radius: 10px;
}
.record {
  margin-top: 50px;
}
.custom {
  margin-top: 100px;
}
.recog-img {
  background-color: hsl(257, 27%, 26%);
  width: 40px;
  height: 40px;
  padding: 15px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  top: -35px;
}
.recog-text {
  margin-top: 70px;
}
.recog-text h4 {
  color: hsl(260, 8%, 14%);
  font-size: 24px;
  margin-bottom: 0;
}
.recog-text p {
  color: hsl(0, 0%, 75%);
}
.link {
  width: 8%;
  height: 10px;
  background-color: hsl(180, 66%, 49%);
}
.one {
  margin-top: 150px;
}
.two {
  margin-top: 200px;
}
@media screen and (max-width: 1279px) {
  .advSta {
    width: 100%;
  }
}
@media screen and (max-width: 1044px){
  .recog,
  .record,
  .custom {
    padding-left: 15px;
    padding-right: 15px;
  }
  .recog-text {
    margin-top: 40px;
    line-height: 21px;
    font-size: 15px;
  }
}
@media screen and (max-width: 980px) {
  .desc {
    width: 55%;
  }
}
@media screen and (max-width: 942px) {

  .recog-text h4 {
    font-size: 20px;
    margin-top: 0;
  }
}
@media screen and (max-width: 768px) {
  .advSta {
    width: 90%;
  }
  .desc {
    width: 100%;
  }
  .desc h3 {
    font-size: 27px;
  }
  .desc-text {
    flex-direction: column;
    align-items: center;
    margin-top: 40px;
  }
  .one,
  .two {
    margin-top: 23px;
    transform: rotateZ(90deg);
  }
  .recog-img {
    left: 50%;
    transform: translate(-50%)
  } 
  .recog,
  .record,
  .custom {
    width: 90%;
    height: 270px;
    padding-left: 25px;
    padding-right: 25px;
  }
  .recog-text {
    margin-top: 60px;
  }
  .recog-text h4 {
    font-size: 24px;
  }
  .recog-text p {
    font-size: 18px;
    line-height: 28px;
  }
  .custom {
    margin-top: 50px;
  }
  .link {
    width: 55px;
  }
}
</style>
