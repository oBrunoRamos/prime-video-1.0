<template>
          <div>
                    <div class="container">                         
                              
                              <div class="div-buttons">
                                        <div class="div-buttons" v-if="noSubscription">
                                                  <button class="button-style button-animate" @click="teste" id="trial-button">
                                                            <p>Watch in {{ provider }}</p>
                                                            <p>Start your 7-day free trial</p>
                                                  </button>
                                                  <button class="button-style button-animate" @click="teste">
                                                            <p>Rent</p><p>UHD {{ rentLocationPrice }}</p>
                                                  </button>
                                                  <button class="button-style button-animate" @click="teste">
                                                            <p>Buy</p><p>UHD {{ buyLocationPrice }}</p>
                                                  </button>
                                        </div>
                                        <button class="button-style button-animate" @click="modalActive=true">
                                                  <p>More purchase options</p>
                                        </button>
                              </div>
                              <!-- <div class="div-buttons">
                                        <button class="button-style button-animate" v-for="(button, index) in buttons" :key="index" @click="button.func" :id="button.id">
                                                  <p>{{ button.firstP }}</p>
                                                  <p>{{ button.secondP }}</p>
                                        </button>
                              </div> -->
                              <div v-if="modalActive" class="modal-container" @click="outSideClick">
                              <div class="modal">
                                        <div class="modal-header"> 
                                                  <h3>More purchase options</h3>
                                                  <button>
                                                            <X
                                                                      :fill="color"
                                                                      height="40"
                                                                      width="40"
                                                                      @click="modalActive = false"
                                                            />
                                                  </button>
                                        </div>
                                        <div>
                                                  <h4>
                                                            <ShoppingBag
                                                                      :fill="color"
                                                                      :stroke="stroke"
                                                                      :height="heigth"
                                                                      :width="width"
                                                            />
                                                            Included with {{ provider }} for {{ monthlyPayment }}/month after trial
                                                  </h4>
                                                  <button class="button-style button-animate" @click="teste">
                                                            <p>Watch in {{ provider }}</p>
                                                            <p>Start your 7-day free trial</p>
                                                  </button>
                                        </div>
                                        <div>
                                                  <h4>Rent</h4>
                                                  <div class="div-buttons">
                                                            <button class="button-style button-animate" @click="teste">
                                                                      <p>Rent</p><p>UHD {{ rentLocationPrice }}</p>
                                                            </button>
                                                            <button class="button-style button-animate" @click="teste">
                                                                      <p>Rent</p><p>HD {{ rentLocationPrice }}</p>
                                                            </button>
                                                            <button class="button-style button-animate" @click="teste">
                                                                      <p>Rent</p><p>SD {{ rentLocationPrice }}</p>
                                                            </button>
                                                  </div>
                                                  <span class="warning">Rentals include 30 days to start watching this video and 48 hours to finish once started.</span>
                                        </div>
                                        <div>
                                                  <h4>Buy</h4>
                                                  <div class="div-buttons">
                                                            <button class="button-style button-animate" @click="teste">
                                                                      <p>Buy</p><p>UHD {{ buyLocationPrice }}</p>
                                                            </button>
                                                            <button class="button-style button-animate" @click="teste">
                                                                      <p>Buy</p><p>HD {{ buyLocationPrice }}</p>
                                                            </button>
                                                            <button class="button-style button-animate" @click="teste">
                                                                      <p>Buy</p><p>SD {{ buyLocationPrice }}</p>
                                                            </button>
                                                  </div>
                                        </div>
                              </div>
                    </div>
                    </div>
                   
          </div>
</template>

<script>
import { ShoppingBag } from 'lucide-vue-next';
import { X } from 'lucide-vue-next';

export default {
          data(){''
                    return{
                              // Icon style
                              stroke:'yellow',

                             heigth:"20",
                             width:"20",

                              rentLocationPrice: null,
                              buyLocationPrice:null,

                              monthlyPayment:29.9,

                              buttons:[
                                        {
                                                  id:'trial-button',
                                                  firstP:`Watch in ${this.provider}`,
                                                  secondP:`Start your 7-day free trial`
                                        },
                                        {
                                                  firstP:`Rent`,
                                                  secondP:`UHD ${ this.rentLocationPrice }`
                                        },
                                        {
                                                  firstP:`Buy`,
                                                  secondP:`UHD ${ this.buyLocationPrice}`
                                        },
                                        {
                                                  firstP:`More purchase options`,
                                                  func:'outSideClick'
                                        }

                              ],

                              modalActive: false,
                    }
          },
          components:{
                    ShoppingBag,
                    X
          },
          props:{
                    provider:String,
                    rentPrice:Number,
                    buyPrice:Number
          },
          methods:{
                    convertPrice(){
                              let lang = document.documentElement.lang;
                              const rent = this.rentPrice;
                              const buy = this.buyPrice;
                              // let currency = ''
                              // if(lang=='pt-br'){
                              //           currency = 'BRL'
                              // }else if(lang=='en-US'){
                              //           currency='USD'
                              // }
                              
                             this.buyLocationPrice = buy.toLocaleString(lang, {style:'currency', currency:'BRL', minimumFractionDigits: 2, maximumFractionDigits: 2})
                             this.rentLocationPrice = rent.toLocaleString(lang, {style:'currency', currency:'BRL', minimumFractionDigits: 2, maximumFractionDigits: 2})
                    },
                    outSideClick(event){
                              if(event.target === event.currentTarget){
                                        this.modalActive=false
                              }
                    },
                    teste(event){
                              console.log(event.target, event.currentTarget);
                    }
          },
          created(){
                    this.convertPrice()
          }
}
</script>
<style scoped>
          .container{
                    display: flex;
                    flex-direction: column;

                    color: #fff;
                    font-weight: bold;
          }
          
          .div-buttons{
                    display: flex;
                    flex-direction: row;
          }
          .button-style{
                    display: flex;
                    flex-direction: column;
                    justify-content: center;
                    align-items: start;

                    width: fit-content;
                   height: 3.5rem;
                   margin:0.6rem;

                    color: #fff;
                    font-weight: 600;
                    padding:2rem 1rem; 

                   background:hsla(0, 0%, 100%, .2);
                   
                   border: none;
                    border-radius: 5px;
          }
          .button-style p{
                    font-size: 15pt;
          }
          #trial-button{
                    display: flex;
                    flex-direction: column;

                    background: #fff;
                    color: rgb(22, 22, 22);
          }
          .animate :hover {
                    background: #fff;
                    color:#222222;
                    width: fit-content;
                   height: 3.5rem;
                   margin:0.6rem;

          }
          .modal-container{
                    position: absolute;
                    
                    display: flex;
                    justify-content: center;
                    align-items: center;

                    z-index: 3;
                    height: 100vh;
                    width: 100vw;
                    background: rgba(0,  0   , 0, .5);
          }
          .modal{
                    position: relative;

                    background: #191e25;

                    padding: 1rem;

                    z-index: 4;
                    height: 80%;
                    width: 80%;
                    max-height: 580px;
                    max-width: 860px;

                    border-radius: 10px;
          }
          .modal-header{
                    display: flex;
                    justify-content: space-between;

                    font-size: 15pt;
                    
                    padding: 0.5rem;

          }
          .modal-header button{
                    background: transparent;
                    border: none;
                    color: #fff;
                    
          }
          .modal h4{
                    font-size: 15pt;
                    padding: 1rem;
                    font-weight: bolder;
          }
          .modal span{
                    color: #aaa;
                    background: transparent;
                    font-size: 15pt;

                    padding: 0 1rem 1rem 1rem;
          }
</style>
