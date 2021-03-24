<template>
  <v-app>
    <!-- upper bar with buttons -->
    <v-app-bar app dark clipped-right flat>
      <v-slide-group show-arrows>
        <v-btn class='ma-2'> Terminal </v-btn>

        <v-btn rounded class='ma-2'>
          <v-file-input hide-input></v-file-input>
        </v-btn>

        <v-btn class='ma-2'> Web scrapping </v-btn>

        <v-btn class='ma-2'> Client Update </v-btn>
      </v-slide-group>
    </v-app-bar>
    <!-- left client navigation -->
    <v-navigation-drawer app dark style='max-height: 100%'>
      <v-list shaped>
        <v-subheader>CLIENTS</v-subheader>
        <v-list-item-group v-model='selectedItem' color='#666666'>
          <v-list-item v-for='(item, i) in items' :key='i'>
            <v-list-item-icon>
              <v-icon v-text='item.icon'></v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title v-text='item.text'></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <!-- right history navigation -->
    <v-navigation-drawer app right clipped dark class='drawer_right'>
      <h1 class='text-center blue-grey--text'>HISTORY</h1>
      <v-divider></v-divider>
    </v-navigation-drawer>

    <!-- Sizes your content based upon application components -->
    <v-main>
      <!-- Provides the application the proper gutter -->
      <v-container fluid> </v-container>
    </v-main>
    <v-footer>
      <v-text-field
        rounded
        name='code'
        placeholder='Command'
        class='command'
      ></v-text-field>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    selectedItem: 1,
    items: [
      { text: 'Nikola', icon: 'mdi-account' },
      { text: 'Aleksandar', icon: 'mdi-account' },
      { text: 'Aki', icon: 'mdi-account' },
      { text: 'Haru', icon: 'mdi-account' },
      { text: 'Eren', icon: 'mdi-account' },
      { text: 'Mikasa', icon: 'mdi-account' },
      { text: 'Milena', icon: 'mdi-account' },
      { text: 'Harry', icon: 'mdi-account' },
    ],
  }),
};
</script>

<style>
.v-main__wrap {
  background-color: #121212;
}
.v-file-input {
  margin-left: 4px;
}
.v-app-bar {
  right: 0px !important;
}
.v-footer {
  background-color: #121212 !important;
  left: 256px;
  right: 256px;
  max-width: calc(100% - 512px);
}
.command {
  background-color: #b0bec5;
}
.command > .v-input__control > .v-input__slot:before,
.command > .v-input__control > .v-input__slot:after {
  content: none;
}
.v-input__slot {
  margin-bottom: -6px !important;
  margin-top: -3px;
}
.v-divider {
  max-width: 70%;
  margin-left: 36px;
}

/* responsive */

@media (max-width: 575.98px) {
  .v-footer {
    left: 0px !important;
    right: 0px !important;
    max-width: 100%;
  }
}

/* MD */

@media (min-width: 768px) and (max-width: 991.98px) {
  .v-footer {
    left: 0px !important;
    right: 0px !important;
    max-width: 100%;
  }
}

/* LG */

@media (min-width: 992px) and (max-width: 1199.98px) {
  .v-footer {
    left: 0px !important;
    right: 0px !important;
    max-width: 100%;
  }
}
</style>