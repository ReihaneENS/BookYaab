<template>
  <div class="footer-wrapper w-full">
    <div class="inner w-full p-12 px-14 flex justify-between items-start">
      <div class="partition w-1/3">
        <ul class="text-white">
          <li class="mb-6 flex items-center">
            <img class="w-20" :src="require(`~/assets/images/logo2.png`)" alt="logo">
            <p class="text-xl font-bold text-white">درباره بوک یاب</p>
          </li>
          <li class="mb-3">
            <p>لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است چاپگرها و
              متون بلکه روزنامه و مجله در ستون و سطرآنچنان که لازم است و برای شرایط فعلی تکنولوژی مورد نیاز و کاربردهای
              متنوع با هدف بهبود ابزارهای کاربردی می باشد کتابهای زیادی در شصت و سه درصد گذشته حال و آینده شناخت فراوان
              جامعه و متخصصان را می طلبد تا با نرم افزارها شناخت بیشتری را برای طراحان رایانه ای علی الخصوص طراحان خلاقی
              است.</p>
          </li>
        </ul>
      </div>
      <div class="partition">
        <ul class="text-white">
          <li class="mb-6">
            <p class="text-xl font-bold text-white">راهنمای خرید</p>
          </li>
          <li class="mb-3" v-for="item in shoppingGuide" :key="item.id">
            <nuxt-link :to="item.url">{{ item.title }}</nuxt-link>
          </li>
        </ul>
      </div>
      <div class="partition">
        <ul class="text-white">
          <li class="mb-6">
            <p class="text-xl font-bold text-white">دسترسی سریع</p>
          </li>
          <li class="mb-3" v-for="item in quickAccess" :key="item.id">
            <nuxt-link :to="item.url">{{ item.title }}</nuxt-link>
          </li>
        </ul>
      </div>
      <div class="partition">
        <ul class="text-white">
          <li class="mb-6">
            <p class="text-xl font-bold text-white">راهنمای تماس با بوک یاب</p>
          </li>
          <li class="flex mb-4 items-center">
            <img class="w-5 ml-2" :src="require(`~/assets/images/icons/location.png`)" alt="location">
            <p>تهران - میدان ولیعصر - ساختمان 26 - واحد 6</p>
          </li>
          <li class="flex items-center">
            <img class="w-5 ml-2" :src="require(`~/assets/images/icons/phone.png`)" alt="location">
            <a href="+tel:02152632210">021-52632210</a>
          </li>
          <li class="mt-4 w-100 flex justify-center items-center flex-col">
            <p class="mb-3">نماد اعتماد الکترونیکی</p>
            <img class="w-32 ml-2 bg-white" :src="require(`~/assets/images/home/enamad.png`)" alt="location">
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      shoppingGuide: [
        {
          id: 1,
          title: ' سیاست حفظ حریم خصوصی',
          url: '/',
        },
        {
          id: 2,
          title: ' شرایط و قوانین',
          url: '/',
        },
        {
          id: 3,
          title: ' شرایط مرجوعی کالا',
          url: '/',
        },
        {
          id: 4,
          title: ' رویه ارسال کالا در بوک یاب',
          url: '/',
        },
        {
          id: 5,
          title: ' راهنمای خرید در سایت بوک یاب',
          url: '/',
        },
        {
          id: 6,
          title: ' راهنمای پرداخت',
          url: '/',
        },
      ],
      quickAccess: [
        {
          id: 1,
          title: ' وبلاگ',
          url: '/',
        },
        {
          id: 2,
          title: 'درباره ما',
          url: '/',
        },
        {
          id: 3,
          title: 'تماس با ما',
          url: '/',
        },
        {
          id: 4,
          title: 'چرا بوک یاب ؟',
          url: '/',
        },
        {
          id: 5,
          title: 'پیگیری سفارش',
          url: '/',
        },
        {
          id: 6,
          title: 'راهنمای رهگیری مرسولات',
          url: '/',
        },
        {
          id: 7,
          title: ' فرصت های شغلی ',
          url: '/',
        },
      ],
    }
  }
}
</script>

