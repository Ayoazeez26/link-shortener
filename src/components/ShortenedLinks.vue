<template>
 <div id='link-display'>
   {{linkInput}}
   {{shortLink}}
   <button> Copy </button>
 </div>
</template>
 
<script>
export default {
 props: ['linkInput', 'shortLink']
}
</script>

<style>
#link-display {
  padding-top: 130px;
  background-color: #FFF;
  border-radius: 10px;
  display: flex;
  justify-content: space-between;
}
#link-display button {
  background-color: hsl(180, 66%, 49%);
  border: 1px solid #EEE;
  padding: 10px 15px;
}
</style>