<template>
    <div class="container-fluid">
        <div class="container">
            <div class="row">
                <div class="col-12 col-sm-5 col-md-5 col-lg-5 col-xl-5 col-xxl-5">
                    <div class="col-12 text-center">
                        <img class="logo" src="@/assets/logousabai.png" />
                        <p class="title1 mt-4">Because every homeowner is a</p>
                        <p class="title2">Member of our family</p>
                        <img class="imguta" src="@/assets/uta.png">
                    </div>
                </div>
                <div class="col-12 col-sm-7 col-md-7 col-lg-7 col-xl-7 col-xxl-7 d-flex  justify-content-center" style="background-color: #fff; margin-bottom: 10px;">
                    <div class="from  mt-3 mb-4">
                        <p class="titl3">register <br>now.!</p>
                        <span class="subtitle">Many privileges are waiting for you.</span>
                        <!-- <form class="mt-4"> -->
                        <div class="mb-3">
                            <label for="exampleInputEmail1" class="form-label">NAME</label>
                            <input type="text" ref="Name" class="form-control" v-model="Name" placeholder="your name">
                            <!-- <span v-if="msg.name">{{ msg.name }}</span> -->
                            <div class="form-text" v-if="msg.name">{{ msg.name }}
                            </div>
                        </div>
                        <div class="mb-3">
                            <label for="exampleInputEmail1" class="form-label">EMAIL ADDRESS</label>
                            <input type="text" ref="email" class="form-control" v-model="email" placeholder="e-mail">
                            <!-- <span v-if="msg.email">{{ msg.email }}</span> -->
                            <div class="form-text" v-if="msg.email">{{ msg.email }}
                            </div>
                        </div>
                        <div class="mb-3">
                            <label for="exampleInputEmail1" class="form-label">LINE ID</label>
                            <input type="text" ref="lineid" class="form-control" v-model="lineid" placeholder="line id">
                            <!-- <span v-if="msg.lineid">{{ msg.lineid }}</span> -->
                            <div class="form-text" v-if="msg.lineid">{{ msg.lineid }}
                            </div>
                        </div>

                        <div class="mb-3">
                            <label for="exampleInputEmail1" class="form-label">PHONE NUMBER</label>
                            <input type="tel" ref="numphone" class="form-control" v-model="numphone" maxlength="10"
                                placeholder="xxx-xxx-xxxx">
                            <!-- <span v-if="msg.numphone">{{ msg.numphone }}</span> -->
                            <div class="form-text" v-if="msg.numphone">{{ msg.numphone }}
                            </div>
                        </div>

                        <div class="mb-3">
                            <label for="exampleInputEmail1" class="form-label">PROJECTS</label>
                            <select class="form-control" v-model="nameproject" ref="nameproject">
                                <option disabled value="">Please select one</option>
                                <option>THE URBANO</option>
                                <option>U-12</option>
                                <option>THE ABSOLUTE</option>
                                <option>THE VELA</option>
                                <option>HARMONIZE</option>
                                <option>TULTIMA</option>
                                <option>SYMBOLIC</option>
                                <option>AURORA</option>
                                <option>ASPECT</option>
                                <option>ESTELLA</option>

                            </select>
                        </div>

                        <button class="btn w-100 mt-3" @click="submit()">Register</button>
                        <!-- </form> -->
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import axios from "axios";
import Swal from 'sweetalert2'
export default {

    data() {
        return {

            Name: '',
            email: '',
            lineid: '',
            numphone: '',
            nameproject:'',
            msg: [],

        }
    }, watch: {
        email(value) {
            this.email = value;
            this.validateEmail(value);
        },
        Name(value) {
            this.Name = value;
            this.validateName(value);
        },
        lineid(value) {
            this.lineid = value;
            this.validatelineid(value);
        },
        numphone(value) {
            this.numphone = value;
            this.validatenumphone(value);
        }

    },
    methods: {

        validateEmail(value) {
            if (/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(value)) {
                this.msg['email'] = '';
            } else if (value === '') {
                this.msg['email'] = '';
            } else {
                this.msg['email'] = 'Invalid Email Address';
            }
        },

        validateName(value) {
            if (value !== '') {
                this.msg['name'] = '';
            } else if (value === '') {
                this.msg['name'] = '';
            } else {
                this.msg['name'] = 'Invalid name';
            }
        }

        , validatelineid(value) {
            if (/^\w+([\.-]?\w+)*\w+$/.test(value)) {
                this.msg['lineid'] = '';
            } else if (value === '') {
                this.msg['lineid'] = '';
            } else {
                this.msg['lineid'] = 'Invalid lineid';
            }
        }
        , validatenumphone(value) {
            let difference = 10 - value.length;
            if (value.length < 10) {
                this.msg['numphone'] = 'Must be 10 characters! ' + difference + ' characters left';
                return false;
            } else {
                this.msg['numphone'] = '';
                return true;
            }
        },


        submit() {
            // Swal.fire('Any fool can use a computer')

            if ((this.Name && this.email && this.lineid && this.numphone) !== '') {
                Swal.fire({
                    icon: 'success',
                    title: 'success',
                    text: 'Registration is complete We will get back to you as soon as possible.',
                    showButton: true,
                }).then((result) => {
                    if (result.isConfirmed) {
                        axios.get("https://www.u-sabai.com/api/web2/registor.php?name=" + this.Name + "&line_id=" + this.lineid + "&phone_Number=" + this.numphone + "&email=" + this.email+"&project="+this.nameproject)
                            .then((res) => (console.log(res),
                                this.$refs["Name"].value = "",
                                this.$refs["email"].value = "",
                                this.$refs["lineid"].value = "",
                                this.$refs["numphone"].value = "",
                                this.$refs["nameproject"].value = ""
                                ));

                    }
                })
            } else {
                Swal.fire({
                    icon: 'warning',
                    title: 'warning',
                    text: 'Please fill out the information completely.',
                })
            }


        }
    },
    mounted() {

    },


}
</script>
<style scoped>
.container-fluid {
    background: linear-gradient(90deg, rgb(63, 0, 125) 0%, #ef233c 100%);
    display: flex;
    height: 100vh;
    width: 100%;
    justify-content: center;
    align-items: center;
}

.from {

    width: 60%;
    /* padding: 10%; */
    background-color: rgb(255, 255, 255);

}


.btn {
    background: linear-gradient(90deg, hsla(328, 75%, 45%, 1) 0%, hsla(269, 85%, 41%, 1) 100%);
    color: rgb(255, 255, 255);
}

.logo {
    width: 80px;
    height: 80px;

}

.title1 {
    color: rgb(255, 255, 255);
    font-size: 24px;
    font-weight: 300;
    margin-bottom: 0px;
}

.title2 {
    font-size: 48px;
    font-weight: 500;
    background: -webkit-linear-gradient(180deg, #F7BA2C 0%, #F36E59 40.98%, #F13C77 68.17%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.titl3 {
    font-size: 36px;
    font-weight: 600;
    text-transform: uppercase;
    margin-bottom: 0px;
}

.form-control {
    border: 2px solid #000000;
    border-radius: 5px;
}

.form-text {
    font-size: 12px;
    color: #ef233c;
    height: 16px;
}


@media only screen and (max-width: 820px) {  


    .container-fluid  {
    /* background-color: blue; */
    /* height: 40vh; */
    padding: 20px;
    height: calc(100vh - calc(100vh - 100%));
  }


  .logo {
    margin-top: 20px;
    width: 100px;
    height: 100px;

}

  .title1{
    font-size: 18px;
  }
  .title2{
    font-size: 20px;
  }

  .titl3 {
    font-size: 28px;
}

  .imguta{
    width: 80%;
  }
  .from{
    width: 80%;
   
  }

  .form-label{
    font-size: 12px;
  }

  .subtitle{
    font-size: 14px;
  }

  .form-control {
  font-size: 16px;
}
  
}


@media only screen and (max-width: 600px) {
    .container-fluid  {
    /* background-color: blue; */
    /* height: 40vh; */
    height: calc(100vh - calc(100vh - 100%));
  }

  .title1{
    font-size: 16px;
  }
  .title2{
    font-size: 18px;
  }
  .imguta{
    width: 50%;
  }
  .from{
    width: 80%;
   
  }

  .form-label{
    font-size: 12px;
  }

  .form-control {
  font-size: 16px;
}

}

</style>