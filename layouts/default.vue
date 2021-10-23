<template>
  <div class="container">
    <CThemeProvider>
      <CColorModeProvider>
        <CBox font-family="body" as="main">
          <CReset />
            <siteHeader/>
            <nuxt />
            <siteFooter/>
        </CBox>
      </CColorModeProvider>
    </CThemeProvider>
  </div>
</template>
<script>
import {
  CThemeProvider,
  CColorModeProvider,
  CReset,
  CBox
} from '@chakra-ui/vue'

import siteHeader from '../components/siteHeader.vue'
import siteFooter from '../components/siteFooter.vue'


export default {
  name: 'App',
  components: {
    CThemeProvider,
    CColorModeProvider,
    CReset,
    CBox,
    siteHeader,
    siteFooter,
  },



  head(){

    return{
      title:"HIT COVID | Monitor Health Safely At Home",
      meta:[
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        { 
          hid:'description',
          name:'description',
          content:"BIT Connect  app is developed by The Percept, Open Source Enthusiast, to help people connect and gain info of their dramatic sides by performing on live feeds and showcasing thier true but hidden sides which they don't usually do.BIT Connect  © 2021, A Product for the Globe and Billions of people in our world"
        },
      ],

    link: [
      { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' },
      {rel: 'preconnect',href: 'https://fonts.googleapis.com'},  
      {rel: 'preconnect',href: 'https://fonts.gstatic.com', crossorigin:""},  
      {rel: 'stylesheet',href: 'https://fonts.googleapis.com/css2?family=Squada+One&display=swap'},  

    ],
    }
  },






}
</script>
