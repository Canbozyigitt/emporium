<template>
  <!-- v-item-group: Bir grup öğeyi barındırır, mandatory olduğu için en az bir öğe seçilmelidir -->
  <v-item-group mandatory class="mt-n1">
    <!-- v-container: İçerikleri düzgün bir şekilde hizalamak için kullanılır -->
    <v-container>
      <!-- v-row: Satır yapısı oluşturur, içerikleri hizalamak için justify="center" kullanılır. -->
      <v-row justify="center" class="space">
        <!-- v-col: Kolon yapısı, her öğe için yer ayırır. -->
        <v-col
          cols="12"
          xs="12"
          sm="4"
          md="2"
          v-for="(category, i) in categories"
          :key="i" 
        ><!-- Her bir öğe için benzersiz bir anahtar oluşturur. -->
          <!-- v-item: İçeriği tıklanabilir öğe yapar, slot ile aktif durumu ve toggle fonksiyonu sağlanır. -->
          <v-item v-slot="{ active, toggle }">
            <!-- v-card: Her bir öğenin kart görünümünde olmasını sağlar. -->
            <v-card
              :color="active ? '#D5F0DB' : 'white'"
              <!-- Kartın arka plan rengini aktifliğe göre değiştirir. -->
              :class="active ? 'borderme' : 'borderout'" <!-- Kartın kenarlık stilini aktifliğe göre değiştirir. -->
              class="d-flex align-center rounded-lg mx-2" <!-- Kartın genel stil ayarları. -->
              dark <!-- Kartın koyu tema olmasını sağlar. -->
              height="180" <!-- Kartın yüksekliğini belirler. -->
              @click="toggle" <!-- Kart tıklandığında öğeyi aktif/pasif yapar. -->
              flat <!-- Kartın gölgesiz olmasını sağlar. -->
            >
              <!-- İçerikleri düzenli hale getirmek için v-row kullanılır. -->
              <v-row>
                <v-col cols="12" sm="12">
                  <!-- v-list-item: Kartın içeriğini düzenler, üç satırlık metni hizalar. -->
                  <v-list-item three-line class="text-center">
                    <v-list-item-content>
                      <div class="d-flex justify-center align-center">
                        <!-- v-img: Kategorilerin resimlerini gösterir, src ile dinamik olarak yükler. -->
                        <v-img
                          :src="`/${category.img}`" <!-- Resim yolu dinamik olarak ayarlanır. -->
                          max-height="80" <!-- Resmin maksimum yüksekliği. -->
                          max-width="80" <!-- Resmin maksimum genişliği. -->
                          contain <!-- Resmin içeriği kutu içine sığdırılır. -->
                        ></v-img>
                      </div>
                      <!-- v-list-item-subtitle: Kart başlığının altındaki metni gösterir. -->
                      <v-list-item-subtitle
                        :class="active ? 'green--text' : 'black--text'" <!-- Metin rengini aktifliğe göre değiştirir. -->
                        class="caption mt-4"
                      >
                        {{ category.title }} <!-- Kategori başlığını dinamik olarak gösterir. -->
                      </v-list-item-subtitle>
                    </v-list-item-content>
                  </v-list-item>
                </v-col>
              </v-row>
            </v-card>
          </v-item>
        </v-col>
      </v-row>
    </v-container>
  </v-item-group>
</template>

<script>
export default {
  data: () => ({
    // categories: Farklı kategorileri içeren bir dizi, her birinin resim yolu ve başlığı var.
    categories: [
      { img: "01.png", title: "Meat & Fish" },
      { img: "02.png", title: "Vegetables" },
      { img: "3.png", title: "Medicine" },
      { img: "4.png", title: "Baby" },
      { img: "5.png", title: "Office" },
      { img: "6.png", title: "Beauty" },
    ],
  }),
};
</script>

<style>
/* İsteğe bağlı olarak stil ekleyebilirsiniz */
</style>
