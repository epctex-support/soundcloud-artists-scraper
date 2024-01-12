# Actor - SoundCloud Artists Scraper

## SoundCloud Artists scraper

Since SoundCloud doesn't provide a good and free API, this actor should help you to retrieve data from it.

The SoundCloud Artists Scraper supports the following features:

-   Search any keyword - Search for any keywords in seconds and retrieve the results with ease.

-   Get users - ID, name, avatar, visuals, badges, and many other deep-level information is ready for your consumption.

-   No limits - The actor has no limitation on the data. Get anything you want!

## Bugs, fixes, updates, and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/soundcloud-artists-scraper/issues).


## Input Parameters

The input of this scraper should be JSON containing the list of pages on SoundCloud that should be visited. Possible fields are:

- `startUrls`: (Required) (Array) List of SoundCloud URLs. URLs to start with. It should be a search or user URL.

- `endPage`: (Optional) (Number) Final number of page that you want to scrape. The default is `Infinite`. This applies to all `search` requests and `startUrls` individually.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Tip

When you want to scrape over a specific list URL, just copy and paste the link as one of the **startUrl**.

If you would like to scrape only the first page of a list then put the link for the page and have the `endPage` as 1.

With the last approach that is explained above you can also fetch any interval of pages. If you provide the 5th page of a list and define the `endPage` parameter as 6 then you'll have the 5th and 6th pages only.

### Compute Unit Consumption

The actor is optimized to run blazing fast and scrape as many items as possible. Therefore, it forefronts all the detailed requests. If the actor doesn't block very often it'll scrape 100 tracks in 2 minutes with ~0.01-0.03 compute units.

### SoundCloud Artists Scraper Input example

```json
{
  "startUrls":[
    "https://soundcloud.com/sibel-dar-c/ekin-ekinci-gel-art-k",
    "https://soundcloud.com/sibel-dar-c",
    "https://soundcloud.com/swedish-hiphop-rap-fm/sets/pistoler-poesi-och-sex",
    "https://soundcloud.com/search/sets?q=dnb",
    "https://soundcloud.com/search/people?q=dnb",
    "https://soundcloud.com/search/albums?q=dnb",
    "https://soundcloud.com/search/sounds?q=dnb"
  ],
  "endPage":3,
  "maxItems":20,
  "includeComments":false,
  "proxy":{
    "useApifyProxy":true
  }
}
```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.
When items are loaded from the page, you should see a message about this event with a loaded item count and total item count for each page.

If you provide incorrect input to the actor, it will immediately stop with a failure state and output an explanation of what is wrong.

## SoundCloud Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any language (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this SoundCloud actor.

## Scraped SoundCloud Properties

The structure of each item in SoundCloud looks like this:

```json
{
	"avatar_url": "https://i1.sndcdn.com/avatars-000417434502-x520gl-large.jpg",
	"city": null,
	"comments_count": 0,
	"country_code": null,
	"created_at": "2016-03-21T18:39:11Z",
	"creator_subscriptions": [
		{
			"product": {
				"id": "free"
			}
		}
	],
	"creator_subscription": {
		"product": {
			"id": "free"
		}
	},
	"description": null,
	"followers_count": 859,
	"followings_count": 0,
	"first_name": "Sibel",
	"full_name": "Sibel Darıcı",
	"groups_count": 0,
	"id": 213512643,
	"kind": "user",
	"last_modified": "2018-03-17T15:38:47Z",
	"last_name": "Darıcı",
	"likes_count": 108,
	"playlist_likes_count": 0,
	"permalink": "sibel-dar-c",
	"permalink_url": "https://soundcloud.com/sibel-dar-c",
	"playlist_count": 0,
	"reposts_count": null,
	"track_count": 8,
	"uri": "https://api.soundcloud.com/users/213512643",
	"urn": "soundcloud:users:213512643",
	"username": "Sibel Darıcı",
	"verified": false,
	"visuals": {
		"urn": "soundcloud:users:213512643",
		"enabled": true,
		"visuals": [
			{
				"urn": "soundcloud:visuals:67152382",
				"entry_time": 0,
				"visual_url": "https://i1.sndcdn.com/visuals-000213512643-fpIXUr-original.jpg"
			}
		],
		"tracking": null
	},
	"badges": {
		"pro": false,
		"pro_unlimited": false,
		"verified": false
	},
	"station_urn": "soundcloud:system-playlists:artist-stations:213512643",
	"station_permalink": "artist-stations:213512643",
	"url": "/sibel-dar-c"
}
```

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that are available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
