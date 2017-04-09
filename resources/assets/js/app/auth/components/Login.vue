<template>
    <div>
    <form class="form-horizontal" role="form" action="#">
        <div class="form-group">
            <label for="email" class="col-md-4 control-label">E-Mail Address</label>
            <div class="col-md-6">
                <input v-model="email" id="email" type="email" class="form-control" name="email" required autofocus>
            </div>
        </div>
        <div class="form-group">
            <label for="email" class="col-md-4 control-label">Password</label>
            <div class="col-md-6">
                <input v-model="password" id="password" type="password" class="form-control" name="password">
            </div>
        </div>
        <div class="form-group">
            <div class="col-md-8 col-md-offset-4">
                <button type="submit" class="btn btn-primary" @click.prevent="login">
                    Login
                </button>
            </div>
        </div>
    </form>
</div>
</template>

<script>
    export default{
        data(){
            return{
                email : '',
                password : ''
            }
        }
        ,
        methods:{
            login(){
                axios.post('/login' , {
                    email : this.email,
                    password : this.password
                }).then((response) => {
                    console.log(response);
                })
            }
        }
        ,
        mounted(){
            
        }
    }
</script>