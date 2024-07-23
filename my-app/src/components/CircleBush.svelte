<!-- SCRIPTS ////////////////////////////////////// -->
<script>
  // IMPORTS -------------------------------
  import randomRange from "../scripts/randomRange";

  // SVG VARIABLES ------------------------------------------
  const svgSize = {width: 500, height: 1000};
  const svgPosition = {x: 100, y: 200};

  // CIRCLE VARIABLES ---------------------------------------
  const number = 300;
  const size = {min: 10, max: 20};
  const strokeSize = {min: 1, max: 2};
  const opacity = 0.5;
  const color = {
    hue: {min:0, max:5}, 
    saturation: {min: 90, max: 100}, 
    lightness: {min: 50, max: 55}
  };

  // ARRAY -----------------------------
  const array = new Array(number);

</script>

<!-- MARKUP ///////////////////////////////////////// -->
<svg style:width={svgSize.width}
  style:height={svgSize.height}
  style:left={svgPosition.x}
  style:top={svgPosition.y}
>
  {#each array as circle}
    <circle cx={randomRange(0,svgSize.width)} cy={randomRange(0,svgSize.height)} 
      r={randomRange(size.min, size.max)}
      fill={`hsla(${randomRange(color.hue.min, color.hue.max)}, ${randomRange(color.saturation.min, color.saturation.max)}%, ${randomRange(color.lightness.min, color.lightness.max)}%, ${opacity})`}
      stroke={`hsla(0, 100%, 100%, ${opacity})`}
      stroke-width={randomRange(strokeSize.min,strokeSize.max)}
    />
  {/each}
</svg>

<!-- STYLES ///////////////////////////////////////////// -->
<style>
svg {
  position: absolute;
  border: 4px solid hsla(0, 100%, 10%);
}
</style>
