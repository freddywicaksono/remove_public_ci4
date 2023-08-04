# Codeigniter 4 

### Remove Port, index.php and public from URL
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
## 2. Copy file .htaccess and index.php from public folder to root directory
Edit file index.php in root directory:
```
require FCPATH . '../app/Config/Paths.php';
```
change into :
```
require FCPATH . 'app/Config/Paths.php';
```
