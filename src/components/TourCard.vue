<script setup>
defineProps({
  title: String,
  extitle: String,
  score: String,
  reviews: String,
  stars: Number,
  distanceToSea: String,
  distanceToAirport: String,
  location: String,
  googleMapsLink: String,
  price: String,
});
const pills = [
  { text: "Близко к центру", color: "blue" },
  { text: "Крытый бассейн", color: "orange" },
  { text: "Песчаный пляж", color: "orange" },
  { text: "Песчаный пляж", color: "orange" },
  { text: "Песчаный пляж", color: "orange" },
  { text: "Отдых с детьми", color: "violet" }
];
</script>

<template>
  <article class="tour-card">
    <section class="hotel-card">
        <div  class="rating">
            <span class="score">{{score}}</span>
            <span class="reviews">{{reviews}} отзывов</span>
        </div>
        <img src="./../image/Button.png" alt="Like" class="like-image">
    </section>
    <section class="tour-info">
        <div class="stars-and-tags">
            <div class="stars" aria-label="Рейтинг">
                <template v-for="n in stars" :key="n">
                    <img src="./../image/Star 1.svg" alt="Звезда" class="star">
                </template>
            </div>
            <section class="tags" aria-label="Дополнительная информация">
                <span class="tag">HV-1</span>
                <time datetime="2018" class="tag">2018 г</time>
            </section>
            <span class="category">реновация</span>
        </div>
        <div class="titles">
            <h3>{{ title }}</h3>
            <h4 class="ex-title">ex. {{extitle}}</h4>            
        </div>

        <div class="info-tags">
            <span class="tag-sea">{{distanceToSea}}</span>
            <span class="tag-air">{{distanceToAirport}}</span>
        </div>
        <a :href="googleMapsLink" target="_blank" rel="noopener noreferrer" class="location-widget">
            {{location}}
        </a>
        <ul class="pills">
            <li v-for="(pill, index) in pills" :key="index" :class="`pill pill--${pill.color}`">
                {{ pill.text }}
            </li>
        </ul>
        <p>с 11 ноября на 7 ночей</p>
    </section>
    <section class="payment">
        <div class="payment-metods">
            <div class="installment">
                <p class="installment-left-text">0₽ сейчас</p>
                <p class="installment-right-text">
                    <span class="big-text">В рассрочку</span>
                    <span class="small-text">120 дней на оплату</span>
                </p>
            </div>
            <div class="t-bank">
                <p class="cashback">Повышeнный кэшбэк до 11 января</p>
                <img src="./../image/Button Pay.svg" alt="Tinkoff" width="57px" height="24px">
                <p class="percent">+3%</p>
            </div>
        </div>
        <div class="price">
            <div class="old-price">
                <p>Стало дешевле <span class="crossed-out">(Вчера 516 888 ₽)</span></p>
            </div>
            <button class="new-price">
                <p class="new-price-text">Цена обновлена 12 минут назад</p>
                <p class="new-price-value">{{ price }}</p>
            </button>
        </div>
    </section>
  </article>
</template>

<style lang="scss" scoped>
@import url("./../assets/tour-card.scss");
</style>