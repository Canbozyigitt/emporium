<template>
  <!-- v-app-bar: Uygulama çubuğu, genellikle üst menü çubuğu için kullanılır. -->
  <v-app-bar app color="white" flat>
    <!-- v-badge: Belirli bir öğenin yanında küçük bir işaret veya sayı göstermek için kullanılır. -->
    <v-badge color="#D5F0DB" dot>
      <!-- v-img: Görüntü öğesi, genellikle logolar veya simgeler için kullanılır. -->
      <v-img src="1.png" contain width="30"></v-img>
    </v-badge>

    <!-- v-toolbar-title: Çubuğun başlığı, genellikle markanın adı veya logosu için kullanılır. -->
    <v-toolbar-title class="ml-4">
      <span class="green--text">e</span><strong>Grocery</strong>
    </v-toolbar-title>

    <!-- v-spacer: İki öğe arasında boşluk bırakmak için kullanılır. -->
    <v-spacer></v-spacer>

    <!-- Kalp simgesinin bulunduğu rozet, bildirim sayısı ile birlikte. -->
    <v-badge color="#FF6D59" overlap content="2" class="mr-2 mt-1">
      <!-- v-avatar: Küçük dairesel profil veya simge resimleri için kullanılır. -->
      <v-avatar color="#FFF0EE" size="40">
        <!-- v-icon: İkon öğesi, genellikle küçük simgeler için kullanılır. -->
        <v-icon x-small color="#FF6D59">far fa-heart</v-icon>
      </v-avatar>
    </v-badge>

    <!-- Alışveriş sepeti simgesinin bulunduğu rozet, bildirim sayısı ile birlikte. -->
    <v-badge color="#41AB55" overlap content="3" class="mr-2 mt-1">
      <v-avatar color="#ECF7EE" size="40">
        <v-icon x-small color="#41AB55">fas fa-shopping-cart</v-icon>
      </v-avatar>
    </v-badge>

    <!-- Kullanıcı selamlaması ve adı, sadece belirli ekran boyutlarında gösterilir. -->
    <span class="grey--text d-none d-sm-flex">
      Hello, <strong>Jonny</strong>
    </span>

    <!-- Kullanıcı profil resmi, küçük bir dairesel görüntü olarak gösterilir. -->
    <v-avatar size="30" class="ml-2">
      <v-img src="https://cdn.vuetifyjs.com/images/lists/2.jpg"></v-img>
    </v-avatar>

    <!-- Aşağı açılır simge için buton. -->
    <v-btn icon dark>
      <v-icon x-small color="#878A94">fas fa-chevron-down</v-icon>
    </v-btn>
  </v-app-bar>
</template>

<script>
export default {};
</script>

<style>
/* Toolbar başlıklarının yazı boyutunu ayarlar. */
.v-toolbar__title {
  font-size: 1rem !important;
}
</style>
