<template>
  <!-- v-row: Ürün kartlarını içinde barındıracak olan satır düzenini oluşturur. -->
  <!-- justify="center": Tüm içeriği yatayda ortalar. -->
  <!-- class="space px-16": Yatayda padding (boşluk) ekler. -->
  <v-row justify="center" class="space px-16">
    <!-- v-col: Grid sisteminde bir kolon oluşturur. -->
    <!-- cols="12" xs="12" sm="6" md="4": Farklı ekran boyutlarında kolonun genişliğini belirler. -->
    <!-- v-for: "products" array'i üzerinde döngü yaparak her bir ürün için bir kolon oluşturur. -->
    <v-col
      cols="12"
      xs="12"
      sm="6"
      md="4"
      v-for="(product, i) in products"
      :key="i"
    >
      <!-- v-card: Her bir ürünü temsil eden kart bileşeni. -->
      <!-- class="mx-auto rounded-xl": Kartı yatayda ortalar ve köşelerini yuvarlar. -->
      <!-- max-width="300": Kartın maksimum genişliğini belirler. -->
      <v-card class="mx-auto rounded-xl" max-width="300" color="" flat outlined>
        <!-- Ürünün resmini ortalamak için div kullanılır. -->
        <div align="center" justify="center">
          <!-- v-img: Ürün resmini gösterir. -->
          <!-- :src="product.img": Resim kaynağını dinamik olarak belirler. -->
          <v-img
            max-height="300"
            max-width="300"
            contain
            :src="product.img"
          ></v-img>
        </div>

        <!-- v-card-title: Ürünün başlığını gösterir. -->
        <v-card-title class="">{{ product.title }}</v-card-title>
        <!-- Ürünün alt başlığını ve fiyatını gösterir. -->
        <v-card-title class="grey--text text-grey-darken-1 caption mt-n6">{{
          product.subtitle
        }}</v-card-title>
        <v-card-title class="mt-n4">{{ product.price }}</v-card-title>

        <!-- v-card-actions: Kartın alt kısmında yer alan butonlar ve diğer aksiyonlar. -->
        <v-card-actions class="mx-2 mt-n4">
          <!-- Ürün miktarını azaltmak için buton. -->
          <v-btn outlined class="mt-n2 add">
            <v-icon color="green" @click="decrement"> mdi-minus </v-icon>
          </v-btn>

          <!-- Ürün miktarını gösterir. -->
          <strong class="mx-2" v-text="bpm"></strong>
          
          <!-- Ürün miktarını artırmak için buton. -->
          <v-btn outlined class="mt-n2 add">
            <v-icon color="green" @click="increment"> mdi-plus </v-icon>
          </v-btn>
          
          <!-- Boşluk oluşturur, butonları sağa yaslar. -->
          <v-spacer></v-spacer>
          
          <!-- Ürünü sepete eklemek için buton. -->
          <v-btn class="mx-2 mt-n3" fab dark small color="green">
            <v-icon dark> mdi-shopping </v-icon>
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    // Ürün miktarı (Başlangıç değeri 1)
    bpm: 1,
    // Ürünleri içeren dizi
    products: [
      { img: "pr1.png", title: "Cabbage", subtitle: "1kg", price: "$13" },
      { img: "pr2.png", title: "Perry's Ice Cream", subtitle: "1kg", price: "$23" },
      { img: "pr3.png", title: "Potato", subtitle: "1kg", price: "$17" },
      { img: "pr4.png", title: "Bundle Pack", subtitle: "Potato, Papaya, Oil, Cabbage", price: "$40" },
      { img: "pr5.png", title: "Oreo Biscuit", subtitle: "270GM", price: "$20" },
      { img: "pr6.png", title: "Papaya", subtitle: "1kg", price: "$10" },
    ],
  }),
  methods: {
    // Ürün miktarını azaltır
    decrement () {
      this.bpm--
    },
    // Ürün miktarını artırır
    increment () {
      this.bpm++
    },
  },
};
</script>

<style>
/* Özel stil eklemeleri yapılabilir */
</style>
