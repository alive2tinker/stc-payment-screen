<template>
    <ion-page>
        <ion-content :fullscreen='true'>
            <div class="rect"></div>
            <div class="main-content">
                <div class="flex h-[90vh]">
                    <div class="m-auto">
                        <div class="flex justify-center">
                            <svg class="w-64 h-64 fade-in1" width="32" height="32" viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M12.0866 15.676L15.2506 18.8387L20.9266 13.1613M26.6639 15.9987C26.6639 21.8882 21.8895 26.6627 15.9999 26.6627C10.1104 26.6627 5.33594 21.8882 5.33594 15.9987C5.33594 10.1091 10.1104 5.33466 15.9999 5.33466C21.8895 5.33466 26.6639 10.1091 26.6639 15.9987Z" stroke="currentColor" stroke-width="1.5" stroke-miterlimit="10" stroke-linecap="round" stroke-linejoin="round"/>
</svg>

                        </div>
                        <h1 class="text-3xl font-bold text-center fade-in2 dark:text-[#2B303A]">Your payment has been confirmed!</h1>
                        <p class="text-center my-4 px-4 text-lg fade-in3 dark:text-[#2B303A]">You have successfully paid your outstanding bills. You can find the receipt in your bill history</p>
                    </div>
                </div>
                <div class="max-w-4xl mx-auto px-4">
                    <ion-button expand="full" class="white-button dark:dark-button" fill="solid" @click="router.push({name: 'Home'})">Close</ion-button>
                </div>
            </div>
        </ion-content>
    </ion-page>
</template>
<script setup>
import {IonPage, IonContent, IonButton} from '@ionic/vue'
import { useRouter } from 'vue-router';

const router = useRouter();
</script>
<style scoped>
.rect{
    width: 100px;
    height: 100px;
    background: #D64933;
    margin: auto;
    position: absolute;
    left: -100px;
    animation: goForward 3s ease-in forwards;
    z-index: 9999999;
    top: 50%;
    transform: translateY(-50%);
}
.white-button{
    --background: #D64933;
    --color: white;
    transform: translateY(299%);
    animation: enter 500ms 8s ease-in forwards;
}
.main-content{
    height: 100px;
    background: #92DCE5;
    animation: goForwardWithExpansion 4s ease-in forwards;
    position: absolute;
    z-index: 10000;
    top: 50%;
    transform: translateY(-50%);
    overflow: hidden;
}

.fade-in1, .fade-in2, .fade-in3{
    opacity: 0;
    animation: fadeIn 2s ease-in forwards;
}

.fade-in1{
    animation-delay: 4s;
}

.fade-in2{
    animation-delay: 5s;
}

.fade-in3{
    animation-delay: 6s;
}

@keyframes goForward {
    0%{
        left: -100px;
    }
    100%{
        left: 100%;
    }
}

@keyframes fadeIn {
    0%{
        opacity: 0;
    }
    100%{
        opacity: 1;
    }
}

@keyframes goForwardWithExpansion {
    0%{
        width: 0;
        height: 100px;
    }
    25%{
        height: 100px;
    }
    50%{
        height: 100px;
    }
    75%{
        width: 100%;
        height: 100px;
    }
    100%{
        height: 100%;
        width: 100%;
    }
}

@keyframes enter {
    0%{
        transform: translateY(299%);
    }
    100%{
        transform: translateY(0);
    }
}
</style>