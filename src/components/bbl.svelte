<script>
	import Overview from './tabs/overview.svelte';
    import Features from './tabs/features.svelte';
    import Technology from './tabs/technology.svelte';
    import Treatments from './tabs/treatments.svelte';
    import Tabs from "./tabs.svelte";


    let items = [
    { label: "Overview",
		 value: 1,
		 component: Overview
		},
    { label: "Features",
		 value: 2,
		 component: Features
		},
    { label: "Technology",
		 value: 3,
		 component: Technology
		},
    { label: "Treatments",
		 value: 4,
		 component: Treatments
        }
  ];
</script>

<main>
 <Tabs {items}  />
</main>


<style>
    main {
        height: auto;
        min-height: 1000px;
        width: 100%;
        padding-bottom: 3rem;
        overflow-x: hidden;
    }
</style>