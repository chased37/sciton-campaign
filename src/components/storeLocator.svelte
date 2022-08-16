<script>
  import { onMount } from "svelte";
  import mapboxgl from "mapbox-gl";
  mapboxgl.accessToken =
    "pk.eyJ1Ijoic2NpdG9ubWFya2V0aW5nIiwiYSI6ImNrd28wYWV2ZzA2MHczMHBhYXBtbWs1bGwifQ.X3UptPPy16vEa8G9lKH46A";

  const stores = {
    type: "FeatureCollection",
    features: [
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [-77.034084142948, 38.909671288923],
        },
        properties: {
          phoneFormatted: "(202) 234-7336",
          phone: "2022347336",
          address: "1471 P St NW",
          city: "Washington DC",
          country: "United States",
          crossStreet: "at 15th St NW",
          postalCode: "20005",
          state: "D.C.",
        },
      },
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [-77.049766, 38.900772],
        },
        properties: {
          phoneFormatted: "(202) 507-8357",
          phone: "2025078357",
          address: "2221 I St NW",
          city: "Washington DC",
          country: "United States",
          crossStreet: "at 22nd St NW",
          postalCode: "20037",
          state: "D.C.",
        },
      },
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [-77.043929, 38.910525],
        },
        properties: {
          phoneFormatted: "(202) 387-9338",
          phone: "2023879338",
          address: "1512 Connecticut Ave NW",
          city: "Washington DC",
          country: "United States",
          crossStreet: "at Dupont Circle",
          postalCode: "20036",
          state: "D.C.",
        },
      },
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [-77.0672, 38.90516896],
        },
        properties: {
          phoneFormatted: "(202) 337-9338",
          phone: "2023379338",
          address: "3333 M St NW",
          city: "Washington DC",
          country: "United States",
          crossStreet: "at 34th St NW",
          postalCode: "20007",
          state: "D.C.",
        },
      },
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [-77.002583742142, 38.887041080933],
        },
        properties: {
          phoneFormatted: "(202) 547-9338",
          phone: "2025479338",
          address: "221 Pennsylvania Ave SE",
          city: "Washington DC",
          country: "United States",
          crossStreet: "btwn 2nd & 3rd Sts. SE",
          postalCode: "20003",
          state: "D.C.",
        },
      },
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [-76.933492720127, 38.99225245786],
        },
        properties: {
          address: "8204 Baltimore Ave",
          city: "College Park",
          country: "United States",
          postalCode: "20740",
          state: "MD",
        },
      },
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [-77.097083330154, 38.980979],
        },
        properties: {
          phoneFormatted: "(301) 654-7336",
          phone: "3016547336",
          address: "4831 Bethesda Ave",
          cc: "US",
          city: "Bethesda",
          country: "United States",
          postalCode: "20814",
          state: "MD",
        },
      },
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [-77.359425054188, 38.958058116661],
        },
        properties: {
          phoneFormatted: "(571) 203-0082",
          phone: "5712030082",
          address: "11935 Democracy Dr",
          city: "Reston",
          country: "United States",
          crossStreet: "btw Explorer & Library",
          postalCode: "20190",
          state: "VA",
        },
      },
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [-77.10853099823, 38.880100922392],
        },
        properties: {
          phoneFormatted: "(703) 522-2016",
          phone: "7035222016",
          address: "4075 Wilson Blvd",
          city: "Arlington",
          country: "United States",
          crossStreet: "at N Randolph St.",
          postalCode: "22203",
          state: "VA",
        },
      },
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [-75.28784, 40.008008],
        },
        properties: {
          phoneFormatted: "(610) 642-9400",
          phone: "6106429400",
          address: "68 Coulter Ave",
          city: "Ardmore",
          country: "United States",
          postalCode: "19003",
          state: "PA",
        },
      },
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [-75.20121216774, 39.954030175164],
        },
        properties: {
          phoneFormatted: "(215) 386-1365",
          phone: "2153861365",
          address: "3925 Walnut St",
          city: "Philadelphia",
          country: "United States",
          postalCode: "19104",
          state: "PA",
        },
      },
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [-77.043959498405, 38.903883387232],
        },
        properties: {
          phoneFormatted: "(202) 331-3355",
          phone: "2023313355",
          address: "1901 L St. NW",
          city: "Washington DC",
          country: "United States",
          crossStreet: "at 19th St",
          postalCode: "20036",
          state: "D.C.",
        },
      },
    ],
  };

  const storeArr = stores.features;
  stores.features.forEach(function (store, i) {
    store.properties.id = i;
  });

  //   function buildLocationList(stores) {
  //     for (const store of stores.features) {
  //       /* Add a new listing section to the sidebar. */
  //       const listings = document.getElementById("listings");
  //       const listing = listings.appendChild(document.createElement("div"));
  //       /* Assign a unique `id` to the listing. */
  //       listing.id = `listing-${store.properties.id}`;
  //       /* Assign the `item` class to each listing for styling. */
  //       listing.className = "item";

  //       /* Add the link to the individual listing created above. */
  //       const link = listing.appendChild(document.createElement("a"));
  //       link.href = "#";
  //       link.className = "title";
  //       link.id = `link-${store.properties.id}`;
  //       link.innerHTML = `${store.properties.address}`;

  //       /* Add details to the individual listing. */
  //       const details = listing.appendChild(document.createElement("div"));
  //       details.innerHTML = `${store.properties.city}`;
  //       if (store.properties.phone) {
  //         details.innerHTML += ` · ${store.properties.phoneFormatted}`;
  //       }
  //       if (store.properties.distance) {
  //         const roundedDistance =
  //           Math.round(store.properties.distance * 100) / 100;
  //         details.innerHTML += `<div><strong>${roundedDistance} miles away</strong></div>`;
  //       }
  //     }
  //   }

  onMount(() => {
    var map = new mapboxgl.Map({
      container: "map",
      style: "mapbox://styles/mapbox/light-v10",
      center: [-77.034084, 38.909671],
      zoom: 13,
      scrollZoom: false,
    });
    function flyToStore(currentFeature) {
      map.flyTo({
        center: currentFeature.geometry.coordinates,
        zoom: 15,
      });
    }

    function createPopUp(currentFeature) {
      const popUps = document.getElementsByClassName("mapboxgl-popup");
      /** Check if there is already a popup on the map and if so, remove it */
      if (popUps[0]) popUps[0].remove();

      const popup = new mapboxgl.Popup({ closeOnClick: false })
        .setLngLat(currentFeature.geometry.coordinates)
        .setHTML(
          `<h3>Sweetgreen</h3><h4>${currentFeature.properties.address}</h4>`
        )
        .addTo(map);
    }
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
      //   buildLocationList(stores);
    });
  });
</script>

<main>
  <div class="sidebar">
    <div class="heading">
      <h1>Our locations</h1>
    </div>
    <div id="listings" class="listings">
      {#each storeArr as store, i}
        <div id={i.toString()}>
          <a href="#" inn={store.properties.address}
            >{store.properties.address}</a
          >
          <p>{store.properties.city}</p>
        </div>
      {/each}
    </div>
  </div>
  <div id="map" class="map" />
</main>

<style>
  main {
    width: 100%;
    height: 600px;
    display: grid;
    grid-template-columns: 1fr 2fr;
  }

  h1 {
    font-size: 22px;
    margin: 0;
    font-weight: 400;
    line-height: 20px;
    padding: 20px 2px;
  }
  /* 
  a {
    color: #404040;
    text-decoration: none;
  }

  a:hover {
    color: #101010;
  } */

  /* The page is split between map and sidebar - the sidebar gets 1/3, map
  gets 2/3 of the page. You can adjust this to your personal liking. */
  .sidebar {
    height: 100%;
    top: 0;
    left: 0;
    overflow: hidden;
    border-right: 1px solid rgba(0, 0, 0, 0.25);
  }

  .map {
  }

  .heading {
    background: #fff;
    border-bottom: 1px solid #eee;
    height: 60px;
    line-height: 60px;
    padding: 0 10px;
  }
  .listings {
    height: 100%;
    overflow: auto;
    padding-bottom: 60px;
  }

  .listings .item {
    border-bottom: 1px solid #eee;
    padding: 10px;
    text-decoration: none;
  }

  .listings .item:last-child {
    border-bottom: none;
  }

  .listings .item .title {
    display: block;
    color: #00853e;
    font-weight: 700;
  }

  .listings .item .title small {
    font-weight: 400;
  }

  .listings .item.active .title,
  .listings .item .title:hover {
    color: #8cc63f;
  }

  .listings .item.active {
    background-color: #f8f8f8;
  }

  ::-webkit-scrollbar {
    width: 3px;
    height: 3px;
    border-left: 0;
    background: rgba(0, 0, 0, 0.1);
  }

  ::-webkit-scrollbar-track {
    background: none;
  }

  ::-webkit-scrollbar-thumb {
    background: #00853e;
    border-radius: 0;
  }
</style>
