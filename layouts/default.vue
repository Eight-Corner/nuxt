<template>
    <div>
        <Navbar :charts="charts" @chartSelected="(chart) => selectedChart = chart"/>
            <component :is="selectedChart.name"/>
        <Nuxt/>
    </div>

</template>

<script>
export default {
    name: 'default',
    data() {
        const charts = []
        for (const c in this.$options.components) {
            if (c.startsWith('Charts')) {
                charts.push({
                    name: c,
                    displayName: c.replace('Charts', ''),
                    component: this.$options.components[c]
                })
            }
        }

        return {
            selectedChart: '',
            charts
        };
    },
}
</script>

<style scoped>

</style>
