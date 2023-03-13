<template>
    <div class="informations">
        <p class="guide">Quiz guide</p>
        <p class="rule">1. the quiz has 10 questions about AWS practitioner</p>
        <p class="rule">2. You cannot go to the next question without having answered the present question</p>
        <p class="rule">3. You will get points based on your correct answers</p>
        <p class="rule">4. You cannot quit the quiz while playing</p>
        <p class="rule">5. Once you complete the quiz, you will find an explanation of the incorrect questions</p>
        <div class="btns">
            <button class="guide-btn" id="continue-btn">Continue</button>
            <button class="guide-btn" id="exit-btn">Exit</button>
        </div>
        
    </div>
</template>

<style scoped>
    .informations{
        background-color: #474747;
        width: 50%;
        margin: 250px auto;
        padding: 20px;
        border-radius: 15px;
        box-shadow: rgba(243, 243, 243, 0.839) 0px 13px 27px -5px, rgba(242, 239, 239, 0.862) 0px 8px 16px -8px;
    }
    .guide{
        color: rgb(113, 184, 149);
        font-family: 'Pacifico', cursive;
        font-size: 30px;
        font-weight: bold;
        margin-bottom: 22px;
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