<script>
    export default {
        props: {
            step: {
                type: Number,
                required: true
            }
        },        
        computed: {
            stepperProgress(){
                return (100/2) * (this.step - 1) + '%'
            }
        }
    }
</script>

<template>
    <div class="wrapper-stepper">
        <div class="stepper">
            <div class="stepper-progress">
                <div class="stepper-progress-bar" :style="'width:' + stepperProgress">

                </div>
            </div>
            <div class="stepper-item" :class="{'current' : step == item, 'success' : step > item }" v-for="item in 3" :key="item">
                <div class="stepper-item-counter">
                    <img class="icon-success" src="../assets/images/check-mark.png" alt="">
                    <span class="number">{{ item }}</span>
                </div>
                <!-- <div class="stepper-item-title">
                    step {{ item }}
                </div> -->
            </div>
        </div>
    </div>
</template>

<style scoped>
    .wrapper-stepper{
        background-color: transparent;
        padding: 20px;
        border-radius: 32px;
        display: flex;
        justify-content:center;
    }
    .stepper{
        display: flex;
        align-items: center;
        justify-content: space-between;
        width: 1200px;
        position: relative;
        z-index: 0;
    }
    .stepper-progress{
        position: absolute;
        background-color: #fff;
        height: 2px;
        z-index: -1;
        left: 0;
        right: 0;
        margin: 0 auto;
    }
    .stepper-progress-bar{
        position: absolute;
        left: 0;
        height: 100%;
        width: 0%;
        background-color: rgba(50, 193, 109, 0.31);
        transition: all 500ms ease;
    }
    .stepper-item{
        display: flex;
        flex-direction: column;
        align-items: center;
        font-weight: bolder;
        color: rgba(43, 61, 51, 0.31);
        transition: all 500ms ease;
    }
    .stepper-item-counter{
        height: 68px;
        width: 68px;
        display: grid;
        place-items: center;
        background-color: #fff;
        border-radius: 100%;
        border: 1px solid rgba(49, 51, 50, 0.074);
        position: relative;
    }
    .icon-success{
        position: absolute;
        opacity: 0;
        transform: scale(0);
        width: 24px;
        transition: all 500ms ease;
    }
    .number{
        color: black;
        font-size: 22px;
        transition: all 500ms ease;
    }
    .stepper-item-title{
        position: absolute;
        font-size: 18px;
        bottom: -24px;
        color: #fff;
        font-weight: bolder;
    }
   
    .stepper-item-success.stepper-item-counter{
        border-color: rgba(14, 23, 17, 0.31);
        background-color: rgba(189, 215, 200, 0.827);
        color: #fff;
        font-weight: 600;
    }
    .stepper-item-success.icon-success{
        opacity: 1;
        transform: scale(1);
    }
    .stepper-item-success.number{
        opacity: 0;
        transform: scale(0);
    }

    .stepper-item-current.stepper-item-counter{
        border-color: rgba(50, 193, 109, 0.31);
        background-color: rgba(73, 209, 129, 0.31);
        color: #fff;
        font-weight: 600;
    }
    .stepper-item-current.stepper-item-title{
        color:  rgba(50, 193, 109, 0.31);
    }
</style>