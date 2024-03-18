<template>
       <div>
            <h2>FAQs</h2>
            
              <dl v-for="faqs in faq" :key="faqs.id">
                     <dt @click="faqs.open =! faqs.open">{{faqs.title }}
                  <i class="fa-solid fa-chevron-down"></i>
                     
                     </dt>
                     <dd v-show="faqs.open">{{ faqs.description }}</dd>
              </dl>

       </div>
</template>

<script>
import FaqsContent from '@/FaqsContent';


       export default {
              data(){
                     return{
                            faq : FaqsContent.faq,
                            activeItemId: false
                     }
              },
              // methods:{
              //   faqOpen(){ 
                       
              //       return  this.activeItemId= !this.activeItemId
              // }
              // }
              
              
       }
</script>

<style scoped>
h2{
       font-size:40px;
       text-align: center;
}
div{
       text-align: center; 
       padding:0px 0px 100px 0px;
}

dt{
       background: #F2F0F0;
       width:800px;
       padding: 20px 40px;
       position: relative;
       margin: auto;
       text-align: left; 
       font-family: 'Inter', sans-serif;

}
dd{
       width:800px;
       padding: 20px 40px;
       position: relative;
       margin: auto;
       text-align: left;   
       font-size: 17px;
       line-height: 25px;
       font-family: 'Inter', sans-serif;
}
i{
       position: absolute;
       display: inline-flex;
       left:50rem;
}
@media screen and (max-width:576px){
       dt{
              width:auto;
       }
       i{
              position: relative;
    /* right: 0; */
    left: 1rem;
    display: flex;
    justify-content: flex-end;
          
       }
       dd{
              width:auto;
       }
       div{
              padding:10px 20px;
       }
       h2{
              font-size: 25px;
       }
}

@media screen and (min-width:577px) and (max-width:768px){
       dt{
       width:75%;
       }
       dd{
              width:75%;
       }
       i{
              left:38rem;
       }
}

@media screen and (max-width:360px){
       i{
              left:1rem;
       }
}
</style>