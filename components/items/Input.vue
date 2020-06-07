<template>

</template>
<script>
export default {
    props:{
        labelName: String,
        labelId: String,
        inputType: String,
        model: String,
        disabled: Boolean,
    },
    computed:{
        inputModel: {
            get(){
                return this.model;
            },
            set(val){
                this.$emit('input', val);
            }
        }
    }
}
</script>
<style>
.input {
        transition: border 0.2s ease-in-out;
    }

.input:focus+.label,
.input:active+.label,
.input.filled+.label {
    font-size: .55rem;
    transition: all 0.2s ease-out;
    top: -0.3rem;
    color: #323232;
}

.label {
    transition: all 0.2s ease-out;
    top: 0.2rem;
    left: 0;
}
</style>
