<script>

</script>
<template>
    
    <div class="start">
        <p class="start-title">Do you have a solid knowledge</p>
        <p class="start-title">of AWS practitioner ?</p>
    </div>
    <div class="intro">
        <p class="intro-text">Test your expertise in AWS practitioner with our quiz in just 10 questions </p>
        <p class="intro-text">and further improve your knowledge</p>
    </div>
    <div class="informations">
        <p class="guide">Quiz guide</p>
        <p class="rule">1. the quiz has 10 questions about AWS practitioner</p>
        <p class="rule">2. You cannot go to the next question without having answered the present question</p>
        <p class="rule">3. You will get points based on your correct answers</p>
        <p class="rule">4. You cannot quit the quiz while playing</p>
        <p class="rule">5. Once you complete the quiz, you will find an explanation of the incorrect questions</p>        
    </div>
    <button class="start-btn">Let's Start</button>
    
</template>

<style scoped>
    .start{
        margin-top: 10px;
    }
    .start-title{
        color: white;
        font-family: 'Righteous', cursive;
        font-size: 75px;
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
        font-size: 25px;
        text-align: center;
        margin-top: 30px;
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
    .informations{
        background-color: #474747;
        width: 50%;
        margin: 50px auto;
        padding: 20px;
        border-radius: 15px;
        box-shadow: rgba(243, 243, 243, 0.839) 0px 13px 27px -5px, rgba(242, 239, 239, 0.862) 0px 8px 16px -8px;
    }
    .guide{
        color: rgb(113, 184, 149);
        font-family: 'Pacifico', cursive;
        font-size: 30px;
        font-weight: bold;
        margin-bottom: 10px;
    }
    .rule{
        color: white;
        font-family: 'Poppins', sans-serif;
        font-size: 18px;
        margin-bottom: 15px;
        margin-left: 15px;
    }
    .btns{
        margin-top: 25px;
        display: flex;
        justify-content: end;
        margin-bottom: 10px;
    }
    .guide-btn{
        background-color: rgb(113, 184, 149);
        color:  #474747;
        font-family:'Poppins', sans-serif;
        font-weight: bolder;
        font-size: 16px;
        padding: 10px 15px;
        border-radius: 5px;
        cursor: pointer;
        border: none;
    }
    #exit-btn{
        margin-left: 10px;
    }
</style>