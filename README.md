# md_xhprof
```
为xhprof升级版,与PHP7配合使用
#使用时需要设置环境变量
export USE_ZEND_DTRACE=1
```
# 安装
```

# 快速安装
curl -fsSL  https://raw.githubusercontent.com/midoks/md_xhprof/master/scripts/install.sh | sh


cd ~~/md_xhprof/src
$DIR/php/$PHP_VER/bin/phpize
./configure \
--with-php-config=~~/php7/bin/php-config --enable-debug
make && make install 

```

# 使用方法及原因

- PHP7编译时要使用(--enable-dtrace)
 * http://lxr.php.net/xref/PHP-7.0/Zend/zend.c#687
 * http://lxr.php.net/xref/PHP-7.1/Zend/zend.c#702

# 调试

- export USE_ZEND_ALLOC=0 	#关闭内存管理
- export USE_ZEND_DTRACE=1 	#开启DTRACE调试
- yum install valgrind
- valgrind --leak-check=full php leak.php
- php -dvld.active=1 leak.php 
