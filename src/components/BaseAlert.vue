<template>
    <!-- <div :class="['alert',{
        'alert-sucess':variant === 'sucess',
        'alert-danger':variant === 'danger'
        }]">
        Seu formulário foi enviado com sucesso!
    </div> -->
    <!-- //dessa forma apararece undefined -->
    <!-- <div :class="`alert alert-${variant}`">
        Seu formulário foi enviado com sucesso!
    </div> -->
    <div :class="baseClass">
        {{ test }}
        <slot />
        <button @click="onclick()">
            X
        </button>
    </div>
</template>

<script>

export default {
    // props:['variant','test'],
    // mounted(){
    //     console.log(this.test)
    // }, 
    props: {
        variant: {
            type:String,
            default:''
        },
        test: {
            type:String,
            default: 'test'
        }
    },
    methods:{
        onclick(){
            this.$emit('close')
            console.log('clicou')
        }
    },
    computed: {
        baseClass() {
            return [
                'alert',
                this.variant ? `alert-${this.variant}` : ''
            ]
        }
    },

}

</script>

<style scoped>
.alert {
    padding: 5px;
    border-radius: 6px;
    color: gray;
    background: #ddd;
    display: flex;
    justify-content: space-between;
}

.alert-sucess {
    background: #42b983;
    color: #fff;
}

.alert-danger {
    background: red;
    color: #fff;
}
</style>