<template>
    <header class="header">
        <div class="header-inner">
            <div class="header-logo">
                <div class="logo-image" />
                <p class="logo-title">Letterboxd</p>
            </div>

            <div class="profile-dropdown">
                <p>{{ user.name.toUpperCase() }}</p>
            </div>

            <div class="header-buttons">
                <p v-for="(button, index) in buttons" v-bind:key="index" class="header-btn">
                    {{ button.name.toUpperCase() }}
                </p>
            </div>

            <div class="header-search">
                <p>Search</p>
            </div>

            <div class="header-log-btn">
                <p>LOG</p>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: 'Header',
    data: function() {
        return {
            buttons: [
                { name: 'Activity' },
                { name: 'Films' },
                { name: 'Lists' },
                { name: 'People' },
            ],
            user: {
                name: 'vitorbarbosa'
            }
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