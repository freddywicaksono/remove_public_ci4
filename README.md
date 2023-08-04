# Codeigniter 4 - Remove index.php nd public from CI-4 URL
Here is example URL in CI-4
```
http://localhost/demo/public/
http://localhost/demo/public/index.php/students
```
You want to remove public from the URL and will be:
```
http://localhost/demo/
http://localhost/demo/students
```
Follow this step:
## 1. Edit file app/Config/App.php
```
public string $baseURL = 'http://localhost:8080/';
public string $indexPage = 'index.php';
public string $uriProtocol = 'REQUEST_URI';
```
change to:
```
public string $baseURL = 'http://localhost/demo/';
public string $indexPage = '';
public string $uriProtocol = 'PATH_INFO';

```
