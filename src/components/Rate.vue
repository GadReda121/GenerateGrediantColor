<template>
    <div class="rates">
        <p>Rate Our Website</p>
        <n-rate clearable allow-half size="large" class="ra"/>
    </div>
</template>

<script>
import { NRate } from "naive-ui";
export default {
    name: "Rate",
    components: {
            NRate
        }
    }
</script>

<style scoped>
    .rates{
        align-self: flex-end;
        display:grid;
        font-weight: 600;
        color:#fff;
        justify-content: center;
        text-align: center;
    }
    .rates p{
        text-align: center;
    }
</style>