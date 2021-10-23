<template>
  <footer>
      <CBox as="nav"  bg="#303030" d="flex" pl="4rem" pr="4rem"  >
          <CBox id="footer-col-1" pt="4rem" pb="4rem" flex="2 1 0" >
                            <CBox>
                                    <CImage mb="1.5rem" size="3rem" :src="require('@/assets/imgs/logo.webp')" alt="" fallback-src="https://via.placeholder.com/150"></CImage>
                                    <CBox>
                                        <CHeading  as="h3" size="xl" tabindex="0" font-family="'Squada One';" color="white">
                                                BIT Connect 
                                        </CHeading>
                                        <CBox as="p"  tabindex="0" color="white">
                                                Show your dramatic self to the world in anonimity 
                                        </CBox>
                                    </CBox>
                            </CBox>

                            <CBox>
                                <CText  pb="1rem" pt="1rem" color="white">BIT Connect  app is developed by The Percept, Open Source Enthusiast, to help people connect and gain info of their dramatic sides by performing on live feeds and showcasing thier true but hidden sides which they don't usually do. BIT Connect  © 2021, A Product for the Globe and Billions of people in our world</CText>
                                <CText font-weight="bold" color="white">Last Updated on </CText>
                                <CText color="white">October 23, 2020 </CText>
                            </CBox>                
            </CBox>

            <CBox id="footer-col-2" pt="4rem" pb="4rem" pl="4rem" pr="4rem" flex="1 1 0">
                <CBox>
                    <CText  pt="4.8rem" pb="1rem" fontSize="xl" font-weight="500" color="white">Quick Access</CText>
                    <CBox as="ul" list-style="none" color="#bfbfbf">
                        
                        <CBox as="li"  pb="1.2rem">
                            <CBox as="a" href="#">My Information</CBox>
                        </CBox>
                        <CBox as="li"  pb="1.2rem">
                            <CBox as="a" href="#">Contact Forms</CBox>
                        </CBox> 
                        <CBox as="li"  pb="1.2rem">
                            <CBox as="a" href="#">Notifications</CBox>
                        </CBox>    
                        <CBox as="li"  pb="1.2rem">
                            <CBox as="a" href="#">Letters Strangers</CBox>
                        </CBox>                                                                     
                        <CBox as="li"  pb="1.2rem">
                            <CBox as="a" href="#">Watch</CBox>
                        </CBox> 
                    </CBox>
                </CBox>                
            </CBox>



            <CBox id="footer-col-3" pt="4rem" pb="4rem" pl="4rem" pr="4rem"   flex="1 1 0">
                <CBox>
                    <CText   pt="4.8rem" pb="1rem" fontSize="xl" font-weight="500" color="white">Usage Information</CText>
                    <CBox as="ul" list-style="none" color="#bfbfbf">
                        
                        <CBox as="li"  pb="1.2rem">
                            <CBox as="a" href="#">Copyright Policies</CBox>
                        </CBox>
                        <CBox as="li"  pb="1.2rem">
                            <CBox as="a" href="#">Terms & Conditions</CBox>
                        </CBox> 
                        <CBox as="li"  pb="1.2rem">
                            <CBox as="a" href="#">Privacy Policy</CBox>
                        </CBox>    
                        <CBox as="li"  pb="1.2rem">
                            <CBox as="a" href="#">Site Map</CBox>
                        </CBox>                                                                     

                    </CBox>
                </CBox>                
            </CBox>


            <CBox id="footer-col-4"  pt="4rem" pb="4rem" pl="4rem"  flex="2 1 0">
                <CBox color="white">
                    <CText   pt="4.8rem"  pb="1rem" fontSize="xl" font-weight="500" color="white">Disclaimer</CText>
                    <CText color="#bfbfbf">Content on this website is published and managed by The Percept, Open Source Enthusiast and every effort is being made to update the information periodically.In case, any discrepancy is found in the content of this website, this may kindly be brought to the notice of The Percept.</CText>
                </CBox>                
            </CBox>


        </CBox>



  </footer>
</template>

<script>
export default {

}
</script>

<style>

</style>