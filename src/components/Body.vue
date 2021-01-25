<template>

  <v-card>

      <!-- Tabs naviagtion start -->
        <v-tabs
          color="deep-purple accent-4"
          right
        >

          <v-tab v-for="cl in data"
              :key="cl">{{cl.classe}}</v-tab>   <!-- dATA Is defined in the script -->

          <v-tab-item
            v-for="item in data"
            :key="item"
          >
            <v-container fluid>
              <v-row>

                  <!-- Conditional rendering of th item -->
                <v-col
                  v-for="cars in data"
                  v-bind:key="cars.name"
                  cols="12"
                  md="4"
                >

               <v-card
               v-if="cars.classe == item.classe"
                class="mx-auto"
                max-width="344"
              >
                <v-img
                  :src="cars.img"
                  aspect-ratio="2"
                ></v-img>      <!-- Image of the car -->

                <v-card-title>
                  {{cars.name}}
                </v-card-title>

                <v-card-subtitle>
                  Constructeur : {{ cars.marque }}
                </v-card-subtitle>

                <v-card-actions>
                  <v-btn
                    color="orange lighten-2"
                    text
                    @click.stop="dialog = true, content = cars"
                  >
                    Details
                  </v-btn>

                  <v-spacer></v-spacer>

                 </v-card-actions>


              </v-card>



            </v-col>
          </v-row>
        </v-container>
      </v-tab-item>
    </v-tabs>

  <!-- Tabs naviagtion End -->

<!-- Dialog details Box Start -->

    <v-dialog
      v-model="dialog"
      max-width="auto"

    >
      <v-card>
        <v-card-title class="headline">
          {{content.name}}
        </v-card-title>


      <v-list-item>
      <v-list-item-content>
        <v-list-item-title>Description</v-list-item-title>
        <v-card-text>
          {{content.description}}
        </v-card-text>
      </v-list-item-content>
    </v-list-item>

      <v-list-item>
      <v-list-item-content>
        <v-list-item-title>Production </v-list-item-title>
        <v-card-text>
          {{content.production}}
        </v-card-text>
      </v-list-item-content>
    </v-list-item>

      <v-list-item>
      <v-list-item-content>
        <v-list-item-title>Cylindree</v-list-item-title>
        <v-card-text>
          {{content.cylindree}}
        </v-card-text>
      </v-list-item-content>
    </v-list-item>

    <v-list-item>
      <v-list-item-content>
        <v-list-item-title>Energie</v-list-item-title>
        <v-card-text>
          {{content.energie}}
        </v-card-text>
      </v-list-item-content>
    </v-list-item>

     <v-list-item>
      <v-list-item-content>
        <v-list-item-title>Transmission</v-list-item-title>
        <v-card-text>
          {{content.transmission}}
        </v-card-text>
      </v-list-item-content>
    </v-list-item>

     <v-list-item>
      <v-list-item-content>
        <v-list-item-title>Acceleration</v-list-item-title>
        <v-card-text>
          {{content.acceleration}}
        </v-card-text>
      </v-list-item-content>
    </v-list-item>
        <v-card-actions>
          <v-spacer></v-spacer>

          <v-btn
            color="green darken-1"
            text
            @click="dialog = false"
          >
            Fermer
          </v-btn>

        </v-card-actions>
      </v-card>
    </v-dialog>

      <!-- End Dialog Box -->

  </v-card>
</template>

<script>
import axios from 'axios'
import data from '../carsData.json'
  export default {
    name: 'pageBody',

    data(){
      return{
        data :data,
        show :false,
        dialog:false,
        content:'',
        }
  },

    methods : {
      // SAME ORING PROBLEM DOESNT PERMIT TO FETCH DATA so i use json instead
     /*  getCars(){
        axios.get('https://jsonkeeper.com/b/0K8O')
        .then(response => {
          console.log(response.data);
        })
      } */
    },


    created(){

    }
  }
</script>
