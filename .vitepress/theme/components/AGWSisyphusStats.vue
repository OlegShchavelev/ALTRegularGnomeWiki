<!-- Не завершено -->
<script>
const statistics_url = 'https://rdb.altlinux.org/api/packageset/repository_statistics'

export default {
    data() {
        return {
            branches: []
        }
    },
    async created() {
        this.response = await fetch(statistics_url).then((response) => response.json())
        this.branches = this.response.branches.map(({ branch, packages_count }) => ({
            branch,
            archs: packages_count.map(({ arch, count, size_hr }) => ({ arch, count, size_hr }))
        }))
    }
}
</script>

<template>
    <PluginTabs>
        <PluginTabsTab v-for="{ branch, archs } in branches">
            📦{{ branch }}
            <div v-for="({ arch, count, size_hr }, index) in archs.slice(0, -1)" class="arch">
                ┣ 📂{{ arch }} ({{ count }}) - {{ size_hr }}
            </div>
            <div>┗ 📂{{ archs.at(-1).arch }} ({{ archs.at(-1).count }}) - {{ archs.at(-1).size_hr }}</div>
        </PluginTabsTab>
    </PluginTabs>
</template>
