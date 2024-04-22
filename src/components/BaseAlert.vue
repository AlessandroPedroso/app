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