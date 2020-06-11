<template>
    <div
        id="dropdown"
        @mouseover="onHover(true)"
        @mouseleave="onHover(false)">
        <div class="dropdown-btn" :class="{ 'hover': hover }">
            <div class="icon">
                <img class="icon-img" :src="userIconUrl" />
            </div>
            <div class="username">
                <p>{{username.toUpperCase()}}</p>
            </div>
            <div class="arrow">
                <p><font-awesome-icon :icon="arrowIcon" /></p>
            </div>
        </div>
        <div class="dropdown-options" v-show="hover">
            <p v-for="(option, index) in options"
                :key="index"
                class="header-btn">
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
        userIconUrl: String,
        username: String,
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
    padding: 0 10px;
}

#dropdown > .dropdown-btn.hover {
    background: #8b99a9;
}

.dropdown-btn > .icon {
    display: flex;
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
}

.dropdown-btn.hover > .username > p {
    color: #f5f6f7;
}

.dropdown-btn.hover > .arrow > p {
    color: #f5f6f7;
}

#dropdown > .dropdown-options {
    position: absolute;
    width: 100%;
    padding: 10px 0;
    background: #8b99a9;
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

</style>