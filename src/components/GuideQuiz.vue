<template>
    <div class="informations">
        <p class="guide">Quiz guide</p>
        <p class="rule">1. the quiz has 10 questions about AWS practitioner</p>
        <p class="rule">2. You cannot go to the next question without having answered the present question</p>
        <p class="rule">3. You will get points based on your correct answers</p>
        <p class="rule">4. You cannot quit the quiz while playing</p>
        <p class="rule">5. once you complete the quiz, you will find an explanation of the incorrect questions</p>
    </div>
</template>

<style>
    .informations{
        background-color: #474747;
        width: 50%;
        margin: 300px auto;
        padding: 20px;
        border-radius: 15px;
        box-shadow: rgba(243, 243, 243, 0.839) 0px 13px 27px -5px, rgba(242, 239, 239, 0.862) 0px 8px 16px -8px;
    }
    .guide{
        color: rgb(113, 184, 149);
        font-family: 'Pacifico', cursive;
        font-size: 22px;
        margin-bottom: 15px;
    }
    .rule{
        color: white;
        font-family: 'Poppins', sans-serif;
        font-size: 15px;
        margin-bottom: 10px;

    }
</style>