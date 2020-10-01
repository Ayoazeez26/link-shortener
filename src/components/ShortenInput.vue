<template>
  <div class="colorStyle">
    <div class="getShowLinks">
      <div class="shortenInput">
        <form class="flexInputs">
          <input
            aria-label="name"
            type="text"
            name="link"
            ref="linkInput"
            v-model="form.linkInput"
            id="link"
            placeholder="Shorten a link here...">
          <button
            class="shorten"
            @click="showLink"
            href="#">
            <p>Shorten It!</p>
            <img
              v-show="isLoading"
              src="../assets/images/spinner.gif"
              alt="spinner"
            >
          </button>
          <p
            class="errorMessage"
            v-show="submitError"
          >
            Input a link and include the 'HTTPS'</p>
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
      checkReturn: false,
      isLoading: false,
      submitError: true
    }
  },
  methods: {
    showLink(e) {
      e.preventDefault();
      if(this.form.linkInput) {
        this.isLoading = true;
        this.submitError = false;
        this.$refs.linkInput.style.border = '2px solid #EEE';
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
      } else {
        this.$refs.linkInput.style.border = '2px solid hsl(0, 87%, 67%)';
        this.submitError = true;
      }
    },
    getLink(link) {
      this.shortLink = `https://rel.ink/api/links/${link}/`;
      if(link) {
        this.checkReturn = true;
        this.isLoading = false;
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
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 90%;
}
#link {
  border-radius: 10px;
  padding: 20px 25px;
  width: 70%;
  font-size: 24px;
  border: 2px solid hsl(0, 87%, 67%);
  outline: none;
}
#link:active {
  outline: none;
  border: none;
}
.shorten {
  color: #FFF;
  background-color: hsl(180, 66%, 49%);
  text-decoration: none;
  cursor: pointer;
  width: 20%;
  padding: 0;
  border: none;
  border-radius: 10px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
.shorten p {
  margin: 0;
  font-size: 1.5em;
  padding: 17px 20px;
  text-align: center;
}
.errorMessage {
  position: absolute;
  bottom: -6px;
  left: 0;
  color: hsl(0, 87%, 67%);
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
}

@media screen and (max-width: 875px) {
  #link {
    width: 60%;
  }
  .shorten {
    width: 27%;
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
    padding-left: 15px;
    padding-right: 15px;
    justify-content: center;
  }
  .shorten p {
    font-size: 1.1em;
    padding: 13px 20px;
    padding-left: 0;
    text-align: center;
  }
  .errorMessage {
    bottom: 63px;
    left: 20px;
  }
}
</style>