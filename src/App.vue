<script setup>
import axios from "axios"
import { ref, onMounted } from 'vue'
import Loading from './components/Loading.vue'

const users = ref([]);
const url = "https://reqres.in/api/users";
let isLoading = ref(false);

const getUsers = () => {
    isLoading.value = true;
    setTimeout(() => {
        axios.get(url)
            .then((response) => {
                users.value = response.data.data;
                isLoading.value = false;
            })
            .catch((error) => {
                console.log('error while getting users');
            });
    }, 2000);
};

onMounted(() => {
    getUsers();
});
</script>

<template>
    <div class="container">
        <div v-if="isLoading">
            <Loading />
        </div>
        <div v-else class="row">
            <div v-for="(user, index) in users" :key="index" class="card  mt-2" style="min-width: 800px; margin: 0 auto;">
                <div class="card-body">
                    <div class="d-flex">
                        <div class="text-left">
                            <img :src="user.avatar" alt="Profile Picture" class="img-fluid rounded-circle mb-3"
                                style="width: 100px; height: 100px;">
                        </div>
                        <div class="ms-3">
                            <h4 class="card-title">{{ user.first_name }} {{ user.last_name }}</h4>
                            <p class="card-text small">{{ user.email }}</p>
                        </div>
                    </div>
                    <p> Lorem ipsum dolor sit, amet consectetur adipisicing elit. Facere nulla itaque vitae optio
                        eligendi
                        est qui ullam totam ipsam sed, repellendus quia numquam commodi obcaecati, veritatis aut
                        quisquam
                        ipsa? Libero. </p>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
/* .spinner {
  animation: spin 1s linear infinite; 
  font-size: 3rem;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
} */
</style>
