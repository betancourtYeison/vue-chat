<template>
    <chat id="app"/>
</template>

<script>
import Chat from "@/components/Chat.vue";
export default {
    components: { Chat }
};
</script>

<style>
html {
    font-size: 62.5% !important; /* 10px / 16px = 0.625 */
}
a {
    text-decoration: none;
    color: #0058be;
}
button:focus {
    outline: 0;
}
input[type="text"] {
    border-radius: 5px;
    font-size: 2.4rem;
    width: 95%;
    line-height: 4rem;
    padding: 3px;
}
.main {
    background-color: #0045cb;
    padding: 10px;
    color: white;
    border-radius: 5px;
    width: 400px;
    font-size: 3rem;
    text-align: center;
}
.section {
    font-size: 2.4rem;
    color: #202020;
    background-color: #e9e9e9;
    border-radius: 5px;
    margin: 10px;
    padding: 10px;
}
.attribute {
    margin: 10px;
}
</style>
