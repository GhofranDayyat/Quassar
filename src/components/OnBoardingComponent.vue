<template>
  <div class="d-flex flex-column">
    <header-component></header-component>
    <login-component v-if="isLoginComponentOpen"></login-component>
    <q-page-container v-else>
      <q-page class="flex flex-center">
        <div class="column">
          <div class="row" style="margin: 10px 30px">
            <img
              :src="
                contentImageList[currentIndex] &&
                contentImageList[currentIndex].imageWallpaper
              "
              spinner-color="white"
              fit="contain"
              style="width: 341px; height: 300px; margin: 10px 0 0 0"
            />
          </div>
          <div
            class="row"
            style="margin: 30px; margin-bottom: 0 display: flex; flex-direction: row-reverse"
          >
            <h3 style="margin: 10px 0">
              {{
                contentImageList[currentIndex] &&
                contentImageList[currentIndex].title
              }}
            </h3>
            <p style="font-size: 17px; direction: rtl">
              {{
                contentImageList[currentIndex] &&
                contentImageList[currentIndex].description
              }}
            </p>
            <img
              :src="
                contentImageList[currentIndex] &&
                contentImageList[currentIndex].imageStepper
              "
              spinner-color="white"
              fit="contain"
              style="width: 90px; height: 10px; margin: 0"
            />
          </div>
          <div class="d-flex j-between item-center">
            <img
              @click="onNextClick"
              :src="arrow"
              spinner-color="white"
              fit="contain"
              height="270px"
            />
            <q-btn
              class="gray-btn"
              flat
              no-wrap
              label="تخطي"
              padding="10px 20px"
              @click="onPassClick"
            />
          </div>
        </div>
      </q-page>
    </q-page-container>
  </div>
</template>

<style scoped>
.gray-btn {
  background-color: #edeff1;
  color: #333333;
  font-size: 18px;
  height: 50px;
  margin-top: 70px;
  margin: 0 30px;
  border-radius: 20%;
}

.d-flex-between {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>

<script lang="ts">

import LoginComponent from './LoginComponent.vue';
import onBoardOne from '../assets/onBoardOne.png';
import onBoardTwo from '../assets/onBoardTwo.png';
import onBoardThree from '../assets/onBoardThree.png';
import stepperOne from '../assets/stepperOne.png';
import stepperTwo from '../assets/stepperTwo.png';
import stepperThree from '../assets/stepperThree.png';
import arrow from '../assets/arrow.png';
import HeaderComponent from './HeaderComponent.vue';

export default {
  name: 'OnBoardingComponent',
  components: { LoginComponent , HeaderComponent},
  data() {
    return {
      arrow,
      isLoginComponentOpen: false ,
      currentIndex  : 0 ,
    };
  },
  methods: {
    onNextClick(): void {
      this.currentIndex  = this.currentIndex + 1;
      if (this.currentIndex > 2 || !this.currentIndex) {
        this.isLoginComponentOpen = true;
      }
    },
    onPassClick(): void {
      this.isLoginComponentOpen = true;
    },
  },
  computed: {
  
    contentImageList(): {
      title: string;
      imageWallpaper: string;
      imageStepper: string;
      description: string;
    }[] {
      return [
        {
          title: 'سهولة الوصول',
          imageWallpaper: onBoardOne,
          imageStepper: stepperOne,
          description:
            'احصـل على جمـيع معـلوماتك الشخصية بسـهولة مـن مكـان واحـد',
        },
        {
          title: 'ادارة الطلبات',
          imageWallpaper: onBoardTwo,
          imageStepper: stepperTwo,
          description:
            'أدر مهامك وطلبـاتك وتتبعها بضمـان تجربـة خاليـة مـن التوتـر .',
        },
        {
          title: 'تنبيهات فورية',
          imageWallpaper: onBoardThree,
          imageStepper: stepperThree,
          description:
            'كن دائما على اطلاع! استلم تحديثات فورية حول طلباتك والقرارت الخاصة بـك',
        },
      ];
    },
  },
};
</script>
