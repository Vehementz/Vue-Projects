<template>
    <div class="block">
        Click here
    </div>
</template>

<script>


export default {
    name: "TimerBlock",
    props: ['delay']
       
    

}

</script>

<style>

.block {
    width: 400px;
    border-radius: 20px;
    background: rgb(161, 226, 161);
    color: black;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}

</style>