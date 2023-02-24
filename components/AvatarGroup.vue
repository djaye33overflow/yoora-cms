<template>
    <div class="avatar-group text-left d-flex">
        <v-avatar class="mr-3">
            <img :src="filePath" alt="" />
        </v-avatar>
        <div>
            <div class="avatar-group__user mb-1 font-weight-bold">{{ username }}</div>
            <p class="avatar-group__position">{{ position }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        filePath: {
            type: String,
            required: true
        },
        username: {
            type: String,
            required: true
        },
        position: {
            type: String,
            required: true
        }
    }
}
</script>

<style lang="scss" scoped>
.avatar-group {

    &__user {
        font-size: 1.4rem;
        line-height: 1.9rem;
    }

    &__position {
        font-size: 1.4rem;
        line-height: 1.9rem;
        color: #404040;
    }
}
</style>