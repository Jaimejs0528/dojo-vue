<template>
    <div id="translateIn">
        <h2>Translation</h2>
        <form v-on:submit="formSubmit">
            <input type="text" v-model="textToTranslate" style="width:fit-content" placeholder="What do u wanna translate? type here!">
            <input type="submit" value="Translate">
            <select v-model="language">
                <option value="en">Ingles</option>
                <option value="it">Italiano</option>
                <option value="es">Español</option>
            </select>
        </form>
    </div>
</template>

<script>
export default {
    name: "translateIn",
    data:function(){
        return{
            textToTranslate:'',
            language:''
        }
    },
    created(){
        this.language='en'
    },
    methods:{
        formSubmit:function(event){
            this.$emit('formSubmit',this.textToTranslate,this.language);
            event.preventDefault();
        }
    }
}
</script>

<style>
form{
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
input[type="text"]{
    width: 100%;
    border-radius: 3px;
    padding:3px 5px;
    margin: 6px;
}

</style>
