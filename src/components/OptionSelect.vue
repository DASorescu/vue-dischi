<template>
    <div>
        <select class="form-select" aria-label="Default select example">
            <option>Seleziona un genere</option>
            <option v-for="(genere, index) in generi" :key="index" :value="genere">{{ genere }}</option>
        </select>
    </div>
</template>






<script>
export default {
    name: 'OptionSelect',

    props: {
        generi: Array
    }
}


</script>





<style lang="scss" scoped>
@import'../assets/scss/style.scss';
</style>

