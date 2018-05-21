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
        </v-btn> <span class="hidden-sm-and-down title">Start Menu</span>
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
      <!-- File Flex -->
      
      <v-toolbar dense>
        <v-toolbar-title>FILE</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn icon>
          <v-icon>view_list</v-icon>
        </v-btn>
      </v-toolbar>
      <v-card id="card-file">
      <section class="card-flex1">
        
        <div class="card-flex1--content">
          <div class="card-flex1-column-item-top"><v-icon style="font-size: 90px;">note_add</v-icon></div>
          <div class="card-flex1-column-item-bottom" style="font-size: 28px;">New</div>
        </div>
        <div class="card-flex1--content">
        <div class="card-flex1-column-item-top"><v-icon style="font-size: 90px;">folder_open</v-icon></div>
          <div class="card-flex1-column-item-bottom" style="font-size: 28px;">Open</div>
        </div>
        <div class="card-flex1--content">
        <div class="card-flex1-column-item-top"><v-icon style="font-size: 90px;">save_alt</v-icon></div>
          <div class="card-flex1-column-item-bottom" style="font-size: 28px;">Save</div>
        </div>
        <div class="card-flex1--content">
          <div class="card-flex1-column-item-top"><v-icon style="font-size: 90px;">compare_arrows</v-icon></div>
          <div class="card-flex1-column-item-bottom" style="font-size: 28px;">Compare</div>
        </div>
        <div class="card-flex1--content">
           <div class="card-flex1-column-item-top"><v-icon style="font-size: 90px;">list</v-icon></div>
          <div class="card-flex1-column-item-bottom" style="font-size: 28px;">Create BOM</div>
        </div>
        <div class="card-flex1--content">
        <div class="card-flex1-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex1-column-item-bottom" style="font-size: 28px;">Empty</div>
        </div>
        <div class="card-flex1--content">
        <div class="card-flex1-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex1-column-item-bottom" style="font-size: 28px;">Empty</div>
        </div>
        <div class="card-flex1--content">
        <div class="card-flex1-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex1-column-item-bottom" style="font-size: 28px;">Empty</div>
        </div>
        <div class="card-flex1--content">
        <div class="card-flex1-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex1-column-item-bottom" style="font-size: 28px;">Empty</div>
        </div>
      </section>
      </v-card>
      <!-- End of File Flex -->
      <!-- Net Flex -->
      
      <v-toolbar dense>
        <v-toolbar-title>NET</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn icon>
          <v-icon>view_list</v-icon>
        </v-btn>
      </v-toolbar>
      <v-card id="card-net">
      <section class="card-flex2">
        
        <div class="card-flex2--content">
          <div class="card-flex2-column-item-top"><v-icon style="font-size: 90px;">image_search</v-icon></div>
          <div class="card-flex2-column-item-bottom" style="font-size: 28px;">Monitoring</div>
        </div>
        <div class="card-flex2--content">
        <div class="card-flex2-column-item-top side-off" ><v-icon style="font-size: 60px;">settings</v-icon><v-icon style="font-size: 60px;">code</v-icon><v-icon style="font-size: 60px;">folder_open</v-icon></div>
          <div class="card-flex2-column-item-bottom" style="font-size: 28px;">Offline Config</div>
        </div>
        <div class="card-flex2--content">
        <div class="card-flex2-column-item-top side-off"><v-icon style="font-size: 60px;">settings</v-icon><v-icon style="font-size: 60px;">code</v-icon><v-icon style="font-size: 60px;">cloud_queue</v-icon></div>
          <div class="card-flex2-column-item-bottom" style="font-size: 28px;">Online Config</div>
        </div>
        <div class="card-flex2--content">
          <div class="card-flex2-column-item-top side-off"><v-icon style="font-size: 60px;">settings</v-icon><v-icon style="font-size: 60px;">arrow_forward</v-icon><v-icon style="font-size: 60px;">cloud_queue</v-icon></div>
          <div class="card-flex2-column-item-bottom" style="font-size: 28px;">Apply Config</div>
        </div>
        <div class="card-flex2--content">
           <div class="card-flex2-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex2-column-item-bottom" style="font-size: 28px;">Empty</div>
        </div>
        <div class="card-flex2--content">
        <div class="card-flex2-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex2-column-item-bottom" style="font-size: 28px;">Empty</div>
        </div>
        <div class="card-flex2--content">
        <div class="card-flex2-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex2-column-item-bottom" style="font-size: 28px;">Empty</div>
        </div>
        <div class="card-flex2--content">
        <div class="card-flex2-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex2-column-item-bottom" style="font-size: 28px;">Empty</div>
        </div>
        <div class="card-flex2--content">
        <div class="card-flex2-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex2-column-item-bottom" style="font-size: 28px;">Empty</div>
        </div>
      </section>
      </v-card>
      <!-- End of Net Flex -->
      <!-- Simul Flex -->
      
      <v-toolbar dense>
        <v-toolbar-title>SIMULATION</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn icon>
          <v-icon>view_list</v-icon>
        </v-btn>
      </v-toolbar>
      <v-card id="card-simul">
      <section class="card-flex3">
        
        <div class="card-flex3--content">
        <div class="card-flex3-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex3-column-item-bottom" style="font-size: 28px;">Empty</div></div>
        <div class="card-flex3--content">
        <div class="card-flex3-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex3-column-item-bottom" style="font-size: 28px;">Empty</div></div>
        <div class="card-flex3--content">
        <div class="card-flex3-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex3-column-item-bottom" style="font-size: 28px;">Empty</div></div>
        <div class="card-flex3--content">
        <div class="card-flex3-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex3-column-item-bottom" style="font-size: 28px;">Empty</div></div>
        <div class="card-flex3--content">
        <div class="card-flex3-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex3-column-item-bottom" style="font-size: 28px;">Empty</div></div>
        <div class="card-flex3--content">
        <div class="card-flex3-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex3-column-item-bottom" style="font-size: 28px;">Empty</div></div>
        <div class="card-flex3--content">
        <div class="card-flex3-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex3-column-item-bottom" style="font-size: 28px;">Empty</div></div>
        <div class="card-flex3--content">
        <div class="card-flex3-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex3-column-item-bottom" style="font-size: 28px;">Empty</div></div>
          <div class="card-flex3--content">
        <div class="card-flex3-column-item-top"><v-icon style="font-size: 90px;">watch_later</v-icon></div>
          <div class="card-flex3-column-item-bottom" style="font-size: 28px;">Empty</div></div>
      </section>
      </v-card>
      <!-- End of Simul Flex -->
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
    transition: 'slide-y-reverse-transition'
    // cards: [
    //   { title: 'Pre-fab homes', src: 'https://vuetifyjs.com/static/doc-images/cards/house.jpg', flex: 12 },
    //   { title: 'Favorite road trips', src: 'https://vuetifyjs.com/static/doc-images/cards/road.jpg', flex: 6 },
    //   { title: 'Best airlines', src: 'https://vuetifyjs.com/static/doc-images/cards/plane.jpg', flex: 6 }
    // ]
  }),
  name: 'App'
}
</script>

<style scoped>
  #card-file {
    border: none;
    margin: 0px;
    cursor: pointer;
  }
   #card-net {
    border: none;
    margin: 0px;
    cursor: pointer;
  }
  #card-simul {
    border: none;
    margin: 0px;
    cursor: pointer;
  }
  .side-off {
    margin-top: 40px;
  }
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

  .card-flex1 {
  display: flex;
  min-width: 100%;
  min-height: 200px;
  overflow-x: auto;
  justify-content: space-between;
}

.card-flex1--content {
  background-color: #ecf0f1;
  min-width: 200px;
  margin: 5px;
  padding: 5px;
  color:#616161;
  align-items: center;
  display: flex;
  flex-direction: column;
  background-color: #9ac7bf;
  border-radius: 5px;
  box-shadow: 0 0 0 2px #ddd inset, 0 2px 2px #fff;
}
.card-flex1--content:hover {
   background: #9FA8DA;
    box-shadow: 0 0 0 1px #aaa inset, 0 1px 1px #aaa;
}
.card-flex1--content:active {
   background: #9ac7bf;
    box-shadow: 0 0 0 1px #aaa inset, 0 1px 1px #aaa;
}
.card-flex1-column-item-top {
  flex: 3;
  align-items: center;
  justify-content: center;
}
.card-flex1-column-item-bottom {
  flex: 1;
}

  .card-flex2 {
  display: flex;
  min-width: 100%;
  min-height: 200px;
  overflow-x: auto;
  justify-content: space-between;
}

.card-flex2--content {
  background-color: #ecf0f1;
  min-width: 200px;
  margin: 5px;
  padding: 5px;
  color: #616161;
  align-items: center;
  display: flex;
  flex-direction: column;
  background-color: #33ff33;
  border-radius: 5px;
  box-shadow: 0 0 0 2px #ddd inset, 0 2px 2px #fff;
}
.card-flex2--content:hover {
   background: #64DD17;
    box-shadow: 0 0 0 1px #aaa inset, 0 1px 1px #aaa;
}
.card-flex2--content:active {
   background: #33ff33 ;
    box-shadow: 0 0 0 1px #aaa inset, 0 1px 1px #aaa;
}
.card-flex2-column-item-top {
  flex: 3;
  align-items: center;
  justify-content: center;
}
.card-flex2-column-item-bottom {
  flex: 1;
}

  .card-flex3 {
  display: flex;
  min-width: 100%;
  min-height: 200px;
  overflow-x: auto;
  justify-content: space-between;
}

.card-flex3--content {
  background-color: #ecf0f1;
  min-width: 200px;
  margin: 5px;
  padding: 5px;
  color: #616161;
  align-items: center;
  display: flex;
  flex-direction: column;
  background-color: #1DE9B6;
  border-radius: 5px;
  box-shadow: 0 0 0 2px #ddd inset, 0 2px 2px #fff;
}
.card-flex3--content:hover {
   background: #00BFA5;
    box-shadow: 0 0 0 1px #aaa inset, 0 1px 1px #aaa;
}
.card-flex3--content:active {
   background: #1DE9B6 ;
    box-shadow: 0 0 0 1px #aaa inset, 0 1px 1px #aaa;
}

.card-flex3-column-item-top {
  flex: 3;
  align-items: center;
  justify-content: center;
}
.card-flex3-column-item-bottom {
  flex: 1;
}

.card-flex1::-webkit-scrollbar {
  display: none;
}
.card-flex2::-webkit-scrollbar {
  display: none;
}

.card-flex3::-webkit-scrollbar {
  display: none;
}


</style>