<template>
    <div class="product-page" id="borderNone">
        <productCard />
        <div class="widthClass">
            <p @click="specificationsOnDisplay">Характеристики:</p>
            <h4 v-if="specificationsClick">{{ specifications }}</h4>
            <p @click="reviewsOnDisplay">Отзывы:</p>
            <reviewProduct v-if="reviewsClick" />
            <reviewButton v-if="isAutorisatoin && reviewsClick"/>
            <p v-else-if="!isAutorisatoin && reviewsClick" class="blueText">Чтобы оставить отзыв войдите или зарегистрируйтесь</p>
        </div>
        <div class="leftClass">
            <p>Сопутствующие товары:</p>
        <h4>{{ relateds }}</h4>
        </div>
    </div>
</template>

<script>
import reviewProduct from "./review-product.vue";
import productCard from "./product-card.vue";
import reviewButton from "./review-button.vue";
export default {
    name: "product-page",
    components: {
        productCard,
        reviewProduct,
        reviewButton
    },
    props: {},
    data() {
        return {
            specificationsClick: false,
            reviewsClick: false,
            relateds: "Извините, сопутствующих товаров не найдено :(",
            rewiews: "какие-то отзывы",
            specifications: "Цвет......................................Белый Емкость аккумулятора......160mWh Bluetooth...............................5 Модель.................................AirPods Pro Страна..................................Китай",
            title: "Смартфоны",
            class1: "blockClass1",
            title2: "Аудиотехника",
            title3: "Аксессуары",
            isAutorisatoin: false
        };
    },
    computed: {},
    methods: {
        specificationsOnDisplay() {
            this.specificationsClick = !this.specificationsClick;
            this.reviewsClick = false;
        },
        reviewsOnDisplay() {
            this.reviewsClick = !this.reviewsClick;
            this.specificationsClick = false;
        },
    },
};
</script>

<style scoped>
.productPage {
    border-width: 1px;
    border-color: rgba(0, 0, 0, 0.1);
    border-style: none none none none;
}
p {
    color: #ed1c24;
    text-decoration-line: underline;
    left: 0px;
}
h4 {
    color: rgba(0, 0, 0, 0.744);
}
.widthClass {
    width: 40%;
}
.leftClass{
    
    left: 5%;
}
.blueText{
    text-decoration-line: underline;
    color: #00a2e8;

}
.imageClass{
    width: 5%;
    height: 5%;
    margin: 5px 3px;
}
</style>