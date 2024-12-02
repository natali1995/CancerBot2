<script setup lang="ts">
import { ref } from 'vue';

const scrollInvoked = ref(0);

// Method to handle scroll events
const onScroll = () => {
  scrollInvoked.value++;
};
</script>

<template>
  <v-card
    v-scroll.self="onScroll"
    class="overflow-y-auto block"
    min-height="1100"
    max-height="1100"
  >
    <template
      #text
    >
      <div class="banner-title">
        Trial Title
      </div>
      <div class="banner-link">
        <a
          href="https://example.com"
          target="_blank"
        >
          https://www.trial-title.com</a>
      </div>
    </template>
    <v-card-text>
      <div
        class="mb-4 text-justify"
      >
        Lorem ipsum dolor sit amet consectetur. Augue ac mattis nulla interdum sit. Augue venenatis ridiculus amet montes arcu leo fusce. Vitae odio tortor quam sit blandit mi. Nulla posuere volutpat tellus purus fringilla bibendum.
        Nisl sed consectetur sed et rhoncus. Felis amet imperdiet et aliquam cras rhoncus nisl. Varius pellentesque neque urna varius malesuada. Vulputate eu velit aliquam duis rhoncus vel. Egestas cursus purus justo potenti facilisi facilisis. Phasellus ultricies iaculis ut euismod nibh cursus orci dui ac. Tellus lectus nec et nibh arcu a. Sed nibh maecenas proin nisl. Pretium lorem fermentum cursus proin nec id augue.
        Mi vulputate penatibus molestie scelerisque adipiscing. Pretium volutpat duis platea sed nec nulla lacus vestibulum eu. Vel in phasellus vel ornare tristique velit. Nisi faucibus et nunc ut mi commodo vel a. Id dignissim molestie sit iaculis. Nibh venenatis pulvinar luctus mauris et libero. Sagittis dignissim aliquet pellentesque commodo semper sagittis mauris sapien.
        Dis vulputate amet posuere tincidunt. Lacinia id semper urna blandit nunc. Rutrum pellentesque enim aliquam elementum nibh id tortor duis. Sit sit et magna in phasellus viverra arcu. Volutpat consectetur integer velit enim ultricies venenatis eu aliquam odio. Blandit nulla et lacus mattis in turpis ut aliquet porta. Elementum elit id eleifend parturient vitae ut feugiat faucibus. Amet nulla rhoncus integer odio quis.
        Dolor a duis adipiscing blandit fermentum fermentum interdum est quis. Pharetra lectus placerat orci sed leo leo nibh nisl. Id in sit mattis ultrices est tempus amet id. Lectus ridiculus nisl at non mi id. Vel ut odio sit diam. Convallis porta enim fusce nec tincidunt adipiscing hendrerit etiam vel. Lectus augue id rutrum tempus massa. Eu fames iaculis mauris cras.
        Tristique in elementum nisl risus nunc eget. Pretium ipsum at morbi nibh cum augue praesent mi augue. Nisi in tellus vestibulum commodo nisi quam. Metus interdum velit enim libero in quisque. Semper sed sit commodo cursus nisl morbi nascetur proin tellus. Velit et dictumst ultrices et mus ultrices morbi mattis. Risus mauris nisi sagittis faucibus diam pharetra lectus amet. Tortor mauris consequat sem diam sed etiam.
        Vulputate mus velit purus scelerisque sit massa viverra et. Pellentesque nec enim pulvinar dictum elit quam accumsan. Morbi adipiscing facilisis mollis condimentum sed. Fermentum ornare hac egestas neque aliquam quisque semper vulputate. Et pellentesque dictumst amet eget at quisque. Aliquet in placerat malesuada nunc turpis nunc tincidunt curabitur ac. Imperdiet at arcu tristique fringilla nulla ut eleifend enim felis.
        Ipsum eget sit neque imperdiet eget pharetra. Dignissim et amet ipsum et cum venenatis mauris. Vel mauris nunc diam amet ornare mauris. Quam duis pharetra quam aenean quis nibh ultrices pharetra. Nec augue neque a leo quis ut congue. Malesuada faucibus maecenas est id et dictum. Nisi ipsum orci eu adipiscing. Enim sit sapien amet in. Pellentesque arcu sit diam semper nunc at. Et velit eu orci diam nulla quam massa pellentesque auctor. Pulvinar tellus pulvinar ullamcorper consectetur. Vitae amet tellus arcu varius donec velit pulvinar. Pretium justo nunc sagittis enim condimentum in parturient sollicitudin lacus.
        Consequat nibh tellus quis et. Mauris pellentesque ac massa scelerisque. Tincidunt sit in dignissim vitae. Quisque scelerisque facilisis lobortis id et metus risus. Sit malesuada non nunc ultrices pharetra erat sodales. Vestibulum eu arcu quis pharetra nulla. Nisl odio etiam laoreet adipiscing massa amet. Non nunc sed neque varius scelerisque aliquam ac. Ultricies nisl adipiscing auctor pellentesque nibh tortor etiam ornare dolor. Tellus a cursus ut malesuada vivamus dignissim.
        Porta vitae venenatis ac morbi non condimentum. Cursus morbi varius adipiscing amet eget felis at vitae tristique. In aliquet ut tristique aliquam vitae ornare dolor odio est. Integer malesuada turpis cursus donec consequat. Suscipit purus ullamcorper nibh lectus at faucibus enim aliquam egestas. Tellus laoreet et id etiam. A fermentum posuere risus magna eget eget. Amet diam elit eu sed mauris amet. A morbi ultrices quis odio ullamcorper suspendisse. Morbi facilisis volutpat quam habitant diam ultrices. Dis risus dui natoque arcu aliquam ridiculus posuere vulputate egestas. Cras nisl dictum convallis nisi ornare viverra eget amet orci. Nunc sagittis pulvinar mauris volutpat egestas. Commodo aliquet proin dignissim dui convallis cursus.
      </div>
    </v-card-text>
  </v-card>
</template>

<style scoped>
.block {
  flex: 1;
  border: solid 2px #4073ff;
  padding: 16px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  text-align: center; /* Center content within the blocks */
}

/* Import and define PT Serif font */
@font-face {
  font-family: 'EBGaramond';
  src: url('@/assets/fonts/EBGaramond-Bold.ttf') format('truetype');
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: 'PT Serif';
  src: url('@/assets/fonts/PTSerif-Regular.ttf') format('truetype');
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: 'Georgia';
  src: url('@/assets/fonts/Georgia.ttf') format('truetype');
  font-weight: normal;
  font-style: normal;
}

/* Ensure the title and link are block-level and spaced out */
.banner-title {
  font-family: 'EBGaramond', serif;
  display: block;
  text-align: center;
  font-size: 24px; /* Adjust as needed */
  color: #3c3c3c;
}

.banner-link {
  display: block; /* Force the link onto a new line */
  text-align: center; /* Center align the link */
  margin-top: 8px; /* Add spacing between the title and the link */
}

.banner-link a {
  text-decoration: none; /* Remove underline */
  color: #4073ff; /* Link color */
  font-size: 0.8rem; /* Adjust link font size */
  font-family: 'PT Serif', serif;
}

.banner-link a:hover {
  text-decoration: underline; /* Add underline on hover */
}

.v-card-text {
  font-family: 'Georgia', serif;
  font-size: 1rem;
  color: #3c3c3c;
}
</style>
