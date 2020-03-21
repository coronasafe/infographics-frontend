<template>
  <div>
    <v-app-bar dark color="blue">
      <v-container class="d-flex">
        
        <v-toolbar-title>Corona Infographics</v-toolbar-title>
              <v-spacer></v-spacer>

              <div>
                <v-menu open-on-hover top offset-y >
                  <template v-slot:activator="{ on }">
                    <v-btn dark v-on="on" color = "blue darken-2">Language</v-btn>
                  </template>

                  <v-list>
                    <v-list-item v-for="(item, index) in items" :key="index" >
                      <v-list-item-title>{{ item }}</v-list-item-title>
                    </v-list-item>
                  </v-list>
                </v-menu>
              </div>

      </v-container>
      
    </v-app-bar>
  </div>
</template>

<script>
export default {
  data: () => ({
    items: ["English", "Hindi"]
  })
};
</script>