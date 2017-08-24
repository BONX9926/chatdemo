<template>
    <div class="chat-composer">
        <input type="text" placeholder="พิมพ์ข้อความ..." v-model="messageText" v-on:keydown.enter="sendMessage">
        <button class="btn btn-primary" @click="sendMessage">ส่ง</button>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                messageText: ''
            }
        },
        methods: {
            sendMessage () {
                this.$emit('messagesent', {
                    message: this.messageText,
                    user: "Atiwat Tumsakka"
                });
                console.log(this.messageText);
                this.messageText = '';
            }
        }
    }
</script>

<style scoped>
.chat-composer {
    display: flex;
}

.chat-composer input {
    flex: 1 auto;
}

.chat-composer button {
    border-radius: 0;
}
</style>