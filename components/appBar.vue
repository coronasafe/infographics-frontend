<template>
  <div>
    <v-app-bar color="#ffffff">
        
        <v-toolbar-title>COVID-19 Infographics</v-toolbar-title>

<v-spacer></v-spacer>
         <v-img
    class="mx-2"
    src="https://gblobscdn.gitbook.com/spaces%2F-M233b0_JITp4nk0uAFp%2Favatar-rectangle-1584020107059.png"
    max-height="150"
    max-width="150"
    contain
  ></v-img>
              <v-spacer></v-spacer>

              <div>
                <v-menu open-on-hover top offset-y >
                  <template v-slot:activator="{ on }">
                    <v-btn v-on="on" icon><font-awesome-icon :icon="['fas', 'language']" style="font-size: 30px"/></v-btn>
                  </template>

                  <v-list>
                    <v-list-item v-for="(item, index) in items" :key="index" >
                      <v-list-item-title>{{ item }}</v-list-item-title>
                    </v-list-item>
                  </v-list>
                </v-menu>
              </div>

      
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