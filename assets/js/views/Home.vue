<template>
    <div class="container">
        <div class="row">
            <div class="col-sm">
                <div class="input-group my-3">
                    <input type="text" class="form-control mx-3" placeholder="API key" v-model="apiKey">
                </div>
            </div>
            <div class="col-sm">
                <div class="input-group my-3">
                    <input type="text" class="form-control" placeholder="City" v-model="city">
                    <div class="input-group-append">
                        <button class="btn btn-success" type="button" @click="getWeather(apiKey, city)">
                            <i class="fas fa-check" />
                        </button>
                    </div>
                </div>
            </div>
        </div>
        <div class="row">
            <div class="col-sm">
                <ul class="nav nav-tabs">
                    <li class="nav-item">
                        <a class="nav-link active" href="#">Active</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Link</a>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    import { mapActions } from 'vuex';

    export default {
        name: "Home",

        data() {
            return {
                city: '',
                apiKey: '',
            }
        },

        methods: {
            ...mapActions([
                "getData",
            ]),

            getWeather(apiKey, city) {
                const payload = {
                    apiKey,
                    city,
                };

                this.getData(payload);
            },
        },
    }
</script>

<style scoped>

</style>