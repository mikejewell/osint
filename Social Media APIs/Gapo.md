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

#### Accounts

##### Get User Profile
GET https://api.gapo.vn/user-profile/v1.0/profile/21387

Response:
```json
{
	"code": 200,
	"data": User,
	"message": "Ok"
}
```

##### Search Users

GET https://api.gapo.vn/search/v2.0/search-user?q=football&page_number=1&limit=10

Response:
```json
{
	"code": 200,
	"message": "Đã xử lý thành công!", // Successfully processed!
	"data": [User]
}
```

```json
{
    "user_id": 21387,
    "full_name": "Trần Văn Tuấn",
    "display_name": "Văn Tuấn",
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
      "education": [
        {
          "school": "THPT Phạm Thành Trung",
          "title": "",
          "privacy": 1
        }
      ],
      "work": [
        {
          "company": "ⓖⓐⓟⓞ",
          "title": "Fan",
          "privacy": 1
        }
      ],
      "bio": "Kết bạn em nha 😍 \nSự cố gắng luôn được đền đáp xứng đáng"
    },
    "interest": [
      29,
      104,
      106
    ],
    "hobbies": [
      {
        "id": 4,
        "title": "Ăn uống",
        "icon": "https://image-1.gapo.vn/images/e564e836-d89d-4e7c-8907-7a400fb1f9e1.png"
      },
      {
        "id": 5,
        "title": "Nghe nhạc",
        "icon": "https://image-1.gapo.vn/images/38f02ccd-7a94-4d04-930e-6cd318d63331.png"
      },
      {
        "id": 8,
        "title": "Vẽ",
        "icon": "https://image-1.gapo.vn/images/8b340baa-d6f9-4e98-8897-4a0dd80ae567.png"
      },
      {
        "id": 11,
        "title": "Đọc sách",
        "icon": "https://image-1.gapo.vn/images/b94b8136-9212-4c7e-a97d-86c5f2a34a6d.png"
      },
      {
        "id": 16,
        "title": "Nhiếp ảnh",
        "icon": "https://image-1.gapo.vn/images/51a13724-839d-487f-be8f-886f59d5fb7b.png"
      },
      {
        "id": 17,
        "title": "Hoạt hình",
        "icon": "https://image-1.gapo.vn/images/bd087f35-4635-4b6e-b73a-43fcde43e985.png"
      },
      {
        "id": 24,
        "title": "V-pop",
        "icon": "https://image-1.gapo.vn/images/7844d421-8083-433d-a0e5-faa3ff300af3.png"
      },
      {
        "id": 25,
        "title": "K-pop",
        "icon": "https://image-1.gapo.vn/images/9b5031db-532e-437c-8235-67ba86addee3.png"
      },
      {
        "id": 28,
        "title": "Đồ công nghệ",
        "icon": "https://image-1.gapo.vn/images/7a9d2091-5b96-480c-ace0-0aa179af8a4e.png"
      }
    ],
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