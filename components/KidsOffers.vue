<template>
  <div class="kids-offers-wrapper">
    <div class="main-title text-xl w-9/12 pb-2">
      <h1 class="font-semibold">کودکان</h1>
    </div>
    <div class="inner-content w-9/12">
      <div class="product-wrapper flex justify-between items-center flex-wrap">
        <nuxt-link to="/" class="product-item relative mb-8 w-1/4 py-2 flex justify-center items-center flex-col"
                   v-for="item in kidsOffers" :key="item.id">
          <div class="image mb-3 w-44 h-56">
            <img class="w-full h-full" :src="require(`@/assets/images/books/kids/${item.imgUrl}`)" alt="">
          </div>
          <div class="info text-center">
            <p class="text-base iran-medium mb-2">{{ item.title }}</p>
            <p class="text-sm"><span class="vazir-digits">{{ item.price }}</span> تومان </p>
          </div>
          <div class="overlay absolute right-1 top-0 opacity-0 duration-300">
            <div class="inner-content flex flex-col items-center">
              <nuxt-link to="/" class="relative bg-white h-10 w-10 p-2 flex items-center justify-center mb-2">
                <i class="fa-regular fa-eye duration-4"></i>
                <div class="absolute tooltip right-full top-1/2 z-20 mr-3 -translate-y-1/2 whitespace-nowrap rounded bg-white py-[6px] px-4 py-1 text-sm hidden">
                  <span class="absolute right-[-3px] top-1/2 -z-10 h-2 w-2 -translate-y-1/2 rounded-sm bg-white"></span>
                  مشاهده جزئیات
                </div>
              </nuxt-link>

              <nuxt-link to="/" class="relative bg-white h-10 w-10 p-2 flex items-center justify-center">
                <i class="fa fa-shopping-cart duration-4"></i>
                <div class="absolute tooltip right-full top-1/2 z-20 mr-3 -translate-y-1/2 whitespace-nowrap rounded bg-white py-[6px] px-4 py-1 text-sm hidden">
                  <span class="absolute right-[-3px] top-1/2 -z-10 h-2 w-2 -translate-y-1/2 rounded-sm bg-white"></span>
                  افزودن به سبد خرید
                </div>
              </nuxt-link>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      kidsOffers: [
        {
          id: 1,
          title: 'دایره المعارف کوچک من',
          author: '',
          price: '54000',
          description: '',
          imgUrl: '1.jpg'
        },
        {
          id: 2,
          title: 'نخ نامرئی',
          author: '',
          price: '57000',
          description: '',
          imgUrl: '2.jpg'
        },
        {
          id: 3,
          title: 'تو بینظیری',
          author: '',
          price: '61000',
          description: '',
          imgUrl: '3.jpg'
        },
        {
          id: 4,
          title: 'گریشا',
          author: '',
          price: '38000',
          description: '',
          imgUrl: '4.jpg'
        },
        {
          id: 5,
          title: 'عمو زنجیرباف',
          author: '',
          price: '46000',
          description: '',
          imgUrl: '5.jpg'
        },
        {
          id: 6,
          title: 'شادی',
          author: '',
          price: '120000',
          description: '',
          imgUrl: '6.jpg'
        },
        {
          id: 7,
          title: 'دایره المعارف کوچک من : جانوران دنیا',
          author: '',
          price: '87000',
          description: '',
          imgUrl: '7.jpg'
        },
        {
          id: 8,
          title: 'ایلیا',
          author: '',
          price: '65000',
          description: '',
          imgUrl: '8.jpg'
        },
      ]
    }
  }
}
</script>
