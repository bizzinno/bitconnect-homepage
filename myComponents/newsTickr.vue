<template>
    <div>
        <CBox v-bind="mainStyles[colorMode]">
            <CBox class="marquee-container" v-bind="mainStyles[colorMode]">
                <CBox as="p">LATEST NEWS</CBox>
            </CBox>
            <CPseudoBox 
            class="marquee-bg"  
            @mouseover="togglemarqueeStatus" @mouseOut="togglemarqueeStatus" 
            v-bind="mainStyles[colorMode]"
            
            bg="gray.100"
            pt="1rem"
            pb="1rem"
            minH="1rem"
            h="4rem"
            d="flex"
            align-items="center">



                
                    <marquee-text :duration="70" :paused="this.marqueeStatus" v-bind="mainStyles[colorMode]">
                        <CBox as='a' :href="item.url"  v-for="(item) in items" :key="item.id" >{{ item.content  }}</CBox>
                    </marquee-text>
                
            </CPseudoBox>
        </CBox>
    </div>    

    

</template>

<script>
import { CBox,CPseudoBox } from '@chakra-ui/vue'

export default {
    name:"newsTickrComponent",

    props:{
    },
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
        return {
            
            marqueeStatus:false,    
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


            items: []

        }
    },
    watch:{
        items(newData,oldData){
            this.$emit('itemsEmitted',newData)
            // console.log(oldData)
        }
    },
    async fetch(){
        console.log(this)
        // const data =await this.$axios.get(`http://localhost:8000/api/gettickr/`) 

        

        
        // console.log(data)
        this.items =[{"url":"https://google.com","option_info":"","content_id":"0e4987d8-b23a-4ba8-bf8a-43a03399cd4c","content":"The Safer’s problems are manifold and intertwined. It is forty-five years old—ancient for an oil tanker. Its age would not matter so much were it being maintained properly, but it is not. In 2014, members of one of Yemen’s powerful clans, the Houthis, launched a successful coup, presaging a brutal conflict that continues to this day. Before the war, the Yemeni state-run firm that owns the ship—the Safer Exploration & Production Operations Company, or sepoc—spent some twenty million dollars a year taking care of the vessel. Now the company can afford to make only the most rudimentary emergency repairs. More than fifty people worked on the Safer before the war; seven remain. This skeleton crew, which operates with scant provisions and no air-conditioning or ventilation below deck—interior temperatures on the ship frequently surpass a hundred and twenty degrees—is monitored by soldiers from the Houthi militia, which now occupies the territory where the Safer is situated. The Houthi leadership has obstructed efforts by foreign entities to inspect the ship or to siphon its oil. The risk of a disaster increases every day.","created_at":"2021-09-28T12:46:40.830093+05:30","updated_at":"2021-09-28T12:46:40.830127+05:30"},{"url":"https://google.com","option_info":"","content_id":"5bfab516-a49f-47fb-a602-bc1e7c48638d","content":"Soon, a vast, decrepit oil tanker in the Red Sea will likely sink, catch fire, or explode. The vessel, the F.S.O. Safer—pronounced “Saffer”—is named for a patch of desert near the city of Marib, in central Yemen, where the country’s first reserves of crude oil were discovered. In 1987, the Safer was redesigned as a floating storage-and-off-loading facility, or F.S.O., becoming the terminus of a pipeline that began at the Marib oil fields and proceeded westward, across mountains and five miles of seafloor. The ship has been moored there ever since, and recently it has degraded to the verge of collapse. More than a million barrels of oil are currently stored in its tanks. The Exxon Valdez spilled about a quarter of that volume when it ran aground in Alaska, in 1989","created_at":"2021-10-04T12:55:51.388088+05:30","updated_at":"2021-10-04T12:55:51.388116+05:30"}]
        
        
    },

    mounted(){
                


    },
    components:{
        


        'marquee-text': () => {
            if (process.client) {
                return import ('vue-marquee-text-component')
                
            }
        },
  
        
        CBox,
        CPseudoBox,


    },
    methods:{

        togglemarqueeStatus(e){
                
                console.log(e)

                if(this.marqueeStatus){
                    this.marqueeStatus = false;
                }else{
                    this.marqueeStatus = true;
                }
        },








    }
}


</script>

<style>


.marquee-container{
    display: flex;
    align-items: center;
    padding-left: 4rem;
    padding-right: 1rem;    
    position: absolute;
    background-color: #C5283D;
    z-index: 222;
    height: 4rem;    
}

.marquee-bg a::before{
    content:""
}
.marquee-bg a::after{
    content: "";
}

.marquee-bg a:hover{
    text-decoration: underline;
}

.marquee-bg a{
    text-decoration: none;
    color: #100072;
    padding-left: 2.8rem;
    padding-right: 2.8rem;

}
.marquee-bg a:active{
    color: #100072;
}
.marquee-bg a:visited{
    color: #100072;
}



.marquee-container p{   
    font-family: Roboto;
    font-style: normal;
    font-weight: bold;
    font-size: 1rem;    
    text-align: center;  
    color: white;  
    /* padding: 0.5rem; */

}

.marquee-bg{
 
    
}



.tickr-item-action{

    width:1.5rem;
    height:1.5rem;
}

.tickr-item-container{
    display: flex;
    justify-content: center;
}
</style>













