# API requests and responses

## Registration

### Request

#### Endpoint:
```
POST /api/?action=registration
```

#### Fields:

| Field | Desc | Possible Values |
|:---:|:---:|:---:|
| user_email | Self Explanatory | A valid email address string |
| user_name | Self Explanatory | A valid user name string |
| user_pass | Self Explanatory | A valid password |

### Response

#### Success Cases:

```js
    {
    "status": "Success"
    }
```


#### Failure Cases:
  
__Case 1__ - Email exists:

```js
    {
     "error": {
     "err_code": 0,
     "err_desc": "This email is already registered."
      }
    }
```

__Case 2__ - Username exists:

```js
    {
    "error": {
    "err_code": 1,
    "err_desc": "This username is taken."
       }
    }
```

__Case 3__ - Blank fields:

```js
    {
    "error": {
    "err_code": 2,
    "err_desc": "Please enter the details."
        }
    }
```

__Case 4__ - Query fail:

```js
    {
    "status": "Failed",
    "error": {
    "err_code": 5,
    "err_desc": "Internal server error."
       }
    }
```