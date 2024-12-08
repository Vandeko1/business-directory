<template>
  <v-table>
    <thead>
      <tr>
        <th class="text-left">Назва</th>
        <th class="text-left">Калорії</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in desserts" :key="item.name">
        <td>{{ item.name }}</td>
        <td>{{ item.calories }}</td>
      </tr>
    </tbody>
  </v-table>
  <v-form>
    <v-container>
      <v-row>
        <v-col cols="12" sm="6">
          <v-text-field
            label="Regular"
            model-value="John Doe"
            disabled
          ></v-text-field>
        </v-col>

        <v-col cols="12" sm="6">
          <v-text-field
            label="Regular"
            model-value="John Doe"
            readonly
          ></v-text-field>
        </v-col>

        <v-col cols="12" sm="6">
          <v-text-field
            label="Solo"
            model-value="John Doe"
            variant="solo"
            disabled
          ></v-text-field>
        </v-col>

        <v-col cols="12" sm="6">
          <v-text-field
            label="Solo"
            model-value="John Doe"
            variant="solo"
            readonly
          ></v-text-field>
        </v-col>

        <v-col cols="12" sm="6">
          <v-text-field
            label="Outlined"
            model-value="John Doe"
            variant="outlined"
            disabled
          ></v-text-field>
        </v-col>

        <v-col cols="12" sm="6">
          <v-text-field
            label="Outlined"
            model-value="John Doe"
            variant="outlined"
            readonly
          ></v-text-field>
        </v-col>

        <v-col cols="12" sm="6">
          <v-text-field
            label="underlined"
            model-value="John Doe"
            variant="underlined"
            disabled
          ></v-text-field>
        </v-col>

        <v-col cols="12" sm="6">
          <v-text-field
            label="underlined"
            model-value="John Doe"
            variant="underlined"
            readonly
          ></v-text-field>
        </v-col>
      </v-row>
    </v-container>
  </v-form>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
    desserts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
