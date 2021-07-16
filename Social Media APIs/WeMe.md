
Get user info:
`GET https://mewe.com/api/v2/mycontacts/user?inviteId=markweinstein2`
```json
{
	"id": "5602c780e4b08f388c897a39",
	"name": "Mark Weinstein",
	"firstName": "Mark",
	"lastName": "Weinstein",
	"fingerprint": "F1482297596208YCECRS",
	"registeredAt": 1443022720,
	"_links": {
		"self": {
			"href": "/api/v2/mycontacts/user"
		},
		"avatar": {
			"href": "/api/v2/photo/profile/{imageSize}/5602c780e4b08f388c897a39?group=&f=F1482297596208YCECRS",
			"templated": true
		},
		"cover": {
			"href": "/img/predefined/cover-picture.jpg",
			"templated": true
		}
	},
	"profile": {
		"userId": "5602c780e4b08f388c897a39",
		"name": "Mark Weinstein",
		"fingerprint": "F1482297596208YCECRS",
		"text": "",
		"active": false
	},
	"canChat": false,
	"canSeeContacts": false,
	"userAllowsToBeInvited": false,
	"verified": true,
	"status": "online",
	"badges": {
		"verified": true
	},
	"contactInviteId": "markweinstein2"
}
```

Get posts for a group (optionally filtered by member):
`GET https://mewe.com/api/v3/group/55f9dd29e4b050c69e693558/[member/5602c780e4b08f388c897a39/]postsfeed`
```json
{
	"feed": [{
		"postItemId": "60f0c1e026266f0591d2c160",
		"userId": "5602c780e4b08f388c897a39",
		"text": "***German Government Privacy Leader Tells Agencies to #DeleteFacebook Due to Privacy Violations*** 🔏\n\n**Friends and Members,**\n\nThe head of Germany's data protection commission sent a letter to all German government organizations and agencies telling them to delete their Facebook pages because FB *\"failed to comply with German and European privacy laws.\"* 👀\n\nThe reality is that FB is a data company masquerading as a social network. FB ignores and violates privacy laws in Europe, the USA, and all over the world and pays the fines it incurs as a \"cost of doing business\". 💸 👎\n\nHats off to Germany's privacy commissioner for fighting back and to people worldwide supporting the MeWe movement - No Tracking, No Ads, NO BS. 🎩👏\n\nMeWe is the first social network with the best social media features **and** a Privacy Bill of Rights for members. 👍 🔏 🤝\n\n**#LetsMeWe**\n\nhttps://www.reuters.com/technology/german-privacy-tsar-tells-ministries-shut-facebook-pages-2021-06-29/",
		"link": {
			"description": "German government organisations have until the end of the year to close their Facebook (FB.O) pages after the data protection commissioner found the social network had failed to change its practices to comply with German and European privacy laws.",
			"title": "German privacy tsar tells ministries to shut Facebook pages | Reuters",
			"thumbnailSize": {
				"width": 564,
				"height": 295
			},
			"_links": {
				"url": {
					"href": "https://www.reuters.com/technology/german-privacy-tsar-tells-ministries-shut-facebook-pages-2021-06-29/"
				},
				"thumbnail": {
					"href": "https://live-mewe-thumbs.s3.amazonaws.com/nqsm_z_75AnUh1P4QJ2_otjzwSw"
				},
				"urlHost": {
					"href": "www.reuters.com"
				}
			}
		},
		"emojis": {
			"userEmojis": [],
			"emojiCounts": [{
				"❤": 1332
			}, {
				"🔐": 389
			}, {
				"✅": 836
			}, {
				"👍": 2170
			}],
			"counts": {
				"❤": 1332,
				"🔐": 389,
				"✅": 836,
				"👍": 2170
			}
		},
		"groupId": "55f9dd29e4b050c69e693558",
		"permissions": {
			"canEmojify": true,
			"reshare": true,
			"follow": true
		},
		"createdAt": 1626391008,
		"updatedAt": 1626391008,
		"hashTags": ["deletefacebook", "letsmewe"],
		"follows": false,
		"sharesCount": 399
	}],
	"order": "comment",
	"users": [{
		"id": "5602c780e4b08f388c897a39",
		"name": "Mark Weinstein",
		"_links": {
			"avatar": {
				"href": "/api/v2/photo/profile/{imageSize}/5602c780e4b08f388c897a39?group=55f9dd29e4b050c69e693558&f=F1482297596208YCECRS",
				"templated": true
			}
		},
		"fingerprint": "F1482297596208YCECRS",
		"firstName": "Mark",
		"lastName": "Weinstein",
		"contactInviteId": "markweinstein2",
		"badges": {
			"verified": true
		}
	}],
	"groups": [{
		"id": "55f9dd29e4b050c69e693558",
		"name": "MeWe News and Updates",
		"color": {
			"defaultColor": "#2d2a82",
			"light": "#7371ab",
			"dark": "#000058",
			"background": "#dcdbea"
		},
		"_links": {
			"self": {
				"href": "/api/v2/group/55f9dd29e4b050c69e693558"
			},
			"groupAvatar": {
				"href": "/api/v2/photo/33lmUK9ccuyACpWDShh-lLNgXxPT_yKw26k9b9vxQyBbHtwjpA8wQ3gWsE4/{imageSize}/img?static={static}",
				"templated": true
			}
		}
	}],
	"_links": {
		"self": {
			"href": "/api/v3/group/55f9dd29e4b050c69e693558/member/5602c780e4b08f388c897a39/postsfeed"
		},
		"nextPage": {
			"href": "/api/v3/group/55f9dd29e4b050c69e693558/member/5602c780e4b08f388c897a39/postsfeed?limit=10&b=608a0968a227f408697952fe"
		}
	}
}
```

Get profile image for a user:
GET https://img.mewe.com/api/v2/photo/profile/150x150/5602c780e4b08f388c897a39
GET https://img.mewe.com/api/v2/photo/profile/400x400/5602c780e4b08f388c897a39

Get user info:
GET https://mewe.com/api/v2/mycontacts/user/5602c780e4b08f388c897a39
```json
{
	"id": "5602c780e4b08f388c897a39",
	"name": "Mark Weinstein",
	"firstName": "Mark",
	"lastName": "Weinstein",
	"fingerprint": "F1482297596208YCECRS",
	"registeredAt": 1443022720,
	"_links": {
		"self": {
			"href": "/api/v2/mycontacts/user/5602c780e4b08f388c897a39"
		},
		"avatar": {
			"href": "/api/v2/photo/profile/{imageSize}/5602c780e4b08f388c897a39?group=55f9dd29e4b050c69e693558&f=F1482297596208YCECRS",
			"templated": true
		},
		"cover": {
			"href": "/api/v2/photo/33lmUK9ccuyACpWDShh-lLNgXxPT_yKw26k9b9vxQyBbHtwjpA8wQ3gWsE4/{imageSize}/img.jpg"
		}
	},
	"profile": {
		"userId": "5602c780e4b08f388c897a39",
		"name": "Mark Weinstein",
		"fingerprint": "F1482297596208YCECRS",
		"text": "",
		"active": false
	},
	"groupRole": "Admin",
	"canChat": false,
	"canSeeContacts": false,
	"userAllowsToBeInvited": false,
	"verified": true,
	"status": "online",
	"badges": {
		"verified": true
	},
	"contactInviteId": "markweinstein2"
}
```