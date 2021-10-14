<template>
  <div class="container">
    <client-only placeholder="loading...">
      <newsTickr/>
    </client-only>
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
  // CHeading
} from '@chakra-ui/vue'

import newsTickr from '../myComponents/newsTickr'

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
