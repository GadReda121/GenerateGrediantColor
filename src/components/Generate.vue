<template>
    <div class="generate">
        <div class="box">
            <p @copy="copyToClipboard">{{ mainColor }}</p>
        </div>
        <button type="button" @click="generateColor">Generate</button>
    </div>
</template>

<script>
// ES6 Modules or TypeScript
import Swal from 'sweetalert2';

export default {
    name: "Generate",
    data(){
        return{
            mainColor : "#eeeeee , #bdbdbd"
        }
    },
    methods: {
        generateColor() {
            let myGen1 = Math.floor(Math.random() * 0xffffff).toString(16);
            let myGen2 = Math.floor(Math.random() * 0xffffff).toString(16);
            const box = document.querySelector(".box");
            box.style.cssText= `background:linear-gradient(to right, ${"#" + myGen1} , ${"#" + myGen2})`
            let p = document.querySelector("p");
            p.innerHTML = `${"#" + myGen1} , ${"#" + myGen2}`;
        },
        copyToClipboard() {
            const box = document.querySelector(".box");
            box.classList.add("animate__animated", "animate__shakeX");
            Swal.fire({
                title: 'Great! You Copied Colors &#128079; &#128293;',
                showClass: {
                    popup: 'animate__animated animate__fadeInDown'
                },
                hideClass: {
                    popup: 'animate__animated animate__fadeOutUp'
                }
            })
        }
    }
    }
</script>

<style scoped>
.generate{
    display:grid;
    justify-content:center;
    grid-gap:20px;
}
button{
    padding:20px 30px;
    border:none;
    outline:none;
    background-color:#000;
    border-radius:10px;
    box-shadow:0px 0px 50px rgba(0,0,0,.1);
    color:#fff;
    cursor: pointer;
}
    .box{
        height:400px;
        width:400px;
        box-shadow:0px 0px 500px rgba(0,0,0,.1);
        border-radius: 25px;
        background:linear-gradient(45deg, #eeeeee,#bdbdbd);
        position: relative;
        animation:box 3s .1s both alternate-reverse ease-in-out infinite;
    }
    @keyframes box{
        from{}
        to{transform:translateY(15px)}
    }
    .box p{
        position: absolute;
        top:-3.5%;
        left: 0%;
        background-color: #000;
        color:#fff;
        padding: 20px;
        border-radius: 25px 0px 0px 0px;
        cursor: pointer;
    }
        @media screen and (max-width:567px){
        .box{
            height:300px;
            width:300px;
        }
        .box p{
            top:-5%;
        }
    }
</style>
