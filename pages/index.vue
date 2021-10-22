<template>
  <div class="container">
    <client-only placeholder="loading...">
      <newsTickr/>
    </client-only>
    <CBox id="hero"  d="flex" >
      <CBox d="flex" h="30rem" w="100%" id="hero" alt=""/>
        <CBox d="flex" flex-direction="column" position="absolute" h="30rem" w="100%" id="heading-container" alignItems="center" justifyContent="center" bg="#00000070" alt="">
          <CHeading color="white">This open source season we are presenting the homepage of our super awesome app</CHeading>

          <CBox>
            <CBox as="img" :src="require('@/assets/imgs/dowb.png')" mt="2rem"/>
          </CBox>
        </CBox>
    </CBox>

    <authoritiesLogin/>


  </div>
</template>


<script lang="js">
import {
  CBox,
  // CButton,
  // CAvatarGroup,
  // CAvatar,
  // CAvatarBadge,
  // CModal,
  // CModalContent,
  // CModalOverlay,
  // CModalHeader,
  // CModalFooter,
  // CModalBody,
  // CModalCloseButton,
  // CIconButton,
  // CFlex,
  CHeading
} from '@chakra-ui/vue'

import newsTickr from '../myComponents/newsTickr'

import authoritiesLogin from '../myComponents/authoritiesLogin'



export default {
  name: 'App',
  components: {
    // CBox,
    // CButton,
    // CAvatarGroup,
    // CAvatar,
    // CAvatarBadge,
    // CModal,
    // CModalContent,
    // CModalOverlay,
    // CModalHeader,
    // CModalFooter,
    // CModalBody,
    // CModalCloseButton,
    // CIconButton,
    // CFlex,
    // CHeading,
    newsTickr,
    authoritiesLogin

  },
  inject: ['$chakraColorMode', '$toggleColorMode'],
  data () {
    return {
      showModal: false,
      mainStyles: {
        dark: {
          bg: 'gray.700',
          color: 'whiteAlpha.900'
        },
        light: {
          bg: 'white',
          color: 'gray.900'
        }
      }
    }
  },
  computed: {
    colorMode () {
      return this.$chakraColorMode()
    },
    theme () {
      return this.$chakraTheme()
    },
    toggleColorMode () {
      return this.$toggleColorMode
    }
  },
  methods: {
    showToast () {
      this.$toast({
        title: 'Account created.',
        description: "We've created your account for you.",
        status: 'success',
        duration: 10000,
        isClosable: true
      })
    }
  }
}
</script>

<style scoped>
#hero{
  background-image: url("../assets/imgs/hero.jpg"), linear-gradient(#eb01a5, #d13531);
  background-size: cover;
}
</style>
