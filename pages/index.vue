<template>
  
    <v-main class="grey lighten-3">
      <v-container>
        <v-row>
          <v-col cols="12" sm="3">
            <v-sheet rounded="lg" min-height="268">
              <v-card-title>{{ fullName }}</v-card-title>
              <v-card-subtitle>{{ userName }}</v-card-subtitle>
              <v-card-text>{{ userInterfaceText }}</v-card-text>
              <v-card-subtitle class="font-weight-medium pad-marg-top"
                >Follower: {{ countFollower }}</v-card-subtitle
              >
              <v-card-subtitle class="font-weight-medium pad-marg-top"
                >Likes: {{ countLikes }}</v-card-subtitle
              >
              <v-card-actions class="flex-space-between">
                <v-btn @click="addFollower">Follow</v-btn>
                <v-btn @click="addLike">Like</v-btn>
              </v-card-actions>
            </v-sheet>
          </v-col>

          <v-col cols="12" sm="6">
            <v-sheet min-height="70vh" rounded="lg">
              <v-container fluid>
                
                  <v-textarea
                    clearable
                    rows="2"
                    auto-grow
                    clear-icon="mdi-close-circle"
                    label="chateAlike"
                    value="chat your Alike."
                    counter
                    :rules="[rules.textarea]"
                    v-model="textAreaInput"
                  ></v-textarea>
                  <v-card-actions>
                    <v-btn
                      @click="createNewText"
                      class="white--text"
                      color="deep-purple accent-4"
                      depressed
                    >
                      SEND
                    </v-btn>
                  </v-card-actions>
                
              </v-container>
            </v-sheet>
          </v-col>

          <v-col cols="12" sm="3">
            <v-sheet rounded="lg" min-height="800">
              
              <ChatText 
              v-for="text in textArea"
              :key="text.id"
              :textArea="text"
              :userName="userName"
              />
              
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  
</template>

<script>
export default {
  data: () => ({
    links: ["Dashboard", "Messages", "Profile", "Updates"],
    firstName: "Wilhelm",
    lastName: "Kampelmann",
    userName: '@_WilhelmKampelmann',
    userInterfaceText: "Hello Vellas and felllows, im fellah",
    countFollower: 0,
    countLikes: 0,
    textAreaInput: '',
    textArea: [
      {id: 1, content: 'Hi i am a String'},
      {id: 2, content: 'Hi i am a String too'},
    ],
    rules: {
      textarea: (v) => !!(v || ''),
    },
  }),
  computed: {
    fullName: function () {
      return this.firstName + " " + this.lastName;
    },
  },
  methods: {
    addFollower() {
      this.countFollower++;
    },
    addLike() {
      this.countLikes++;
    },
    createNewText() {
      this.textArea.unshift(
        {
          id: this.textArea.length + 1,
          content: this.textAreaInput,
        }
      );
      console.log(this.textArea);
    },
  },
};
</script>

<style scoped>
.font-weight-medium {
  font-weight: 200;
}
.pad-marg-top {
  padding-top: 0.2rem;
}
.flex-space-between {
  display: flex;
  justify-content: center;
}
</style>>




