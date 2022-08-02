<template>
    <div>
        <select class="form-select" aria-label="Default select example" v-model="selectedOption" @change="emitChange">
            <option value="">{{ placeholder || 'Select an option' }}</option>
            <option v-for="(genere, index) in generi" :key="index" :value="genere">{{ genere }}</option>
        </select>
    </div>
</template>






<script>
export default {
    name: 'OptionSelect',
    data() {
        return { selectedOption: '' }
    },
    props: {
        placeholder: String,
        generi: Array
    },
    methods: {
        emitChange() {
            this.$emit('option-change', this.selectedOption)
        }
    }
}


</script>





<style lang="scss" scoped>
@import'../assets/scss/style.scss';
</style>

