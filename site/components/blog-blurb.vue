<template>
    <div class="blog" :class="category">
        <div id="author">
            Sample Author
        </div>
        <div id="title">
            Sample Title
        </div>
        <div id="content">
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras eget quam in neque tincidunt interdum et ac ante. Donec accumsan eros sed dolor pharetra facilisis. Cras interdum dui eget ex cursus, eu consequat velit maximus. Aenean quis viverra libero. Morbi convallis, elit sit amet maximus tempor, odio nibh hendrerit orci, eu congue ex mi sit amet magna. Sed et consequat quam, sed consequat nisl. Quisque mattis orci sit amet dignissim consectetur. Praesent a quam aliquam, posuere elit vel, interdum tortor. Cras molestie vitae risus ut condimentum. Praesent ante diam, fringilla vel tincidunt eget, fringilla id neque. Ut et ligula risus.

Vestibulum in iaculis purus. In in arcu vitae leo vulputate mollis. Suspendisse tincidunt sapien nisl, ut pellentesque magna pretium in. In vitae nulla eleifend, volutpat magna at, suscipit magna. Sed efficitur pretium ante, in ornare elit tristique eget. Nam ultricies, nibh imperdiet aliquet iaculis, eros augue pulvinar elit, laoreet porttitor nulla ipsum nec tellus. In ullamcorper sodales euismod. Aliquam gravida vulputate enim in suscipit. Praesent maximus pellentesque posuere. Fusce a bibendum erat, in hendrerit purus.

Integer suscipit justo sit amet magna pulvinar, eu efficitur augue blandit. Aliquam at cursus nulla, a condimentum odio. Praesent nec metus dui. Morbi id fringilla orci. Donec ut odio in eros feugiat rhoncus. Etiam tempor libero vitae magna fringilla, in egestas ipsum finibus. Cras ullamcorper mi sit amet est consequat ornare. Vivamus magna urna, maximus ut mattis id, aliquet vitae ligula. In auctor lacus a porttitor cursus. Curabitur non enim a diam gravida tincidunt.

Donec vel neque hendrerit, rhoncus neque at, porttitor ligula. Donec scelerisque ipsum est, ut vulputate purus maximus sed. Phasellus mattis viverra varius. Aliquam molestie ut orci sit amet volutpat. Nullam ullamcorper nibh quam, vel facilisis nunc maximus ac. Donec vel elit id ligula cursus maximus. Duis sodales sem a nunc sodales, eu semper ligula vestibulum. Ut vitae varius nisi, ut feugiat dui. Curabitur at tellus ac lectus pharetra cursus. Duis quam mi, gravida in diam eget, dapibus luctus lorem.

Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Morbi condimentum tortor molestie, venenatis enim eu, maximus enim. Quisque fringilla diam sed neque dictum, id tristique felis dignissim. Vestibulum vehicula, nisl ut sodales tincidunt, augue elit vehicula orci, ut ultricies magna arcu non mauris. Donec at gravida mi. Praesent nec auctor magna. Proin porttitor, tortor sed ornare porttitor, purus erat dictum augue, nec vulputate nisl massa non ante. In eget maximus nulla, sed vulputate mauris. Vivamus eu lobortis neque, vel consequat nisl. Praesent metus urna, semper at turpis vel, placerat maximus neque. Suspendisse potenti. Duis ut vestibulum quam, vitae dapibus ante. Sed eleifend nunc eros, in rhoncus dolor accumsan euismod. 
        </div>
    </div>
</template>

<style scoped>
    @import '/styles/blog-blurb.css';
</style>

<script setup>
    const props = defineProps({
        category: String,
        author: String,
        content: String,
        title: String
    });
</script>