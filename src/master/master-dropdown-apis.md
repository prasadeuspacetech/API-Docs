# API Master Documentation

**Base URL:** `http://bandhan-setu-prod.eba-am6hwsad.ap-south-1.elasticbeanstalk.com`

---

## GET Martial Status (MASTER)

**Endpoint:**
`GET /api/auth/marital-statuses/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US

```

**Request:**
No request body required

**Response (200):**
```json
[
    {
        "id": "ms02b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Divorced"
    },
    {
        "id": "ms01a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "Never Married"
    },
    {
        "id": "ms05e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Separated"
    },
    {
        "id": "ms03c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "Widowed"
    }
]
```

---

## GET Religion (MASTER)

**Endpoint:**
`GET /api/auth/religions/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US
```

**Request:**
No request body required

**Response (200):**
```json
[
    {
        "id": "r006f6a1b2c3d4e5f6a1b2c3d4e5f6a1",
        "label": "Buddhist"
    },
    {
        "id": "37de2b4e6a074cbd8dc358a5065a9f06",
        "label": "dummy religion"
    },
    {
        "id": "r001a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "Hindu"
    },
    {
        "id": "r005e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Jain"
    },
    {
        "id": "r008b2c3d4e5f6a1b2c3d4e5f6b2b2c3",
        "label": "Jewish"
    },
    {
        "id": "r002b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Muslim"
    },
    {
        "id": "r007a1b2c3d4e5f6a1b2c3d4e5f6b2b2",
        "label": "Parsi"
    },
    {
        "id": "r004d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "Sikh"
    }
]
```

---

## GET Cast (MASTER)

**Endpoint:**
`GET /api/auth/castes/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US
```

**Query Params:**
- `religion_id` : string (required)

**Example:**
`/api/auth/castes/list?religion_id=r001a1b2c3d4e5f6a1b2c3d4e5f6a1b2`

**Response (200):**
```json
[
    {
        "id": "ca01a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "Brahmin"
    },
    {
        "id": "ca02b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Kshatriya"
    },
    {
        "id": "ca11e5f6a1b2c3d4e5f6c2b2c3d4e5f6",
        "label": "Lingayat"
    },
    {
        "id": "ca06f6a1b2c3d4e5f6a1b2c3d4e5f6a1",
        "label": "Maratha"
    },
    {
        "id": "ca10d4e5f6a1b2c3d4e5f6c2b2c3d4e5",
        "label": "Naidu"
    },
    {
        "id": "ca09c3d4e5f6a1b2c3d4e5f6c2b2c3d4",
        "label": "Nair"
    },
    {
        "id": "ca07a1b2c3d4e5f6a1b2c3d4e5f6c2b2",
        "label": "Patel"
    },
    {
        "id": "ca05e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Rajput"
    },
    {
        "id": "ca08b2c3d4e5f6a1b2c3d4e5f6c2b2c3",
        "label": "Reddy"
    },
    {
        "id": "ca04d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "Shudra"
    },
    {
        "id": "ca03c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "Vaishya"
    },
    {
        "id": "ca12f6a1b2c3d4e5f6c2b2c3d4e5f6a1",
        "label": "Vokkaliga"
    }
]
```

**Response (400):**
```json
{
    "message": "Invalid religion_id(s): r001a1b2c3d4e5f6a1b2c3d4e5f6a1"
}
```

**Response (400):**
```json
{
    "message": "religion_id query parameter is required."
}
```

---

## GET Subcast (MASTER)

**Endpoint:**
`GET /api/auth/subcastes/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US
```

**Query Params:**
- `caste_id` : string (required)

**Example:**
`/api/auth/subcastes/list?caste_id=ca01a1b2c3d4e5f6a1b2c3d4e5f6a1b2`

**Response (200):**
```json
[
    {
        "id": "sc03c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "Deshastha"
    },
    {
        "id": "sc02b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Iyengar"
    },
    {
        "id": "sc01a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "Iyer"
    },
    {
        "id": "sc04d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "Koknastha"
    },
    {
        "id": "sc06f6a1b2c3d4e5f6a1b2c3d4e5f6a1",
        "label": "Niyogi"
    },
    {
        "id": "sc05e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Saraswat"
    }
]
```

**Response (400):**
```json
{
    "message": "Invalid caste_id(s): ca01a1b2c3d4e5f6a1b2c3d4e5f6a1b"
}
```

**Response (400):**
```json
{
    "message": "caste_id query parameter is required."
}
```

---

## GET Education-Levels (MASTER)

**Endpoint:**
`GET /api/auth/education-levels/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US
```

**Request:**
No request body required

**Response (200):**
```json
[
    {
        "id": "el03c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "Bachelor's Degree"
    },
    {
        "id": "el02b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Diploma"
    },
    {
        "id": "el05e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Doctorate (PhD)"
    },
    {
        "id": "41c183792fa14b3d949572eaa32673c8",
        "label": "High School"
    },
    {
        "id": "el04d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "Master's Degree"
    },
    {
        "id": "el06f6a1b2c3d4e5f6a1b2c3d4e5f6a1",
        "label": "Professional Degree"
    }
]
```

---

## GET Education-fields (MASTER)

**Endpoint:**
`GET /api/auth/education-fields/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US
```

**Query Params:**
- `education_level_id` : string (required)

**Example:**
`/api/auth/education-fields/list?education_level_id=el03c3d4e5f6a1b2c3d4e5f6a1b2c3d4`

**Response (200):**
```json
[
    {
        "id": "ef04d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "Arts / Humanities"
    },
    {
        "id": "ef03c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "Commerce / Accounting"
    },
    {
        "id": "ef01a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "Engineering / Technology"
    },
    {
        "id": "ef06f6a1b2c3d4e5f6a1b2c3d4e5f6a1",
        "label": "Law"
    },
    {
        "id": "ef02b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Medicine / MBBS"
    },
    {
        "id": "ef05e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Science"
    }
]
```

**Response (400):**
```json
{
    "message": "education_level_id query parameter is required."
}
```

**Response (400):**
```json
{
    "message": "Invalid education_level_id(s): el03c3d4e5f6a1b2c3d4e5f6a1b2c3d"
}
```

---

## GET Income (MASTER)

**Endpoint:**
`GET /api/auth/incomes/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US
```

**Request:**
No request body required

**Response (200):**
```json
[
    {
        "id": "628e46b3da264fb3b411db916250d858",
        "label": "no income"
    },
    {
        "id": "ai02b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Below 1 Lakh"
    },
    {
        "id": "e13444860b0e4f3a83e03af26bf97b4a",
        "label": "1.5 to 2 lakh"
    },
    {
        "id": "ai03c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "1 - 2 Lakh"
    },
    {
        "id": "ai04d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "2 - 4 Lakh"
    },
    {
        "id": "ai05e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "4 - 6 Lakh"
    },
    {
        "id": "ai06f6a1b2c3d4e5f6a1b2c3d4e5f6a1",
        "label": "6 - 10 Lakh"
    },
    {
        "id": "ai07a1b2c3d4e5f6a1b2c3d4e5f6i1b2",
        "label": "10 - 15 Lakh"
    },
    {
        "id": "ai08b2c3d4e5f6a1b2c3d4e5f6i1b2c3",
        "label": "15 - 20 Lakh"
    },
    {
        "id": "ai09c3d4e5f6a1b2c3d4e5f6i1b2c3d4",
        "label": "20 - 30 Lakh"
    },
    {
        "id": "ai11e5f6a1b2c3d4e5f6i1b2c3d4e5f6",
        "label": "50 Lakh - 1 Crore"
    },
    {
        "id": "ai10d4e5f6a1b2c3d4e5f6i1b2c3d4e5",
        "label": "30 - 60 Lakh"
    },
    {
        "id": "ai12f6a1b2c3d4e5f6i1b2c3d4e5f6a1",
        "label": "Above 1 Crore"
    }
]
```

---

## GET Country (MASTER)

**Endpoint:**
`GET /api/auth/countries/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US
```

**Request:**
No request body required

**Response (200):**
```json
[
    {
        "id": "a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "India"
    },
    {
        "id": "9ecd7733e4c741ed9dcadc85b2790184",
        "label": "test country"
    },
    {
        "id": "c5ba78f02c3346caa6ffd1dd213fb033",
        "label": "test country 1"
    }
]
```

---

## GET State (MASTER)

**Endpoint:**
`GET /api/auth/states/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US
```

**Query Params:**
- `country_id` : string (required)

**Example:**
`/api/auth/states/list?country_id=a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4`

**Response (200):**
```json
[
    {
        "id": "s009c3d4e5f6a1b2c3d4e5f6b1b2c3d4",
        "label": "Andhra Pradeshhh"
    },
    {
        "id": "s029e5f6c1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Arunachal Pradeshhh"
    },
    {
        "id": "s016d4e5f6b1b2c3d4e5f6a1b2c3d4e5",
        "label": "Assam"
    },
    {
        "id": "s013a1b2c3d4e5f6b1b2c3d4e5f6a1b2",
        "label": "Bihar"
    },
    {
        "id": "s018f6b1b2c3d4e5f6a1b2c3d4e5f6a1",
        "label": "Chhattisgarh"
    },
    {
        "id": "s022d4e5f6a1b2c3d4e5f6c1b2c3d4e5",
        "label": "Delhi"
    },
    {
        "id": "s021c3d4e5f6a1b2c3d4e5f6c1b2c3d4",
        "label": "Goa"
    },
    {
        "id": "s002b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Gujarat"
    },
    {
        "id": "s012f6a1b2c3d4e5f6b1b2c3d4e5f6a1",
        "label": "Haryana"
    },
    {
        "id": "s020b2c3d4e5f6a1b2c3d4e5f6c1b2c3",
        "label": "Himachal Pradesh"
    },
    {
        "id": "s023e5f6a1b2c3d4e5f6c1b2c3d4e5f6",
        "label": "Jammu & Kashmir"
    },
    {
        "id": "s017e5f6b1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Jharkhand"
    },
    {
        "id": "6c9690db0a5b435a998cdf74e3e44a4b",
        "label": "jhweef"
    },
    {
        "id": "s006f6a1b2c3d4e5f6a1b2c3d4e5f6a1",
        "label": "Karnataka"
    },
    {
        "id": "s008b2c3d4e5f6a1b2c3d4e5f6b1b2c3",
        "label": "Kerala"
    },
    {
        "id": "s005e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Madhya Pradesh"
    },
    {
        "id": "s001a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "Maharashtra"
    },
    {
        "id": "s024f6a1b2c3d4e5f6c1b2c3d4e5f6a1",
        "label": "Manipur"
    },
    {
        "id": "s025a1b2c3d4e5f6c1b2c3d4e5f6a1b2",
        "label": "Meghalaya"
    },
    {
        "id": "s028d4e5f6c1b2c3d4e5f6a1b2c3d4e5",
        "label": "Mizoram"
    },
    {
        "id": "s027c3d4e5f6c1b2c3d4e5f6a1b2c3d4",
        "label": "Nagaland"
    },
    {
        "id": "s015c3d4e5f6b1b2c3d4e5f6a1b2c3d4",
        "label": "Odisha"
    },
    {
        "id": "s011e5f6a1b2c3d4e5f6b1b2c3d4e5f6",
        "label": "Punjab"
    },
    {
        "id": "s003c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "Rajasthan"
    },
    {
        "id": "s030f6c1b2c3d4e5f6a1b2c3d4e5f6a1",
        "label": "Sikkim"
    },
    {
        "id": "s007a1b2c3d4e5f6a1b2c3d4e5f6b1b2",
        "label": "Tamil Nadu"
    },
    {
        "id": "s010d4e5f6a1b2c3d4e5f6b1b2c3d4e5",
        "label": "Telangana"
    },
    {
        "id": "s026b2c3d4e5f6c1b2c3d4e5f6a1b2c3",
        "label": "Tripura"
    },
    {
        "id": "s004d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "Uttar Pradesh"
    },
    {
        "id": "s019a1b2c3d4e5f6a1b2c3d4e5f6c1b2",
        "label": "Uttarakhand"
    },
    {
        "id": "s014b2c3d4e5f6b1b2c3d4e5f6a1b2c3",
        "label": "West Bengal"
    }
]
```

**Response (400):**
```json
{
    "message": "Invalid country_id(s): a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d"
}
```

**Response (400):**
```json
{
    "message": "country_id query parameter is required."
}
```

---

## GET CITIES (MASTER)

**Endpoint:**
`GET /api/auth/cities/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US
```

**Query Params:**
- `state_id` : string (required)

**Example Request:**
`/api/auth/cities/list?state_id=s014b2c3d4e5f6b1b2c3d4e5f6a1b2c3`

**Response (200):**
```json
[
    {
        "id": "c031a1b2c3d4e5f6e1b2c3d4e5f6a1b2",
        "label": "Kolkata"
    },
    {
        "id": "c032b2c3d4e5f6e1b2c3d4e5f6a1b2c3",
        "label": "Siliguri"
    }
]
```

**Response (400):**
```json
{
    "message": "Invalid state_id(s): s014b2c3d4e5f6b1b2c3d4e5f6a1b2c"
}
```

**Response (400):**
```json
{
    "message": "state_id query parameter is required."
}
```

---

## GET Diets (MASTER)

**Endpoint:**
`GET /api/auth/diets/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US

```

**Response (200):**
```json
[
    {
        "id": "di03c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "Eggetarian"
    },
    {
        "id": "di05e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Jain"
    },
    {
        "id": "di02b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Non-Vegetarian"
    },
    {
        "id": "di06f6a1b2c3d4e5f6a1b2c3d4e5f6a1",
        "label": "Occasionally Non-Veg"
    },
    {
        "id": "di04d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "Vegan"
    },
    {
        "id": "di01a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "Vegetarian"
    }
]
```

---

## GET Body-types (MASTER)

**Endpoint:**
`GET /api/auth/body-types/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US

```

**Response (200):**
```json
[
    {
        "id": "bt02b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Athletic"
    },
    {
        "id": "bt03c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "Average"
    },
    {
        "id": "bt04d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "Heavy"
    },
    {
        "id": "bt05e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Plus Size"
    },
    {
        "id": "bt01a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "Slim"
    }
]
```

---

## GET Skins-tones (MASTER)

**Endpoint:**
`GET /api/auth/skin-tones/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US

```

**Response (200):**
```json
[
    {
        "id": "st05e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Dark"
    },
    {
        "id": "st02b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Fair"
    },
    {
        "id": "st01a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "Very Fair"
    },
    {
        "id": "st03c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "Wheatish"
    },
    {
        "id": "st04d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "Wheatish Brown"
    }
]
```

---

## GET Currency (MASTER)

**Endpoint:**
`GET /api/auth/currencies/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US

```

**Response (200):**
```json
[
    {
        "id": "b7eadf67722143e3ac865edcb6361e79",
        "label": "Doller"
    },
    {
        "id": "cu01a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "INR - Indian Rupee"
    }
]
```

---

## GET Mother-Tongues (MASTER)

**Endpoint:**
`GET /api/auth/mother-tongues/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US

```

**Response (200):**
```json
[
    {
        "id": "mt14b2c3d4e5f6f1b2c3d4e5f6a1b2c3",
        "label": "Assamese"
    },
    {
        "id": "mt08b2c3d4e5f6a1b2c3d4e5f6f1b2c3",
        "label": "Bengali"
    },
    {
        "id": "mt16d4e5f6f1b2c3d4e5f6a1b2c3d4e5",
        "label": "English"
    },
    {
        "id": "mt03c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "Gujarati"
    },
    {
        "id": "mt01a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "Hindi"
    },
    {
        "id": "mt06f6a1b2c3d4e5f6a1b2c3d4e5f6a1",
        "label": "Kannada"
    },
    {
        "id": "mt13a1b2c3d4e5f6f1b2c3d4e5f6a1b2",
        "label": "Konkani"
    },
    {
        "id": "mt15c3d4e5f6f1b2c3d4e5f6a1b2c3d4",
        "label": "Maithili"
    },
    {
        "id": "mt07a1b2c3d4e5f6a1b2c3d4e5f6f1b2",
        "label": "Malayalam"
    },
    {
        "id": "mt02b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Marathi"
    },
    {
        "id": "mt10d4e5f6a1b2c3d4e5f6f1b2c3d4e5",
        "label": "Odia"
    },
    {
        "id": "mt09c3d4e5f6a1b2c3d4e5f6f1b2c3d4",
        "label": "Punjabi"
    },
    {
        "id": "mt12f6a1b2c3d4e5f6f1b2c3d4e5f6a1",
        "label": "Sindhi"
    },
    {
        "id": "mt04d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "Tamil"
    },
    {
        "id": "mt05e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Telugu"
    },
    {
        "id": "mt11e5f6a1b2c3d4e5f6f1b2c3d4e5f6",
        "label": "Urdu"
    }
]
```

---

## GET working-categories (MASTER)

**Endpoint:**
`GET /api/auth/working-categories/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US

```

**Response (200):**
```json
[
    {
        "id": "wc10d4e5f6a1b2c3d4e5f6l1b2c3d4e5",
        "label": "Agriculture / Farming"
    },
    {
        "id": "wc06f6a1b2c3d4e5f6a1b2c3d4e5f6a1",
        "label": "Business / Trade"
    },
    {
        "id": "wc05e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Education / Teaching"
    },
    {
        "id": "wc03c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "Engineering"
    },
    {
        "id": "wc04d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "Finance / Banking"
    },
    {
        "id": "wc09c3d4e5f6a1b2c3d4e5f6l1b2c3d4",
        "label": "Government / Admin"
    },
    {
        "id": "wc01a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "IT / Software"
    },
    {
        "id": "wc07a1b2c3d4e5f6a1b2c3d4e5f6l1b2",
        "label": "Legal / Law"
    },
    {
        "id": "wc08b2c3d4e5f6a1b2c3d4e5f6l1b2c3",
        "label": "Media / Entertainment"
    },
    {
        "id": "wc02b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Medical / Healthcare"
    }
]
```

---

## GET working-subcategories (MASTER)

**Endpoint:**
`GET /api/auth/working-subcategories/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US

```

**Query Params:**
- `category_id`: string (required)

**Example:**
`/api/auth/working-subcategories/list?category_id=wc01a1b2c3d4e5f6a1b2c3d4e5f6a1b2`

**Response (200):**
```json
[
    {
        "id": "ws02b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Data Scientist"
    },
    {
        "id": "ws05e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "DevOps / Cloud"
    },
    {
        "id": "ws03c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "Product Manager"
    },
    {
        "id": "ws01a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "Software Engineer"
    },
    {
        "id": "ws04d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "UI/UX Designer"
    }
]
```

**Response (400):**
```json
{
    "message": "Invalid category_id(s): wc01a1b2c3d4e5f6a1b2c3d4e5f6a1b"
}
```

**Response (400):**
```json
{
    "message": "category_id query parameter is required."
}
```

---

## GET working-with (MASTER)

**Endpoint:**
`GET /api/auth/working-with/list`

**Headers:**
```
Authorization: Bearer {{token}}
x-app-type: user
Accept-Language: en-US

```

**Response (200):**
```json
[
    {
        "id": "ww05e5f6a1b2c3d4e5f6a1b2c3d4e5f6",
        "label": "Business / Entrepreneur"
    },
    {
        "id": "ww03c3d4e5f6a1b2c3d4e5f6a1b2c3d4",
        "label": "Defence / Civil Services"
    },
    {
        "id": "ww02b2c3d4e5f6a1b2c3d4e5f6a1b2c3",
        "label": "Government / PSU"
    },
    {
        "id": "ww07a1b2c3d4e5f6a1b2c3d4e5f6k1b2",
        "label": "NGO / Social Work"
    },
    {
        "id": "ww06f6a1b2c3d4e5f6a1b2c3d4e5f6a1",
        "label": "Not Working"
    },
    {
        "id": "ww01a1b2c3d4e5f6a1b2c3d4e5f6a1b2",
        "label": "Private Company"
    },
    {
        "id": "ww04d4e5f6a1b2c3d4e5f6a1b2c3d4e5",
        "label": "Self Employed"
    }
]
```
