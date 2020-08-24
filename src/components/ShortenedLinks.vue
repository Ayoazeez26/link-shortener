<template>
 <div id='link-display'>
   <div class="short-link">
    <p>{{linkInput}}</p>
    <a :href="shortLink">{{shortLink}}</a>
    <button
      v-clipboard="shortLink"
      v-clipboard:success="clipboardSuccessHandler"
      v-clipboard:error="clipboardErrorHandler"
      ref="change"
    >
      Copy
    </button>
   </div>
 </div>
</template>
 
<script>
export default {
 props: ['linkInput', 'shortLink'],
 methods: {
   clipboardSuccessHandler() {
    this.$refs.change.innerHTML = 'Copied!';
    this.$refs.change.style.backgroundColor = 'hsl(257, 27%, 26%)';
   },
   clipboardErrorHandler() {
     console.log('Error!!!');
   }
 }
}
</script>

<style>
#link-display {
  margin-top: 30px;
}
.short-link {
  background-color: #FFF;
  border-radius: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 30px;
}
.short-link p {
  flex-grow: 9;
}
.short-link a {
  text-decoration: none;
  color: hsl(180, 66%, 49%);
  text-align: right;
  flex-grow: 2;
}
.short-link button {
  background-color: hsl(180, 66%, 49%);
  border: 1px solid #EEE;
  padding: 15px 5px;
  color: #FFF;
  border-radius: 10px;
  flex-grow: 1;
  margin-left: 20px;  
  transition: all .2s cubic-bezier(.03, .84, .18, 1.01);
}
@media screen and (max-width: 768px) {
  .short-link {
    flex-direction: column;
    align-items: flex-start;
  }
  .short-link a {
    margin-bottom: 15px;
  }
  .short-link button {
    width: 100%;
    margin-left: 0;
  }
}
</style>