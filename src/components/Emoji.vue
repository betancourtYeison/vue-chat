<template>
    <button @click="handleClickCharacter">{{character}}</button>
</template>

<script>
export default {
    props: ["character"],
    methods: {
        handleClickCharacter() {
            this.$emit("handleClickCharacter", this.character);
        }
    }
};
</script>