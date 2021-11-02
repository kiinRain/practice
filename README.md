# test
<<<<<<< HEAD
none
=======

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

## Error
分支合并主干
Git push 时 fatal: unable to access 'https://github.com/****/**.git/': OpenSSL SSL_connect: SSL_ERROR_SYSCALL in connection to github.com:443 
解决方法 ：取消http代理：

$ git config --global --unset http.proxy
$ git config --global --unset https.proxy

设置env GIT_SSL_NO_VERIFY为true然后再次部署：

$ env GIT_SSL_NO_VERIFY=true 

