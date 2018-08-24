<template>
  <v-app id="inspire">

    <!-- navbar -->
    <v-navigation-drawer
      :clipped="$vuetify.breakpoint.lgAndUp"
      v-model="drawer"
      fixed
      app
      height="100%"
    >
      <!-- logo -->
      <span class="group pa-5">
        <v-avatar
            :size="avatarSize"
            color="grey lighten-4"
        >
            <img src="https://vuetifyjs.com/apple-touch-icon-180x180.png" alt="avatar">
        </v-avatar>
      </span>
      <!-- end logo -->
      <v-spacer></v-spacer>
      
      <v-list dense class="pt-0">
        <v-list-tile
          v-for="item in items"
          :key="item.title"
          @click=""
          :to="item.route"
          active-class="active-bar"
          class="menu-bar"
        >
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>

          <v-list-tile-content>
            <v-list-tile-title>{{ item.title }}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>

      <!-- footer -->
      <v-footer 
        fixed
        height="auto"
        
      >
        <span>
          Admin สวงนออโต้
          <v-btn
            class="flex"
            flat
            tile
              left
              >
          <v-icon  medium >contacts</v-icon>
          </v-btn>
        </span>
      
      </v-footer>
    </v-navigation-drawer>
    <!-- end navbar -->

    <!-- content -->
    <v-content>
      <router-view/>
    </v-content>
    <!-- end content -->

    <!-- <v-btn
      fab
      bottom
      right
      color="pink"
      dark
      fixed
      @click.stop="dialog = !dialog"
    >
      <v-icon>add</v-icon>
    </v-btn>
    <v-dialog v-model="dialog" width="800px">
      <v-card>
        <v-card-title
          class="grey lighten-4 py-4 title"
        >
          Create contact
        </v-card-title>
        <v-container grid-list-sm class="pa-4">
          <v-layout row wrap>
            <v-flex xs12 align-center justify-space-between>
              <v-layout align-center>
                <v-avatar size="40px" class="mr-3">
                  <img
                    src="//ssl.gstatic.com/s2/oz/images/sge/grey_silhouette.png"
                    alt=""
                  >
                </v-avatar>
                <v-text-field
                  placeholder="Name"
                ></v-text-field>
              </v-layout>
            </v-flex>
            <v-flex xs6>
              <v-text-field
                prepend-icon="business"
                placeholder="Company"
              ></v-text-field>
            </v-flex>
            <v-flex xs6>
              <v-text-field
                placeholder="Job title"
              ></v-text-field>
            </v-flex>
            <v-flex xs12>
              <v-text-field
                prepend-icon="mail"
                placeholder="Email"
              ></v-text-field>
            </v-flex>
            <v-flex xs12>
              <v-text-field
                type="tel"
                prepend-icon="phone"
                placeholder="(000) 000 - 0000"
                mask="phone"
              ></v-text-field>
            </v-flex>
            <v-flex xs12>
              <v-text-field
                prepend-icon="notes"
                placeholder="Notes"
              ></v-text-field>
            </v-flex>
          </v-layout>
        </v-container>
        <v-card-actions>
          <v-btn flat color="primary">More</v-btn>
          <v-spacer></v-spacer>
          <v-btn flat color="primary" @click="dialog = false">Cancel</v-btn>
          <v-btn flat @click="dialog = false">Save</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog> -->
  </v-app>
</template>

<script>
  export default {
    data: () => ({
      dialog: false,
      drawer: null,
      
      items: [
        { icon: 'contacts', title: 'ภาพรวมทั้งหมด',route:'/' },
        { icon: 'history', title: 'รายการสั่งซื้อ',route:'/history' },
        { icon: 'content_copy', title: 'จัดการคลังสินค้า',route:'/store' },
        { icon: 'settings', title: 'รายชื่อข้อมูลลูกค้า',route:'/customer' },
        { icon: 'chat_bubble', title: 'จัดการผู้ใช้งาน',route:'/login' },
        { icon: 'help', title: 'ตั้งค่า',route:'/setting' },
      ]
    }),
    props: {
      source: String
    },
    computed: {
      avatarSize () {
        return '150px'
      }
    }
  }

  
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scope>

  .active-bar{
    background-color:rgb(14, 67, 163);
  }
  .menu-bar:hover{
    background-color:rgb(14, 67, 163);
  }

</style>