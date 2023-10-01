

<template>
    <p>Enter Your Name:</p><input type="text" v-model="name" placeholder="Juan.."> 
    <button @click="clickEnter">Click</button>
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
        <div>
            <img src="../public/asset/dog.jpg"  style="width:50%;height:50%;" />
        </div>
    </div>
    <div v-else-if="selectedPet === 'Cat'">
        <p>You Selected: {{selectedPet}}</p>
        <div>
            <img src="../public/asset/cat.jpg"  style="width:50%;height:50%;" />
        </div>
    </div>
    <div v-else-if="selectedPet === 'Hamster'">
        <p>You Selected: {{selectedPet}}</p>
        <div>
            <img src="../public/asset/cute-hamsters.jpg"  style="width:50%;height:50%;" />
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
            showMessage.value = false;
        }
    };
    
    
     
</script>