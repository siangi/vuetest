<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <!-- <Location :name="Dahoam" :adress="" :description="woas am scheensten is"/> -->
    
    <ul id="joke">
        <li v-for="l in locations" :key="l.name">
          <Location :name="l.fields.name" :adress="l.fields.location.lat" :description="l.fields.location.lon"/>
        </li>
    </ul>
    <Funbutton></Funbutton>
  </div>
</template>

<script>
// @ is an alias to /src
import Location from '@/components/location.vue';
import Funbutton from '@/components/funbutton.vue';
import {createClient} from 'contentful';


export default {
  name: 'Home',
  components: {
    Location,
    Funbutton
  },

  data: function() {
    return{
      locations: []      
    }
  },

  created: function(){
    let client = createClient({
            space: '3wz3xq1zmb7m',
            accessToken: 'Gd5hdBdjGmq0duHIYa_sDvYo_vzb6OMGK2XPhuwGAtU',
        });

    client.getEntries({
      content_type: 'location'
    }).then(entries => {
          this.locations = entries.items;
          console.log(entries);
      })
  }
}
</script>
