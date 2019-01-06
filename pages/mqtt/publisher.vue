<template>
  <div>

    <input type="text" name="message" placeholder="Please, input a text"  />
    <button type="button">전송</button>
  </div>
</template>


<script>
    export default {
    }
    const client = required("mqtt").connect('localhost:1883');

    const publish = message=>{
      client.publish('presence', message);
    }
</script>

<style scoped>

</style>
