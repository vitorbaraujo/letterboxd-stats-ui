<template>
    <div id="main-stats">
        <div class="main-content">
            <div class="title">
                <p>A Life in Film</p>
                <Dropdown class="dropdown" :options="filterOptions" />
            </div>
            <div class="user-info">
                <div class="user-image">
                    <img :src="gravatarUrl(user.gravatarUrl)" />
                </div>
                <div class="stats">
                    <p>{{user.name}}'s all-time stats</p>
                </div>
            </div>
            <div class="social-info">
                <p class="share-title">Share</p>
                <p><font-awesome-icon :icon="twitterIcon" /></p>
                <p><font-awesome-icon :icon="facebookIcon" /></p>
            </div>
            <div class="other-stats">
                <div v-for="(stat,index) in stats" :key="index" class="stat">
                    <p class="stat-count">{{stat.count}}</p>
                    <p class="stat-category">{{stat.category}}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Dropdown from './Dropdown.vue'
import { faTwitter, faFacebook } from '@fortawesome/free-brands-svg-icons'

export default {
    name: 'MainStats',
    components: {
        Dropdown
    },
    props: {
        user: Object,
    },
    data: function() {
        return {
            filterOptions: [
                { name: 'All time...' },
                { name: '2020', customClass: 'top-border' },
                { name: '2019', customClass: 'top-border' },
                { name: '2018', customClass: 'top-border' },
                { name: '2017', customClass: 'top-border' },
                { name: '2016', customClass: 'top-border' },
                { name: '2015', customClass: 'top-border' },
                { name: '2014', customClass: 'top-border' },
            ],
            stats: [
                { count: 624, category: 'films' },
                { count: 1175, category: 'hours' },
                { count: 411, category: 'directors' },
                { count: 39, category: 'countries' },
            ],
            twitterIcon: faTwitter,
            facebookIcon: faFacebook
        }
    },
    methods: {
        gravatarUrl(userHash) {
            return `https://gravatar.com/avatar/${userHash}`
        }
    }
}
</script>

<style scoped>
#main-stats {
    display: flex;
    justify-content: center;
}

#main-stats > .main-content {
    width: 650px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 80px 0;
}

#main-stats > .main-content > .title {
    display: flex;
    align-items: center;
}

#main-stats > .main-content > .title > p {
    font-size: 100px;
    margin: 0px;
}

#main-stats > .main-content > .title > .dropdown {
    font-size: 30px;
}

#main-stats > .main-content > .user-info {
    display: flex;
    align-items: center;
}

#main-stats > .main-content > .user-info > .user-image {
    width: 30px;
    height: 30px;
    padding-right: 10px;
}

#main-stats > .main-content > .user-info > .user-image > img {
    border-radius: 50%;
    width: 100%;
    height: 100%;
}

#main-stats > .main-content > .user-info > .stats > p {
    margin: 0px;
    font-size: 20px;
}

#main-stats > .main-content > .social-info {
    display: flex;
    align-items: center;
    border: 1px solid #24303c;
    margin: 20px;
}

#main-stats > .main-content > .social-info > p {
    margin: 0px;
    padding: 5px;
}

#main-stats > .main-content > .other-stats {
    width: 70%;
    justify-content: space-between;
    display: flex;
    align-items: center;
    margin-top: 60px;
}

#main-stats > .main-content > .other-stats > .stat {
    display: flex;
    flex-direction: column;
    align-items: center;
}

#main-stats > .main-content > .other-stats >.stat > p {
    margin: 0px;
}

#main-stats > .main-content > .other-stats > .stat > .stat-count {
    font-size: 30px;
    font-weight: bold;
}
</style>