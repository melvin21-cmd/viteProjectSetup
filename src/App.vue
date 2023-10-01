

<template>
    <div class="container d-flex flex-column justify-content-start align-items-center " style="height:95vh;">
        <div class="d-flex flex-column justify-content-start align-items-start shadow rounded bg-light p-3 w-100 mt-3 height: 100%;">
            <div class="form-group w-100 mw-100 mt-5 d-flex flex-column justify-content-center align-items-center">
                <div class="w-50 d-flex flex-column justify-content-center ">
                    <label class="mr-5">Enter Your Name:</label>
                    <div class="d-flex w-100">
                        <input type="text" v-model="name" class="form-control" placeholder="Juan.."> 
                        <button @click="clickEnter">Click</button>
                    </div>
                </div>
            </div>
            <div v-if="showMessage">
            <p>{{welcomeMessage}}</p>

            <p>{{selectMessage}}</p>
            <select v-model="selectedPet">
            <option value="Dog">Dog</option>
            <option value="Cat">Cat</option>
            <option value="Hamster">Hamster</option>
            </select>
            <div v-if="selectedPet === 'Dog'">
                <p>You Selected: {{selectedPet}}</p>
                <div class="d-flex ">
                    <img src="/asset/dog.jpg"  style="width:45%;height:45%;" />
                    <p style="padding:94px;">DOGS CAN UNDERSTAND THE LANGUAGE OF LOVE!!</p>
                </div>
            </div>
            <div v-else-if="selectedPet === 'Cat'">
                <p>You Selected: {{selectedPet}}</p>
                <div class="d-flex ">
                    <img src="/asset/cat.jpg"  style="width:42%;height:45%;" />
                    <p style="padding:94px;text-align:center;">WHEN CATS SLOWLY BLINK AT YOU, THEY'RE BASICALLY SAYING "I LOVE YOU!!"</p>
                </div>
            </div>
            <div v-else-if="selectedPet === 'Hamster'">
                <p>You Selected: {{selectedPet}}</p>
                <div class="d-flex">
                    <img src="/asset/cute-hamsters.jpg"  style="width:39%;height:45%;max-height: 466px;" />
                    <p style="padding:94px;text-align:center;margin-left: 34%;">404</p>
                </div>
            </div>
            
            </div>
        </div>
    </div>
</template>

<script setup>
    import {ref} from 'vue';
    let name = ref('');
    const welcomeMessage = ref('');
    const selectMessage = ref('');
    const selectedPet = ref('');
    const naSelect = ref('');
    const showMessage = ref(false);

    let inputName = name.value;
    console.log('select :', naSelect);
    function clickEnter() {
        console.log('1 :', name.value);
        if (name.value) {
            console.log('2');
            welcomeMessage.value = `Welcome ${name.value}!`;
            selectMessage.value = `Kindly select the pet you want`;
            showMessage.value = true;
        } else {
            console.log('3');
            welcomeMessage.value = ``;
            selectedPet.value = ``;
            showMessage.value = false;
        }
    };
    
    
     
</script>