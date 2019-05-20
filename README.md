# swiper-animate
和swiper滑动插件相结合的animate文件

## 在vue中的使用方法
### 1.    引入</br>
                            ```import * as swiperAni from '@/utils/swiper.animate.min.js'```
### 2.    配置</br>
                        
          
                            data() {
                              return {
                                  swiperOption: {
                                      // swiper configs 所有的配置同swiper4官方api配置
                                     ...//其他配置参考官网
                                      on: {
                                          init: function () {
                                              swiperAni.swiperAnimateCache(this); //隐藏动画元素
                                              swiperAni.swiperAnimate(this); //初始化完成开始动画
                                          },
                                          slideChangeTransitionEnd: function () {
                                              swiperAni.swiperAnimate(this); //每个slide切换结束时也运行当前slide动画
                                          }
                                      }
                                  },
                                  }
                            }
                           
### 3.    使用<br>

                           

                            <p class="ani" swiper-animate-effect="fadeInLeft" swiper-animate-duration="0.6"
                               swiper-animate-delay="0.6s">第一行</p>
                            <p class="ani" swiper-animate-effect="fadeInLeft" swiper-animate-duration="0.6"
                               swiper-animate-delay="1.2s">第二行</p>
                            <p class="ani" swiper-animate-effect="fadeInLeft" swiper-animate-duration="0.6"
                               swiper-animate-delay="1.8s">第三行</p>
                               //class="ani" 不能少
                               //swiper-animate-effect： 动画类型，参照animate官网
                               //swiper-animate-duration：动画持续时间
                               //swiper-animate-delay：动画延时执行时间
                           
