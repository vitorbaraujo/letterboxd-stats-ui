<template>
    <div id="log-btn">
        <p class="icon"><font-awesome-icon :icon="plusIcon" /></p>
        <p class="text">LOG</p>
    </div>
</template>

<script>
import { faPlus } from '@fortawesome/free-solid-svg-icons'

export default {
    name: 'LogButton',
    data: function() {
        return {
            plusIcon: faPlus
        }
    }
}
</script>

<style scoped>
#log-btn {
    display: flex;
    align-items: center;
    background: #03b021;
    padding: 2px 5px;
    border-radius: 10%;
}

#log-btn > p {
    margin: 0px;
    color: #f5f6f7;
    font-weight: bold;
    font-size: 14px;
}

#log-btn > .icon {
    padding-right: 5px;
}
</style>