<template>
    <div class="container">
        <form v-if="!isSubmitted">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <h1>SignUp Form</h1>
                    <hr>
                    <app-fullname v-model="fullName"></app-fullname>
                    <div class="form-group">
                        <label for="email">Email:</label>
                        <input type="text"
                                class="form-control"
                                v-model="email">
                    </div>
                    <div class="form-group">
                        <label for="password">Password:</label>
                        <input type="password"
                                class="form-control"
                                v-model="password">
                    </div>
                     <div class="row">
                        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                            <label for="Yes">Store Data:
                                <input
                                        type="radio"
                                        value="Yes"
                                        v-model="storeData"> Yes
                            </label>
                            <label for="No">
                                <input
                                        type="radio"
                                        value="No"
                                        v-model="storeData"> No
                            </label>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                            <button
                                    class="btn btn-primary"
                                    @click="isSubmitted=true">Submit!
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="isSubmitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ fullName }}</p>
                        <p>Mail: {{ email }}</p>
                        <p>Password: {{ password }}</p>
                        <p>Store in Database?: {{ storeData }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import FullName  from './FullName.vue';
    export default {
        data(){
            return {
                fullName: 'Vinita Gupta',
                email: '',
                password: '',
                storeData: 'Yes',
                isSubmitted: false
            }
        },
        methods: {
            submitted(){
                this.isSubmitted=true;
            }
        },
        components: {
            appFullname: FullName
        }
    }
</script>

<style>
</style>
