<script>
  // @ts-nocheck

  // @ts-ignore
  import { stores } from "./stores.js";
  import { onMount } from "svelte";
  import mapboxgl from "mapbox-gl";
  mapboxgl.accessToken =
    "pk.eyJ1Ijoic2NpdG9ubWFya2V0aW5nIiwiYSI6ImNrd28wYWV2ZzA2MHczMHBhYXBtbWs1bGwifQ.X3UptPPy16vEa8G9lKH46A";

  const storeArr = stores.features;
  stores.features.forEach(function (store, i) {
    store.properties.id = i;
  });

  let loadedMap;

  function createPopUp(currentFeature) {
    const popup = new mapboxgl.Popup({
      closeOnClick: false,
      focusAfterOpen: false,
    })
      .setLngLat(currentFeature.geometry.coordinates)
      .setHTML(
        `<div style="border-radius:3px;font-family:adrianna;height:200px;width:200px;display:grid;grid-template-columns:1fr;"><h3 style="font-size:16px;font-weight:600;text-align:center;width:100%;">${currentFeature.properties.title}</h3><h4 style="font-size:15px;text-align:center;width:100%;">${currentFeature.properties.address}<br>${currentFeature.properties.city}, ${currentFeature.properties.state}<br>${currentFeature.properties.postalCode}</h4><a href=${currentFeature.properties.website} target="_blank" style="display:flex;justify-content:center;align-items:center;text-decoration:none;margin:auto;font-size:12px;width:80%;height:50px;color:#fafafa;background-color:#bfa888;border:none;border-radius:5px;">BOOK APPOINTMENT</a></div>`
      )
      .addTo(loadedMap);
  }

  let activeStoreSelect = null;
  function flyToStore(currentFeature) {
    const popUps = document.getElementsByClassName("mapboxgl-popup");

    if (popUps[0]) popUps[0].remove();

    createPopUp(currentFeature);

    activeStoreSelect = currentFeature.properties.id;
    loadedMap.flyTo({
      center: currentFeature.geometry.coordinates,
      zoom: 17,
    });
  }

  onMount(() => {
    const dfw = new mapboxgl.LngLat(-97, 32.75);
    var map = new mapboxgl.Map({
      container: "map",
      style: "mapbox://styles/mapbox/light-v10",
      center: dfw,
      zoom: 8.5,
      scrollZoom: false,
    });
    loadedMap = map;

    map.on("style.load", () => {
      map.setFog({}); // Set the default atmosphere style
    });
    map.on("load", () => {
      /* Add the data to your map as a layer */
      map.addLayer({
        id: "locations",
        type: "circle",
        /* Add a GeoJSON source containing place coordinates and information. */
        source: {
          type: "geojson",
          data: stores,
        },
      });
    });
    map.on("mouseenter", "locations", () => {
      map.getCanvas().style.cursor = "pointer";
    });

    // Change it back to a pointer when it leaves.
    map.on("mouseleave", "locations", () => {
      map.getCanvas().style.cursor = "";
    });

    map.on("click", "locations", (e) => {
      const popUps = document.getElementsByClassName("mapboxgl-popup");
      /** Check if there is already a popup on the map and if so, remove it */
      if (popUps[0]) popUps[0].remove();

      activeStoreSelect = e.features[0].properties.id;

      const coordinates = e.features[0].geometry.coordinates.slice();
      const description = `<div style="font-family:adrianna;height:200px;width:200px;display:grid;grid-template-columns:1fr;"><h3 style="font-size:15px;font-weight:600;text-align:center;width:100%;">${e.features[0].properties.title}</h3><h4 style="font-size:15px;text-align:center;width:100%;">${e.features[0].properties.address}<br>${e.features[0].properties.city}, ${e.features[0].properties.state}<br>${e.features[0].properties.postalCode}</h4><button style="margin:auto;font-size:12px;width:80%;height:50px;color:#fafafa;background-color:#bfa888;border:none;border-radius:5px;">BOOK APPOINTMENT</button></div>`;

      while (Math.abs(e.lngLat.lng - coordinates[0]) > 180) {
        coordinates[0] += e.lngLat.lng > coordinates[0] ? 360 : -360;
      }

      new mapboxgl.Popup({ focusAfterOpen: false })
        .setLngLat(coordinates)
        .setHTML(description)
        .addTo(map);
    });

    map.addControl(
      new mapboxgl.GeolocateControl({
        positionOptions: {
          enableHighAccuracy: true,
        },
        // When active the map will receive updates to the device's location as it changes.
        trackUserLocation: true,
        // Draw an arrow next to the location dot to indicate which direction the device is heading.
        showUserHeading: true,
      })
    );
    map.addControl(new mapboxgl.NavigationControl());
  });

  let stringToMatch = "";
  let providerMatch = "";

  function getFilteredStores(storeArr, stringToMatch, providerMatch) {
    stringToMatch.toString();
    if (stringToMatch) {
      return storeArr.filter((store) => {
        return (
          store.properties.postalCode
            .toLowerCase()
            .includes(stringToMatch.toLowerCase()) ||
          store.properties.city
            .toLowerCase()
            .includes(stringToMatch.toLowerCase())
        );
      });
    } else {
      storeArr;
    }

    if (providerMatch) {
      return storeArr.filter((store) => {
        return store.properties.title
          .toLowerCase()
          .includes(providerMatch.toLowerCase());
      });
    } else {
      return storeArr;
    }
  }
</script>

<main>
  <div class="sidebar">
    <div class="heading">
      <h1 class="map__title">
        Find Your Local <br /> BBL HERO Providers
      </h1>
      <p>Filter Results</p>
      <div class="map__search">
        <input
          placeholder="City or Zip"
          bind:value={stringToMatch}
          class="map__input"
        />
      </div>
    </div>
    <div id="listings" class="listings-sidebar">
      {#each getFilteredStores(storeArr, stringToMatch, providerMatch) as store, i}
        <div class="map__store" id={store.properties.id}>
          <div class="map__store--c-buttons">
            <button
              class={activeStoreSelect === store.properties.id
                ? "map__store--title-active"
                : "map__store--title"}
              on:click={() => flyToStore(store)}
              >{store.properties.title}</button
            >
            <a
              href={store.properties.website}
              target="_blank"
              class="map__store--book">BOOK APPOINTMENT</a
            >
          </div>

          <div>
            <div>
              <p class="map__store--desc">{store.properties.address}</p>
              <p class="map__store--desc">
                {store.properties.city}, {store.properties.state}
              </p>
              <p class="map__store--desc">{store.properties.postalCode}</p>
              <p class="map__store--desc">{store.properties.phoneFormatted}</p>
              <a
                href={store.properties.website}
                target="_blank"
                class="map__store--book map__store--book--mobile"
                >BOOK APPOINTMENT</a
              >
            </div>
            <div />
          </div>
        </div>
      {/each}
    </div>
  </div>
  <div id="map" class="map" />
</main>

<style>
  main {
    width: 100%;
    min-height: 500px;
    height: 75vh;
    display: grid;
    grid-template-columns: 2fr 3fr;
  }

  h1 {
    font-size: 22px;
    margin: 0;
    font-weight: 400;
    line-height: 20px;
    padding: 20px 2px;
  }

  .sidebar {
    height: 100%;
    overflow: hidden;
    border-right: 1px solid rgba(0, 0, 0, 0.25);
    min-width: 500px;
  }

  .map {
    height: 100%;
  }

  .heading {
    background: var(--secondary);
    height: 250px;
    border-bottom-right-radius: 15px;
    display: grid;
    grid-template-columns: 1fr;
  }

  .map__store {
    height: auto;
    min-height: 150px;
    width: 100%;
  }

  .map__title {
    color: var(--offWhite);
    font-family: var(--ivyMode);
    width: 90%;
    font-size: 40px;
    line-height: 1.2;
    margin: auto;
  }

  .heading p {
    color: var(--offWhite);
    font-family: var(--ivyMode);
    width: 90%;
    font-size: 15px;
    margin: auto;
  }

  .listings-sidebar {
    height: calc(100% - 250px);
    overflow-y: scroll;
  }

  .listings-sidebar::-webkit-scrollbar {
    -webkit-appearance: none;
  }

  .listings-sidebar::-webkit-scrollbar:vertical {
    width: 11px;
  }

  .listings-sidebar::-webkit-scrollbar-thumb {
    border-radius: 8px;
    border: 2px solid white;
    background-color: rgba(0, 0, 0, 0.5);
  }

  .map__store--c-buttons {
    width: 90%;
    display: grid;
    grid-template-columns: 2fr 1fr;
    height: 75px;
    border-bottom: 1px solid var(--secondary);
    margin: auto;
  }

  .map__store--title {
    background-color: var(--offWhite);
    border: none;
    color: var(--primary);
    padding: none;
    font-family: var(--adrianna);
    font-size: 20px;
    text-align: left;
    font-weight: 600;
  }

  .map__store--title:hover {
    cursor: pointer;
    color: var(--secondary);
    transform: all ease 2s;
  }

  .map__store--title-active {
    color: var(--secondary);
    background-color: var(--offWhite);
    border: none;
    padding: none;
    font-family: var(--adrianna);
    font-size: 20px;
    text-align: left;
    font-weight: 600;
  }

  .map__store--book {
    height: 40px;
    margin: auto;
    width: 150px;
    font-size: 12px;
    color: var(--offWhite);
    background-color: var(--secondary);
    border-radius: 5px;
    border: none;
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: var(--adrianna);
    text-decoration: none;
  }
  .map__store--book--mobile {
    display: none;
  }

  .map__store--book:hover {
    cursor: pointer;
  }

  .map__search {
    display: flex;
    width: 90%;
    margin: auto;
    justify-content: flex-start;
    align-items: center;
  }
  .map__input {
    border: 1px solid lightgrey;
    border-radius: 5px;
    height: 30px;
    padding: 0 5px;
    width: 40%;
  }
  .map__input:focus {
    outline: none;
  }
  .map__input:nth-child(2) {
    margin-left: 15px;
  }

  .map__store--desc {
    margin: auto;
    width: 90%;
    color: rgba(0, 0, 0, 0.473);
    padding-top: 3px;
  }
  .map__store--desc:nth-child(1) {
    padding-top: 10px;
  }

  ::-webkit-scrollbar {
    width: 3px;
    height: 3px;
    border-left: 0;
  }

  ::-webkit-scrollbar-track {
    background: none;
  }

  ::-webkit-scrollbar-thumb {
    border-radius: 0;
  }

  @media screen and (max-width: 1000px) {
    main {
      grid-template-columns: 1fr;
      height: 800px;
    }
    .sidebar {
      grid-row: 2;
      display: grid;
      grid-template-columns: 1fr;
      min-width: auto;
    }
    .heading {
      height: 100px;
      border-radius: 0;
    }
    .map__title {
      display: none;
    }
    .listings-sidebar {
      height: 100%;
    }
    .map__search {
      margin: auto;
    }
    .map {
      height: 400px;
      width: 100%;
    }
  }
  @media screen and (max-width: 600px) {
    .map {
      height: 300px;
    }
    .map__store--c-buttons {
      grid-template-columns: 1fr;
    }
    .map__store--book {
      display: none;
    }

    .map__store--book--mobile {
      margin: 15px auto 0 5%;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: var(--adrianna);
      text-decoration: none;
    }
  }
</style>
