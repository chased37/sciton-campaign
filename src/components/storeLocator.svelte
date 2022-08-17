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
        geometry: { type: "Point", coordinates: [-96.770767, 33.01687] },
        properties: {
          phoneFormatted: "",
          address: "5508 W Plano Parkway Suite 200",
          city: "Plano",
          country: "United States",
          postalCode: "75093",
          state: "TX",
          title: "Advanced Surgical Arts",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.82231095, 32.95041743] },
        properties: {
          phoneFormatted: "",
          address: "5100 Beltline Road #320",
          city: "Dallas",
          country: "United States",
          postalCode: "75254",
          state: "TX",
          title: "Aesthetic Intelligence",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.3271504, 32.7454817] },
        properties: {
          phoneFormatted: "",
          address: "201 W. Lancaster Ave #204",
          city: "Fort Worth",
          country: "United States",
          postalCode: "76102",
          state: "TX",
          title: "Aesthetic Technologies",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.831122, 33.0158909] },
        properties: {
          phoneFormatted: "",
          address: "6020 West Plano Parkway",
          city: "Plano",
          country: "United States",
          postalCode: "75093",
          state: "TX",
          title: "American Institute for Plastic Surgery",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8108577, 33.1285116] },
        properties: {
          phoneFormatted: "",
          address: "8501 Wade Blvd Suite #1160",
          city: "Frisco",
          country: "United States",
          postalCode: "75034",
          state: "TX",
          title: "ATA Health & Wellness",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8408047, 33.1047325] },
        properties: {
          phoneFormatted: "",
          address: "3140 Legacy Drive",
          city: "Frisco",
          country: "United States",
          postalCode: "75034",
          state: "TX",
          title: "Atomic Beauty Med Spa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7712982, 32.8751442] },
        properties: {
          phoneFormatted: "",
          address: "9301 N CENTRAL EXPY STE 470",
          city: "Dallas",
          country: "United States",
          postalCode: "75231",
          state: "TX",
          title: "Austin & Reddick Dermatology",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.788174, 32.8490662] },
        properties: {
          phoneFormatted: "",
          address: "6825 Snider Plaza",
          city: "University Park",
          country: "United States",
          postalCode: "75205",
          state: "TX",
          title: "Aya Medical Spa & University Park Texas",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.4607083, 32.9144127] },
        properties: {
          phoneFormatted: "",
          address: "1307 Ridge Rd Suite 1104 Room 117",
          city: "Rockwall",
          country: "United States",
          postalCode: "75087",
          state: "TX",
          title: "Beauty Spot Rockwall",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8351361, 33.0328069] },
        properties: {
          phoneFormatted: "",
          address: "6213 Chapel Hill Blvd SUITE A",
          city: "Plano",
          country: "United States",
          postalCode: "75093",
          state: "TX",
          title: "Beyond Beautiful",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.4207717, 32.8126576] },
        properties: {
          phoneFormatted: "",
          address: "3963 Boat Club Rd",
          city: "Fort Worth",
          country: "United States",
          postalCode: "76135",
          state: "TX",
          title: "Boat Club Medical Spa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.70909779, 33.19783014] },
        properties: {
          phoneFormatted: "",
          address: "6956 Mediterranean Dr,",
          city: "McKinney",
          country: "United States",
          postalCode: "75071",
          state: "TX",
          title: "Body by Blink",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.797299, 33.0823348] },
        properties: {
          phoneFormatted: "",
          address: "4800 Hedgcoxe Suite 250",
          city: "Plano",
          country: "United States",
          postalCode: "75024",
          state: "TX",
          title: "Brobst Facial Plastic Surgery and Aesthetics",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8369148, 32.8090589] },
        properties: {
          phoneFormatted: "",
          address: "1935 Medical District Dr",
          city: "Dallas",
          country: "United States",
          postalCode: "75235",
          state: "TX",
          title: "Children's Medical Center",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7165384, 33.1430933] },
        properties: {
          phoneFormatted: "",
          address: "7850 Collin McKinney Pkwy",
          city: "McKinney",
          country: "United States",
          postalCode: "75070",
          state: "TX",
          title: "Cooper Clinic at Craig Ranch",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.1983038, 32.9347104] },
        properties: {
          phoneFormatted: "",
          address: "2900 West Southlake Blvd Suite 160",
          city: "Southlake",
          country: "United States",
          postalCode: "76092",
          state: "TX",
          title: "Corinthian Wellness Spa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8658843, 32.819076] },
        properties: {
          phoneFormatted: "",
          address: "7929 Brookriver Drive",
          city: "Dallas",
          country: "United States",
          postalCode: "75247",
          state: "TX",
          title: "Cosmetic Procedures Clinic of North Dallas",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8045717, 32.8930168] },
        properties: {
          phoneFormatted: "",
          address: "10703 Preston Rd",
          city: "Dallas",
          country: "United States",
          postalCode: "75230",
          state: "TX",
          title: "Dallas Associated Dermatologist",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7916496, 33.0140611] },
        properties: {
          phoneFormatted: "",
          address: "4716 Alliance Blvd #750",
          city: "Plano",
          country: "United States",
          postalCode: "75093",
          state: "TX",
          title: "Dallas Diagnostic Assoc. - Baylor Health",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7744115, 32.9126714] },
        properties: {
          phoneFormatted: "",
          address: "7777 Forest Lane #C303",
          city: "Dallas",
          country: "United States",
          postalCode: "75230",
          state: "TX",
          title: "Dallas Medical Spa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7662118, 32.8808555] },
        properties: {
          phoneFormatted: "",
          address: "8144 Walnut Hill Lane Ste 901",
          city: "Dallas",
          country: "United States",
          postalCode: "75231",
          state: "TX",
          title: "Dallas Premier Plastic Surgery P.L.L.C.",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8051576, 32.8929851] },
        properties: {
          phoneFormatted: "",
          address: "10707 Preston Rd",
          city: "Dallas",
          country: "United States",
          postalCode: "75230",
          state: "TX",
          title: "Dauwe Plastic Surgery",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.2874341, 32.7382882] },
        properties: {
          phoneFormatted: "",
          address: "101 Sage Suite E",
          city: "Terrell",
          country: "United States",
          postalCode: "75160",
          state: "TX",
          title: "Deja Vu MediSpa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8684053, 32.9156219] },
        properties: {
          phoneFormatted: "",
          address: "9 Medical Parkway Ste. 105",
          city: "Farmers Branch",
          country: "United States",
          postalCode: "75234",
          state: "TX",
          title: "Dermatology Consultants-Dallas",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8081956, 32.862844] },
        properties: {
          phoneFormatted: "",
          address: "8222 Douglas Ave. Suite 950",
          city: "Dallas",
          country: "United States",
          postalCode: "75225",
          state: "TX",
          title: "Dermatology Office, Dr. Ellen Turner",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8081956, 32.862844] },
        properties: {
          phoneFormatted: "",
          address: "8222 Douglas Avenue Suite 950",
          city: "Dallas",
          country: "United States",
          postalCode: "75225",
          state: "TX",
          title: "DermLaser Institute of Dallas",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.0688778, 33.0442225] },
        properties: {
          phoneFormatted: "",
          address: "2560 Central Park Ave. Suite 200",
          city: "Flower Mound",
          country: "United States",
          postalCode: "75028",
          state: "TX",
          title: "Dr. Drew Sanderson, Flowermound Plastic Surgery",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7978394, 33.0813729] },
        properties: {
          phoneFormatted: "",
          address: "7709 San Jacinto Pl #100",
          city: "Plano",
          country: "United States",
          postalCode: "75024",
          state: "TX",
          title: "Dr. Hina Rizvi",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.4112118, 32.7073608] },
        properties: {
          phoneFormatted: "",
          address: "5825 Edwards Ranch Rd Suite #200",
          city: "Fort Worth",
          country: "United States",
          postalCode: "76109",
          state: "TX",
          title: "Dr. Jon Kurkjian Plastic Surgery",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7712725, 32.8750274] },
        properties: {
          phoneFormatted: "",
          address: "9301 North Central Expressway, 551",
          city: "Dallas",
          country: "United States",
          postalCode: "75231",
          state: "TX",
          title: "Dr. Ramsey Choucair",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.3171726, 32.5863525] },
        properties: {
          phoneFormatted: "",
          address: "11807 South Freeway, Suite 361",
          city: "Burleson",
          country: "United States",
          postalCode: "76028",
          state: "TX",
          title: "Dr. Randy Lew, DPM",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7606896, 32.8816367] },
        properties: {
          phoneFormatted: "",
          address: "8230 Walnut Hill Ln #808",
          city: "Dallas",
          country: "United States",
          postalCode: "75231",
          state: "TX",
          title: "Elevate Med Spa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.2920538, 32.9143378] },
        properties: {
          phoneFormatted: "",
          address: "4400 Heritage Trace Parkway, Suite 204",
          city: "Fort Worth",
          country: "United States",
          postalCode: "76244",
          state: "TX",
          title: "Elite Health Center - Michael Bailey, MD",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7712352, 32.8724069] },
        properties: {
          phoneFormatted: "",
          address: "9101 N. Central Expy. Suite 500",
          city: "Dallas",
          country: "United States",
          postalCode: "75231",
          state: "TX",
          title: "EpiCentre Skin Care & Laser Center",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.811241, 33.0630758] },
        properties: {
          phoneFormatted: "",
          address: "5425 W. Spring Creek Parkway",
          city: "Plano",
          country: "United States",
          postalCode: "75024",
          state: "TX",
          title: "Erase",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.4148809, 32.7294606] },
        properties: {
          phoneFormatted: "",
          address: "6038 Camp Bowie Blvd",
          city: "Fort Worth",
          country: "United States",
          postalCode: "76116",
          state: "TX",
          title: "European Skincare & Med Spa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7665636, 32.8793388] },
        properties: {
          phoneFormatted: "",
          address: "8140 Walnut Hill Lane Suite 601",
          city: "Dallas",
          country: "United States",
          postalCode: "75231",
          state: "TX",
          title: "Facial Techniques",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8111108, 33.1287324] },
        properties: {
          phoneFormatted: "",
          address: "8501 Wade Boulevard",
          city: "Frisco",
          country: "United States",
          postalCode: "75034",
          state: "TX",
          title: "Fine Line Aesthetics",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8387221, 33.1507648] },
        properties: {
          phoneFormatted: "",
          address: "5500 Frisco Square Blvd",
          city: "Frisco",
          country: "United States",
          postalCode: "75034",
          state: "TX",
          title: "Forest Park Medical Center - Frisco",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8221204, 32.927956] },
        properties: {
          phoneFormatted: "",
          address: "5005 LBJ Fwy #107",
          city: "Dallas",
          country: "United States",
          postalCode: "75244",
          state: "TX",
          title: "Fresh Image Cosmetic Surgery Center",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.82573564, 33.12495774] },
        properties: {
          phoneFormatted: "",
          address: "6898 Lebanon Road",
          city: "Frisco",
          country: "United States",
          postalCode: "75034",
          state: "TX",
          title: "Frisco Plastic Surgery",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.773254, 32.910057] },
        properties: {
          phoneFormatted: "",
          address: "7777 Forest Ln Ste C717",
          city: "Dallas",
          country: "United States",
          postalCode: "75230",
          state: "TX",
          title: "Genecov Plastic Surgery Group PA",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.4645384, 32.7554618] },
        properties: {
          phoneFormatted: "",
          address: "108 E US Hwy 80, Suite 150",
          city: "Forney",
          country: "United States",
          postalCode: "75126",
          state: "TX",
          title: "Genesis Wellness & Pain",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8000014, 32.8662491] },
        properties: {
          phoneFormatted: "",
          address: "6211 W. Northwest Hwy., Suite C255",
          city: "Dallas",
          country: "United States",
          postalCode: "75225",
          state: "TX",
          title: "GOH Medical Spa - Scott Conard, MD",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.820664, 32.9513587] },
        properties: {
          phoneFormatted: "",
          address: "5100 Belt Line, STE 620",
          city: "Dallas",
          country: "United States",
          postalCode: "75254",
          state: "TX",
          title: "Grand Spa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7612476, 32.8818916] },
        properties: {
          phoneFormatted: "",
          address: "8220 Walnut Hill Lane, Building 2, Suite 108",
          city: "Dallas",
          country: "United States",
          postalCode: "75231",
          state: "TX",
          title: "Gregg Anigian, MD",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.2891656, 32.9163856] },
        properties: {
          phoneFormatted: "",
          address: "9734 North Beach Street #100",
          city: "Fort Worth",
          country: "United States",
          postalCode: "76244",
          state: "TX",
          title: "Hidden Door Med Spa Fort Worth",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.1303591, 32.9430433] },
        properties: {
          phoneFormatted: "",
          address: "1422 Main st #263",
          city: "Southlake",
          country: "United States",
          postalCode: "76092",
          state: "TX",
          title: "Hidden Door Medspa at Southlake Town Square",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.1143198, 32.6830907] },
        properties: {
          phoneFormatted: "",
          address: "3751 Matlock Road Suite 113",
          city: "Arlington",
          country: "United States",
          postalCode: "76015",
          state: "TX",
          title: "Ideal Image - Arlington",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.14806, 32.892951] },
        properties: {
          phoneFormatted: "",
          address: "5712 Colleyville Blvd Suite 140",
          city: "Colleyville",
          country: "United States",
          postalCode: "76034",
          state: "TX",
          title: "Ideal Image - Colleyville",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.6153228, 32.9574111] },
        properties: {
          phoneFormatted: "",
          address: "4430 Lavon Drive Suite 364",
          city: "Garland",
          country: "United States",
          postalCode: "75040",
          state: "TX",
          title: "Ideal Image - Garland",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8042464, 33.0956049] },
        properties: {
          phoneFormatted: "",
          address: "8612 Preston Road Suite 100",
          city: "Plano",
          country: "United States",
          postalCode: "75024",
          state: "TX",
          title: "Ideal Image - Plano",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7965091, 32.8097457] },
        properties: {
          phoneFormatted: "",
          address: "3839 McKinney Ave Suite 100",
          city: "Dallas",
          country: "United States",
          postalCode: "75204",
          state: "TX",
          title: "Ideal Image - West Village",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.3992737, 32.6752918] },
        properties: {
          phoneFormatted: "",
          address: "5000 South Hulen St Suite 116",
          city: "Fort Worth",
          country: "United States",
          postalCode: "76132",
          state: "TX",
          title: "Ideal Image - Fort Worth",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.1416798, 32.5641817] },
        properties: {
          phoneFormatted: "",
          address: "116 N. Main St.",
          city: "Mansfield",
          country: "United States",
          postalCode: "76063",
          state: "TX",
          title: "In2ition Medical Aesthetics",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.337225, 32.7446667] },
        properties: {
          phoneFormatted: "",
          address: "1401 Henderson St.",
          city: "Fort Worth",
          country: "United States",
          postalCode: "76102",
          state: "TX",
          title: "Institute of Age Management & Aesthetic Medicine",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7744115, 32.9126714] },
        properties: {
          phoneFormatted: "",
          address: "7777 Forest Lane C230",
          city: "Plano",
          country: "United States",
          postalCode: "75230",
          state: "TX",
          title: "John Antonetti",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.4664362, 32.8996027] },
        properties: {
          phoneFormatted: "",
          address: "2455 Ridge Road Suite 157",
          city: "Rockwall",
          country: "United States",
          postalCode: "75087",
          state: "TX",
          title: "Juvanew Medspa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8145455, 32.8192494] },
        properties: {
          phoneFormatted: "",
          address: "4525 Lemmon Ave",
          city: "Dallas",
          country: "United States",
          postalCode: "75219",
          state: "TX",
          title: "Kevin Hanz, MD.",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8408579, 33.10448] },
        properties: {
          phoneFormatted: "",
          address: "3140 Legacy Dr Suite 110",
          city: "Frisco",
          country: "United States",
          postalCode: "75034",
          state: "TX",
          title: "Legacy Dermatology - Frisco",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8019238, 32.9886236] },
        properties: {
          phoneFormatted: "",
          address: "17370 Preston Rd ste 412",
          city: "Dallas",
          country: "United States",
          postalCode: "75252",
          state: "TX",
          title: "Lily Med Spa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7508566, 32.8980598] },
        properties: {
          phoneFormatted: "",
          address: "8722 Greenville Ave Suite 101",
          city: "Dallas",
          country: "United States",
          postalCode: "75243",
          state: "TX",
          title: "Lonnie Whiddon, MD",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7965027, 32.8038901] },
        properties: {
          phoneFormatted: "",
          address: "2801 Lemmon Ave #300",
          city: "Dallas",
          country: "United States",
          postalCode: "75204",
          state: "TX",
          title: "Mark Deuber MD",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.830494, 33.0646382] },
        properties: {
          phoneFormatted: "",
          address: "6000 W Spring Creek Parkway Suite 200",
          city: "Plano",
          country: "United States",
          postalCode: "75024",
          state: "TX",
          title: "McGuiness Dermatology",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.3078451, 32.5816178] },
        properties: {
          phoneFormatted: "",
          address: "701 East Rendon Crowley Road",
          city: "Burleson",
          country: "United States",
          postalCode: "76028",
          state: "TX",
          title: "Med Spa at Seena One",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8232926, 32.937356] },
        properties: {
          phoneFormatted: "",
          address: "13701 Dallas Parkway",
          city: "Dallas",
          country: "United States",
          postalCode: "75240",
          state: "TX",
          title: "Med Spa Studios",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7915582, 33.0140835] },
        properties: {
          phoneFormatted: "",
          address: "Baylor Regional Medical Center Pavillion Two",
          city: "Plano",
          country: "United States",
          postalCode: "75093",
          state: "TX",
          title: "Medical Aesthetics of North Dallas",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.9852588, 32.8928397] },
        properties: {
          phoneFormatted: "",
          address: "2448 Gateway Dr. Ste 150",
          city: "Irving",
          country: "United States",
          postalCode: "75063",
          state: "TX",
          title: "Medical Alliance, Inc",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7744115, 32.9126714] },
        properties: {
          phoneFormatted: "",
          address: "7777 Forest Ln",
          city: "Dallas",
          country: "United States",
          postalCode: "75230",
          state: "TX",
          title: "Medical City Children's Hospital",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8631823, 33.1537468] },
        properties: {
          phoneFormatted: "",
          address: "3110 W. Main Street Suite 150",
          city: "Frisco",
          country: "United States",
          postalCode: "75034",
          state: "TX",
          title: "MediLaser - Mauricio Giraldo, MD",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.3988785, 32.7098204] },
        properties: {
          phoneFormatted: "",
          address: "5160 Marathon Avenue",
          city: "Fort Worth",
          country: "United States",
          postalCode: "76109",
          state: "TX",
          title: "Milk + Honey Fort Worth",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7711941, 32.8723873] },
        properties: {
          phoneFormatted: "",
          address: "9101 N. Central Expressway Ste 150",
          city: "Dallas",
          country: "United States",
          postalCode: "75231",
          state: "TX",
          title: "Modern Dermatology",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7668158, 32.9122369] },
        properties: {
          phoneFormatted: "",
          address: "11970 N Central Expy #270",
          city: "Dallas",
          country: "United States",
          postalCode: "75243",
          state: "TX",
          title: "Modern Medical Spa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8512651, 32.8611427] },
        properties: {
          phoneFormatted: "",
          address: "3850 W NW Highway Suite 1100",
          city: "Dallas",
          country: "United States",
          postalCode: "75220",
          state: "TX",
          title: "National Laser Institute - Texas",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8053675, 32.8938067] },
        properties: {
          phoneFormatted: "",
          address: "5952 ROYAL LANE SUITE 120",
          city: "Dallas",
          country: "United States",
          postalCode: "75230",
          state: "TX",
          title: "NeoGenesis Anti Aging Center Dallas",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8048141, 32.8627605] },
        properties: {
          phoneFormatted: "",
          address: "8201 Preston Road, Suite 540",
          city: "Dallas",
          country: "United States",
          postalCode: "75225",
          state: "TX",
          title: "Neu Med Spa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8013608, 32.8159746] },
        properties: {
          phoneFormatted: "",
          address: "3888 Oak Lawn Avenue",
          city: "Dallas",
          country: "United States",
          postalCode: "75219",
          state: "TX",
          title: "OVME Aesthetics - Dallas",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8260333, 33.0798548] },
        properties: {
          phoneFormatted: "",
          address: "Legacy West 7500 Windrose Ave Suite B192",
          city: "Plano",
          country: "United States",
          postalCode: "75024",
          state: "TX",
          title: "OVME Aesthetics - Plano, TX",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8080492, 32.8633169] },
        properties: {
          phoneFormatted: "",
          address: "8226 Douglas Ave. Ste. 540",
          city: "Dallas",
          country: "United States",
          postalCode: "75225",
          state: "TX",
          title: "Park Cities Dermatology",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8352201, 32.8142564] },
        properties: {
          phoneFormatted: "",
          address: "5223 Tex Oak Ave.",
          city: "Dallas",
          country: "United States",
          postalCode: "75235",
          state: "TX",
          title: "Parkland Hospital",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7717161, 33.0168592] },
        properties: {
          phoneFormatted: "",
          address: "4104 W. 15th St. Ste 200",
          city: "Plano",
          country: "United States",
          postalCode: "75093",
          state: "TX",
          title: "Premier Plastic Surgery of Texas",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8082147, 32.8633178] },
        properties: {
          phoneFormatted: "",
          address: "8226 Douglas Suite #104",
          city: "Dallas",
          country: "United States",
          postalCode: "75225",
          state: "TX",
          title: "Resurrect Skin M.D.",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8047688, 32.8627241] },
        properties: {
          phoneFormatted: "",
          address: "8201 Preston Rd #440",
          city: "Dallas",
          country: "United States",
          postalCode: "75225",
          state: "TX",
          title: "Revival Dermatology",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7731653, 33.0581787] },
        properties: {
          phoneFormatted: "",
          address: "6300 Stonewood Dr. 110",
          city: "Plano",
          country: "United States",
          postalCode: "75024",
          state: "TX",
          title: "Rosemary Bates MD",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.13458431, 32.95018806] },
        properties: {
          phoneFormatted: "",
          address: "750 N Carroll Ave",
          city: "Southlake",
          country: "United States",
          postalCode: "76092",
          state: "TX",
          title: "Sedo Laser",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8277048, 32.99669585] },
        properties: {
          phoneFormatted: "",
          address: "18170 Dallas Pkwy",
          city: "Dallas",
          country: "United States",
          postalCode: "75287",
          state: "TX",
          title: "Setty Plastic Surgery",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.0577847, 33.0332999] },
        properties: {
          phoneFormatted: "",
          address: "3535 Firewheel A-112",
          city: "Flower Mound",
          country: "United States",
          postalCode: "75067",
          state: "TX",
          title: "Simply Embellish",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.804373, 32.8063347] },
        properties: {
          phoneFormatted: "",
          address: "3131 Turtle Creek Boulevard Suite 600",
          city: "Dallas",
          country: "United States",
          postalCode: "75219",
          state: "TX",
          title: "Skin Pharm - Dallas/Turtle Creek",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7606896, 32.8816367] },
        properties: {
          phoneFormatted: "",
          address: "8230 Walnut Hill Ln Suite 808",
          city: "Dallas",
          country: "United States",
          postalCode: "75231",
          state: "TX",
          title: "Skincepts Medical Skincare",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8476218, 33.1578975] },
        properties: {
          phoneFormatted: "",
          address: "9560 Legacy Suite 200",
          city: "Frisco",
          country: "United States",
          postalCode: "75034",
          state: "TX",
          title: "Skinn Bar",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.83280227, 33.05475206] },
        properties: {
          phoneFormatted: "",
          address: "6100 Windhaven Parkway",
          city: "Plano",
          country: "United States",
          postalCode: "75093",
          state: "TX",
          title: "Skinnovations",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7744115, 32.9126714] },
        properties: {
          phoneFormatted: "",
          address: "7777 Forest Ln, Ste B-410",
          city: "Dallas",
          country: "United States",
          postalCode: "75230",
          state: "TX",
          title: "Skyn Lab Med Spa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8097713, 33.1051014] },
        properties: {
          phoneFormatted: "",
          address: "8600 Gaylord Parkway Suite 1",
          city: "Frisco",
          country: "United States",
          postalCode: "75034",
          state: "TX",
          title: "Sonoma Skin Works",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.1375551, 32.941649] },
        properties: {
          phoneFormatted: "",
          address: "900 E. Southlake Boulevard Suite 100",
          city: "Southlake",
          country: "United States",
          postalCode: "76092",
          state: "TX",
          title: "Southlake Plastic Surgery",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.368149, 32.731117] },
        properties: {
          phoneFormatted: "",
          address: "3455 Locke Ave, #320",
          city: "Fort Worth",
          country: "United States",
          postalCode: "76107",
          state: "TX",
          title: "Steven Camp MD Plastic Surgery",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.0585357, 33.0722492] },
        properties: {
          phoneFormatted: "",
          address: "2300 Highland Village Road , Suite 300",
          city: "Highland Villag",
          country: "United States",
          postalCode: "75077",
          state: "TX",
          title: "Studio 360 Med Spa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8028626, 32.8209778] },
        properties: {
          phoneFormatted: "",
          address: "4311 Oak Lawn #380",
          city: "Dallas",
          country: "United States",
          postalCode: "75219",
          state: "TX",
          title: "Surface Clinical",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.4664624, 32.8852928] },
        properties: {
          phoneFormatted: "",
          address: "3142 Horizon Road, Suite 201",
          city: "Rockwall",
          country: "United States",
          postalCode: "75032",
          state: "TX",
          title: "Texas Dermatology & Skin Cancer Center",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7770034, 32.7912842] },
        properties: {
          phoneFormatted: "",
          address: "3900 Junius St Suite 145",
          city: "Dallas",
          country: "United States",
          postalCode: "75246",
          state: "TX",
          title: "Texas Dermatology Associates",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8387851, 33.105148] },
        properties: {
          phoneFormatted: "",
          address: "5575 Warren Parkway Suite 314 Prof Bldg 1",
          city: "Frisco",
          country: "United States",
          postalCode: "75034",
          state: "TX",
          title: "Texas Gynecology",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7253113, 32.9745103] },
        properties: {
          phoneFormatted: "",
          address: "399 W. Campbell Rd Medical Bldg 2 Ste 412",
          city: "Richardson",
          country: "United States",
          postalCode: "75080",
          state: "TX",
          title: "The Finer Touch",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.1553745, 32.9405032] },
        properties: {
          phoneFormatted: "",
          address: "351 West Southlake Boulevard",
          city: "Southlake",
          country: "United States",
          postalCode: "76092",
          state: "TX",
          title: "The LAB MedSpa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8837356, 33.0275908] },
        properties: {
          phoneFormatted: "",
          address: "4340 N Josey Ln #100",
          city: "Carrollton",
          country: "United States",
          postalCode: "75010",
          state: "TX",
          title: "Trinity Dermatology",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.344213, 32.736237] },
        properties: {
          phoneFormatted: "",
          address: "800 8th Ave., Suite 326",
          city: "Fort Worth",
          country: "United States",
          postalCode: "76104",
          state: "TX",
          title: "Trinity Vista Dermatology",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7893117, 32.8139484] },
        properties: {
          phoneFormatted: "",
          address: "4144 North Central Expressway; Suite 855",
          city: "Dallas",
          country: "United States",
          postalCode: "75204",
          state: "TX",
          title: "Uptown Derm - Farhad Niroomand, M.D., P.A.",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.1299772, 32.7438366] },
        properties: {
          phoneFormatted: "",
          address: "723 N Fielder Rd Ste B",
          city: "Arlington",
          country: "United States",
          postalCode: "76012",
          state: "TX",
          title: "US Dermatology Medical Group",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8458178, 32.816098] },
        properties: {
          phoneFormatted: "",
          address: "1801 Inwood Rd 5th Floor",
          city: "Dallas",
          country: "United States",
          postalCode: "75390",
          state: "TX",
          title:
            "UT Southwestern Medical Center-Plastic Surgery - Jeffrey Kenkel, MD",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8485427, 32.8195873] },
        properties: {
          phoneFormatted: "",
          address: "6263 Harry Hines Blvd. 4th Floor, Room 120",
          city: "Dallas",
          country: "United States",
          postalCode: "75390",
          state: "TX",
          title: "UT Southwestern Medical - Dermatology",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8463936, 32.8158484] },
        properties: {
          phoneFormatted: "",
          address: "1801 Inwood Rd",
          city: "Dallas",
          country: "United States",
          postalCode: "75390",
          state: "TX",
          title: "UTSW",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7691595, 32.8604732] },
        properties: {
          phoneFormatted: "",
          address: "8080 N. Central Express Way Suite 1250",
          city: "Dallas",
          country: "United States",
          postalCode: "75206",
          state: "TX",
          title: "Vansanity - Dallas",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8067158, 33.1014628] },
        properties: {
          phoneFormatted: "",
          address: "2693 Preston Rd. - 1080 / #40",
          city: "Frisco",
          country: "United States",
          postalCode: "75034",
          state: "TX",
          title: "Vibrant Skincare and Laser Center, LLC",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.7945503, 33.0058879] },
        properties: {
          phoneFormatted: "",
          address: "18800 Preston Rd, Ste 310",
          city: "Dallas",
          country: "United States",
          postalCode: "75252",
          state: "TX",
          title: "Vital Wellness and Weight Loss",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8045541, 32.8498138] },
        properties: {
          phoneFormatted: "",
          address: "6915 Preston Rd",
          city: "Dallas",
          country: "United States",
          postalCode: "75205",
          state: "TX",
          title: "Vitalyc Medspa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.6977559, 33.198036] },
        properties: {
          phoneFormatted: "",
          address: "5971 Virginia Pkwy Suite 100",
          city: "McKinney",
          country: "United States",
          postalCode: "75070",
          state: "TX",
          title: "Warthan Dermatology",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.8048141, 32.8627605] },
        properties: {
          phoneFormatted: "",
          address: "8201 Preston Rd. #540",
          city: "Dallas",
          country: "United States",
          postalCode: "75225",
          state: "TX",
          title: "Wellskin Med Spa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.3379423, 32.7308068] },
        properties: {
          phoneFormatted: "",
          address: "1200 W. Magnolia Ave",
          city: "Fort Worth",
          country: "United States",
          postalCode: "76104",
          state: "TX",
          title: "West Magnolia Plastic Surgery",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.808683, 33.0158037] },
        properties: {
          phoneFormatted: "",
          address: "5316 W. Plano Parkway",
          city: "Plano",
          country: "United States",
          postalCode: "75093",
          state: "TX",
          title: "Wilcox Robert D. MD",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-96.6832138, 33.089836] },
        properties: {
          phoneFormatted: "",
          address: "941 West Bethany Dr",
          city: "Allen",
          country: "United States",
          postalCode: "75013",
          state: "TX",
          title: "Youthful Infusion",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.219731, 33.0132604] },
        properties: {
          phoneFormatted: "",
          address: "1212 N Hwy 377 Suite 119",
          city: "Roanoke",
          country: "United States",
          postalCode: "76262",
          state: "TX",
          title: "Youthology MedSpa",
        },
      },
      {
        type: "Feature",
        geometry: { type: "Point", coordinates: [-97.1053589, 32.9435107] },
        properties: {
          phoneFormatted: "",
          address: "2301 Westgate Plaza",
          city: "Grapevine",
          country: "United States",
          postalCode: "76051",
          state: "TX",
          title: "2301 Plastic Surgery",
        },
      },
    ],
  };

  const storeArr = stores.features;
  stores.features.forEach(function (store, i) {
    store.properties.id = i;
  });

  let loadedMap;

  function createPopUp(currentFeature) {
    const popUps = document.getElementsByClassName("mapboxgl-popup");
    /** Check if there is already a popup on the map and if so, remove it */
    if (popUps[0]) popUps[0].remove();

    const popup = new mapboxgl.Popup({ closeOnClick: false })
      .setLngLat(currentFeature.geometry.coordinates)
      .setHTML(
        `<div style="border-radius:3px;font-family:adrianna;height:200px;width:200px;display:grid;grid-template-columns:1fr;"><h3 style="font-size:16px;font-weight:600;text-align:center;width:100%;">${currentFeature.properties.title}</h3><h4 style="font-size:15px;text-align:center;width:100%;">${currentFeature.properties.address}<br>${currentFeature.properties.city}, ${currentFeature.properties.state}<br>${currentFeature.properties.postalCode}</h4><button style="margin:auto;font-size:12px;width:80%;height:50px;color:#fafafa;background-color:#bfa888;border:none;border-radius:5px;">BOOK APPOINTMENT</button></div>`
      )
      .addTo(loadedMap);
  }

  function flyToStore(currentFeature) {
    // document.getElementById(currentFeature.properties.id).className =
    //   "map__store--title-active";
    loadedMap.flyTo({
      center: currentFeature.geometry.coordinates,
      zoom: 17,
    });

    setTimeout(function () {
      createPopUp(currentFeature);
    }, 3000);
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
      const coordinates = e.features[0].geometry.coordinates.slice();
      const description = `<div style="font-family:adrianna;height:200px;width:200px;display:grid;grid-template-columns:1fr;"><h3 style="font-size:15px;font-weight:600;text-align:center;width:100%;">${e.features[0].properties.title}</h3><h4 style="font-size:15px;text-align:center;width:100%;">${e.features[0].properties.address}<br>${e.features[0].properties.city}, ${e.features[0].properties.state}<br>${e.features[0].properties.postalCode}</h4><button style="margin:auto;font-size:12px;width:80%;height:50px;color:#fafafa;background-color:#bfa888;border:none;border-radius:5px;">BOOK APPOINTMENT</button></div>`;

      while (Math.abs(e.lngLat.lng - coordinates[0]) > 180) {
        coordinates[0] += e.lngLat.lng > coordinates[0] ? 360 : -360;
      }

      new mapboxgl.Popup()
        .setLngLat(coordinates)
        .setHTML(description)
        .addTo(map);
    });
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
            .includes(stringToMatch.toLowerCase()) ||
          store.properties.title
            .toLowerCase()
            .includes(providerMatch.toLowerCase())
        );
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
        Find Your Local <br /> BBL &reg; HERO &trade; Providers
      </h1>
      <div class="map__search">
        <input
          placeholder="City, Zip"
          bind:value={stringToMatch}
          class="map__input"
        />
        <input
          placeholder="Provider"
          bind:value={providerMatch}
          class="map__input"
        />
      </div>
    </div>
    <div id="listings" class="listings-sidebar">
      {#each getFilteredStores(storeArr, stringToMatch, providerMatch) as store, i}
        <div class="map__store" id={store.properties.id}>
          <div class="map__store--c-buttons">
            <button class="map__store--title" on:click={() => flyToStore(store)}
              >{store.properties.title}</button
            >
            <button class="map__store--book">BOOK APPOINTMENT</button>
          </div>

          <div>
            <div>
              <p class="map__store--desc">{store.properties.address}</p>
              <p class="map__store--desc">
                {store.properties.city}, {store.properties.state}
              </p>
              <p class="map__store--desc">{store.properties.postalCode}</p>
              <p class="map__store--desc">{store.properties.phoneFormatted}</p>
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
    height: 100vh;
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

  .listings-sidebar {
    height: calc(100% - 250px);
    overflow-y: scroll;
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

  /* .map__store--title-active {
    color: var(--secondary);
    background-color: var(--offWhite);
    border: none;
    padding: none;
    font-family: var(--adrianna);
    font-size: 20px;
    text-align: left;
    font-weight: 600;
  } */

  .map__store--book {
    height: 40px;
    margin: auto;
    width: 150px;
    font-size: 12px;
    color: var(--offWhite);
    background-color: var(--secondary);
    border-radius: 5px;
    border: none;
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
    }
    .heading {
      height: 75px;
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
</style>
