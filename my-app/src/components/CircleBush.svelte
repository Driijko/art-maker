<!-- SCRIPTS ////////////////////////////////////// -->
<script>
  // IMPORTS -------------------------------
  import randomRange from "../scripts/randomRange";

  // SVG VARIABLES ------------------------------------------
  const svgSize = {width: window.innerWidth, height: window.innerHeight};
  const svgPosition = {x: 0, y: 0};

  // CIRCLE VARIABLES ---------------------------------------
  const number = 100;
  const size = {min: 10, max: 100};
  const strokeSize = {min: 1, max: 5};
  const opacity = 1;
  const color = {
    hue: {min:100, max:105}, 
    saturation: {min: 90, max: 100}, 
    lightness: {min: 80, max: 85}
  };
  const strokeColor = {
    hue: {min: 100, max: 105},
    saturation: {min: 90, max: 100},
    lightness: {min: 80, max: 90},
  };

  // ARRAY -----------------------------
  const array = [];
  for (let i = 0 ; i < number ; i++) {
    array[i] = {x: randomRange(0, window.innerWidth), y: randomRange(0, window.innerHeight)};
  };

</script>

<!-- MARKUP ///////////////////////////////////////// -->
<svg style:width={svgSize.width}
  style:height={svgSize.height}
  style:left={svgPosition.x}
  style:top={svgPosition.y}
>
  <!-- <g id="circles">
  {#each array as circle}
    <circle cx={circle.x} cy={circle.y} 
      r={randomRange(size.min, size.max)}
      fill={`hsla(${randomRange(color.hue.min, color.hue.max)}, ${randomRange(color.saturation.min, color.saturation.max)}%, ${randomRange(color.lightness.min, color.lightness.max)}%, ${opacity})`}
      stroke={`hsla(
      ${randomRange(strokeColor.hue.min, strokeColor.hue.max)}, 
      ${randomRange(strokeColor.saturation.min, strokeColor.saturation.max)}%, ${randomRange(strokeColor.lightness.min, strokeColor.lightness.max)}%, ${opacity})`}
      stroke-width={randomRange(strokeSize.min,strokeSize.max)}
    />
  {/each}
  </g> -->
  <!-- <clipPath id="cp">
    <use href="#circles" />
  </clipPath> -->
  <!-- <image clip-path="url(#cp)" href="./image1.jpg" height={window.innerHeight} x="0" y="0" /> -->
   <defs>
    <clipPath id="circles">
      {#each array as circle}
      <circle cx={circle.x} cy={circle.y} 
        r={randomRange(size.min, size.max)}
        fill={`hsla(${randomRange(color.hue.min, color.hue.max)}, ${randomRange(color.saturation.min, color.saturation.max)}%, ${randomRange(color.lightness.min, color.lightness.max)}%, ${opacity})`}
        stroke={`hsla(
        ${randomRange(strokeColor.hue.min, strokeColor.hue.max)}, 
        ${randomRange(strokeColor.saturation.min, strokeColor.saturation.max)}%, ${randomRange(strokeColor.lightness.min, strokeColor.lightness.max)}%, ${opacity})`}
        stroke-width={randomRange(strokeSize.min,strokeSize.max)}
      />
    {/each}
    </clipPath>
   </defs>
   <image clip-path="url(#circles)" href="./image1.jpg" width={window.innerWidth} x="0" y="0" />
</svg>

<!-- STYLES ///////////////////////////////////////////// -->
<style>
svg {
  position: absolute;
  border: 4px solid hsla(0, 100%, 10%);
}
image {
  opacity: 1;
}
</style>
