# JavaScript HTTP Snippet Pack for VS Code
VS Code extension for http requests snippets with Axios, Fetch and Superagent

You can install it [Here](https://marketplace.visualstudio.com/items?itemName=Heigen007.http-requests-snippets-extension)
## Usage

-----------------------------------------

This extension ships a bunch of useful http libraries snippets for the JavaScript editors.

Here's the full list of all the snippets:

# Axios

### [axHead] axios.head

```javascript
  axios.head('$1')
  .then(() => {
      console.log('OK')
  })
  .catch(err => {
      console.log(err)
  })
```

### [axGet] axios.get

```javascript
  axios.get('$1')
  .then(res => {
    console.log(res)
  })
  .catch(err => {
    console.log(err)
  })
```

### [axPost] axios.post

```javascript
  axios.post('$1', {$2})
  .then(res => {
    console.log(res)
  })
  .catch(err => {
    console.log(err)
  })
```

### [axDel] axios.delete

```javascript
  axios.delete('$1', { data: {$2} })
  .then(res => {
    console.log(res)
  })
  .catch(err => {
    console.log(err)
  })
```

### [axPut] axios.put

```javascript
  axios.put('$1', {$2})
  .then(res => {
    console.log(res)
  })
  .catch(err => {
    console.log(err)
  })
```

### [axPatch] axios.patch

```javascript
  axios.patch('$1', {$2})
  .then(res => {
    console.log(res)
  })
  .catch(err => {
    console.log(err)
  })
```

### [axOpt] axios.options

```javascript
  axios.options('$1')
  .then(res => {
    console.log(res)
  })
  .catch(err => {
    console.log(err)
  })
```

### [axFullOpt] axios full options list

```javascript
  axios({,
      url: '/user',
      method: 'get',
      baseURL: 'https://some-domain.com/api/',
      transformRequest: [function (data, headers) {
        return data;
      }],
      transformResponse: [function (data) {
        return data;
      }],
      headers: {'X-Requested-With': 'XMLHttpRequest'},
      params: {
        ID: 12345
      },
      paramsSerializer: function(params) {
        return Qs.stringify(params, {arrayFormat: 'brackets'})
      },
      data: {
        firstName: 'Fred'
      },
      timeout: 1000,
      withCredentials: false, // default
      adapter: function (config) {
        /* ... */
      },
      auth: {
        username: 'janedoe',
        password: 's00pers3cret'
      },,
      responseType: 'json', // default
      xsrfCookieName: 'XSRF-TOKEN', // default
      xsrfHeaderName: 'X-XSRF-TOKEN', // default
      onUploadProgress: function (progressEvent) {},
      onDownloadProgress: function (progressEvent) {},
      maxContentLength: 2000,
      validateStatus: function (status) {
        return status >= 200 && status < 300; // default
      },,
      maxRedirects: 5, // default
      httpAgent: new http.Agent({ keepAlive: true }),
      httpsAgent: new https.Agent({ keepAlive: true }),
      proxy: {
        host: '127.0.0.1',
        port: 9000,
        auth: {
        username: 'mikeymike',
        password: 'rapunz3l'
        }
      },
      cancelToken: new CancelToken(function (cancel) {})
  }),
  .then(res => {
    console.log(res)
  })
  .catch(err => {
    console.log(err)
  })
```

### [axCreate] axios.create

```javascript
  const instance = axios.create({
    baseURL: $1,
    headers: {$2},
    timeout: 10000
  });
```

### [axIntercept] axios interception

```javascript
  axios.interceptors.request.use(
    request => {
      if ($1) {
        return request;
      }
      else {
        throw { someValue: 'someValue' };
      }
    },
    error => {
      return Promise.reject(error);
    }
  )
```


# Fetch

### [fchHead] fetch head method

```javascript
  fetch('$1', {
    method: 'HEAD',
  })
  .then(res => console.log(res))
```

### [fchGet] fetch get method

```javascript
  fetch('$1')
  .then(response => {
    return response.json()
  })
  .then(res => console.log(res))
```

### [fchOpt] fetch post method

```javascript
  fetch('$1', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json;charset=utf-8'
    },
    body: JSON.stringify({})
  })
  .then(response => {
    return response.json()
  })
  .then(res => console.log(res))
```

### [fchDel] fetch delete method

```javascript
  fetch('$1', {
    method: 'DELETE',
    headers: {
      'Content-Type': 'application/json;charset=utf-8'
    },
    body: JSON.stringify({})
  })
  .then(response => {
    return response.json()
  })
  .then(res => console.log(res))
```

### [fchPut] fetch put method

```javascript
  fetch('$1', {
    method: 'PUT',
    headers: {
      'Content-Type': 'application/json;charset=utf-8'
    },
    body: JSON.stringify({})
  })
  .then(response => {
    return response.json()
  })
  .then(res => console.log(res))
```

### [fchPatch] fetch patch method

```javascript
  fetch('$1', {
    method: 'PATCH',
    headers: {
      'Content-Type': 'application/json;charset=utf-8'
    },
    body: JSON.stringify({})
  })
  .then(response => {
    return response.json()
  })
  .then(res => console.log(res))
```

### [fchOpt] fetch options method

```javascript
  fetch('$1', {
    method: 'OPTIONS',
  })
  .then(response => {
    return response.json()
  })
  .then(res => console.log(res))
```

### [fchIntercept] fetch interception

```javascript
  const constantMock = window.fetch;
  window.fetch = function() {
    if(true) return constantMock.apply(this, arguments)
  }
```

# Superagent

### [supHead] superagent head method

```javascript
  superagent,
    .head('$1')
    .query({$2})
    .then(res => {
      console.log(res);
    })
    .catch(err => {
      console.log(err);
    });
```

### [supGet] superagent get method

```javascript
  superagent
    .get('$1')
    .query({$2})
    .then(res => {
      console.log(res);
    })
    .catch(err => {
      console.log(err);
    });
```

### [supPost] superagent post method

```javascript
  superagent,
    .post('$1')
    .send({$2})
    .then(res => {
      console.log(res);
    })
    .catch(err => {
      console.log(err);
    });
```

### [supDel] superagent delete method

```javascript
  superagent,
    .post('$1')
    .del({$2})
    .then(res => {
      console.log(res);
    })
    .catch(err => {
      console.log(err);
    });
```

### [supPut] superagent put method

```javascript
  superagent
    .put('$1')
    .send({$2})
    .then(res => {
      console.log(res);
    })
    .catch(err => {
      console.log(err);
    });
```

### [supPatch] superagent patch method

```javascript
  superagent
    .patch('$1')
    .send({$2})
    .then(res => {
      console.log(res);
    })
    .catch(err => {
      console.log(err);
    });
```

### [supOpt] superagent options method

```javascript
  superagent
    .options('$1')
    .then(res => {
      console.log(res);
    })
    .catch(err => {
      console.log(err);
    });
```
