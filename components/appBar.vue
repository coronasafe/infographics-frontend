<template>
  <div>
    <v-app-bar color="#ffffff">
      <v-container class="d-flex">
        
        <v-toolbar-title>COVID-19 Infographics</v-toolbar-title>

<v-spacer></v-spacer>
         <v-img
    class="mx-2"
    src="https://gblobscdn.gitbook.com/spaces%2F-M233b0_JITp4nk0uAFp%2Favatar-rectangle-1584020107059.png"
    max-height="100"
    max-width="100"
    contain
  ></v-img>
              <v-spacer></v-spacer>

              <div>
                <v-menu open-on-hover top offset-y >
                  <template v-slot:activator="{ on }">
                    <v-btn v-on="on" color="#ffffff">Language</v-btn>
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