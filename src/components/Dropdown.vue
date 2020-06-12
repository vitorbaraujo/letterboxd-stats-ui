<template>
    <div
        id="dropdown"
        @mouseover="onHover(true)"
        @mouseleave="onHover(false)">
        <div class="dropdown-btn" :class="{ 'hover': hover }">
            <div class="icon">
                <img class="icon-img" :src="gravatarUrl(user.gravatarUrl)" />
            </div>
            <div class="username">
                <p>{{user.name.toUpperCase()}}</p>
            </div>
            <div class="arrow">
                <p><font-awesome-icon :icon="arrowIcon" /></p>
            </div>
        </div>
        <div class="dropdown-options" v-show="hover">
            <p v-for="(option, index) in options"
                :key="index"
                :class="['header-btn', option.customClass]">
                {{ option.name }}
            </p>
        </div>
    </div>
</template>

<script>
import { faAngleDown, faAngleUp } from '@fortawesome/free-solid-svg-icons'

export default {
    name: 'Dropdown',
    props: {
        user: Object,
        options: Array,
    },
    data: function() {
        return {
            hover: false,
            arrowIcon: faAngleDown
        }
    },
    methods: {
        onHover: function(isHovering) {
            this.hover = isHovering
            this.arrowIcon = isHovering ? faAngleUp : faAngleDown
        },
        gravatarUrl(userHash) {
            return `https://gravatar.com/avatar/${userHash}`
        }
    }
}
</script>

<style scoped>
#dropdown {
    display: inline-block;
    position: relative;
}

#dropdown > .dropdown-btn {
    display: flex;
    align-items: center;
    padding: 5px 10px;
    border-top-left-radius: 2%;
    border-top-right-radius: 2%;
}

#dropdown > .dropdown-btn.hover {
    background: #8b99a9;
}

.dropdown-btn > .icon {
    display: flex;
    padding-right: 2px;
    height: 24px;
    width: 24px;
}

.dropdown-btn > .icon > .icon-img {
    height: 100%;
    width: 100%;
    border-radius: 50%;
}

.dropdown-btn > .username {
    padding: 0 5px;
    font-size: 14px;
    font-weight: 800;
}

.dropdown-btn > .username > p {
    margin: 0px;
}

.dropdown-btn.hover > .username > p {
    color: #f5f6f7;
}

.dropdown-btn > .arrow > p {
    margin: 0px;
}

.dropdown-btn.hover > .arrow > p {
    color: #f5f6f7;
}

#dropdown > .dropdown-options {
    position: absolute;
    width: 100%;
    padding-bottom: 10px;
    background: #8b99a9;
    border-bottom-left-radius: 1%;
    border-bottom-right-radius: 1%;
}

.dropdown-options > p {
    margin: 0px;
    padding: 2px 10px;
    text-align: left;
    font-size: 16px;
    color: #2f3540;
}

.dropdown-options > p:hover {
    background: #697787;
    color: #f5f6f7;
}

.dropdown-options > .top-border {
    border-top: 1px solid #7e8b99;
}

</style>