<template>
  <div class="root">
    <v-container class="fixed-width">
      <v-row class="spacing6">
        
        <v-col cols="12" lg="5" md="6" class="pa-6">
           <!--$t('agencyLanding.office_title')-->
          <div class="block">
            <u-animate-container>
              <u-animate
                :offset="-50"
                name="fadeInLeftShort"
                delay="0.3s"
                duration="0.3s"
              >
                <v-card class="paper">
                  <h6 class="title">
                  <!--  {{ $t('agencyLanding.office_head') }} -->
                  </h6>
                  <v-row>
                    <v-col cols="12" sm="6">
                      <v-icon class="icon">mdi-phone</v-icon>
                      <span>+123 456 78 91</span>
                    </v-col>
                    <v-col cols="12" sm="6">
                      <v-icon class="icon">mdi-email</v-icon>
                      <span>hello@luxi.com</span>
                    </v-col>
                    <v-col cols="12" sm="12">
                      <v-icon class="icon">mdi-map-marker</v-icon>
                      Lorem ipsum street no.14 Block A
                    </v-col>
                  </v-row>
                </v-card>
              </u-animate>
              <u-animate
                :offset="-50"
                name="fadeInLeftShort"
                delay="0.5s"
                duration="0.3s"
              >
                <v-card class="paper">
                  <h6 class="title">
                  <!--  {{ $t('agencyLanding.office_branch') }} -->
                  </h6>
                  <v-row>
                    <v-col cols="12" sm="6">
                      <v-icon class="icon">mdi-phone</v-icon>
                      <span>+98 765 432 10</span>
                    </v-col>
                    <v-col cols="12" sm="6">
                      <v-icon class="icon">mdi-email</v-icon>
                      <span>hello@luxi.com</span>
                    </v-col>
                    <v-col cols="12" sm="12">
                      <v-icon class="icon">mdi-map-marker</v-icon>
                      Lorem ipsum street Block C - Vestibullum Building
                    </v-col>
                  </v-row>
                </v-card>
              </u-animate>
            </u-animate-container>
          </div>
        </v-col>
        <v-col cols="12" md="6" class="pa-6">
          <v-card class="map">
            <GMap
              ref="gMap"
              :cluster="{options: {styles: clusterStyle}}"
              :center="{lat: locations[0].lat, lng: locations[0].lng}"
              :options="{fullscreenControl: false}"
              :zoom="6"
            >
              <GMapMarker
                v-for="location in locations"
                :key="location.id"
                :position="{lat: location.lat, lng: location.lng}"
              />
            </GMap>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<style lang="scss" scoped>
@import './map-address-style.scss';
</style>

<script>


export default {
  components: {
    
  },
  data() {
    return {
      currentLocation: {},
      locations: [
        {
          lat: 44.933076,
          lng: 15.629058
        }
      ],
      clusterStyle: [
        {
          url:
            'https://maps.gstatic.com/mapfiles/api-3/images/spotlight-poi2.png',
          width: 56,
          height: 56,
          textColor: '#fff'
        }
      ]
    }
  },

}
</script>
