<script setup>
// import StartQuiz from './components/StartQuiz.vue'
// import GuideQuiz from './components/GuideQuiz.vue'
// import Stepper from './components/Stepper.vue'
// import Quiz from './components/Quiz.vue'
// import Result from './components/Result.vue'
import {ref, computed} from 'vue';

const questions = ref([
    {
        question: 'Why is AWS more economical than traditional data centers for applications with varying compute workloads ?',
        answer:2,
        options:[
            'Amazon EC2 costs are billed on a monthly basis',
            'Users retain full administrative access to their Amazon EC2 instances',
            'Amazon EC2 instances can be launched on demand when needed',
            'Users can permanently run enough instances to handle peak workloads'
        ],
        selected: null
    },
    {
        question: 'Which AWS service would simplify the migration of a database to AWS ?',
        answer:1,
        options:[
            'AWS Storage Gateway',
            'AWS Database Migration Service (AWS DMS)',
            'Amazon EC2',
            'Amazon AppStream 2.0'
        ],
        selected: null
    },
    {
        question: 'Which AWS offering enables users to find, buy, and immediately start using software solutions in their AWS environment ?',
        answer:3,
        options:[
            'AWS Config',
            'AWS OpsWorks',
            'AWS SDK',
            'AWS Marketplace'
        ],
        selected: null
    },
    {
        question: 'Which AWS networking service enables a company to create a virtual network within AWS ?',
        answer:3,
        options:[
            'AWS Config',
            'Amazon Route 53',
            'AWS Direct Connect',
            'Amazon Virtual Private Cloud (Amazon VPC)'
        ],
        selected: null
    },
    {
        question: 'Which of the following is an AWS responsibility under the AWS shared responsibility model ?',
        answer:1,
        options:[
            'Configuring third-party applications',
            'Maintaining physical hardware',
            'Securing application access and data',
            'Managing guest operating systems'
        ],
        selected: null
    },
    {
        question: ') Which component of the AWS global infrastructure does Amazon CloudFront use to ensure low-latency delivery ?',
        answer:1,
        options:[
            'AWS Regions',
            'Edge locations',
            'Availability Zones',
            'Virtual Private Cloud (VPC)'
        ],
        selected: null
    },
    {
        question: 'How would a system administrator add an additional layer of login security to a user\'s AWS Management Console ?',
        answer:2,
        options:[
            'Use Amazon Cloud Directory',
            'Audit AWS Identity and Access Management (IAM) roles',
            'Enable multi-factor authentication',
            'Enable AWS CloudTrail'
        ],
        selected: null
    },
    {
        question: 'Which service can identify the user that made the API call when an Amazon EC2 instance is terminated ?',
        answer:1,
        options:[
            'AWS Trusted Advisor',
            'AWS CloudTrail',
            'AWS X-Ray',
            'AWS Identity and Access Management (AWS IAM)'
        ],
        selected: null
    },
    {
        question: 'Which service would be used to send alerts based on Amazon CloudWatch alarms ?',
        answer:0,
        options:[
            'Amazon Simple Notification Service (Amazon SNS)',
            'AWS CloudTrail',
            'AWS Trusted Advisor',
            'Amazon Route 53'
        ],
        selected: null
    },
    {
        question: ' Where can a user find information about prohibited actions on the AWS infrastructure ?',
        answer:3,
        options:[
            'AWS Trusted Advisor',
            'AWS Identity and Access Management (IAM)',
            'AWS Billing Console',
            'AWS Acceptable Use Policy'
        ],
        selected: null
    }

])

const quizCompleted = ref(false)

const currentQuestion = ref(0)

const score = computed(()=>{
    let value = 0;
    questions.value.map(q=>{
        if (q.selected == q.answer) {
            value++;
        }
    });
    return value;
})
const getCurrentQuestion = computed(()=>{
    let question = questions.value[currentQuestion.value]
    question.index = currentQuestion.value
    return question
})

const setAnswer = e =>{
    questions.value[currentQuestion.value].selected = e.target.value;
    evt.target.value = null;
}

const nextQuestion = ()=>{
    if (currentQuestion.value < questions.value.length-1) {
        currentQuestion.value++;
    }else{
        quizCompleted.value = true;
    }
}
</script>
<template>

    <!-- <StartQuiz/> -->
    <!-- <GuideQuiz/> -->
    <!-- <Stepper/> -->
    <!-- <Quiz/> -->
    <!-- <Result/> -->
    <main class="app">
        <div class="application" id="quiz-app">
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
                <p id="question" class="question-titre">{{getCurrentQuestion.question}}</p>
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
    </main>
</template>
<style scoped>
    .application{
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

