<template>
  <div class="latest-products-wrapper best-sellers-wrapper bg-white py-10">
    <div class="main-title text-xl w-9/12 pb-2">
      <h1 class="font-semibold">پر فروش ترین محصولات</h1>
    </div>
    <div class="inner-content mt-4">
      <div class="product-wrapper flex justify-between items-center flex-wrap w-9/12 py-5">
        <nuxt-link to="/" class="product-item rounded-md relative mb-8 mx-1 py-2 flex justify-between items-center flex-col"
                   v-for="item in specialOffers" :key="item.id">
          <div class="image mb-3 w-44 h-4/6">
            <img class="w-full h-full" :src="require(`@/assets/images/books/${item.imgUrl}`)" alt="">
          </div>
          <div class="info text-center h-2/6 w-10/12 flex align-center justify-center flex-col">
            <p class="text-base iran-medium mb-2">{{ item.title }}</p>
            <p class="text-sm"><span class="vazir-digits">{{ item.price }}</span> تومان </p>
          </div>
          <div class="overlay absolute right-1 top-5 opacity-0 duration-300">
            <div class="inner-content flex flex-col items-center">
              <nuxt-link to="/" class="relative bg-white h-10 w-10 p-2 flex items-center justify-center mb-2">
                <i class="fa-regular fa-eye duration-4"></i>
                <div
                  class="absolute tooltip right-full top-1/2 z-20 mr-3 -translate-y-1/2 whitespace-nowrap rounded bg-white py-[6px] px-4 py-1 text-sm hidden">
                  <span class="absolute right-[-3px] top-1/2 -z-10 h-2 w-2 -translate-y-1/2 rounded-sm bg-white"></span>
                  مشاهده جزئیات
                </div>
              </nuxt-link>

              <nuxt-link to="/" class="relative bg-white h-10 w-10 p-2 flex items-center justify-center">
                <i class="fa fa-shopping-cart duration-4"></i>
                <div
                  class="absolute tooltip right-full top-1/2 z-20 mr-3 -translate-y-1/2 whitespace-nowrap rounded bg-white py-[6px] px-4 py-1 text-sm hidden">
                  <span class="absolute right-[-3px] top-1/2 -z-10 h-2 w-2 -translate-y-1/2 rounded-sm bg-white"></span>
                  افزودن به سبد خرید
                </div>
              </nuxt-link>
            </div>
          </div>
        </nuxt-link>
        <div class="more-btn w-full flex items-center justify-center mt-5">
          <nuxt-link to="/" class="rounded-md px-5 py-2 w-40 text-center   text-white duration-300">محصولات بیشتر</nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
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
          title: 'نمایش افسانه ای برای وقتی دیگر',
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
       /* {
          id: 10,
          title: 'کتابخانه نیمه شب',
          author: 'مت هیگ',
          price: '85000',
          description: '',
          imgUrl: '11.jpg'
        },*/
      ]
    }
  },
}
</script>

