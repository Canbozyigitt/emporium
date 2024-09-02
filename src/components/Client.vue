<template>
  <!-- v-row: Her bir satır için yer ayırır, mt-10 ve mb-5 sınıflarıyla üst ve alt boşluklar eklenir. -->
  <v-row class="mt-10 mb-5">
    <!-- v-col: Kolon yapısı, her bir client için yer ayırır. -->
    <v-col
      cols="12"
      xs="12"
      sm="6"
      md="4"
      
      v-for="(client, i) in clients"
      :key="i" 
    > <!-- clients dizisindeki her bir öğe için bir kolon oluşturur.-->
      <!-- v-card: Her bir client için kart yapısı oluşturur. -->
      <v-card class="elevation-16 mx-auto" width="300"> <!-- Kartın genişliğini ve gölge seviyesini ayarlar. -->
        <!-- v-list: Kartın içeriğini düzenler, subheader ve iki satırlı metin içerir. -->
        <v-list subheader two-line>
          <!-- v-list-item: Her bir list itemini düzenler. -->
          <v-list-item>
            <!-- v-list-item-avatar: Avatar alanı oluşturur, client.img'den alınan resim burada gösterilir. -->
            <v-list-item-avatar>
              <v-img :src="client.img"></v-img> <!-- Client'in resmini gösterir. -->
            </v-list-item-avatar>

            <!-- v-list-item-content: Başlık ve alt başlık içeriğini düzenler. -->
            <v-list-item-content>
              <!-- v-list-item-title: Client'in başlığını gösterir. -->
              <v-list-item-title>{{ client.title }}</v-list-item-title>

              <!-- v-list-item-subtitle: Client'in alt başlığını gösterir. -->
              <v-list-item-subtitle>{{ client.subtitle }}</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-list>
        
        <!-- v-card-text: Kartın ana metin içeriğini barındırır. -->
        <v-card-text>
          <!-- mt-n7: Yukarıya doğru margin ekleyerek öğeleri birbirine yaklaştırır. -->
          <div class="mt-n7">
            <!-- v-rating: Puanlama sistemini gösterir, rating değeri modelden alınır. -->
            <v-rating
              v-model="rating" <!-- Puan değeri dinamik olarak modele bağlanır. -->
              color="yellow darken-3" <!-- Aktif yıldızların rengi. -->
              background-color="grey darken-1" <!-- Boş yıldızların rengi. -->
              empty-icon="$ratingFull" <!-- Boş yıldız simgesi (dolgun görünümde). -->
              half-increments <!-- Yarı puan artırımı sağlar. -->
              hover <!-- Üzerine gelindiğinde yıldızlar değişir. -->
              small <!-- Küçük boyutlu yıldızlar. -->
            ></v-rating>
          </div>
          <!-- client.bio: Client'in biyografi metnini gösterir. -->
          {{ client.bio }}
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    rating: 4.5, // Tüm client'ler için varsayılan puan değeri.

    clients: [
      {
        img: "https://cdn.vuetifyjs.com/images/lists/1.jpg", // Client'in avatar resmi.
        title: "Kareem Benji", // Client'in adı.
        subtitle: "CPO on Maqua", // Client'in pozisyonu.
        bio: "If you enjoy using Vuetify, please take a few seconds to rate your experience with the framework. It really helps!", // Client'in biyografisi.
      },
      {
        img: "https://cdn.vuetifyjs.com/images/lists/2.jpg",
        title: "AAE IdeaPro",
        subtitle: "CPO on Maqua",
        bio: "If you enjoy using Vuetify, please take a few seconds to rate your experience with the framework. It really helps!",
      },
      {
        img: "https://cdn.vuetifyjs.com/images/lists/3.jpg",
        title: "Raul Seem ",
        subtitle: "CPO on Maqua",
        bio: "If you enjoy using Vuetify, please take a few seconds to rate your experience with the framework. It really helps!",
      },
    ],
  }),
};
</script>

<style>
/* İsteğe bağlı olarak stil ekleyebilirsiniz */
</style>
