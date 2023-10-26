<template>
    <div class="container">
        <div class="row">

            <div v-for="index in 6" class="card skeleton-loading mt-2"
                style="min-width: 800px;min-height: 200px; margin: 0 auto;">
                <div class="card-body">
                    <div class="d-flex">
                        <div class="text-left">
                            <div class="skeleton-profile"></div>
                        </div>
                        <div class="ms-3">
                            <div class="skeleton-name"></div><br>
                            <div class="skeleton-email"></div>
                        </div>
                    </div>
                    <div class="skeleton-text"></div>
                    <div class="skeleton-text2"></div>
                </div>
            </div>

        </div>
    </div>
</template>
  
<style scoped>
.skeleton-loading {
    border-radius: 8px;
    background-color: #fff;
    animation: loading 1.5s ease-in-out infinite;
}

.skeleton-profile {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    background: linear-gradient(to right, transparent 0%, #E0E0E0 50%, transparent 100%);
    animation: loading 1.5s infinite;
}

.skeleton-name,
.skeleton-email {
    height: 20px;
    width: 200px;
    float: left;
    margin-top: 10px;
    background: linear-gradient(to right, transparent 0%, #E0E0E0 50%, transparent 100%);
    animation: loading 1.5s infinite;
}

.skeleton-text {
    height: 30px;
    width: 100%;
    background: linear-gradient(to right, transparent 0%, #E0E0E0 50%, transparent 100%);

    margin-top: 10px;
    animation: loading 1.5s ease-in-out infinite;
}

.skeleton-text2 {
    height: 10px;
    width: 50%;
    background: linear-gradient(to right, transparent 0%, #E0E0E0 50%, transparent 100%);

    margin-top: 10px;
    animation: loading 1.5s ease-in-out infinite;
}

@keyframes loading {
    0% {
        background-position: -200px 0;
    }

    100% {
        background-position: 200px 0;
    }
}
</style>
  