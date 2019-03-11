<template>
    <div>
        <button :class="$style.hand"> 단일 </button>
        <button :class="[$style.hand, $style.border]"> 여러개  </button>
    </div>
</template>

<script>
export default {
    created(){
        console.log(this.$style);
    }
}
</script>

<style module>
.hand{ cursor:pointer; background-color: purple;  color:yellow;}
</style>


