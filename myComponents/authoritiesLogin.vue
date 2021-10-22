<template>
    <div>

        <CBox  
            pl="4rem"
            pr="4rem"
            pt="3rem"  
            d="flex"
            v-bind="mainStyles[colorMode]"
            >

            <CBox 
            class="auth-login-child" 
            v-bind="mainStyles[colorMode]"
            pr="6rem"
            
            >
            
                <CHeading as="h3" size="lg" pb="1rem" >Top features of our APP</CHeading>
                <CBox d="flex"
                pb="2.2rem"
                class="dash-container">
                    <div class="dash-one"></div>
                    <div class="dash-two"></div>
                </CBox>
                <CBox as="ul" list-style="none" >
                    <CBox as="li" pt="0" pb="1rem" d="flex" borderBottom="1px solid #E8E8E8">
                        <CBox w="4rem" h="4rem" borderRadius="50%" border="1px solid #E8E8E8">
                            <CImage border-radius="50%;"
                            :src="require('@/assets/imgs/pk.png')" class="authorities-img" alt=""/>
                        </CBox>
                        <CBox class="authorities-info">
                            <CText fontSize="2xl">
                                Player Knockout Battle Ground
                            </CText>
                            <CText>
                                PKBG, compete with the crowd
                            </CText>
                        </CBox>
                    </CBox>

                    <CBox as="li" pt="1rem" pb="1rem" d="flex" borderBottom="1px solid #E8E8E8">
                        <CBox w="4rem" h="4rem" borderRadius="50%" border="1px solid #E8E8E8">
                            <CImage border-radius="50%;"
                            :src="require('@/assets/imgs/coins.png')" class="authorities-img" alt=""/>


                        </CBox>
                        <CBox class="authorities-info">
                            <CText fontSize="2xl">
                                Gifting on Calls
                            </CText>
                            <CText>
                                Send the virtual giifts by using the coins you've purchased.
                            </CText>
                        </CBox>
                    </CBox>


                    <CBox as="li" pt="1rem" pb="1rem" d="flex" borderBottom="1px solid #E8E8E8">
                        <CImage border-radius="50%;"
                        
                        :src="require('@/assets/imgs/calls.png')" class="authorities-img" alt=""/>

                        <CBox class="authorities-info">
                            <CText fontSize="2xl">
                                Better Call History
                            </CText>
                            <CText>
                                No downtime on voice calls
                            </CText>
                        </CBox>
                    </CBox>            
                </CBox>
            </CBox>
            <CBox class="auth-login-child" >
                <CHeading as="h3" size="lg" pb="1rem">Login to the Battle Ground portal</CHeading>

                <div class="pb-0 dash-container ">
                    <div class="dash-one"></div>
                    <div class="dash-two"></div>

                    
                </div>  
                <CBox as="ul" list-style="none"  d="flex" flexDirection="column">
                    <CBox as="li" list-style="none" borderBottom="2px solid #E8E8E8">
                        <CBox 
                       
                            bg="#F2F2F2" 
                            padding="1rem"  d="flex" >
                                <CImage :src="require('@/assets/imgs/battle_ground.png')" w="5rem" h="5rem" alt=""/>
                                <CBox flex="1 1 0" padding="1rem" paddingTop="0" paddingBottom="0" >
                                    <CText fontSize="2xl"  >
                                        Battle Ground Premium Players
                                    </CText>
                                    <CText pr="0.5rem">
                                        Login on the web portal
                                    </CText>
                                </CBox>
                                    <CBox>
                                            <CBox as="a" href="#" border="1px solid #C5283D" padding="1rem 0" w="12rem" d="flex" align-items="center" justify-content="center" text-decoration="none" >
                                                <CText color="#C5283D" font-weight="bold">
                                                    LOGIN
                                                </CText>
                                            </CBox>
                                        </CBox>
                            </CBox>
                    </CBox>


                    <CBox as="li" >
                        <CBox padding="1rem" bg="#F2F2F2" d="flex" >
                            <CImage :src="require('@/assets/imgs/quil.png')" w="5rem" h="5rem" alt=""/>
                            <CBox flex="1 1 0" padding="1rem" paddingTop="0" paddingBottom="0" >
                                <CText fontSize="2xl">
                                    Regular Players
                                </CText>
                                <CText pr="0.5rem">
                                    Our regular players can use this app 
                                </CText>
                            </CBox>
                            <CBox>
                                <CBox as="a" href="#" border="1px solid #C5283D" padding="1rem 0" w="12rem" d="flex" align-items="center" justify-content="center" text-decoration="none" >
                                    <CText color="#C5283D" font-weight="bold">
                                        DOWNLOAD
                                    </CText>
                                </CBox>
                            </CBox>
                        </CBox>
                    </CBox>

                </CBox>
            </CBox>
        </CBox>




    </div>
</template>

<script>
import { CBox,CPseudoBox,CHeading,CText,CDivider } from '@chakra-ui/vue'

export default {

	name:"authLogin",

    inject: ['$chakraColorMode', '$toggleColorMode'],

    computed:{

        toggleColorMode () {
                return this.$toggleColorMode
            },

        colorMode() {
        return this.$chakraColorMode()
        },

    },
    components: {
        CBox,
        CPseudoBox,
        CHeading,
        CText,
        CDivider
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


    }






}
</script>

<style>
ul{ 

    list-style: none;

}



.authorities-img{
    
    width: 4rem;
    height: 4rem;
    border: 1px solid #E8E8E8;
}

.authorities-ul li{
    display:flex;
    padding:1rem 0;
    border-bottom: 1px solid #E8E8E8;
}
.authorities-ul li:nth-child(1){
    padding-top:0
}
.authorities-login-container{
    display:flex;
}

.login-download-ul li div{
    padding: 1rem;
    background-color: #F2F2F2;  
      
    
}

.login-download-ul li div div{
font-style: normal;
font-weight: 300;
}



.site-heading{
    font-style: normal;  
    font-weight: normal; 
    font-size: 1.5rem; 
    padding-bottom: 1rem;
}
.dash-container{
   display: flex;
   padding-bottom: 2.2rem;

}

.main-h3{
    font-style: normal;
    font-size: 1.5rem; 
    font-weight: 300;  
}
.authorities-info{
    font-style: normal;
    font-weight: 300;
    padding-left: 1.5rem;
    
}


.auth-login-child{
    flex: 1 1 0;
    
}

#auth-login-child-one{
    padding-right:6rem ;
}

.login-download-ul li img{
    width: 5rem;
    height: 5rem; 
    
}

.login-download-ul li div:nth-child(2){
    flex : 1 1 0;
}
.login-download-ul li:nth-child(1){
    border-bottom: 2px solid #E8E8E8;
}

.btn-secondary{
    border: 1px solid #C5283D;
    display:inline-block;
    padding: 1rem 0;
    width: 12rem;
    /* max-width: 12rem; */
    display: flex;
    align-items: center;
    justify-content: center;
    text-decoration: none;
}


</style>