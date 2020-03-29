<template>
    <div class = "register">
        <h1 class = "title">Apply to be a templar!</h1>
        <div class = "skeleton">
            <div class = "container" v-for = "(one,index) in data " :key = "index">
                <p class = "basicTitle">{{one.name}}</p>
                <input class = "input" :placeholder = "[[one.name]]" v-model = one.value :class = "{inputRed : one.warning}">
            </div> 
           
            <div class = "container">
                <p class = "basicTitle">Deus Vult</p>
                <textarea class = "inputDeus" placeholder = " Deus Vult " v-model = "deusVult"></textarea>
            </div>
            <div>
                <p class = "robot">I m not a robot!</p>
                <input type = "checkbox" v-model = "checkBox" class = "checkBox">
            </div>
            <div>
                <button type = "submit" class = "submit" @click="checkValueData()">Deus Vult!</button>
            </div>
            <p v-if = "!checkBox">Please verifiy that you are not a robot!</p>
            <p v-if = "!checkValue">Please fill in all the fields!</p>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            data:[
            {name:'First Name', warning: false, value:''},
            {name:'Latin First Name', warning: false, value:''},
            {name:'Last Name', warning: false, value: ''},
            {name:'Creed', warning: false, value: '' }] ,
            deusVult:'',
            checkValue: true,
            checkBox: false,
            red: false
            }
    },
    methods: {

        checkValueData: function() {
            let  wave= this.data;
            let ok;
                for(let i of wave)
                {
                    if(!i.value)
                        {
                            i.warning = true;
                            this.checkValue = false;
                            ok = false;
                        }
                    else 
                        {
                            i.warning = false;
                            this.checkValue = true;
                            ok = true;
                        }
                }
            if(ok && this.checkBox)
            {
                for(let z of x)
                {
                    console.log(z.value );
                }
                if(this.deusVult)
                    console.log(this.deusVult);
            }
              
        }   
        
    }
    
}
</script>

<style>
    .title {
        color: gold;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        font-size: 60px;
    }

    .skeleton {
        display: flex;
        flex-direction: column;
        margin: auto;
        margin-top: 30px;
        background-color: grey;
        height: 700px;
        width: 400px;
        border-radius: 5%;
        box-shadow: 0px 0px 19px 5px rgba(189, 147, 10, 0.945);
    }

    .container {
        margin-top: 10px;
    }

    .basicTitle {
        text-align: start;
        margin-left: 30px;
        margin-bottom: 10px;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        font-size: 22px;
    }

    .input {
        border-radius: 12%;
        width: 350px;
    }

    .inputRed {
        border-radius: 12%;
        width: 350px;
        border-color: red;
    }

    .inputDeus {
        border-radius: 15%;
        width: 350px;
        height: 50px;
    }

    .robot {
        font-size: 20px;
        color: darkslategrey;
        margin-bottom: 5px;
    }

    .checkBox {
         height: 20px;
         width: 20px;
    }

    .checkBox:hover {
        box-shadow: 2px -1px 10px 5px rgba(0,0,0,0.75);
    }

    .submit {
        border-radius: 10%;
        margin-top: 20px;
        font-size: 20px;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    }

    .submit:hover {
        box-shadow: 2px -1px 10px 5px rgba(0,0,0,0.75);
    }
</style>