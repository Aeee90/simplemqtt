<template>
    <section id="client">
      <h1></h1>
      <span>{{message}}}</span>
    </section>
</template>

<script>
  export default {
      asyncData(context) {
        return {message: "Hello ~ Mosquitto Client"}
      }
  }
  const client = required("mqtt").connect('localhost:1883');

  client.on('message', function (topic, message) {
    // message is Buffer
    console.log(` :${message.toString()}`);
    client.end()
  })
</script>

<style scoped>
</style>
