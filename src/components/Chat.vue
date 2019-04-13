<template>
    <div class="main">
        <div>Chat</div>
        <div class="emojis section">
            <emoji
                :character="item.character"
                @handleClickCharacter="handleClickCharacter"
                v-for="(item, index) in emojis"
                :key="index"
                :style="'grid-row: ' + item.row + '; grid-column: ' + item.column + ';'"
            />
        </div>
        <div class="section">
            <input ref="inputMessage" v-model="message" @keyup.enter="sendMessage" type="text">
        </div>
        <list v-if="listMessages.length > 0">
            <div v-for="(listMessage, index) in listMessages" :key="index" slot="messages">
                <span>{{listMessage}}</span>
            </div>
        </list>
    </div>
</template>

<script>
import Emoji from "./Emoji.vue";
import List from "./List.vue";
export default {
    components: { Emoji, List },
    data() {
        return {
            message: "",
            listMessages: [],
            emojis: [
                { character: "😃", row: 1, column: 1 },
                { character: "😄", row: 1, column: 2 },
                { character: "😅", row: 1, column: 3 },
                { character: "😆", row: 1, column: 4 },
                { character: "😉", row: 1, column: 5 },
                { character: "😊", row: 2, column: 1 },
                { character: "😋", row: 2, column: 2 },
                { character: "😢", row: 2, column: 3 },
                { character: "😍", row: 2, column: 4 },
                { character: "😳", row: 2, column: 5 },
                { character: "😱", row: 3, column: 1 },
                { character: "😤", row: 3, column: 2 },
                { character: "😲", row: 3, column: 3 },
                { character: "🙁", row: 3, column: 4 },
                { character: "😔", row: 3, column: 5 },
                { character: "🎉", row: 4, column: 1 },
                { character: "🎁", row: 4, column: 2 },
                { character: "🎈", row: 4, column: 3 },
                { character: "❤️", row: 4, column: 4 },
                { character: "👍", row: 4, column: 5 }
            ]
        };
    },
    methods: {
        handleClickCharacter(character) {
            this.message += character;
            this.$refs.inputMessage.focus();
        },
        sendMessage(event) {
            if (event.target.value.length > 0) {
                this.listMessages.unshift(event.target.value);
                this.message = "";
            }
        }
    },
    mounted() {
        this.$refs.inputMessage.focus();
    }
};
</script>

<style>
button {
    width: 60px;
    height: 60px;
    cursor: pointer;
    background-color: #ececec;
    font-size: 30px;
    border-style: solid;
    border-width: 3px;
    border-color: #0058be;
    border-radius: 5px;
}

.emojis {
    display: grid;
    grid-template-rows: repeat(auto, 4);
    grid-template-columns: repeat(auto, 5);
    grid-gap: 10px;
    justify-content: center;
}
</style>
