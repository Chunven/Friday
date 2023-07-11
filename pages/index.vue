<template>
  <div class="pa-6">
    <v-card class="pa-4">
      <v-row>
        <v-col :cols="12">
          <div class="row">
            <div
              v-for="(item, index) in 20"
              :key="index"
              class="col-12 col-md-3 col-sm-6 col-xs-6 text-center"
            >
              <product-card></product-card>
            </div>
          </div>
        </v-col>
      </v-row>
    </v-card>
  </div>
</template>

<script>
export default {}
</script>

<style>
.v-card--reveal {
  align-items: center;
  bottom: 0;
  justify-content: center;
  opacity: 0.5;
  position: absolute;
  width: 100%;
}
.product-border {
  border: 1px solid #01532b !important;
}
</style>
