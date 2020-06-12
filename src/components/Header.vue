<template>
    <header class="header">
        <div class="header-inner">
            <div class="header-logo">
                <div class="logo-image" />
                <p class="logo-title">Letterboxd</p>
            </div>

            <Dropdown
                :user="user"
                :options="profileDropdownOptions" />

            <div class="header-buttons">
                <p v-for="(button, index) in buttons" v-bind:key="index" class="header-btn">
                    {{ button.name.toUpperCase() }}
                </p>
            </div>

            <div class="header-search">
                <p><font-awesome-icon :icon="searchIcon" /></p>
            </div>

            <LogButton />
        </div>
    </header>
</template>

<script>
import Dropdown from './Dropdown.vue'
import LogButton from './LogButton.vue'
import { faSearch } from '@fortawesome/free-solid-svg-icons'

export default {
    name: 'Header',
    components: {
        Dropdown,
        LogButton
    },
    props: {
        user: Object
    },
    data: function() {
        return {
            buttons: [
                { name: 'Activity' },
                { name: 'Films' },
                { name: 'Lists' },
                { name: 'People' },
            ],
            profileDropdownOptions: [
                { name: 'Home', customClass: 'top-border' },
                { name: 'Profile' },
                { name: 'Diary' },
                { name: 'Reviews' },
                { name: 'Watchlist' },
                { name: 'Lists' },
                { name: 'Likes' },
                { name: 'Tags' },
                { name: 'Networks' },
                { name: 'Stats' },
                { name: 'Settings', customClass: 'top-border' },
                { name: 'Sign Out' }
            ],
            searchIcon: faSearch
        }
    }
}
</script>

<style scoped>
.header {
    background: #13181c;
    display: flex;
    justify-content: center;
}

.header-inner {
    width: 950px;
    padding: 10px 0;
    display: flex;
    align-items: center;
}

.header p {
    font-size: 14px;
    font-weight: 800;
}

.header-logo {
    flex: 1;
    display: flex;
}

.header-logo > .logo-title {
    font-size: 32px;
    margin: 0;
}

.header-buttons {
    display: flex;
}

.header-buttons > .header-btn {
    padding: 0 5px;
}

.header-search {
    padding: 0 10px;
}

</style>