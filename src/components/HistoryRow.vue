<template>
  <div>
    <h3 style="text-align: center;">My Google Maps Demo</h3>
    <div id="map"></div>
  </div>
</template>

<style type="text/css">
  #map {
    width: 50%;
    height: 400px;
    background-color: grey;
    margin-left: 25%;
  }
</style>

<script>
  function initMap() {
    var uluru = {lat: 42.4506983, lng: -76.48};
    var map = new google.maps.Map(document.getElementById('map'), {
      zoom: 14,
      center: uluru
    });
    var marker = new google.maps.Marker({
      position: uluru,
      map: map
    });
  }
</script>
<script async defer
  src="https://maps.googleapis.com/maps/api/js?key=AIzaSyC-2XyglkiO02UPyKwBNnHslzyFHDrOa_0&callback=initMap">
</script>