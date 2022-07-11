<template>
  <div>

    <select name="genres" id="genres">

        <option value="" @click="$emit('selectFilter', '')">
            Seleziona un {{ filterName }}
        </option>

        <option 
            :value="filter" 
            v-for="(filter, index) in filters"
            :key="index"
            @click="$emit('selectFilter', filter)"
        >
            {{ filter }}
        </option>
    </select>
  </div>
</template>

<script>
export default {
    name: 'Select',
    props: {
        filters: Array,
        filterName: String
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    
</style>