<template>
    <main>
        <section class="albums h-100 container d-flex align-items-center ">
            <div v-if="discs.length === 10" class="discs-list row gy-3 gx-2">
                <div class="column p-4 " v-for="(disc, i) in filteredDiscs" :key="i">
                    <DiscCard :image="disc.poster" :title="disc.title" :author="disc.author" :year="disc.year" />
                </div>
            </div>
            <div v-else class="charging">
                <h3>Loading...</h3>
                <div class="fa-3x fa-spin ">
                    <font-awesome-icon icon="fa-solid fa-compact-disc" />
                </div>
            </div>
        </section>
    </main>
</template>

<script>
import axios from 'axios';
import DiscCard from './DiscCard.vue';
export default {
    name: "TheMain",
    components: { DiscCard },
    data() {
        return {
            discs: [],
            genera: [],
        };
    },
    props: {
        selectedGenre: String,
    },
    computed: {
        filteredDiscs() {
            if (!this.selectedGenre) return this.discs;
            return this.discs.filter((disc) => disc.genre === this.selectedGenre
            )
        }
    },
    methods: {
        getAlbums() {
            axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((res) => {
                this.discs = res.data.response;

                for (let disc of this.discs) {
                    if (!this.genera.includes(disc.genre)) {
                        this.genera.push(disc.genre)
                    }
                }
                this.$emit('generi', this.genera)
            });
        }
    },
    mounted() {
        this.getAlbums();
    },
}
</script>

<style lang="scss">
@import'../assets/scss/vars';


main {
    color: #fff;
    background-color: $main_bg;
    height: 93vh;

    .column {
        width: calc(100% / 5 - 40px);
        margin: 10px 20px;
        background-color: $secondary_bg;
    }

    .charging {
        width: 100%;
        text-align: center;
        position: relative;

        div {
            width: 50px;
            position: absolute;
            left: 47%;

        }

    }

}
</style>
                


