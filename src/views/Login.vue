<template>
        <div class="row justify-content-center">
            <div class="col-lg-5 col-md-7">
                <div class="card bg-secondary shadow border-0">
                    
                    <div class="card-body px-lg-5 py-lg-5">

                        <form role="form">
                            <base-input class="input-group-alternative mb-3"
                                        placeholder="Correo"
                                        addon-left-icon="ni ni-email-83"
                                        :valid="validEmail(model.email)"
                                        v-model="model.email">
                            </base-input>

                            <base-input class="input-group-alternative"
                                        placeholder="Contraseña"
                                        type="password"
                                        addon-left-icon="ni ni-lock-circle-open"
                                        :valid="validPassword(model.password)"
                                        v-model="model.password">
                            </base-input>

                            <base-checkbox class="custom-control-alternative">
                                <span class="text-muted">Recordarme</span>
                            </base-checkbox>
                            <div class="text-center">
                                <base-button type="primary" class="my-4">Iniciar</base-button>
                            </div>
                        </form>
                    </div>
                </div>
                <div class="row mt-3">
                    <div class="col-6">
                        <a href="#" class="text-light"><small>¿Olvide mi contraseña?</small></a>
                    </div>                    
                </div>
            </div>
        </div>
</template>
<script>
  export default {
    name: 'login',
    data() {
      return {
        model: {
          email: '',
          password: ''
        }
      }
    },
    methods:{
        validEmail: function (email) {
            if(email.length == 0) return undefined
            var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
            return re.test(email);
        },
        validPassword: function(pass){
            if(pass.length == 0) return undefined
            return pass.length > 3
        }
    }
  }
</script>
<style>
</style>
