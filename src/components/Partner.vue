<template>
  <!-- v-row: İçinde kolonları düzenlemek için bir satır oluşturur. px-16 ile yatayda padding eklenir, mt-10 ile üstten margin eklenir. -->
  <v-row class="px-16 mt-10">
    <!-- v-col: Grid sisteminde bir kolon oluşturur. cols="3" ile her kolon ekranın 1/4'ünü kaplar. -->
    <!-- v-for: "partners" array'i üzerinde döngü yaparak her bir partner için bir kolon oluşturur. -->
    <v-col cols="3" v-for="(partner, i) in partners" :key="i">
      <!-- İçeriği ortalamak için div kullanılır. -->
      <div align="center" justify="center">
        <!-- v-img: Görüntü bileşeni, "partner.img" değeri ile dinamik olarak kaynak belirlenir. -->
        <v-img
          :src="partner.img"
          max-height="80"
          max-width="80"
          contain
        ></v-img>
      </div>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    // Partnerlerin görüntü bilgilerini içeren dizi
    partners: [
      { img: "airbnb.png" },
      { img: "adidas.png" },
      { img: "swords.png" },
      { img: "castle.png" },
    ],
  }),
};
</script>

<style>
/* Özel stil eklemeleri burada yapılabilir */
</style>
