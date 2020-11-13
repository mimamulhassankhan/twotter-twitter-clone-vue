<template>
    <div>
        <div class="user_profile">
            <div class="user_profile_user_panel">
                <h1 class="user_profile_name">@{{user.userName}}</h1>
                <div class="user_profile_follower_count">
                    <strong>Followers: </strong> {{followers}}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'UserProfile',
        data() {
            return{
                followers : 0,
                user : {
                    id: 1,
                    userName: 'imamul_hk',
                    firstName: 'Imamul',
                    lastName: 'Hassan',
                    email: 'pappuhassan440@gmail.com',
                    isAdmin: true
                }
            }
        },
        computed: {
            getFullName() {
                return `${this.user.firstName} ${this.user.lastName}`;
            }
        },
        methods: {
            followUser(){
                this.followers++;
            }
        },
        mounted(){
            this.followUser();
        }
    }
</script>

<style>
    .user_profile{
        display: grid;
        grid-template-columns: 1fr 3fr;
        width: 90%;
        padding: 50px 5%;
    }

    .user_profile_user_panel{
        display: flex;
        flex-direction: column;
        margin-right: 50px;
        padding: 20px;
        background-color: white;
        border-radius:  5px;
        border: 1px solid #DEF3E8;
    }

    h1{
        margin: 0;
    }

</style>