<template>
  <v-app :style="{ background: $vuetify.theme.themes.dark.background }">
    <v-container fluid>
      <v-row>
        <v-col cols="12" sm="3" class="border">
          <v-app-bar flat color="rgba(0,0,0,0)">
            <v-btn tile color="white" x-large block>
              <v-icon left color="blue">
                fas fa-plus
              </v-icon>
              <v-divider class="mx-3" vertical></v-divider>
              Написать
            </v-btn>
          </v-app-bar>

          <v-app-bar flat color="rgba(0,0,0,0)">
            <v-toolbar-title class="title">
              Переписки
            </v-toolbar-title>

            <v-spacer></v-spacer>
            <v-btn icon>
              <v-icon>fas fa-ellipsis-h</v-icon>
            </v-btn>
          </v-app-bar>
          <v-app-bar flat color="rgba(0,0,0,0)">
            <v-text-field
              filled
              label="Поиск..."
              append-icon="mdi-magnify"
              color="grey"
            ></v-text-field>
          </v-app-bar>

          <v-list two-line color="rgba(0,0,0,0)">
            <v-list-item-group
              v-model="selected"
              active-class="blue lighten-4"
              multiple
            >
              <template v-for="(item, index) in items">
                <v-list-item :key="item.title">
                  <v-badge
                    bordered
                    bottom
                    color="green"
                    dot
                    offset-x="22"
                    offset-y="26"
                  >
                    <v-list-item-avatar>
                      <v-img :src="item.avatar"></v-img>
                    </v-list-item-avatar>
                  </v-badge>
                  <template>
                    <v-list-item-content>
                      <v-list-item-title
                        v-text="item.title"
                      ></v-list-item-title>

                      <v-list-item-subtitle
                        v-text="item.subtitle"
                      ></v-list-item-subtitle>
                    </v-list-item-content>
                  </template>
                </v-list-item>

                <v-divider
                  v-if="index < items.length - 1"
                  :key="index"
                ></v-divider>
              </template>
            </v-list-item-group>
          </v-list>
        </v-col>
        <v-col cols="12" sm="6" class="border">
          <v-app-bar color="rgba(0,0,0,0)" flat>
            <v-badge
              bordered
              bottom
              color="green"
              dot
              offset-x="11"
              offset-y="13"
            >
              <v-avatar class="mt-n7" size="40" elevation="10">
                <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" />
              </v-avatar>
            </v-badge>
            <v-toolbar-title class="title pl-0 ml-2 mt-n4">
              Атай Омурзаков
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-title class="title pl-0 mr-2 mt-n4">
              Участники :
            </v-toolbar-title>
            <v-btn
              color="blue"
              icon
              class="mt-n5 mr-n2"
              outlined
              max-height="35"
              max-width="35"
            >
              <v-icon small>fas fa-plus</v-icon>
            </v-btn>
            <v-avatar class="mt-n5 mr-2" size="30" elevation="10">
              <img src="https://cdn.vuetifyjs.com/images/lists/5.jpg" />
            </v-avatar>
            <v-divider vertical inset class="mt-n1"></v-divider>
            <v-btn color="black" icon class="mt-n5">
              <v-icon>mdi-cog</v-icon>
            </v-btn>
          </v-app-bar>
          <v-app-bar color="rgba(0,0,0,0)" flat class="mb-16">
            <v-spacer></v-spacer>
            <v-card class="mt-10 mr-2" max-width="350px" color="blue" dark>
              <v-list-item three-line>
                <v-list-item-content>
                  <div class=" mb-4">
                    Доброе утро. Как дела?
                  </div>
                  <v-list-item-subtitle
                    >16 минут назад
                    <span class="ml-16"
                      >Прочитано 1:03</span
                    ></v-list-item-subtitle
                  >
                </v-list-item-content>
              </v-list-item>
            </v-card>
            <v-badge
              bordered
              bottom
              color="green"
              dot
              offset-x="10"
              offset-y="10"
            >
              <v-avatar class="mt-n5 " size="30" elevation="10">
                <img src="https://cdn.vuetifyjs.com/images/lists/5.jpg" />
              </v-avatar>
            </v-badge>
          </v-app-bar>
          <v-app-bar color="rgba(0,0,0,0)" flat class="mb-16">
            <v-badge
              bordered
              bottom
              color="green"
              dot
              offset-x="16"
              offset-y="9"
            >
              <v-avatar class="mt-n5 mr-2" size="30" elevation="10">
                <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" />
              </v-avatar>
            </v-badge>
            <v-card class="mt-10 " max-width="350px">
              <v-list-item three-line>
                <v-list-item-content>
                  <div class=" mb-4">
                    Привет. Я в офисе отправлю пару фото с офиса
                  </div>
                  <v-list-item-subtitle>12 минут назад</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-card>
            <v-btn color="black" icon class="mb-n10">
              <v-icon>fas fa-ellipsis-h</v-icon>
            </v-btn>
          </v-app-bar>
          <v-app-bar color="rgba(0,0,0,0)" flat class="mb-16">
            <v-badge
              bordered
              bottom
              color="green"
              dot
              offset-x="10"
              offset-y="10"
            >
              <v-avatar class="mt-n5 " size="30" elevation="10">
                <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" />
              </v-avatar>
            </v-badge>
            <v-card class="mt-10 ml-2" max-width="350px">
              <v-list-item three-line>
                <v-list-item-content>
                  <div class=" mb-4">
                    Атай отправил 3 фотографии :<br /><br />
                    <v-avatar size="60" tile class="mr-2">
                      <v-img
                        src="https://cdn.vuetifyjs.com/images/lists/5.jpg"
                      ></v-img>
                    </v-avatar>
                    <v-avatar size="60" tile class="mr-2">
                      <v-img
                        src="https://cdn.vuetifyjs.com/images/lists/5.jpg"
                      ></v-img>
                    </v-avatar>
                    <v-avatar size="60" tile>
                      <v-img
                        src="https://cdn.vuetifyjs.com/images/lists/5.jpg"
                      ></v-img>
                    </v-avatar>
                  </div>

                  <v-list-item-subtitle>12 минут назад</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-card>
          </v-app-bar>
          <v-app-bar color="rgba(0,0,0,0)" flat class="mb-8">
            <v-spacer></v-spacer>
            <v-card class="mt-10 mr-2" max-width="350px" color="blue" dark>
              <v-list-item three-line>
                <v-list-item-content>
                  <div class=" mb-4">
                    Оу круто
                  </div>
                  <v-list-item-subtitle
                    >2 минут назад
                    <span class="ml-16"
                      >Прочитано 1:23</span
                    ></v-list-item-subtitle
                  >
                </v-list-item-content>
              </v-list-item>
            </v-card>
            <v-badge
              bordered
              bottom
              color="green"
              dot
              offset-x="10"
              offset-y="10"
            >
              <v-avatar class="mt-n5 " size="30" elevation="10">
                <img src="https://cdn.vuetifyjs.com/images/lists/5.jpg" />
              </v-avatar>
            </v-badge>
          </v-app-bar>
          <v-app-bar color="rgba(0,0,0,0)" flat class="mb-16">
            <v-spacer></v-spacer>
            <v-card class="mt-10 mr-2" max-width="350px" color="blue" dark>
              <v-list-item three-line>
                <v-list-item-content>
                  <div class=" mb-4">
                    До скорой встречи !!!!!!!!!!!!!!
                  </div>
                  <v-list-item-subtitle
                    >3 минут назад
                    <span class="ml-16"
                      >Прочитано 1:24</span
                    ></v-list-item-subtitle
                  >
                </v-list-item-content>
              </v-list-item>
            </v-card>
            <v-badge
              bordered
              bottom
              color="green"
              dot
              offset-x="10"
              offset-y="10"
            >
              <v-avatar class="mt-n5 " size="30" elevation="10">
                <img src="https://cdn.vuetifyjs.com/images/lists/5.jpg" />
              </v-avatar>
            </v-badge>
          </v-app-bar>
          <v-app-bar color="rgba(0,0,0,0)" flat>
            <v-text-field
              v-model="message"
              append-icon="mdi-emoticon"
              :append-outer-icon="message ? 'mdi-send' : 'mdi-microphone'"
              filled
              clear-icon="mdi-close-circle"
              clearable
              label="Сообщение..."
              type="text"
              @click:append-outer="sendMessage"
              @click:clear="clearMessage"
            ></v-text-field>
          </v-app-bar>
        </v-col>
        <v-col cols="12" sm="3">
          <v-card class="text-center mt-8 mb-3" shaped>
            <v-badge
              bordered
              bottom
              color="green"
              dot
              offset-x="11"
              offset-y="13"
            >
              <v-avatar class="mt-n7" size="60" elevation="10">
                <img src="https://cdn.vuetifyjs.com/images/lists/1.jpg" />
              </v-avatar>
            </v-badge>
            <v-card-title class="layout justify-center"
              >Атай Омурзаков</v-card-title
            >
            <v-card-subtitle class="layout justify-center"
              >CEO в Кундолуке</v-card-subtitle
            >
            <v-list> </v-list>
          </v-card>
          <v-expansion-panels v-model="panel" multiple>
            <v-expansion-panel>
              <v-expansion-panel-header>
                <h3>Информация</h3>
              </v-expansion-panel-header>
              <v-expansion-panel-content> </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header>
                <h3>Фотографии(14)</h3>
              </v-expansion-panel-header>
              <v-expansion-panel-content> </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header>
                <h3>Файлы(3)</h3>
              </v-expansion-panel-header>
              <v-expansion-panel-content>
                <v-list shaped>
                  <v-list-item-group>
                    <v-list-item v-for="(item, i) in files" :key="i">
                      <v-list-item-icon>
                        <v-icon v-text="item.icon" color="green"></v-icon>
                      </v-list-item-icon>
                      <v-list-item-content>
                        <v-list-item-title
                          v-text="item.text"
                        ></v-list-item-title>
                      </v-list-item-content>
                    </v-list-item>
                  </v-list-item-group>
                </v-list>
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel>
              <v-expansion-panel-header>
                <h3>Закрепленные</h3>
              </v-expansion-panel-header>
              <v-expansion-panel-content> </v-expansion-panel-content>
            </v-expansion-panel>
          </v-expansion-panels>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>
<script>
export default {
  data: () => ({
    selected: [2],
    items: [
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/1.jpg",
        subtitle: `Привет. Как дела?`,
        title: "Атай Омурзаков"
      },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/2.jpg",
        subtitle: `Привет. Как дела?`,
        title: "Атай Омурзаков"
      },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/3.jpg",
        subtitle: `Привет. Как дела?`,
        title: "Атай Омурзаков"
      },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/4.jpg",
        subtitle: `Привет. Как дела?`,
        title: "Атай Омурзаков"
      },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/5.jpg",
        subtitle: `Привет. Как дела?`,
        title: "Атай Омурзаков"
      },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/1.jpg",
        subtitle: `Привет. Как дела?`,
        title: "Атай Омурзаков"
      },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/2.jpg",
        subtitle: `Привет. Как дела?`,
        title: "Атай Омурзаков"
      },
      {
        avatar: "https://cdn.vuetifyjs.com/images/lists/3.jpg",
        subtitle: `Привет. Как дела?`,
        title: "Атай Омурзаков"
      }
    ],
    files: [
      { text: "Landing_page.zip", icon: " mdi-cloud-upload" },
      { text: "Requirements.pdf", icon: " mdi-cloud-upload" },
      { text: "Uwagi.docx", icon: " mdi-cloud-upload" }
    ],
    panel: [2],

    password: "Password",
    show: false,
    message: "Написать сообщение",
    marker: true,
    iconIndex: 0
  }),
  computed: {
    theme() {
      return this.$vuetify.theme.dark ? "dark" : "light";
    }
  },
  methods: {
    sendMessage() {
      this.resetIcon();
      this.clearMessage();
    },
    clearMessage() {
      this.message = "";
    },
    resetIcon() {
      this.iconIndex = 0;
    }
  }
};
</script>
<style scoped>
.border {
  border-right: 1px solid grey;
}
</style>
