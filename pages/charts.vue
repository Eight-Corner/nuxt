<template>
    <div>
        <Navbar :charts="charts" @chartSelected="(chart) => selectedChart = chart"/>
        <component :is="selectedChart.name"/>
    </div>
</template>

<script>
export default {
    name: 'ChartsPage',
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
