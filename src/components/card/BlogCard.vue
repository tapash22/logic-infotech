<template>
    <div class="blog-content">
        <div v-for="blogL in blogList" :key="blogL.id" class="relative w-full h-auto group my-10">
            <div class="blog-part-image-block">
                <img :src="blogL.image"
                    class="blog-card-image" />
            </div>
            <div class="blog-date-part">
                <p class="blog-date-part-date">
                    {{ blogL.day }}
                </p>
                <p class="blog-date-part-month">
                    {{ blogL.month }}
                </p>
            </div>

            <div class="blog-card-details">
                <ul class="blog-card-details-block">
                    <li class="blog-card-details-block-list" v-for="bl in blogL.infoList" :key="bl.id">
                        <i :class="bl.icon" class="blog-card-details-block-list-icon"></i>
                        <span v-if="bl.count" class="blog-card-details-block-list-count">{{ bl.count }}</span>
                        <span class="blog-card-details-block-list-name">
                            {{ bl.title }}
                        </span>
                    </li>
                </ul>
                <p class="blog-card-details-block-list-title">
                    {{ blogL.title }}
                </p>
                <p class="blog-card-details-block-list-link">
                    Read More <i class="fa fa-arrow-right blog-card-details-block-list-link-icon"></i>
                </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['blogList']
}
</script>

<style>

</style>