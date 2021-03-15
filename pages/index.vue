<!--
<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <div class="text-center">
      </div>
    </v-col>
  </v-row>
</template>
-->
<template>
  <v-container>
    <v-row>
      <v-col v-for="n in 24" :key="n" cols="3">
        <v-card height="300" color="#12121F" tile elevation="0">
          <v-img
            class="mx-2"
            src="https://i.ytimg.com/vi/ASjNZZ7Ujqw/hqdefault.jpg?sqp=-oaymwEcCOADEI4CSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLAtA11B9ICD7gub_jwletdNl79x3A"
            contain
          ></v-img>
          <v-card-actions>
            <v-list-item-avatar size="40">
              <v-img
                src="https://i.ytimg.com/vi/ASjNZZ7Ujqw/hqdefault.jpg?sqp=-oaymwEcCOADEI4CSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLAtA11B9ICD7gub_jwletdNl79x3A"
              ></v-img>
            </v-list-item-avatar>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  components: {}
};
</script>
