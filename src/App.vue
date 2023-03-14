<script setup>
// import StartQuiz from './components/StartQuiz.vue'
// import GuideQuiz from './components/GuideQuiz.vue'
// import Stepper from './components/Stepper.vue'
// import Quiz from './components/Quiz.vue'
// import Result from './components/Result.vue'
import {ref, computed} from 'vue';

var incorrect= [];

const questions = ref([
    {
        id : 1,
        question: 'Why is AWS more economical than traditional data centers for applications with varying compute workloads ?',
        answer:2,
        options:[
            'Amazon EC2 costs are billed on a monthly basis',
            'Users retain full administrative access to their Amazon EC2 instances',
            'Amazon EC2 instances can be launched on demand when needed',
            'Users can permanently run enough instances to handle peak workloads'
        ],
        justification:'The ability to launch instances on demand when needed allows users to launch and terminate instances in response to a varying workload. This is a more economical practice than purchasing enough on-premises servers to handle the peak load.',
        selected: null
    },
    {
        id : 2,
        question: 'Which AWS service would simplify the migration of a database to AWS ?',
        answer:1,
        options:[
            'AWS Storage Gateway',
            'AWS Database Migration Service (AWS DMS)',
            'Amazon EC2',
            'Amazon AppStream 2.0'
        ],
        justification:' AWS DMS helps users migrate databases to AWS quickly and securely. The source database remains fully operational during the migration, minimizing downtime to applications that rely on the database. AWS DMS can migrate data to and from most widely used commercial and open-source databases.',
        selected: null
    },
    {
        id : 3,
        question: 'Which AWS offering enables users to find, buy, and immediately start using software solutions in their AWS environment ?',
        answer:3,
        options:[
            'AWS Config',
            'AWS OpsWorks',
            'AWS SDK',
            'AWS Marketplace'
        ],
        justification:'AWS Marketplace is a digital catalog with thousands of software listings from independent software vendors that makes it easy to find, test, buy, and deploy software that runs on AWS.',
        selected: null
    },
    {
        id : 4,
        question: 'Which AWS networking service enables a company to create a virtual network within AWS ?',
        answer:3,
        options:[
            'AWS Config',
            'Amazon Route 53',
            'AWS Direct Connect',
            'Amazon Virtual Private Cloud (Amazon VPC)'
        ],
        justification:'Amazon VPC lets users provision a logically isolated section of the AWS Cloud where users can launch AWS resources in a virtual network that they define',
        selected: null
    },
    {
        id : 5,
        question: 'Which of the following is an AWS responsibility under the AWS shared responsibility model ?',
        answer:1,
        options:[
            'Configuring third-party applications',
            'Maintaining physical hardware',
            'Securing application access and data',
            'Managing guest operating systems'
        ],
        justification:'Maintaining physical hardware is an AWS responsibility under the AWS shared responsibility model.',
        selected: null
    },
    {
        id : 6,
        question: 'Which component of the AWS global infrastructure does Amazon CloudFront use to ensure low-latency delivery ?',
        answer:1,
        options:[
            'AWS Regions',
            'Edge locations',
            'Availability Zones',
            'Virtual Private Cloud (VPC)'
        ],
        justification:'To deliver content to users with lower latency, Amazon CloudFront uses a global network of points of presence (edge locations and regional edge caches) worldwide. ',
        selected: null
    },
    {
        id : 7,
        question: 'How would a system administrator add an additional layer of login security to a user\'s AWS Management Console ?',
        answer:2,
        options:[
            'Use Amazon Cloud Directory',
            'Audit AWS Identity and Access Management (IAM) roles',
            'Enable multi-factor authentication',
            'Enable AWS CloudTrail'
        ],
        justification:'Multi-factor authentication (MFA) is a simple best practice that adds an extra layer of protection on top of a username and password. With MFA enabled, when a user signs in to an AWS Management Console, they will be prompted for their username and password (the first factor—what they know), as well as for an authentication code from their MFA device (the second factor—what they have). Taken together, these multiple factors provide increased security for AWS account settings and resources.',
        selected: null
    },
    {
        id : 8,
        question: 'Which service can identify the user that made the API call when an Amazon EC2 instance is terminated ?',
        answer:1,
        options:[
            'AWS Trusted Advisor',
            'AWS CloudTrail',
            'AWS X-Ray',
            'AWS Identity and Access Management (AWS IAM)'
        ],
        justification:'AWS CloudTrail helps users enable governance, compliance, and operational and risk auditing of their AWS accounts. Actions taken by a user, role, or an AWS service are recorded as events in CloudTrail. Events include actions taken in the AWS Management Console, AWS Command Line Interface (CLI), and AWS SDKs and APIs.',
        selected: null
    },
    {
        id : 9,
        question: 'Which service would be used to send alerts based on Amazon CloudWatch alarms ?',
        answer:0,
        options:[
            'Amazon Simple Notification Service (Amazon SNS)',
            'AWS CloudTrail',
            'AWS Trusted Advisor',
            'Amazon Route 53'
        ],
        justification:'Amazon SNS and Amazon CloudWatch are integrated so users can collect, view, and analyze metrics for every active SNS. Once users have configured CloudWatch for Amazon SNS, they can gain better insight into the performance of their Amazon SNS topics, push notifications, and SMS deliveries.',
        selected: null
    },
    {
        id : 10,
        question: ' Where can a user find information about prohibited actions on the AWS infrastructure ?',
        answer:3,
        options:[
            'AWS Trusted Advisor',
            'AWS Identity and Access Management (IAM)',
            'AWS Billing Console',
            'AWS Acceptable Use Policy'
        ],
        justification:'The AWS Acceptable Use Policy provides information regarding prohibited actions on the AWS infrastructure.',
        selected: null
    }

])

const start = ref(false)
const myQuiz = ref(false)
const questionBlock = ref(false)
const quizCompleted = ref(false)

const currentQuestion = ref(0)

const score = computed(()=>{
    let value = 0;
    questions.value.map(q=>{
        if (q.selected == q.answer) {
            value++;
        }else if (q.answer != q.selected){
            incorrect.push(q)
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
    e.target.value = null;
}

const nextQuestion = ()=>{
    if (currentQuestion.value < questions.value.length-1) {
        currentQuestion.value++;
    }else{
        quizCompleted.value = true;
        myQuiz.value = false;
    }
}
const startQuiz =()=>{
    start.value = true;
    myQuiz.value = true;
}
const exit=()=>{
    location.reload();
}
</script>
<template>

    <main class="app">
        <section class="welcome" v-if="!start">
            <div class="start">
                <p class="start-title">Do you have a solid knowledge of</p>
                <p class="start-title">AWS practitioner ?</p>
            </div>
            <div class="intro">
                <p class="intro-text">Test your expertise in AWS practitioner with our quiz in just 10 questions and further improve your knowledge</p>
            </div>
            <div class="guide">
                <div class="informations">
                    <p class="guide">Quiz guide</p>
                    <p class="rule">1. the quiz has 10 questions about AWS practitioner</p>
                    <p class="rule">2. You cannot go to the next question without having answered the present question</p>
                    <p class="rule">3. You will get points based on your correct answers</p>
                    <p class="rule">4. You cannot quit the quiz while playing</p>
                    <p class="rule">5. Once you complete the quiz, you will find an explanation of the incorrect questions</p>
                </div>
            </div>
            <button class="start-btn" @click="startQuiz">Let's Start</button>
        </section>
        
        
        <section class="application" id="quiz-app" v-if="!quizCompleted && myQuiz">
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
                <label v-for="(option,index) in getCurrentQuestion.options" :key="index"
                    :class="`option ${
                        getCurrentQuestion.selected == index 
                        ?index == getCurrentQuestion.answer 
                        ?'correct' 
                        :'wrong' 
                        :''                 
                    }${
                        getCurrentQuestion.selected != null && index != getCurrentQuestion.selected
                        ?'disabled'
                        :''
                    }`"
                >
                    <input type="radio"
                        :name="getCurrentQuestion.index"
                        :value="index"
                        v-model="getCurrentQuestion.selected"
                        :disabled="getCurrentQuestion.selected"
                        @change="setAnswer"
                    >
                    <span>{{ option }}</span>
                </label>
            </div>
            <div class="app-footer">
                <p id="total"> 1 of 10 questions</p>
                <button @click="nextQuestion"
                    :disabled="!getCurrentQuestion.selected"
                class="next-btn" id="btnNext"> 
                    {{ 
                        getCurrentQuestion.index==questions.length -1
                        ?'Finish'
                        :getCurrentQuestion.selected==null
                            ?'Choice an answer'
                            :'Next'
                     }}
                </button>
            </div>
        </section>
        
        <section class="result" v-if="quizCompleted && !myQuiz">
            <div class="result-body">
                <p class="result-title">You have finished the quiz</p>
                <p class="result-text">Your score is : {{ score }} / {{questions.length}}</p>
                <div class="explication" v-for="(question, index) in incorrect" :key="index">
                    <div class="q">
                        <p class="q-number">{{ question.index + 1 }}. </p>
                        <p class="q-title">{{ question.question }}</p>
                    </div>
                    <div class="choices">
                        <p class="choix" id="ch1">{{ question.options[question.selected] }}</p>
                        <p class="choix" id="ch2">{{ question.options[question.answer] }}</p>
                    </div>
                    <div class="justif">
                        <p class="explic">{{ question.justification }}</p>
                    </div>
                    <hr class="line">
                </div>
                <button id="exit-btn" class="exit-btn" @click="exit">
                    Exit
                </button>
            </div>
            
        </section>
    </main>
</template>
<style scoped>
    .start{
        margin-top: 90;
    }
    .start-title{
        color: white;
        font-family: 'Righteous', cursive;
        font-size: 60px;
        font-weight: bold;
        text-align: center;
        margin-top: 40px;
    }
    .intro{
        margin-top: 30px;
    }
    .intro-text{
        color: white;
        font-family: 'Poppins', sans-serif;
        font-size: 24px;
        text-align: center;
        margin-top: 40px;
    }
    .start-btn{
        color: white;
        background-color: rgb(61, 131, 97);
        width: 40%;
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
        width: 70%;
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
        margin-bottom: 22px;
    }
    .rule{
        color: white;
        font-family: 'Poppins', sans-serif;
        font-size: 18px;
        margin-bottom: 15px;
        margin-left: 15px;
    }
    
    .application{
        width: 1300px;
        height: 780px;
        background-color: #1b1b1b;
        color: white;
        margin: 60px auto;
        font-family: 'Poppins', sans-serif;
        padding: 25px 25px;
        box-shadow: rgba(40, 94, 68, 0.984) 0px 10px 36px 0px, rgb(40, 94, 68) 0px 0px 0px 1px;    
    }
    .app-heading{
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-top: 20px;
    }
    .line{
        width: 100%;
        margin-top: 45px;
        background-color: rgb(48, 67, 58);
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
        appearance: none;
        outline: none;
        cursor: pointer;
    }
    .next-btn.disabled{
        background-color:  rgb(102, 174, 139);
        
    }
    .options{
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 0 20px 20px;
        margin-top: 15px;
        height: 430px;
        width: 100%;
    }
    .option{
        background-color: transparent;
        display: block;
        cursor: pointer;
        width: 100%;
        margin: 15px auto;
        border-radius: 10px;
        padding: 20px 20px;
        font-size: 15px;
        overflow: hidden;
        border: 1px solid gray;
        font-size: 18px;
    }
    .option:hover{
        background-color: rgb(40, 94, 68);
    }
    .option.correct{
        background-color: #2cee7d;
        color: black;
    }
    .option.wrong{
        background-color: #ff5a5f;
    }
    .option.disabled{
        opacity: 0.5;
    }
    .option input{
        display: none;
    }
    .result-body{
        width: 1300px;
        height: auto;
        background-color: #1b1b1b;
        color: white;
        margin: 60px auto;
        font-family: 'Poppins', sans-serif;
        padding: 25px 25px;
        box-shadow: rgba(242, 242, 244, 0.823) 0px 50px 100px -20px, rgba(249, 249, 249, 0.863) 0px 30px 60px -30px, rgba(237, 239, 241, 0.948) 0px -2px 6px 0px inset;    }
    .result-title{
        text-align: center;
        font-size: 40px;
        font-weight: 700;
        margin-bottom: 25px;
    }
    .result-text{
        text-align: center;
        font-size: 20px;
        font-style: oblique;
        font-weight: 500;
        color: gray;
    }
    .explication{
        margin-top: 40px;
    }
    .q{
        display: flex;
        align-items: center;
        margin-bottom: 10px;
        padding: 10px 24px;
        border-radius: 16px;
    }
    .q-number{
        margin-right: 7px;
        font-size: 17px;
    }
    .q-title{
        font-size: 17px;
    }
    #ch1{
        background-color: #e14242;
        margin-top: 36px;
        margin-left: 8px;
        margin-right: 8px;
        padding: 10px 15px;
        border-radius: 8px;
    }
    #ch2 {
        background-color: #59CE8F;
        color: black;
        margin: 20px 8px;
        padding: 10px 15px;
        border-radius: 8px;
    }
    .justif{
        background-color: rgb(46, 79, 79);
        color: black;
        padding: 10px 15px;
        border-radius: 5px;
    }
    .exit-btn{
        display: flex;
        justify-content: end;
        margin-top: 25px;
        margin-bottom: 10px;
        margin-left: auto;
        background-color: rgb(113, 184, 149);
        color:  #474747;
        font-family:'Poppins', sans-serif;
        font-weight: bolder;
        font-size: 16px;
        padding: 10px 50px;
        border-radius: 5px;
        cursor: pointer;
        border: none;
    }
</style>

