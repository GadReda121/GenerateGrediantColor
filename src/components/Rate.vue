<template>
    <div class="rates">
        <p>Rate Our Website</p>
        <n-rate clearable allow-half size="large" @click="Rating"/>
    </div>
</template>

<script>
import { NRate } from "naive-ui";
import Swal from 'sweetalert2';
export default {
    name: "Rate",
    components: {
            NRate
        },
    methods: {
        Rating() {
            Swal.fire(
                {
                    position: 'center',
                    icon: 'success',
                    title: 'Thanks For Rating &#128515;',
                    showConfirmButton: false,
                    timer: 1500
                }
            )
            }
        },
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