
Get posts for a user:

GET https://mewe.com/api/v3/group/55f9dd29e4b050c69e693558/member/5602c780e4b08f388c897a39/postsfeed

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