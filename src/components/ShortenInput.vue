<template>
  <div class="colorStyle">
    <div class="getShowLinks">
      <div class="shortenInput">
        <form class="flexInputs">
          <input
            type="text"
            name="link"
            v-model="form.linkInput"
            id="link"
            placeholder="Shorten a link here...">
          <a class="shorten" @click="showLink" href="#">Shorten It!</a>
        </form>
      </div>
      <div class="linkOutput"> 
        <shortened-links
          v-show="checkReturn"
          v-for="link in wholeLinks"
          :key="link.id"
          :linkInput="link.mainLink"
          :shortLink="link.shortLink"
        />
      </div>
    </div>
  </div>
</template>

<script>
import ShortenedLinks from './ShortenedLinks.vue';
import { v4 as uuidv4 } from 'uuid';


var axios = require('axios');

export default {
  components: {
    'shortened-links' : ShortenedLinks
  },
  name: 'ShortenInput',
  data() {
    return {
      form: {
        linkInput: ''
      },
      wholeLinks: [],
      shortLink: '',
      checkReturn: false
    }
  },
  methods: {
    showLink(e) {
      e.preventDefault();
      axios
      .post('https://rel.ink/api/links/', {
        url : this.form.linkInput
      })
      .then(response => {
        this.getLink(response.data.hashid)
        }
      )
      .catch(function (error) {
        console.log(error);
      });
    },
    getLink(link) {
      this.shortLink = `https://rel.ink/${link}/`;
      if(link) {
        this.checkReturn = true;
      }
      this.wholeLinks.unshift({
        mainLink: this.form.linkInput,
        shortLink: this.shortLink,
        id: uuidv4()
      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.colorStyle {
  background-color: #F0F1F6;

}
.getShowLinks {
  width: 1280px;
  margin: 0 auto;
  position: relative;
}
.shortenInput {
  position: absolute;
  width: 100%;
  top: -70px;
  background-image: url("../assets/images/bg-shorten-desktop.svg");
  height: 150px;
  border-radius: 15px;
  background-color: hsl(257, 27%, 26%);
  display: flex;
  justify-content: center;
  align-content: center;
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
.linkOutput {
  padding-top: 130px;
}
@media screen and (max-width: 1279px) {
  .getShowLinks {
    width: 100%;
  }
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
  .getShowLinks {
    margin-top: 70px;
    width: 90%;
  }
  .shortenInput {
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