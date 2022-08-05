<template>
    <main class="w-screen h-screen">
        <v-map class="w-full h-full" :options="state.map" />
    </main>
</template>
<script lang="ts">
import VMap from "v-mapbox";
export default defineComponent({
    name: "CommonMap",
    components: {
        VMap,
    },
    setup() {
        const state = reactive({
            map: {
                container: "map",
                accessToken:
                    "pk.eyJ1IjoiYWthc2hheS1ob3N1cmthciIsImEiOiJjbDZnZjlpajYwcXI0M2RvcjMxb3NtenJ0In0.b84huBKG717zaOvLyAjkeg",
                style: "mapbox://styles/mapbox/streets-v11?optimize=true",
                // style: "https://basemaps.cartocdn.com/gl/dark-matter-gl-style/style.json",
                center: [73.7868, 18.5590] as number[],
                zoom: 2,
                maxZoom: 22,
                crossSourceCollisions: false,
                failIfMajorPerformanceCaveat: false,
                preserveDrawingBuffer: true,
                hash: false,
                minPitch: 0,
                attributionControl: false,
                maxPitch: 60,
            },
        });
        return {
            state,
        };
    },
});
</script>
<style>
.w-screen {
    width: 100vw;
}
.h-screen {
    height: 100vh;
}
.h-full {
    height: 100%;
}
.w-full {
    width: 100%;
}
</style>

