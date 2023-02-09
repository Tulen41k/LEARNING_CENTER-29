<template>
    <div class="review-product">
        <div>
            <div v-for="review in reviews" :key="review.id">
                <p class="loginClass">{{ review.login }}</p>
                <p class="ratingClass">{{ review.ratingReview }}/5</p>
                <img
                    :src="review.imageReview"
                    class="imageClass"
                    v-if="review.imageReview"
                />
                <p class="textClass">{{ review.textReview }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "review-product",
    components: {},
    props: {},
    data() {
        return {
            reviews: [
                {
                    login: "Имя пользователя",
                    textReview:
                        "текст отзыва вот такой вот текст отзыва, отзыва текст, какой большой текст, да",
                    imageReview: null,
                    ratingReview: "5",
                },
                {
                    login: "Имя пользователя",
                    textReview:
                        "текст отзыва, текст, да",
                    imageReview: null,
                    ratingReview: "5",
                },
                {
                    login: "Имя пользователя",
                    textReview: "текст отзыва",
                    imageReview: null,
                    ratingReview: "5",
                },
                {
                    login: "Имя пользователя",
                    textReview:
                        "текст отзыва вот такой вот текст отзыва, отзыва текст, текст, текст, текст, текст, текст, текст, текст, текст, текст, текст!",
                    imageReview: null,
                    ratingReview: "5",
                },
            ],
        };
    },
    computed: {},
};
</script>

<style scoped>
.loginClass {
    color: #00a2e8;
}
.ratingClass {
    color: #000000;
}
.imageClass {
    width: 12%;
    height: 12%;
    max-height: 100px;
    max-width: 120px;
    margin: 5px 3px;
}
.textClass {
    color: rgba(0, 0, 0, 0.62);
}
</style>