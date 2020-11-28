<template>
  <v-container class="container">
    <v-card-subtitle>
        {{ userName }} wrote:
    </v-card-subtitle>   
    <v-card-text>
        {{ textArea.content }}
    </v-card-text>
    </v-container>
</template>

<script>
export default {
  name: "chatText",
  props: {
    userName: {
      type: String,
      required: true,
    },
    textArea: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.container{
    background: rebeccapurple;
    margin-bottom: 1rem;
    border-radius: 5px;

}
</style>