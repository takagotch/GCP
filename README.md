### GCP Google Clound Platform
---
https://github.com/GoogleCloudPlatform

```py
// https://github.com/GoogleCloudPlatform/python-docs-samples
// trace/main_test.py
import os
import main

def test_index():
  project_id = os.environ['GCLOUD_PROJECT']
  main.app.testing = True
  main.app.config['TRACER'] = main.initialize_tracer(project_id)
  client = main.app.test_client()
  
  resp = client.get('/index.html')
  assert resp.status_code == 200
  assert 'Tracing requests' in resp.data.decode('utf-8')

def test_redirect():
  project_id = os.environ['GCLOUD_PROJECT']
  main.app.testing = True
  main.app.config['TRACER'] = main.initialize_tracer(project_id)
  client = main.app.test_client()
  
  resp = client.get('/')
  assert resp.status_code == 302
  assert '/index.html' in resp.headers.get('location', '')
```

```
```

```
```


