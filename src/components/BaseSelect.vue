<template>
    <div>
        <select id="base-select" class="form-select" v-model="optionValue" @change="$emit('set-option', optionValue)">
            <option value="" selected>Seleziona un genere</option>
            <option v-for="(genre, i) in genresList" :key="i" :value="genre">{{ genre }}</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'BaseSelect',
    props: {genresList: Array},
    data(){
        return {
            optionValue: ''
        }
    }
}
</script>

<style>
</style>