<template>
  <v-container>
    <v-app-bar
      app
      color="primary"
      dark
      dense
    >
      <v-app-bar-nav-icon
        @click="getCurrentUser"
      />
    </v-app-bar>
    <v-navigation-drawer
      v-model="drawyer"
      fixed
      temporary
    >
      <v-list
        nav
      >
        <v-list-item-group>
          <v-list-item
            @click="home"
          >
            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>
              Home
            </v-list-item-title>
          </v-list-item>
          <v-list-item
            @click="account"
          >
            <v-list-item-icon>
              <v-icon>mdi-account</v-icon>
            </v-list-item-icon>
            <v-list-item-title>
              Account
            </v-list-item-title>
          </v-list-item>
          <v-list-item
            v-if="isAdmin"
            @click="admin"
          >
            <v-list-item-icon>
              <v-icon>mdi-database-cog</v-icon>
            </v-list-item-icon>
            <v-list-item-title>
              Admin
            </v-list-item-title>
          </v-list-item>
          <v-list-item
            :disabled="!loggedIn"
            @click="logout"
          >
            <v-list-item-icon>
              <v-icon>mdi-logout</v-icon>
            </v-list-item-icon>
            <v-list-item-title>
              Logout
            </v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
      <template #append>
        <v-btn
          block
          href="https://github.com/kaythomas0/noisedash"
          target="_blank"
        >
          Source Code
        </v-btn>
      </template>
    </v-navigation-drawer>
  </v-container>
</template>

<script src="./appbar.js"></script>
