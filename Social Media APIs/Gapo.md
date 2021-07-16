# Gapo

### Authentication

An `Authorization` header is required, with `Bearer <token>` (where token is your token). You can use the following Python script to get this (you'll need the `requests` module):

```python
import requests
import sys
import uuid
from getpass import getpass

def main():
        phone = input("Phone number (+44-1234567890):")
        password = getpass()
        device_id = uuid.uuid4()
        r = requests.post('https://api.gapo.vn/auth/v2.0/login', json={'client_id':'does_not_matter', 'device_id':str(device_id), 'password':password, 'phone_number':phone, 'trusted_device':False})
        j = r.json()
        if j['code'] != 200:
                print("Unexpected status code %d: %s"  % (j['code'], j['message']))
                sys.exit(1)

        print("Auth token: %s" % j['data']['access_token'])

if __name__ == "__main__":
        main()

```

#### Users

```json
{
	"user_id": 12345,
	"full_name": "Joe Bloggs",
	"display_name": "Joe",
	"gender": {
		"gender": 1,
		"privacy": 1
	},
	"cover": "https://image-5.gapo.vn/images/9f0efc3b-7130-4cd3-92c0-c9f12da0ef6c.jpeg",
	"avatar": "https://image-5.gapo.vn/images/fc034ca7-de12-4987-9506-cceade29e4e3.jpeg",
	"birthday": {},
	"social_links": {
		"facebook": "158188511978953",
		"instagram": "",
		"tiktok": "",
		"youtube": ""
	},
	"featured_media": {
		"photos": [],
		"posts": [],
		"stories": []
	},
	"status_kyc": 3,
	"status_verify": 0,
	"count": {
		"post_count": 872,
		"react_count": 586494,
		"share_count": 0,
		"friend_count": 4014,
		"follow_count": 6446
	},
	"info": {
		"website": "",
		"address": {
			"hometown": {
				"city": 58,
				"privacy": 1
			},
			"current": {
				"city": 58,
				"privacy": 1
			}
		},
		"relationship": {
			"title": "Độc thân",
			"privacy": 1
		},
		"education": [{
			"school": "THPT Phạm Thành Trung",
			"title": "",
			"privacy": 1
		}],
		"work": [{
			"company": "ⓖⓐⓟⓞ",
			"title": "Fan",
			"privacy": 1
		}],
		"bio": "Kết bạn em nha 😍 \nSự cố gắng luôn được đền đáp xứng đáng"
	},
	"interest": [
		29,
		104,
		106
	],
	"hobbies": [{
		"id": 4,
		"title": "Ăn uống",
		"icon": "https://image-1.gapo.vn/images/e564e836-d89d-4e7c-8907-7a400fb1f9e1.png"
	}, ...],
	"link_profile": "tvt21387",
	"cover_data": {
		"id": "3a9df71f-b742-497a-b490-7b7e4bc35ee2",
		"src": "https://image-5.gapo.vn/images/9f0efc3b-7130-4cd3-92c0-c9f12da0ef6c.jpeg",
		"width": 1242,
		"height": 558,
		"src_thumb_pattern": "https://cdn-thumb-image-5.gapo.vn/$size$/smart/9f0efc3b-7130-4cd3-92c0-c9f12da0ef6c.jpeg"
	},
	"avatar_data": {
		"id": "1e1f8f6a-d765-4ddc-83e8-ca032f679c9a",
		"src": "https://image-5.gapo.vn/images/fc034ca7-de12-4987-9506-cceade29e4e3.jpeg",
		"width": 2048,
		"height": 2048,
		"src_thumb_pattern": "https://cdn-thumb-image-5.gapo.vn/$size$/smart/fc034ca7-de12-4987-9506-cceade29e4e3.jpeg"
	},
	"background": {
		"src": "",
		"width": 0,
		"height": 0,
		"src_thumb_pattern": ""
	},
	"workspace_account": 0,
	"avatar_thumb_pattern": "https://cdn-thumb-image-5.gapo.vn/$size$/smart/fc034ca7-de12-4987-9506-cceade29e4e3.jpeg",
	"cover_thumb_pattern": "https://cdn-thumb-image-5.gapo.vn/$size$/smart/9f0efc3b-7130-4cd3-92c0-c9f12da0ef6c.jpeg",
	"relation": "",
	"see_first": 0,
	"follow": 0,
	"domain": "gapo.vn",
	"link": "https://gapo.vn/tvt21387"
}

```

##### Get User Profile
`GET https://api.gapo.vn/user-profile/v1.0/profile/12345`
Response:
```json
{
	"code": 200,
	"data": User,
	"message": "Ok"
}
```

##### Get User Feed
`GET https://api.gapo.vn/main/v1.4/feed/user/12345?expand=comments&from_id&limit=10&next=`

#### Posts

Get post reactions:
`GET https://api.gapo.vn/react/v3.0/post/list-user-react/qozo38gi3`
Response:
```json
{
	"code": 0,
	"data": [{
		"user": User,
		"react_type": 1,
		"updated_at": 1614715051000,
		"relation": ""
	}],
	"links": {
		"next": "last_time=1614110434000",
		"prev": "last_time=1614715051000"
	},
	"message": "Ok"
}
```

#### Pages
```json
{
	"create_at": 1623682397795,
	"last_update": 1623682451829,
	"page_id": "1782757920457414464",
	"title": "Football Credent",
	"alias": "",
	"description": "",
	"info": "",
	"type": 17,
	"type_name": "Thể thao",
	"avatar": "https://image-5.gapo.vn/images/dbb72e92-2745-4456-9671-bc7ba5864a87.jpeg",
	"cover": "https://image-5.gapo.vn/images/202b112e-8765-4125-bcc0-d821d594f33e.jpeg",
	"email": "",
	"phone": "",
	"website": "",
	"status": 1,
	"page_status": 1,
	"status_verify": 0,
	"province": 0,
	"labels": [],
	"background": {
		"src_thumb_pattern": "",
		"src": "",
		"width": 0,
		"height": 0,
		"position": 0,
		"media_id": ""
	},
	"is_like": 0,
	"see_first": 0,
	"follow_count": 0,
	"avatar_thumb_pattern": "https://cdn-thumb-image-5.gapo.vn/$size$/smart/dbb72e92-2745-4456-9671-bc7ba5864a87.jpeg",
	"cover_thumb_pattern": "https://cdn-thumb-image-5.gapo.vn/$size$/smart/202b112e-8765-4125-bcc0-d821d594f33e.jpeg"
}
```

Get page:
`GET https://api.gapo.vn/page/v1.1/pages/1774723903168544996`
Response:
```json
{
	"code": 200,
 	"message": "Đã xử lý thành công!",
	"data": Page
}
``
#### Groups
```json
{
	"id": "2352381379997745152",
	"name": "DLS FOOTBALL GANE",
	"description": "Dành cho những ai đam mê DLS mobile",
	"privacy": "PUBLIC",
	"owner_id": "1180326917",
	"cover": "",
	"cover_thumb_pattern": "",
	"member_count": "1",
	"blocked": false,
	"created_at": "1597600195",
	"discoverability": "VISIBLE",
	"post_need_approve": false,
	"current_user_status": "GUEST",
	"alias": "",
	"is_hot": false,
	"approve_requests": "Auto",
	"hidden_managers": false,
	"background_image": "",
	"has_rules": false,
	"background_position": 0,
	"labels": [],
	"current_user_joined_at": "0",
	"score": 0,
	"total_post": "0",
	"preview_members": [],
	"current_member": {
		"user_id": "",
		"role": ""
	},
	"premium_status": "Free",
	"workspace_group": false,
	"workspace_id": "",
	"workspace_name": ""
}
```

Get group:
`GET https://api.gapo.vn/group/v1.1/groups/2352381379997745152`
Response:
```json
{
	"data": Group
}
```
#### Search

Search for users:
`GET https://api.gapo.vn/search/v2.0/search-user?q=joe&page_number=1&limit=10`
Response:
```json
{
	"code": 200,
	"message": "Đã xử lý thành công!", // Successfully processed!
	"data": [User],
	"links": {
    	"next": "page_number=2&limit=10&q=joe",
    	"prev": "",
    	"total_pages": 500
	}
}
```


Search for groups:
`GET https://api.gapo.vn/search/v2.0/search-group?q=football&page_number=1&limit=10`
Response:
```json
{
	"code": 200,
	"message": "Đã xử lý thành công!", // Successfully processed!
	"data": [Group],
	"links": {
    	"next": "page_number=2&limit=10&q=football",
    	"prev": "",
    	"total_pages": 500
	}
}
```


Search for pages:
`GET https://api.gapo.vn/search/v2.0/search-page?q=football&page_number=1&limit=10`
Response:
```json
{
	"code": 200,
	"message": "Đã xử lý thành công!", // Successfully processed!
	"data": [Page],
	"links": {
    	"next": "page_number=2&limit=10&q=football",
    	"prev": "",
    	"total_pages": 500
	}
}
```

