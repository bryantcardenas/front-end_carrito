<template>
  <v-container-fluid>
    <v-footer dark padless>
      <v-card class="flex" flat tile>
        <v-card-title class="red accent-4">
          <strong class="subheading  mx-6">VIRTUAL  GYM   SHOP</strong>
          <v-spacer></v-spacer>
            <v-text-field  right label="BUSCAR" solo dende   >
             
      </v-text-field>
          <v-spacer></v-spacer>
          <v-spacer></v-spacer>
         
          <v-btn v-for="icon in icons" :key="icon" class="mx-6" dark icon>
            <v-icon size="30px">
              {{ icon }}
            </v-icon>
          </v-btn>
        
        </v-card-title>
      </v-card>
      
    </v-footer>
      <v-carousel>
                  <v-carousel-item v-for="(item, i) in items" :key="i" :src="item.src"
                    reverse-transition="fade-transition" transition="fade-transition"></v-carousel-item>
                </v-carousel>
    <v-row class="foto">
      <br>
      <v-col cols="2"></v-col><br>
      <br>
      <br>
      <br>
      <v-col cols="6">
      <br>
    
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="3" v-for="(p, i) in productos" :key="i">
        <template>

          <v-card :loading="loading" class="mx-auto my-12" max-width="374">
            <template slot="progress">
              <v-progress-linear color="deep-purple" height="10" indeterminate></v-progress-linear>
            </template>

            <v-img height="250" :src="p.imagen"></v-img>

            <v-card-title>{{ p.nombre }}</v-card-title>

            <v-card-text>
              <v-row align="center" class="mx-0">
               



                <div class="grey--text ms-4">
                  4.5 (413)
                </div>
              </v-row>

              <div class="my-4 text-subtitle-1">
                $ {{ p.precio }}
              </div>

              <div>{{ p.descripcion }}
              </div>
            </v-card-text>

            <v-divider class="mx-4"></v-divider>

            <v-card-title>Kit Pesas Mancuernas 20 Kg 40 Lb Gimnasio Portatil + Estuche</v-card-title>

            <v-card-text>
              <v-chip-group v-model="selection" active-class="deep-purple accent-4 white--text" column>

                <v-chip>5:30PM</v-chip>

                <v-chip>7:30PM</v-chip>

                <v-chip>8:00PM</v-chip>

                <v-chip>9:00PM</v-chip>
              </v-chip-group>
            </v-card-text>

            <v-card-actions>
              <v-btn color="light-blue grey darken-3" text @click="add(p)">AGREGAR AL CARRITO</v-btn>
              

            </v-card-actions>
          </v-card>

        </template>
      </v-col>


    </v-row>


  </v-container-fluid>
</template>
<script>
export default {
  data: () => ({
    icons: [
      "mdi-cart",
      "mdi-facebook",
      "mdi-twitter",
      "mdi-whatsapp",
      "mdi-instagram",
     
    ],
    items: [
      {
        src: 'https://img.freepik.com/foto-gratis/persona-gimnasio-deportivo-usando-pesas-rusas_23-2149255814.jpg?w=2000',
      },
      {
        src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
      },
      {
        src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
      },
      {
        src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
      },
    ],

    productos: [
      { nombre: "Mancuernas", precio: 100000, descripcion: "Llantas para tractomula", imagen: "https://www.sincable.mx/wp-content/uploads/2021/05/v36-qaC-Mancuernas-10-Kg-0-120776489_m.jpg" },
      { nombre: "Multifuncional", precio: 100000, descripcion: "Llantas para tractomula", imagen: "https://fitnesstotal.com.co/wp-content/uploads/2021/07/MS-651S.jpg" },
      { nombre: "Spining", precio: 100000, descripcion: "Llantas para tractomula", imagen: "https://ventaspop-images.staticgnt.com/HGRZXkht1xLIvYvDe4-52fxUhdM=/filters:strip_exif():quality(70)/files/products/252/1578/S10.JPG" },
      { nombre: "Banda Trotadora", precio: 100000, descripcion: "Llantas para tractomula", imagen: "https://www.gymhome.com.co/wp-content/uploads/2022/01/GH-T001-BANDA-CAMIN_4-600x709.jpg" },
      { nombre: "Saco de Boxeo", precio: 100000, descripcion: "Llantas para tractomula", imagen: "https://www.superprof.mx/blog/wp-content/uploads/2018/01/clases-de-boxeo-para-principiantes.jpg" },
      { nombre: "Tennis", precio: 100000, descripcion: "Llantas para tractomula", imagen: "https://underarmour.scene7.com/is/image/Underarmour/SS20_LATAM_FTW_TRAIN_DIG?scl=1" },
      { nombre: "Bancos Multifuncion", precio: 100000, descripcion: "Llantas para tractomula", imagen: "https://s3.amazonaws.com/imagenes-sellers-mercado-ripley/2021/08/31162225/PRESSRACKROJO_0.jpg" },
      { nombre: "Suplementos", precio: 100000, descripcion: "Llantas para tractomula", imagen: "https://www.vanguardia.com/binrepository/1200x600/0c0/0d0/none/12204/XDFL/gym-supplements-background-bodybuilding-pre-workout-whey-protein-powder-pre-workout_5330387_20210206113139.jpg" },
    ]
  }),
  methods: {
    add(ad) {
      console.log(ad);
    }
  }
};
</script>
<style>
.foto {
  height: 600px;
  width: 100dw;
  background-image: url("https://bodytech.com.co/uploads/post/1f35241ad69c489faaddd218c50ef3e2/entrenar-seguro-1_1920x854.jpg");
}
</style>