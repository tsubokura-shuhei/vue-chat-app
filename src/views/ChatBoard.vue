<template>
  <v-app id="inspire">

    <v-main>
      <v-container
        class="py-8 px-6"
        fluid
      >
        <v-row>
          <v-col
            v-for="card in cards"
            :key="card"
            cols="12"
          >
            <v-card>
              <v-subheader>{{ card }}</v-subheader>

              <v-list two-line>
                <template v-for="n in 6">
                  <v-list-item

                    :key="n"
                  >
                    <v-list-item-avatar color="grey darken-1">
                    </v-list-item-avatar>

                    <v-list-item-content>
                      <!-- <v-list-item-title>Message {{ n }}</v-list-item-title> -->

                      <v-list-item-subtitle class="message">
                        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nihil repellendus distinctio similique
                      </v-list-item-subtitle>
                    </v-list-item-content>
                  </v-list-item>

                  <v-divider
                    v-if="n !== 6"
                    :key="`divider-${n}`"
                    inset
                  ></v-divider>
                </template>
              </v-list>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
      <v-textarea
          append-icon="mdi-comment"
          class="mx-2"
          label="メッセージを送信する"
          rows="3"
          auto-grow
        ></v-textarea>
    </v-main>
  </v-app>
</template>

<script>
  export default {
    created() {
      this.user_id = this.$route.query.user_id;
      console.log("user_id", this.user_id)
    },
    data: () => ({
      user_id: '',
      cards: ['Today'],
      drawer: null,
      links: [
        ['mdi-inbox-arrow-down', 'Inbox'],
        ['mdi-send', 'Send'],
        ['mdi-delete', 'Trash'],
        ['mdi-alert-octagon', 'Spam'],
      ],
    }),
  }
</script>

<style scoped>
.message{
  text-align: left;
}
</style>