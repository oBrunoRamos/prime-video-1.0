<template>
          <div class="container">
          <div class="navbar">
                    <a href="">
                              <img class="logo" src="../../../public/primeLogo.png" alt="" />
                    </a>
                    <nav>
                              <li v-for="(navLink, index) in links" :key="index" class="nav-itens">
                                        {{navLink.title}}
                              </li>
                    </nav>
                    <Search/>
                    <div class="user">
                              <h3>{{ user.username }}</h3>
                              <img class="user-image" src="../../assets/icons/user-image.png" alt="">
                    </div>
          </div>
          </div>
</template>

<script>

import { Search } from 'lucide-vue-next';

export default {
  data() {
    return {
          hoverActive:false,
          links:[
                    {
                              title:"Home",
                              link:"",
                              content:[
                                        {
                                                  title: "All",
                                                  link: "",
                                        },
                                        {
                                                  title: "Movies",
                                                  link: "",
                                        },
                                        {
                                                  title: "TV shows",
                                                  link: "",
                                        },
                                        {
                                                  title: "Sports",
                                                  link: "",
                                        }
                              ]
                    },
                    {
                              title:"Store",
                              link:"",
                              content:[
                                        {
                                                  title:"All",
                                                  link:""
                                        },
                                        {
                                                  title:"Rent or Buy",
                                                  link:""
                                        },
                                        {
                                                  title:"Channels",
                                                  link:""
                                        }
                              ]
                    },
                    {
                              title:"Live TV",
                              link:""
                    },
                    {
                              title:"Categories",
                              link:"",
                              content:{
                                        genres: [
                                                  {
                                                            title: "Action and adventure",
                                                            link: "",
                                                  },
                                                  {
                                                            title: "Anime",
                                                            link: "",
                                                  },
                                                  {
                                                            title: "Comedy",
                                                            link: "",
                                                  },
                                                  {
                                                            title: "Documentary",
                                                            link: "",
                                                  },
                                                  {
                                                            title: "Drama",
                                                            link: "",
                                                  },
                                                  {
                                                            title: "Fantasy",
                                                            link: "",
                                                  },
                                                  {
                                                            title: "Horror",
                                                            link: "",
                                                  },
                                                  {
                                                            title: "Kids",
                                                            link: "",
                                                  },
                                                  {
                                                            title: "Mystery and thrillers",
                                                            link: "",
                                                  },
                                                  {
                                                            title: "Romance",
                                                            link: "",
                                                  },
                                                  {
                                                            title: "Science fiction",
                                                            link: "",
                                                  }
                                        ],
                                        featuredCollections:[
                                                  {
                                                            title:"Celebrate awards season",
                                                            link:""
                                                  },
                                                  {
                                                            title:"Sports",
                                                            link:""
                                                  },
                                                  {
                                                            title:"Black voices",
                                                            link:""
                                                  },
                                                  {
                                                            title:"LGBTQIAP+",
                                                            link:""
                                                  },
                                                  {
                                                            title:"Home Premiere",
                                                            link:""
                                                  }
                                        ]
                              }
                    },
                    {
                              title:"My Stuff",
                              link:"",
                              content:[
                                        {
                                                  title:"All",
                                                  link:""
                                        },
                                        {
                                                  title:"Watchlist",
                                                  link:""
                                        },
                                        {
                                                  title:"Purchases & Rentals",
                                                  link:""
                                        }
                              ]
                    }
          ],
          user:{
                    username:"User",
                    userImage:"",
                    options:[
                              {
                                        title:"Your Account",
                                        links:[
                                                  {
                                                            title:"Help",
                                                            link:""
                                                  },
                                                  {
                                                            title:"Watch Anywhere",
                                                            link:""
                                                  },
                                                  {
                                                            title:"Account & Settings",
                                                            link:""
                                                  },
                                                  {
                                                            title:"Prime Benefits",
                                                            link:""
                                                  },
                                                  {
                                                            title:"Sing out",
                                                            link:""
                                                  }
                                        ]
                              },
                              {
                                        title:"Profiles",
                                        profiles:{

                                        },
                                        links:[
                                                  {
                                                            title:"Manage profiles",
                                                            link:""
                                                  },
                                                  {
                                                            title:"Learn more",
                                                            link:""
                                                  }
                                        ]
                              }

                    ]
          }
    };
  },
  components:{
          Search
  },
  methods:{
          fixNavbar(){
                    const container = document.querySelector('.container')
                    if(container.offsetHeight >110){
                              container.style.background = 'transparent'
                              container.style.padding = '1rem 0 0 0'
                    }
                    console.log( container.offsetHeight);
          },
          comebackNavbar(){
                    
          }
  },
  watch(){
          this.fixNavbar()
  }
};
</script>

<style scoped>
          .container{
                    display: flex;
                    justify-content: center;
                    align-items: center;

                    background: red;
                    color: #fff;

                    height: 6vh;
          }
          .logo{
                    height: 25px;
          }
          .navbar{
                    display: flex;
                    justify-content: center;
                    align-items: center;

                    height: 100%;
                    width: fit-content;

                    background: #00060a;

                    padding: 0 1.5rem;
                    border-radius: 10px;
          }
          .navbar nav{
                    display: flex;
                    justify-content: center;
                    align-items: center;

                    list-style: none;

                    margin: 2.5rem;
          }

          .nav-itens::after{
                    content: '🠻';
                    margin: 0.2rem;
          }
          .nav-itens{
                    font-size: 14pt;
                    font-weight: 600;
                    margin: 0 1rem;
          }
          .user{
                    display: flex;
                    justify-content: center;
                    align-items: center;

                    margin-left: 1.5rem;
          }
          .user-image{
                    height: 38px;
                    margin-left: 0.5rem;
          }
</style>