<template>
  <!-- v-footer: Uygulamanın alt bilgi (footer) alanını tanımlar. -->
  <v-footer dark padless>
    <!-- v-card: Footer içinde düz (flat) ve döşeme (tile) tarzında kart oluşturur, arka planı siyah ve metin rengi beyazdır. -->
    <v-card flat tile class="black white--text py-12 px-5" width="100%">
      <v-row>
        <!-- v-col: Kolon yapısı, her bir footer bölümü için yer ayırır -->
        <v-col cols="12" xs="12" sm="6" md="4" class="pa-16">
          <!-- v-toolbar: Üst kısımda logo ve başlığı içeren bir araç çubuğu oluşturur. -->
          <v-toolbar color="transparent" flat>
            <!-- v-badge: Logo için noktalı rozet (badge) ekler-->
            <v-badge color="#D5F0DB" dot>
              <!-- v-img: Logo görüntüsünü içerir. -->
              <v-img src="1.png" contain width="30"></v-img>
            </v-badge>

            <!-- v-toolbar-title: Araç çubuğunun başlığını tanımlar. -->
            <v-toolbar-title class="ml-4">
              <span class="green--text">e</span><strong>Grocery</strong> <!-- Uygulama adı. -->
            </v-toolbar-title>
          </v-toolbar>

          <!-- v-card-text: Sosyal medya ikonlarını içeren butonlar için alan oluşturur. -->
          <v-card-text class="pt-0">
            <!-- v-btn: Sosyal medya ikonları için döngü ile butonlar oluşturur. -->
            <v-btn
              v-for="icon in icons"
              :key="icon"
              icon
              fab
              outlined
              small
            >
              <!-- v-icon: İkonları içerir ve her biri dinamik olarak icons dizisinden alınır. -->
              <v-icon size="20px">
                {{ icon }}
              </v-icon>
            </v-btn>
          </v-card-text>
        </v-col>

        <!-- "About" bölümü, footer'ın bilgi kısmını içerir. -->
        <v-col cols="12" xs="12" sm="6" md="2">
          <v-card-text class="white--text pt-0">
            <h3>About</h3>
          </v-card-text>
          <v-card-text class="grey--text"> How it Work</v-card-text>
          <v-card-text class="grey--text mt-n4"> Our Programs </v-card-text>
          <v-card-text class="grey--text mt-n4"> Promotions </v-card-text>
          <v-card-text class="grey--text mt-n4"> Refer A Friend </v-card-text>
        </v-col>

        <!-- "Delivery" bölümü, teslimat ile ilgili bilgileri içerir. -->
        <v-col cols="12" xs="12" sm="6" md="2">
          <v-card-text class="white--text pt-0">
            <h3>Delivery</h3>
          </v-card-text>
          <v-card-text class="grey--text"> Cost on Delivery </v-card-text>
          <v-card-text class="grey--text mt-n4"> Payment Method </v-card-text>
          <v-card-text class="grey--text mt-n4"> Delivery Status </v-card-text>
          <v-card-text class="grey--text mt-n4"> Returns </v-card-text>
        </v-col>

        <!-- "Contact" bölümü, iletişim bilgilerini içerir. -->
        <v-col cols="12" xs="12" sm="6" md="4">
          <v-card-text class="white--text pt-0">
            <h3>Contact</h3>
          </v-card-text>
          <v-card-text class="grey--text"> AAE IdeaPro </v-card-text>
          <v-card-text class="grey--text mt-n4">
            216 / C EAST Road
          </v-card-text>
          <v-card-text class="grey--text mt-n4"> aae.idapro.com </v-card-text>
          <v-card-text class="grey--text mt-n4"> -B8254552214 </v-card-text>
        </v-col>
      </v-row>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    icons: [
      "fab fa-apple",          // Apple ikonu.
      "fab fa-google-plus-g",  // Google Plus ikonu.
      "fab fa-twitter",        // Twitter ikonu.
      "fab fa-facebook-f",     // Facebook ikonu.
    ],
  }),
};
</script>

<style>
</style>
