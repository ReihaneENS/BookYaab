<template>
  <div class="services-wrapper bg-white">
    <div class="inner-content w-9/12 flex justify-between item-center">
      <div class="card duration-300 px-4 py-5 mx-2 rounded w-4/12 flex items-center flex-col justify-center"
           v-for="item in services" :key="item.id">
        <div class="title text-center">
          <p class="text-lg font-semibold">{{ item.title }}</p>
        </div>
        <div class="desc text-center my-4">
          <p class="text-sm">{{ item.description }}</p>
        </div>
        <div class="icon p-4">
          <img class="w-12 h-12" :src="require(`@/assets/images/icons/${item.iconUrl}`)" alt="">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      services: [
        {
          title: 'خرید و فروش',
          id: 1,
          description: 'خرید و فروش آسان کتاب های دلخواهتان',
          iconUrl: 'sell.png',
        },
        {
          title: 'کتابخانه الکترونیک',
          id: 2,
          description: 'دانلود و مطالعه کتاب های دلخواهتان در کتابخانه الکترونیکی بوک یاب',
          iconUrl: 'e-book.png',
        },
        {
          title: 'ارسال رایگان',
          id: 3,
          description: 'ارسال رایگان خرید های بالای 250 هزارتومان',
          iconUrl: 'delivery.png',
        },
      ]
    }
  }
}
</script>

