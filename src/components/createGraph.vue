<template>
    <div class="row mt-4">
        <div class="col-sm-6">
        <chartjs-line :datalabel="mylabel" :labels="mylabels" :data="mydata" :fill="true"></chartjs-line>
        </div>
    </div>
</template>

<script>

export default {
    name: 'graph1',
    data() {
        return { 
            mylabel: 'Jake\'s Weight',
            mylabels: ['1st Week', '2nd Week', '3rd Week', '4th week'],
            mydata: [164, 166, 158, 170]
        };
    },
};
</script>
<style scoped>

</style>


