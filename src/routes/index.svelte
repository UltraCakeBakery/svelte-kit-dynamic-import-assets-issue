<script context="module">
    export async function load({ page })
    {
        const assets = [
            'illustrations/one.svg', 
            'illustrations/two.jpg'
        ]

		return { 
			props: { 
				assets: await Promise.all( assets.map( asset => import( `../assets/${asset}` ) ) ) 
			}
		}
    }
</script>

<script>
    export let assets = []
</script>

{ #each assets as asset } 
    { asset }
    <img src={asset} alt="" />
{ /each }