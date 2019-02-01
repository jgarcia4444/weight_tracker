<template>
    <div class="row mt-4">
        <div class="col-sm-6">
        <chartjs-line :datalabel="mylabel" :labels="mylabels" :data="mydata"></chartjs-line>
        </div>
    </div>
</template>

<script>

export default {
    data() {
        return { 
            mylabel: 'Jake\'s Weight',
            mylabels: ['1st Week', '2nd Week', '3rd Week'],
            mydata: [164, 158, 168],
        };
    },
};
</script>
<style scoped>

</style>


