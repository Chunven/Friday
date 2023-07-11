<template>
  <div>
    <v-hover v-slot:default="{ hover }" open-delay="50">
      <v-card
        :elevation="hover ? 12 : 0"
        outlined
        class="product-border  secondary"
      >
        <v-img
          class="primary--text align-end"
          max-width="250"
          :src="require('~/assets/img/pic1.jpg')"
        >
          <!-- <v-card-title class="font-weight-meduim primary--text"
            >ກະເປົາເດີນທາງ</v-card-title
          > -->
        </v-img>

        <v-card-text class="text-start">
          <div class="font-weight-meduim primary--text">
            ສິນຄ້າ: ກະເປົາເດີນທາງ COME ແດງ
          </div>
          <div class="font-weight-meduim primary--text">ລາຄາ: 189000 LAK</div>
        </v-card-text>
      </v-card>
    </v-hover>
  </div>
</template>

<script>
export default {
  name: 'product-card',
}
</script>

<style></style>
