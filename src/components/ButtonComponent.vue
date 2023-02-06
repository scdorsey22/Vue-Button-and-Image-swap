<template>
    <div class='container'>
        <button class="btn" :style="{ backgroundColor: buttonColor }" @click="toggleSubscribe" >{{ subscribeText }}</button>
        <div>
            <img :src="imageSource" />
        </div>
    </div>
</template>

<script>

export default {
    name: 'ButtonComponent',
   
    data() {
        return {
            subscribed: false,
            imageOne: false
        }
    },
        computed: {
            subscribeText() {
                return this.subscribed ? 'Unsubscribe' : 'Subscribe'
            },
            imageSource() {
                return this.imageOne ? 'https://user-images.githubusercontent.com/2340575/216665542-e18a45e5-b4e9-467f-9f37-eda4c73618d8.png' : 'https://user-images.githubusercontent.com/2340575/216665469-1fe3f8cf-e879-45b2-9067-28915194ec26.png'
            },
            buttonColor() {
                return this.subscribed ? 'red' : 'blue'
            }
        },
        methods: {
            toggleSubscribe() {
                this.subscribed = !this.subscribed
                this.imageOne = !this.imageOne
            }
    },
}
</script>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
