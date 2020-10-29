<script>
  export let icon;
  export let style = "Solid";
  //Styles : Solid, Regular, Light, DuoTone, Brands

  let iconStyle = "";
  switch (style) {
    case "Solid":
      iconStyle = "fas";
      break;
    case "Regular":
      iconStyle = "far";
      break;
    case "Light":
      iconStyle = "fal";
      break;
    case "DuoTone":
      iconStyle = "fad";
      break;
    case "Brands":
      iconStyle = "fab";
      break;
  }
</script>

<style>
  i {
    width: 1rem;
    height: 1rem;
    display: inline-flex;
    align-items: center;
    justify-content: center;
  }
</style>

<i class="{iconStyle} fa-{icon}" />
