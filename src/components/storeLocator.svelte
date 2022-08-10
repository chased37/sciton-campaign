
<script>
	import StoreLocator from 'store-locator'; 
    import jsonp from 'jsonp'

    const endpoint = 'https://stockist.co/api/v1/<account-id>/locations/search'


    function convertToQuery (request) {
    return Object.keys(request).map(key => (
        `${key}=${encodeURIComponent(request[key])}`
    )).join('&')
    }

    const locator = new StoreLocator({
    lookup (request, next) {
        const query = convertToQuery(request)

        jsonp(`${endpoint}?${query}`, {
        param: 'callback'
        }, (err, {locations = []}) => {
        if (err) {
            throw new Error(':( Oh no!')
        }
        
        locations = locations
            .map(({latitude, longitude, ...location}) => ({
            lat: latitude,
            lng: longitude,
            ...location
            }))
        
        next({locations})
        })
    },
    settings: {
        key: '<google-maps-key>',
    }
    })
</script>


<main></main>

<style></style>