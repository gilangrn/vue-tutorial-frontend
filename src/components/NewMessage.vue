<template>
  <v-flex sm8 offset-sm2>
    <v-card>
      <v-toolbar dark>
        <v-toolbar-title>New Messages</v-toolbar-title>
      </v-toolbar>
      <v-form>
        <v-container>
          <v-row>
            <v-col cols="12" md="4">
              <v-text-field
                v-model="messageBody"
                label="Message"
                required
              ></v-text-field>
              <v-btn color="success" class="mr-4" @click="submit">
                Submit
              </v-btn>
            </v-col>
          </v-row>
        </v-container>
      </v-form>
    </v-card>
  </v-flex>
</template>

<script>
export default {
  data() {
    return {
      messageBody: "",
    };
  },
  methods: {
    async submit() {
      try {
        this.$store.dispatch("newMessage", this.messageBody);
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>
