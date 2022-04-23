# Swiper
## 匯入
### 模組
```jsx
// 主要匯入的元件
import { Swiper, SwiperSlide } from 'swiper/react';
// 其他模組（<Swiper> 的 props）
import { Navigation, Pagination, Scrollbar, A11y } from 'swiper';
```
### 樣式
```jsx
// Import Swiper styles
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import 'swiper/css/scrollbar';
```
## 初始設定（預設）
JS 的話：
```js
// 第一個是預計放入 Swiper 的容器（這裡是用一個 html class 裝）
const swiper = new Swiper('.swiper', {
	// 第二個放入這個 Swiper 的自訂 Parameters
  speed: 400,
  spaceBetween: 100,
});
```
>請參照 [[Swiper Parameters]]
```js
const swiper = document.querySelector('.swiper').swiper;

// 建立 swiper 實例後就可以. 各種 Method, property 來使用
swiper.slideNext();
```
>請參照[Methods & Properties](https://swiperjs.com/swiper-api#methods-and-properties)

## React 預設
Swiper 元件不要放到 container 中，會跑版
```jsx
export default () => {
  return (
    <Swiper
      // install Swiper modules
      modules={[Navigation, Pagination, Scrollbar, A11y]}
			// 預設必兩個參數
      spaceBetween={50}
      slidesPerView={3}
      navigation
      pagination={{ clickable: true }}
      scrollbar={{ draggable: true }}
      onSwiper={(swiper) => console.log(swiper)}
      onSlideChange={() => console.log('slide change')}
    >
      <SwiperSlide>Slide 1</SwiperSlide>
      <SwiperSlide>Slide 2</SwiperSlide>
      <SwiperSlide>Slide 3</SwiperSlide>
      <SwiperSlide>Slide 4</SwiperSlide>
      ...
    </Swiper>
  );
};
```

#js/react #api #swiper 