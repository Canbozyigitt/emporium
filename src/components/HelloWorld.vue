<template>
  <!-- v-container: İçerik için bir kapsayıcı oluşturur. -->
  <v-container>
    <!-- v-row: Satır yapısı, elemanların düzenli yerleştirilmesini sağlar. -->
    <v-row class="text-center">
      <!-- v-col: Sütun yapısı, içerik için yer ayırır. -->
      <v-col cols="12">
        <!-- v-img: Bir görüntü öğesi oluşturur. -->
        <v-img
          :src="require('../assets/logo.svg')" 
          class="my-3" 
          contain
          height="200" 
        />
      </v-col>

      <v-col class="mb-4">
        <!-- h1: Başlık elemanı, büyük ve kalın font ile metni gösterir. -->
        <h1 class="display-2 font-weight-bold mb-3">
          Welcome to Vuetify <!-- Ana başlık -->
        </h1>

        <!-- p: Paragraf elemanı, açıklama metnini içerir. -->
        <p class="subheading font-weight-regular">
          For help and collaboration with other Vuetify developers,
          <br>please join our online
          <a
            href="https://community.vuetifyjs.com" 
            target="_blank"
          >Discord Community</a> <!-- Kullanıcıları Discord topluluğuna yönlendirir. -->
        </p>
      </v-col>

      <!-- "What's next?" bölümü, kullanıcıya sonraki adımlar hakkında bilgi verir. -->
      <v-col class="mb-5" cols="12">
        <h2 class="headline font-weight-bold mb-3">
          What's next?
        </h2>

        <!-- v-row: Bağlantıların ortalanmasını sağlar. -->
        <v-row justify="center">
          <!-- v-for: Sonraki adımların bağlantılarını döngüyle oluşturur. -->
          <a
            v-for="(next, i) in whatsNext"
            :key="i"
            :href="next.href" 
            class="subheading mx-3" 
            target="_blank"
          >
            {{ next.text }} <!-- Bağlantı metni. -->
          </a>
        </v-row>
      </v-col>

      <!-- "Important Links" bölümü, kullanıcıya önemli bağlantıları gösterir. -->
      <v-col class="mb-5" cols="12">
        <h2 class="headline font-weight-bold mb-3">
          Important Links
        </h2>

        <!-- v-row: Bağlantıların ortalanmasını sağlar. -->
        <v-row justify="center">
          <!-- v-for: Önemli bağlantıları döngüyle oluşturur. -->
          <a
            v-for="(link, i) in importantLinks"
            :key="i"
            :href="link.href" 
            class="subheading mx-3" 
            target="_blank"
          >
            {{ link.text }} <!-- Bağlantı metni. -->
          </a>
        </v-row>
      </v-col>

      <!-- "Ecosystem" bölümü, ekosistem ile ilgili kaynakları gösterir. -->
      <v-col class="mb-5" cols="12">
        <h2 class="headline font-weight-bold mb-3">
          Ecosystem
        </h2>

        <!-- v-row: Bağlantıların ortalanmasını sağlar. -->
        <v-row justify="center">
          <!-- v-for: Ekosistem bağlantılarını döngüyle oluşturur. -->
          <a
            v-for="(eco, i) in ecosystem"
            :key="i"
            :href="eco.href" 
            class="subheading mx-3" 
            
            target="_blank"
          >
            {{ eco.text }} <!-- Bağlantı metni. -->
          </a>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'HelloWorld', // Bileşenin adı.

    data: () => ({
      // Ekosistem ile ilgili bağlantıları tutar.
      ecosystem: [
        {
          text: 'vuetify-loader', // Bağlantı metni.
          href: 'https://github.com/vuetifyjs/vuetify-loader', // Bağlantı URL'si.
        },
        {
          text: 'github',
          href: 'https://github.com/vuetifyjs/vuetify',
        },
        {
          text: 'awesome-vuetify',
          href: 'https://github.com/vuetifyjs/awesome-vuetify',
        },
      ],
      // Önemli bağlantıları tutar.
      importantLinks: [
        {
          text: 'Documentation',
          href: 'https://vuetifyjs.com',
        },
        {
          text: 'Chat',
          href: 'https://community.vuetifyjs.com',
        },
        {
          text: 'Made with Vuetify',
          href: 'https://madewithvuejs.com/vuetify',
        },
        {
          text: 'Twitter',
          href: 'https://twitter.com/vuetifyjs',
        },
        {
          text: 'Articles',
          href: 'https://medium.com/vuetify',
        },
      ],
      // Sonraki adımlar için bağlantıları tutar.
      whatsNext: [
        {
          text: 'Explore components',
          href: 'https://vuetifyjs.com/components/api-explorer',
        },
        {
          text: 'Select a layout',
          href: 'https://vuetifyjs.com/getting-started/pre-made-layouts',
        },
        {
          text: 'Frequently Asked Questions',
          href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions',
        },
      ],
    }),
  }
</script>
