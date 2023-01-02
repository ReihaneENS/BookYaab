<template>
  <div class="special-offers-wrapper">
    <div class="main-title text-xl w-9/12 pb-2">
      <h1 class="font-semibold">پیشنهادات ویژه</h1>
    </div>
    <div class="inner-content w-9/12">
      <carousel-3d>
        <slide v-for="item in specialOffers" :key="item.id" :index="item.id" class="bg-white">
          <nuxt-link to="/" class="content p-3 bg-white w-full h-full flex justify-center items-center flex-col">
            <div class="image w-52 h-4/5">
              <img class="h-full w-full" :src="require(`@/assets/images/books/${item.imgUrl}`)" alt="">
            </div>
            <div class="info h-1/5 text-center">
<!--              <p class="text-lg my-2">{{ item.title }}</p>-->
              <p class="text-lg mt-4"> <span class="vazir-digits">{{ item.price }}</span> تومان </p>
            </div>
          </nuxt-link>
        </slide>
      </carousel-3d>
    </div>
  </div>
</template>

<script>
import {Carousel3d, Slide} from 'vue-carousel-3d';

export default {
  data() {
    return {
      specialOffers: [
        {
          id: 0,
          title: 'بی حد و مرز',
          author: 'جیم کوییک',
          price: '54000',
          description: '',
          imgUrl: '1.jpg'
        },
        {
          id: 1,
          title: 'پرسش های فیلسوفان بزرگ جهان',
          author: 'لشک کولاکوفسکی',
          price: '60000',
          description: '',
          imgUrl: '2.jpg'
        },
        {
          id: 2,
          title: 'نمایس افسانه ای برای وقتی دیگر',
          author: 'لویی فردینان سلین',
          price: '125000',
          description: '',
          imgUrl: '3.jpg'
        },
        {
          id: 3,
          title: 'سنگ کاغذ قیچی',
          author: 'آلیس فینی',
          price: '87000',
          description: '',
          imgUrl: '4.jpg'
        },
        {
          id: 4,
          title: 'ساندویچ دزد',
          author: 'گودبرگر برگسون',
          price: '45000',
          description: '',
          imgUrl: '5.jpg'
        },
        {
          id: 5,
          title: 'علی زاوا شاهزاده خیابان',
          author: 'ناتالی سوژون',
          price: '130000',
          description: '',
          imgUrl: '6.jpg'
        },
        {
          id: 6,
          title: 'اندوه سفید',
          author: 'یونس گرامی',
          price: '78000',
          description: '',
          imgUrl: '7.jpg'
        },
        {
          id: 7,
          title: 'تلخو شیرین',
          author: 'سوزان کین',
          price: '92000',
          description: '',
          imgUrl: '8.jpg'
        },
        {
          id: 8,
          title: 'بیایان',
          author: 'آنتوان چخوف',
          price: '65000',
          description: '',
          imgUrl: '9.jpg'
        },
        {
          id: 9,
          title: 'هر دو در نهایت می میرند',
          author: 'آدام سیلورا',
          price: '134000',
          description: '',
          imgUrl: '10.jpg'
        },
        {
          id: 10,
          title: 'کتابخانه نیمه شب',
          author: 'مت هیگ',
          price: '85000',
          description: '',
          imgUrl: '11.jpg'
        },
      ]
    }
  },
  components: {
    Carousel3d,
    Slide
  },
}
</script>
