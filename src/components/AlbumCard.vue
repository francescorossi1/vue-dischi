<template>
    <div class="col album-card">
        <figure class="p-3 h-100">
            <img :src="albumDetails.poster" :alt="albumDetails.title" class="img-fluid mb-3">
            <figcaption class="h-100 text-center">
                <h5 class="mb-3 text-white">{{ albumDetails.title.toUpperCase() }}</h5>
                <div class="text-muted">{{ albumDetails.author }}</div>
                <div class="text-muted">{{ albumDetails.year }}</div>
            </figcaption>
        </figure>
    </div>
</template>

<script>
export default {
    name: 'AlbumCard',
    props: { albumDetails: Object }
}
</script>

