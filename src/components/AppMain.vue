<script>
import { cards } from "../store.js";
export default{
    data(){
    return{
      cards
    }
  }
}
</script>

<template>
    <div>
        <div class="bg-orange">
            <div class="container">
                <div class="row">
                    <div class="col-12 p-3">
                        <div class="input-group ms-4">
                            <select class="custom-select text-start">
                                <option value="0">
                                    <h3 class="text-start">Alien</h3>
                                </option>
                                <option value="1">One</option>
                                <option value="2">Two</option>
                                <option value="3">Three</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
            <div class="container">
                <div class="row">
                    <div class="col-12 pad-3rem bg-white">
                        <div class="col-12 p-2 bg-black">
                            <h5>Found {{ counter }} cards</h5>
                        </div>
                    </div>
                </div>
                <div class="row row-cols-5 px-5 bg-white">
                    <div class="col" v-for="card in cards.cardsarray">
                        <div class="card">
                            <img :src="card.card_images[0].image_url" class="card-img-top">
                            <div class="card-body bg-orange">
                                <h5 class="card-title text-center">{{ card.name }}</h5>
                                <p class="card-text text-center">{{ card.archetype }}</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss';

.bg-orange{
    background-color: variables.$primary-color;
    .custom-select{
        border-radius: 5px;
        border: none;
        padding: 10px 80px 10px 5px;
    }
}

.bg-white{
    background-color: white;
}
.bg-black{
    background-color: rgb(20, 20, 20);
    h5{
        color: white;
        margin-bottom: 0px;
    }
}
.card{
    border: none;
    border-radius: 0px;
}
.pad-3rem{
    padding: 3rem 3rem 0px 3rem;
}
</style>