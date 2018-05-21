<template>
  <v-app id="inspire">
    <v-navigation-drawer
      fixed
      :clipped="$vuetify.breakpoint.mdAndUp"
      app
      v-model="drawer"
    >
      <v-list dense>
        <template v-for="item in items">
          <v-layout
            row
            v-if="item.heading"
            align-center
            :key="item.heading"
          >
            <v-flex xs6>
              <v-subheader v-if="item.heading">
                {{ item.heading }}
              </v-subheader>
            </v-flex>
            <v-flex xs6 class="text-xs-center">
              <a href="#!" class="body-2 black--text">EDIT</a>
            </v-flex>
          </v-layout>
          <v-list-group
            v-else-if="item.children"
            v-model="item.model"
            :key="item.text"
            :prepend-icon="item.model ? item.icon : item['icon-alt']"
            append-icon=""
          >
            <v-list-tile slot="activator">
              <v-list-tile-content>
                <v-list-tile-title>
                  {{ item.text }}
                </v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
            <v-list-tile
              v-for="(child, i) in item.children"
              :key="i"
              @click=""
            >
              <v-list-tile-action v-if="child.icon">
                <v-icon>{{ child.icon }}</v-icon>
              </v-list-tile-action>
              <v-list-tile-content>
                <v-list-tile-title>
                  {{ child.text }}
                </v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
          </v-list-group>
          <v-list-tile v-else @click="" :key="item.text">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>
                {{ item.text }}
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </template>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      color="grey darken-2"
      dark
      app
      :clipped-left="$vuetify.breakpoint.mdAndUp"
      fixed
    >
      <v-toolbar-title style="width: 300px" class="ml-0 pl-3">
        <v-btn icon style="background-color: #E56353;">
        <v-icon>apps</v-icon>
        </v-btn>
        <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
        
       
      </v-toolbar-title><v-btn icon style="background-color: #33FF33;">
        <v-icon>settings_applications</v-icon>
        </v-btn> <span class="hidden-sm-and-down title">Main tile</span>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>search</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>more_vert</v-icon>
      </v-btn>
      <!-- <v-btn icon large>
        <v-avatar size="32px" tile>
          <img
            src="https://vuetifyjs.com/static/doc-images/logo.svg"
            alt="Vuetify"
          >
        </v-avatar>
      </v-btn> -->
    </v-toolbar>
    <v-content style="background-color: #E6E6E6;">
     
      <!-- <v-container fluid fill-height>
        <v-layout>
          <v-tooltip right>
          </v-tooltip>
        </v-layout>
      </v-container> -->
      <v-layout row>
      <v-flex xs12 sm6>
        <v-toolbar color="indigo" dark>
          <v-toolbar-side-icon></v-toolbar-side-icon>
          <v-toolbar-title>Discover</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn icon>
            <v-icon>search</v-icon>
          </v-btn>
        </v-toolbar>
        <v-card>
          <v-container fluid grid-list-md>
            <v-layout row wrap>
              <v-flex
                v-for="card in cards"
                v-bind="{ [`xs${card.flex}`]: true }"
                :key="card.title"
              >
                <v-card>
                  <v-card-media
                    :src="card.src"
                    height="200px"
                  >
                    <v-container fill-height fluid>
                      <v-layout fill-height>
                        <v-flex xs12 align-end flexbox>
                          <span class="headline white--text" v-text="card.title"></span>
                        </v-flex>
                      </v-layout>
                    </v-container>
                  </v-card-media>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn icon>
                      <v-icon>favorite</v-icon>
                    </v-btn>
                    <v-btn icon>
                      <v-icon>bookmark</v-icon>
                    </v-btn>
                    <v-btn icon>
                      <v-icon>share</v-icon>
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-flex>
            </v-layout>
          </v-container>
        </v-card>
      </v-flex>
      <v-flex xs12 sm6>
        <v-toolbar color="indigo" dark>
          <v-toolbar-side-icon></v-toolbar-side-icon>
          <v-toolbar-title>Discover</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn icon>
            <v-icon>search</v-icon>
          </v-btn>
        </v-toolbar>
        <v-card>
          <v-container fluid grid-list-md>
            <v-layout row wrap>
              <v-flex
                v-for="card in cards"
                v-bind="{ [`xs${card.flex}`]: true }"
                :key="card.title"
              >
                <v-card>
                  <v-card-media
                    :src="card.src"
                    height="200px"
                  >
                    <v-container fill-height fluid>
                      <v-layout fill-height>
                        <v-flex xs12 align-end flexbox>
                          <span class="headline white--text" v-text="card.title"></span>
                        </v-flex>
                      </v-layout>
                    </v-container>
                  </v-card-media>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn icon>
                      <v-icon>favorite</v-icon>
                    </v-btn>
                    <v-btn icon>
                      <v-icon>bookmark</v-icon>
                    </v-btn>
                    <v-btn icon>
                      <v-icon>share</v-icon>
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-flex>
            </v-layout>
          </v-container>
        </v-card>
      </v-flex>
      <v-flex xs12 sm6>
        <v-toolbar color="indigo" dark>
          <v-toolbar-side-icon></v-toolbar-side-icon>
          <v-toolbar-title>Discover</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn icon>
            <v-icon>search</v-icon>
          </v-btn>
        </v-toolbar>
        <v-card>
          <v-container fluid grid-list-md>
            <v-layout row wrap>
              <v-flex
                v-for="card in cards"
                v-bind="{ [`xs${card.flex}`]: true }"
                :key="card.title"
              >
                <v-card>
                  <v-card-media
                    :src="card.src"
                    height="200px"
                  >
                    <v-container fill-height fluid>
                      <v-layout fill-height>
                        <v-flex xs12 align-end flexbox>
                          <span class="headline white--text" v-text="card.title"></span>
                        </v-flex>
                      </v-layout>
                    </v-container>
                  </v-card-media>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn icon>
                      <v-icon>favorite</v-icon>
                    </v-btn>
                    <v-btn icon>
                      <v-icon>bookmark</v-icon>
                    </v-btn>
                    <v-btn icon>
                      <v-icon>share</v-icon>
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-flex>
            </v-layout>
          </v-container>
        </v-card>
      </v-flex>
      </v-layout>
    </v-content>

    <!-- <v-btn
      fab
      bottom
      right
      color="pink"
      dark
      fixed
      @click.stop="sheet = !sheet"
      class="bottom-btn">
      <v-icon>add</v-icon>
      <v-icon>edit</v-icon>
    </v-btn>  -->
    
    <v-speed-dial
        v-model="fab"
        :top="top"
        :bottom="bottom"
        :right="right"
        :left="left"
        fixed
        :direction="direction"
        :open-on-hover="hover"
        :transition="transition"
        class="bottom-btn"
      >
        <v-btn
          slot="activator"
          v-model="fab"
          color="blue darken-2"
          dark
          fab
          @click="sheet = !sheet"
        >
          <v-icon>close</v-icon>
          <v-icon>add</v-icon>
        </v-btn>
        <!-- <v-btn
          fab
          dark
          small
          color="green"
        >
          <v-icon>edit</v-icon>
        </v-btn>
        <v-btn
          fab
          dark
          small
          color="indigo"
        >
          <v-icon>add</v-icon>
        </v-btn>
        <v-btn
          fab
          dark
          small
          color="red"
        >
          <v-icon>delete</v-icon>
        </v-btn> -->
      </v-speed-dial>





    <!-- <div class="text-xs-center"> -->
      <v-bottom-sheet v-model="sheet" class="bottom-sheet">
        <v-flex xs12 sm12 offset-sm0 style="display: flex;">
        <v-card style="height: 300px; width: 300px;" class="card grow">
          <v-card-media
            height="200px"
            src="https://andpro.ru/upload/resize_cache/iblock/550/340_340_140cd750bba9870f18aada2478b24840a/646c62f1_33b9_11e6_80cb_001e67d1aaeb_a0b6cad0_663d_11e7_80da_001e67d1aaeb.jpg"
          >
            <v-container fill-height fluid>
              <v-layout fill-height>
                <v-flex xs12 align-end flexbox>
                </v-flex>
              </v-layout>
            </v-container>
          </v-card-media>
          <v-card-title>
            <div>
              <span>Add Devices</span>
            </div>
          </v-card-title>
        </v-card>
        <v-card style="height: 300px; width: 300px;" class="card grow">
          <v-card-media
            height="200px"
            src="https://andpro.ru/upload/resize_cache/iblock/550/340_340_140cd750bba9870f18aada2478b24840a/646c62f1_33b9_11e6_80cb_001e67d1aaeb_a0b6cad0_663d_11e7_80da_001e67d1aaeb.jpg"
          >
            <v-container fill-height fluid>
              <v-layout fill-height>
                <v-flex xs12 align-end flexbox>
                </v-flex>
              </v-layout>
            </v-container>
          </v-card-media>
          <v-card-title>
            <div>
              <span>Action2</span>
            </div>
          </v-card-title>
        </v-card>
        <v-card style="height: 300px; width: 300px;" class="card grow">
          <v-card-media
            height="200px"
            src="https://andpro.ru/upload/resize_cache/iblock/550/340_340_140cd750bba9870f18aada2478b24840a/646c62f1_33b9_11e6_80cb_001e67d1aaeb_a0b6cad0_663d_11e7_80da_001e67d1aaeb.jpg"
          >
            <v-container fill-height fluid>
              <v-layout fill-height>
                <v-flex xs12 align-end flexbox>
                </v-flex>
              </v-layout>
            </v-container>
          </v-card-media>
          <v-card-title>
            <div>
              <span>Action3</span>
            </div>
          </v-card-title>
        </v-card>
        <v-card style="height: 300px; width: 300px;" class="card grow">
          <v-card-media
            height="200px"
            src="https://andpro.ru/upload/resize_cache/iblock/550/340_340_140cd750bba9870f18aada2478b24840a/646c62f1_33b9_11e6_80cb_001e67d1aaeb_a0b6cad0_663d_11e7_80da_001e67d1aaeb.jpg"
          >
            <v-container fill-height fluid>
              <v-layout fill-height>
                <v-flex xs12 align-end flexbox>
                </v-flex>
              </v-layout>
            </v-container>
          </v-card-media>
          <v-card-title>
            <div>
              <span>Action4</span>
            </div>
          </v-card-title>
        </v-card>
        <v-card style="height: 300px; width: 300px;" class="card grow">
          <v-card-media
            height="200px"
            src="https://andpro.ru/upload/resize_cache/iblock/550/340_340_140cd750bba9870f18aada2478b24840a/646c62f1_33b9_11e6_80cb_001e67d1aaeb_a0b6cad0_663d_11e7_80da_001e67d1aaeb.jpg"
          >
            <v-container fill-height fluid>
              <v-layout fill-height>
                <v-flex xs12 align-end flexbox>
                </v-flex>
              </v-layout>
            </v-container>
          </v-card-media>
          <v-card-title>
            <div>
              <span>Action5</span>
            </div>
          </v-card-title>
        </v-card>
        <v-card style="height: 300px; width: 300px;" class="card grow">
          <v-card-media
            height="200px"
            src="https://andpro.ru/upload/resize_cache/iblock/550/340_340_140cd750bba9870f18aada2478b24840a/646c62f1_33b9_11e6_80cb_001e67d1aaeb_a0b6cad0_663d_11e7_80da_001e67d1aaeb.jpg"
          >
            <v-container fill-height fluid>
              <v-layout fill-height>
                <v-flex xs12 align-end flexbox>
                </v-flex>
              </v-layout>
            </v-container>
          </v-card-media>
          <v-card-title>
            <div>
              <span>Action5</span>
            </div>
          </v-card-title>
        </v-card>
      </v-flex>
      </v-bottom-sheet>
    </div>
  </v-app>
</template>

<script>
export default {
 data: () => ({
      dialog: false,
      drawer: null,
      items: [
        { icon: 'contacts', text: 'Item1' },
        { icon: 'history', text: 'Item2' },
        { icon: 'content_copy', text: 'Item3' },
        {
          icon: 'keyboard_arrow_up',
          'icon-alt': 'keyboard_arrow_down',
          text: 'Item4',
          model: true,
          children: [
            { icon: 'add', text: 'Item5' }
          ]
        },
        {
          icon: 'keyboard_arrow_up',
          'icon-alt': 'keyboard_arrow_down',
          text: 'Item6',
          model: false,
          children: [
            { text: 'Import' },
            { text: 'Export' },
            { text: 'Print' },
            { text: 'Undo changes' },
            { text: 'Other contacts' }
          ]
        },
        { icon: 'settings', text: 'Item7' },
        { icon: 'chat_bubble', text: 'Item8' },
        { icon: 'help', text: 'Item9' },
        { icon: 'phonelink', text: 'Item10' },
        { icon: 'keyboard', text: 'Item11' }
      ],
      sheet: false,
    tiles: [
      { img: 'keep.png', title: 'Item12' },
      { img: 'inbox.png', title: 'Item14' },
      { img: 'hangouts.png', title: 'Item15' },
      { img: 'messenger.png', title: 'Item16' },
      { img: 'google.png', title: 'Item17' }
    ],
    direction: 'top',
    fab: true,
    fling: false,
    hover: false,
    tabs: null,
    top: false,
    right: true,
    bottom: true,
    left: false,
    transition: 'slide-y-reverse-transition',
    cards: [
      { title: 'Pre-fab homes', src: 'https://vuetifyjs.com/static/doc-images/cards/house.jpg', flex: 12 },
      { title: 'Favorite road trips', src: 'https://vuetifyjs.com/static/doc-images/cards/road.jpg', flex: 6 },
      { title: 'Best airlines', src: 'https://vuetifyjs.com/static/doc-images/cards/plane.jpg', flex: 6 }
    ]
    }),
  name: 'App'
}
</script>

<style scoped>
  .card {
    border: 2px solid #34495e;
    margin-left: 5px;
    margin-right: 5px;
    cursor: pointer;
  }
  .grow { transition: all .3s ease-in-out; }
  .grow:hover { transform: scale(1.05); }

  .bottom-btn {
    z-index: 99999;
  }
  .bottom-sheet {
    z-index: 100;
  }

</style>