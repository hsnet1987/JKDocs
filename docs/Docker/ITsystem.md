### 
PHP > 8.0  
扩展  
fileinfo  
sockets  
opcache  
pdo_mysql  
mbstring  
禁用函数  
putenv  
proc_open  
symlink  

### 安装依赖

```
composer require dcat/laravel-admin:"2.*" -vvv
```

### 执行安装

````
php artisan cklist:install
````

### 伪静态规则为

```
location / {
    try_files $uri $uri/ /index.php?$query_string;
} 
```

默认用户密码 admin/admin