<script>
  export let icon;

  //Styles : Solid, Regular, Light, DuoTone, Brands
  let style = "Light";
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

<i class="fa {iconStyle} fa-{icon}" />
