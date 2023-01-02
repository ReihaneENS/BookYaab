<template>
  <div class="header-wrapper fixed w-full bg-white">
    <div class="inner-content relative flex justify-start flex-wrap items-center w-11/12 py-4">
      <div class="logo-wrapper mx-3">
        <nuxt-link to="/">
          <img :src="require(`@/assets/images/logo2.png`)" alt="logo" class="h-20">
        </nuxt-link>
      </div>
      <div class="header-menu mx-3">
        <ul class="flex flex-row justify-start items-center">
          <li v-for="item in headerMenu" :key="item.id" class="mx-3.5 cursor-pointer"
              @click="id=item.id" :class="{'active' : id===item.id}">
            <div class="inner-content flex items-center">
              <nuxt-link class="ml-2" v-if="item.isLinked===true" :to="item.url">{{ item.title }}</nuxt-link>
              <p v-else class=" ml-2">{{ item.title }}</p>
              <i class="fa-solid fa-chevron-down" v-if="item.dropDown===true"></i>
            </div>
            <div class="drop-down rounded-b px-8 py-4 w-full right-0 absolute bg-white text-right"
                 v-if="item.dropDown===true && id===item.id" @mouseleave="id=null">
              <div v-if="id===2" class="inner-content w-11/12 flex justify-between items-center">
                <ul class="w-6/12 menu-items flex flex-col flex-wrap">
                  <li v-for="item in authors" :key="item.id" @mouseover="authorId=item.authorId"
                      @mouseleave="authorId=null" class="h-9 flex items-center duration-300">
                    <nuxt-link class="h-full w-full flex items-center" :to="item.url">{{ item.name }}
                    </nuxt-link>
                  </li>
                </ul>
                <ul class="w-6/12">
                  <li v-for="item in authors" :key="item.id" v-show="authorId===item.authorId" class="flex items-center justify-between">
                    <img class="h-60 border-2 border-rose-800 w-3/6 mx-1"
                         :src="require(`@/assets/images/authors/${item.img}`)" alt="">
                    <img class="h-60 border-2 border-rose-800 w-3/6 mx-1"
                         :src="require(`@/assets/images/authors/${item.img}`)" alt="">
                  </li>
                </ul>
              </div>
              <div v-if="id===1" class="inner-content w-11/12 flex justify-between items-center">
                <ul class="w-6/12 menu-items">
                  <li v-for="item in categories" :key="item.id" @mouseover="categoryId=item.id"
                      @mouseleave="categoryId=null" class="h-9 flex items-center duration-300">
                    <nuxt-link class="h-full w-full flex items-center" :to="item.url">{{ item.title }}
                    </nuxt-link>
                  </li>
                </ul>
                <ul class="w-6/12">
                  <li v-for="item in categories" :key="item.id" v-show="categoryId===item.id" class="flex items-center justify-between">
                    <img class="h-60 border-2 border-rose-800 w-3/6 mx-1"
                         :src="require(`@/assets/images/categories/${item.img}`)" alt="">
                    <img class="h-60 border-2 border-rose-800 w-3/6 mx-1"
                         :src="require(`@/assets/images/categories/${item.img}`)" alt="">
                  </li>
                </ul>
              </div>
            </div>
          </li>
        </ul>
      </div>
      <div class="search-box mx-3">
        <div class="inner-content w-full">
          <form class="w-full py-2">
            <button type="submit" class="w-1/6">
              <i class="fa fa-search"></i>
            </button>
            <input class="w-4/5 focus:outline-none" type="text" placeholder="جستجو بر اساس نام کتاب، نویسنده، شابک">
          </form>
        </div>
      </div>
      <div class="account-info mx-3 flex justify-evenly items-center">
        <div class="cart">
          <nuxt-link to="/">
            <img :src="require(`@/assets/images/icons/shopping-cart.png`)" alt="cart">
          </nuxt-link>
        </div>
        <div class="account relative border-2 rounded-3xl py-1 px-4 text-white duration-300">
          <div class="reg-login">
            <nuxt-link to="/">
              ورود / ثبت نام
            </nuxt-link>
          </div>
          <div class="user-account hidden cursor-pointer flex justify-center items-center" @click="toggleDropDown">
            <i class="fa fa-user"></i>
            <p class="px-2">حساب کاربری</p>
            <i class="fa fa-chevron-down"></i>
          </div>
          <div v-if="dropDownOpened===true" @mouseleave="dropDownOpened=false"
               class="profile-drop-down rounded-b min-w-max absolute top-10 text-center left-0 bg-white text-black">
            <ul class="px-4">
              <li v-for="item in profile" :key="item.id" class="my-2 w-full">
                <nuxt-link class="w-full duration-300" :to="item.url">{{ item.title }}</nuxt-link>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      id: null,
      authorId: null,
      categoryId: null,
      dropDownOpened: false,
      headerMenu: [
        {
          title: 'دسته بندی',
          url: '/',
          dropDown: true,
          isLinked: false,
          id: 1,
        },
        {
          title: 'نویسندگان',
          url: '/',
          dropDown: true,
          isLinked: false,
          id: 2,
        },
        {
          title: 'کتاب ها',
          url: '/',
          dropDown: false,
          isLinked: true,
          id: 3,
        }
      ],
      authors: [
        {
          name: 'پائلو کوئیلو',
          authorId: 1,
          url: '/',
          img: 'first.jpg'
        },
        {
          name: 'ویکتور هوگو',
          authorId: 2,
          url: '/',
          img: 'second.jpg'
        },
        {
          name: 'جلال آل احمد',
          authorId: 3,
          url: '/',
          img: 'third.jpg'
        },
        {
          name: 'جان اشتاین بک',
          authorId: 4,
          url: '/',
          img: 'fourth.jpg'
        },
        {
          name: 'جوجو مویز',
          authorId: 5,
          url: '/',
          img: 'fifth.jpg'
        },
        {
          name: 'جی کی رولینگ',
          authorId: 6,
          url: '/',
          img: 'sixth.jpg'
        },
        {
          name: 'پائلو کوئیلو',
          authorId: 7,
          url: '/',
          img: 'first.jpg'
        },
        {
          name: 'ویکتور هوگو',
          authorId: 8,
          url: '/',
          img: 'second.jpg'
        },
        {
          name: 'جلال آل احمد',
          authorId: 9,
          url: '/',
          img: 'third.jpg'
        },
        {
          name: 'جان اشتاین بک',
          authorId: 10,
          url: '/',
          img: 'fourth.jpg'
        },
        {
          name: 'جوجو مویز',
          authorId: 11,
          url: '/',
          img: 'fifth.jpg'
        },
        {
          name: 'جی کی رولینگ',
          authorId: 12,
          url: '/',
          img: 'sixth.jpg'
        }
      ],
      categories: [
        {
          title: 'فلسفه',
          id: 1,
          url: '/',
          img: '1.png',
        },
        {
          title: 'عاشقانه',
          id: 2,
          url: '/',
          img: '2.png',
        },
        {
          title: 'رمان ایرانی',
          id: 3,
          url: '/',
          img: '3.png',
        },
        {
          title: 'رمان خارجی',
          id: 4,
          url: '/',
          img: '4.png',
        },
        {
          title: 'ترسناک',
          id: 5,
          url: '/',
          img: '5.png',
        },
        {
          title: 'روانشناسی',
          id: 6,
          url: '/',
          img: '6.png',
        },
        {
          title: 'کودکان',
          id: 7,
          url: '/',
          img: '7.png',
        },
      ],
      profile: [
        {
          title: 'ریحانه ابراهیمی نسب',
          id: 1,
          url: '/',
        },
        {
          title: 'ویرایش حساب کاربری',
          id: 2,
          url: '/',
        },
        {
          title: 'سبد خرید',
          id: 3,
          url: '/',
        },
        {
          title: 'خروج',
          id: 4,
          url: '/',
        },
      ]
    }
  },
  methods: {
    toggleDropDown() {
      this.dropDownOpened = !this.dropDownOpened;
    }
  }
}
</script>

