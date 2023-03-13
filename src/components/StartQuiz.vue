<template>
    
    <div class="start">
        <p class="start-title">Do you have a solid knowledge</p>
        <p class="start-title">of AWS practitioner ?</p>
    </div>
    <div class="intro">
        <p class="intro-text">Test your expertise in AWS practitioner with our quiz in just 10 questions </p>
        <p class="intro-text">and further improve your knowledge</p>
    </div>
    <button class="start-btn">Let's Start</button>
    
</template>

<style scoped>
    .start{
        margin-top: 100px;
    }
    .start-title{
        color: white;
        font-family: 'Righteous', cursive;
        font-size: 80px;
        font-weight: bold;
        text-align: center;
        margin-top: 40px;
    }
    .intro{
        margin-top: 50px;
    }
    .intro-text{
        color: white;
        font-family: 'Poppins', sans-serif;
        font-size: 30px;
        text-align: center;
        margin-top: 40px;
    }
    .start-btn{
        color: white;
        background-color: rgb(61, 131, 97);
        font-size: 22px;
        font-family: 'Poppins', sans-serif;
        font-weight: 700;
        text-align: center;
        margin: 60px auto;
        padding: 20px 60px;
        display: flex;
        justify-content: center;
        cursor: pointer;
        border-radius: 20px;
        border: none;
    }
    .start-btn:hover{
        color: rgb(61, 131, 97);
        background-color: white;
        font-size: 24px;
        padding: 24px 64px;
    }
</style>