<template>
  <div>

    <!-- Label -->
    <label for="genre">
        Seleziona un genere:
    </label>

    <!-- Select -->
    <select name="genre" 
            id="genre" 
            v-model="userSelect" 
            @change="$emit('selectedGenre', userSelect)"
    >
        <option value="all">
            Tutti
            </option>
        <option value="Rock">
            Rock
            </option>
        <option value="Pop">
            Pop
            </option>
        <option value="Jazz">
            Jazz
            </option>
        <option value="Metal">
            Metal
            </option>
    </select>
    
  </div>
</template>

<script>
export default {
    name: 'PageSelect',
    data() {
        return {
            userSelect : ''
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';

    label {
        color: #17d860;
    }
</style>