<template>
  <div class="text-center">
    <v-dialog v-model="dialog" persistent width="800">
      <v-card>
        <v-card-title class="headline grey lighten-2" style="color: #656565">
          Criar Dimensão
        </v-card-title>

        <v-container>
          <v-text-field
            label="Nome"
            hide-details="auto"
            v-model="dimension"
          ></v-text-field>
          <v-divider class="pb-2"></v-divider>
          <v-row>
            <v-col
              md="2"
              sm="4"
              xs="12"
              class="d-flex justify-center align-center"
            >
            </v-col>
          </v-row>
        </v-container>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="error" text @click="$emit('cancel-create')"
            >Cancelar</v-btn
          >
          <v-btn color="primary" text @click="createADimension"
            >Confirmar</v-btn
          >
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name: "CreateDimension",
  props: {
    dialog: Boolean,
    dimensions: Array,
  },
  data: () => ({
    dimension: "",
  }),
  created() {},
  methods: {
    createADimension() {
      this.$emit("create-dimension", this.dimension);
      this.dimension = "";
    },
  },
};
</script>