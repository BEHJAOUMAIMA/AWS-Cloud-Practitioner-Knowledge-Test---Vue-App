<template>
    <div class="app" id="quiz-app">
        <div class="app-heading">
            <div class="categorie">
                AWS Certified Cloud Practitioner (CLF-C01) - Sample Exam Questions
            </div>
            <div class="progress">
                <div>
                    <div class="progress-done">

                    </div>
                </div>
            </div>
        </div>
        <hr class="line">
        <div class="question">
            <p id="question" class="question-titre">Why is AWS more economical than traditional data centers for applications with varying compute workloads?</p>
        </div>
        <div id="options" class="options">
            <p class="answer" id="option1">Amazon EC2 costs are billed on a monthly basis</p>
            <p class="answer" id="option2">Users retain full administrative access to their Amazon EC2 instances</p>
            <p class="answer" id="option3">Amazon EC2 instances can be launched on demand when needed</p>
            <p class="answer" id="option4">Users can permanently run enough instances to handle peak workloads</p>
        </div>
        <div class="app-footer">
            <p id="total"> 1 of 10 questions</p>
            <button class="next-btn" id="btnNext"> Next</button>
        </div>
    </div>
</template>

<style scoped>
    .app{
        width: 1300px;
        height: 780px;
        background-color: #1b1b1b;
        color: white;
        margin: 60px auto;
        font-family: 'Poppins', sans-serif;
        padding: 25px 25px;
        box-shadow: rgba(40, 94, 68, 0.984) 0px 10px 36px 0px, rgb(40, 94, 68) 0px 0px 0px 1px;    }
    .app-heading{
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-top: 20px;
    }
    .line{
        width: 100%;
        margin-top: 45px;
        background-color: rgb(40, 94, 68);
        border: none;
        height: 1px;
    }
    .progress{
        background-color: gray;
        border-radius: 20px;
        height: 30px;
        width: 300px;
    }
    .progress-done{
        display: flex;
        align-items: center;
        background-image: repeating-linear-gradient(to left,rgb(40, 94, 68), rgb(60, 139, 101) , rgb(103, 230, 168));
        box-shadow: 0 5px 5px -6px rgb(40, 94, 68), 0 3px 7px rgb(60, 139, 101);
        border-radius: 20px;
        height: 100%;
        width: 0;
        color: #fff;
        transition: 1s ease 0.3s;
    }
    .question-titre{
        color: #fff;
        margin-top: 35px;
        margin-bottom: 60px;
        font-size: 20px;
        text-align: center;
    }
    .options{
        padding: 0 20px 20px;
        margin-top: 15px;
        height: 430px;
        width: 100%;
    }
    .answer{
        height: 68px;
        width: 100%;
        margin: 30px auto;
        border-radius: 10px;
        padding: 20px 20px;
        font-size: 15px;
        overflow: hidden;
        cursor: pointer;
        border: 1px solid gray;
        font-size: 18px;
    }
    .answer:hover{
        background-color: rgb(40, 94, 68);
    }
    .app-footer{
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin: 0 30px;
    }
    .next-btn{
        font-size: 15px;
        font-weight: bold;
        padding: 15px 36px;
        color: #fff;
        background-color: rgb(33, 64, 49);
        border: none;
        border-radius: 4px;

    }
</style>
