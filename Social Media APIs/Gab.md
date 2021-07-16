# Gab

## Authentication

An `Authorization` header is required, with `Bearer <token>` (where token is your token).

## API

### Accounts

```json
{
	"id": "73820",
	"username": "MatthewTrump",
	"acct": "MatthewTrump",
	"display_name": "Matthew Trump",
	"locked": false,
	"bot": false,
	"created_at": "2016-11-21T16:32:45.000Z",
	"note": "\u003cp\u003e\u0026quot;No one should fear to undertake any task in the name of our Saviour, if it is just and if the intention is purely for His holy service.\u0026quot; - Christopher Columbus\u003c/p\u003e",
	"url": "https://gab.com/MatthewTrump",
	"avatar": "https://gab.com/media/user/bb-5bb91cb933c4d.jpeg",
	"avatar_static": "https://gab.com/media/user/bb-5bb91cb933c4d.jpeg",
	"header": "https://gab.com/media/user/bb-5bba8f99cfc89.png",
	"header_static": "https://gab.com/media/user/bb-5bba8f99cfc89.png",
	"is_spam": false,
	"followers_count": 3595,
	"following_count": 14,
	"statuses_count": 19,
	"is_pro": false,
	"is_verified": true,
	"is_donor": false,
	"is_investor": false,
	"emojis": [],
	"fields": []
}
```


#### Get an account by username
`GET https://gab.com/api/v1/account_by_username/MatthewTrump`

Response: A single Account

#### Get an account by ID
`GET https://gab.com/api/v1/accounts/73820`

Response: A single Account

#### Get followings / followers
`GET https://gab.com/api/v1/accounts/2891614/[following|followers]`

Response: An array of Accounts

### Statuses

```json
{
	"id": "106557617192553453",
	"created_at": "2021-07-10T18:03:23.765Z",
	"revised_at": null,
	"in_reply_to_id": null,
	"in_reply_to_account_id": null,
	"sensitive": false,
	"spoiler_text": "",
	"visibility": "public",
	"language": "en",
	"uri": "/TheChickenRight/posts/106557617192553453",
	"url": "https://gab.com/TheChickenRight/posts/106557617192553453",
	"replies_count": 124,
	"reblogs_count": 361,
	"pinnable": false,
	"pinnable_by_group": false,
	"favourites_count": 667,
	"quote_of_id": null,
	"expires_at": null,
	"has_quote": false,
	"bookmark_collection_id": null,
	"favourited": false,
	"reblogged": false,
	"content": "Lmao wtf<br />\"More fully vaccinated people died, that's because the vaccine is good, but not perfect\"",
	"rich_content": "",
	"plain_markdown": null,
	"reblog": null,
	"quote": null,
	"account": User,
	"group": null,
	"media_attachments": [{
		"id": "78908662",
		"type": "video",
		"url": "https://media.gab.com/system/media_attachments/files/078/908/662/original/ef1096deb284ac18.mp4",
		"preview_url": "https://media.gab.com/system/media_attachments/files/078/908/662/small/ef1096deb284ac18.png",
		"source_mp4": "https://media.gab.com/system/media_attachments/files/078/908/662/playable/ef1096deb284ac18.mp4",
		"remote_url": null,
		"text_url": "https://gab.com/media/jkBPUljh5zODiqwmkD4",
		"meta": {
			"length": "0:00:15.17",
			"duration": 15.17,
			"audio_encode": "aac (LC) (mp4a / 0x6134706D)",
			"audio_bitrate": "44100 Hz",
			"audio_channels": "stereo",
			"fps": 30,
			"size": "576x320",
			"width": 576,
			"height": 320,
			"aspect": 1.8,
			"original": {
				"width": 576,
				"height": 320,
				"frame_rate": "30/1",
				"duration": 15.166667,
				"bitrate": 787138
			},
			"small": {
				"width": 400,
				"height": 222,
				"size": "400x222",
				"aspect": 1.8018018018018018
			},
			"playable": {
				"width": 576,
				"height": 320,
				"frame_rate": "30/1",
				"duration": 15.186,
				"bitrate": 1324266
			}
		},
		"description": null,
		"blurhash": "UIK]in[U0yROu%VsX-ofCROXicWBVsROS2tR",
		"file_content_type": "video/mp4"
	}],
	"mentions": [],
	"tags": [],
	"emojis": [],
	"card": null,
	"poll": null
}
```

#### Get statuses for an account
`GET https://gab.com/api/v1/accounts/2891614/statuses?pinned=[true|false]&exclude_replies=[true|false]&only_media=[true|false]&limit=20&media_type=[photo|video]&max_id=id`

Options:
- pinned: only include pinned statuses
- exclude_replies: don't include replies
- only_media: only include replies with 'media_attachments' sections
- media_type: filter to the specific media type
- limit: only return N statuses
- max_id: appears to start at the given ID

Response: An array of Statuses

#### Get a single status
`GET https://gab.com/api/v1/statuses/106557617192553453`

#### Get comments for a status
`GET https://gab.com/api/v1/statuses/106557617192553453/comments`

Response:
```json
{
	"ancestors":null, // tbc
	"descendants":[Status]
}
```

### Groups

```json
{
	"id": "981",
	"title": "Trump 2020",
	"description": "We support the President of the United States!",
	"description_html": "\u003cp\u003eWe support the President of the United States!\u003c/p\u003e",
	"cover_image_url": "https://media.gab.com/system/groups/cover_images/000/000/981/original/29354314_801037073569634_4298433919081563056_o.jpg",
	"is_archived": false,
	"member_count": 238458,
	"created_at": "2018-07-30T21:44:21.000Z",
	"is_private": false,
	"is_visible": true,
	"slug": null,
	"url": "https://gab.com/groups/981",
	"tags": null,
	"group_category": null,
	"password": null,
	"has_password": false
}
```

#### Get a single group
`GET https://gab.com/api/v1/groups/981`

### Search
`GET https://gab.com/api/v2/search?onlyVerified=[true|false]&q=trump&resolve=[true|false]`

Options:
- onlyVerified: true or false; whether to include verified accounts
- q: the query string (e.g. 'trump')
- resolve: tbc

Response:
```json
{
	"accounts": [User],
	"statuses": [tbc],
	"groups": [Group],
	"links": [tbc]
}
```
