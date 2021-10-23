<template>
    <c-box as="header"  width="100%"
        v-bind="mainStyles[colorMode]"
        display=flex justify-content="flex-end" flex-direction="column" 

        >

        <c-box as="ul" pb="0.5rem" pt="0.5rem" width="100%" d="flex" justify-content="flex-end" pl="4rem" pr="4rem">
            <CIconButton
                ml="3"
                
                :icon="colorMode === 'light' ? 'moon' : 'sun'"
                :aria-label="`Switch to ${
                colorMode === 'light' ? 'dark' : 'light'
                } mode`"
                @click="toggleColorMode"
            />

            <CIconButton
                ml="3"
                icon="increaseFontSize"
                :aria-label="`Switch to ${
                colorMode === 'light' ? 'dark' : 'light'
                } mode`"
            />
        </c-box>
        <CDivider mt="0"/>

        <c-box         pl="4rem" pr="4rem">
            <c-box as="nav" pt="0.5rem" pb="0.5rem" d="flex" justify-content="space-between">
                <nuxt-link to="/">
                    <c-box  d="flex">
                        <CImage size="3rem" :src="require('@/assets/imgs/logo.webp')" alt="" fallback-src="https://via.placeholder.com/150"></CImage>
                        <c-box  pl="1rem">
                            <CHeading as="h3" size="lg" tabindex="0" font-family="'Squada One';">
                                BIT Connect
                            </CHeading>
                            <c-box as="p"  tabindex="0">
                                Show your dramatic self to the world in anonimity 
                            </c-box>
                        </c-box>
                    </c-box>
                </nuxt-link>
                <c-box d="flex" >
                    <c-box as="ul" d="flex" list-style="none" align-items="center"  border-top="1px solid #BFBFBF"  tabindex="0" >
                        <CPseudoBox  
                            as="li" 
                            border-right="1px solid #BFBFBF" 
                            border-bottom="1px  solid #BFBFBF" 
                            border-left="1px  solid #BFBFBF" 
                            height="100%" 
                            d="flex" 
                            align-items="center" 
                            pl="1rem" 
                            pr="1rem"  
                            tabindex="0"
                            cursor="pointer"
                            :_hover="{borderBottom  : '1px solid red' }"
                            >
                            <c-box as="a" >My Information</c-box>
                        </CPseudoBox>


                        <CPseudoBox  
                            as="li" 
                            border-right="1px solid #BFBFBF" 
                            border-bottom="1px  solid #BFBFBF" 
                            height="100%" 
                            d="flex" 
                            align-items="center" 
                            pl="1rem" 
                            pr="1rem"  
                            tabindex="0"
                            cursor="pointer"
                            :_hover="{borderBottom  : '1px solid red' }"
                            >
                            <c-box as="a" >Contact Forms</c-box>
                        </CPseudoBox>

                        <CPseudoBox  
                            as="li" 
                            border-right="1px solid #BFBFBF" 
                            border-bottom="1px  solid #BFBFBF" 
                            height="100%" 
                            d="flex" 
                            align-items="center" 
                            pl="1rem" 
                            pr="1rem"  
                            tabindex="0"
                            cursor="pointer"
                            :_hover="{borderBottom  : '1px solid red' }"
                            >
                            <c-box as="a" >Notifications</c-box>
                        </CPseudoBox>

                        <CPseudoBox  
                            as="li" 
                            border-right="1px solid #BFBFBF" 
                            border-bottom="1px  solid #BFBFBF" 
                            height="100%" 
                            d="flex" 
                            align-items="center" 
                            pl="1rem" 
                            pr="1rem"  
                            tabindex="0"
                            cursor="pointer"
                            :_hover="{borderBottom  : '1px solid red' }"
                            >
                            <c-box as="a" >Letters Strangers</c-box>
                        </CPseudoBox>
    

                        <CPseudoBox  
                            as="li" 
                            border-right="1px solid #BFBFBF" 
                            border-bottom="1px  solid #BFBFBF" 
                            height="100%" 
                            d="flex" 
                            align-items="center" 
                            pl="1rem" 
                            pr="1rem"  
                            tabindex="0"
                            cursor="pointer"
                            :_hover="{borderBottom  : '2px solid red' }"
                            >
                            <c-box as="a" >Watch</c-box>
                        </CPseudoBox>                                                     

                    </c-box>                
                    <c-box d="flex" >
                        <CImage size="3rem" :src="require('@/assets/imgs/acc.png')" alt="" ml="1rem" mr="1rem" ></CImage>
                        <CImage width="2rem" h="3.2rem" :src="require('@/assets/imgs/emblem.png')" alt=""></CImage>                    
                    </c-box>
                </c-box>
            </c-box>

        </c-box>
        <CDivider mt="0"/>



    </c-box>
    
</template>

<script >
import { CIconButton,CIcon,CDivider,CImage,CHeading,CPseudoBox } from '@chakra-ui/vue'



export default {
    name:'siteHeader',

    inject: ['$chakraColorMode', '$toggleColorMode'],

    computed:{

        toggleColorMode () {
                return this.$toggleColorMode
            },

        colorMode () {
        return this.$chakraColorMode()
        },

    },

    data(){
        return{

            mainStyles: {
                dark: {
                bg: 'gray.700',
                color: 'whiteAlpha.900'
                },
                light: {
                bg: 'white',
                color: 'gray.900'
                }
            },



        }

    },

    mounted(){
        console.log("HERE..")
        console.log(this.$chakra)
    },

    components:{
        CIconButton,
        CIcon,
        CDivider,
        CImage,
        CHeading,
        CPseudoBox
    }


}
</script>

<style>

</style>