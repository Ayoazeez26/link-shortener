<template>
 <div id='link-display'>
   <div class="short-link">
    <p>{{linkInput}}</p>
    <a :href="shortLink">{{shortLink}}</a>
    <button> Copy </button>
   </div>
 </div>
</template>
 
<script>
export default {
 props: ['linkInput', 'shortLink']
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