1. #### php安装xdebug扩展
   >      pecl install xdebug
2. #### 配置php.ini
   >     xdebug.remote_enable=On  
   >     xdebug.idekey=PHPSTORM (下面配置chrome浏览器的debug会用到)
   >     xdebug.remote_port=9100 (默认是9000会和php-fpm的端口冲突)
3. #### 配置phpstorm
   ![loading](../../images/xdebug-port.png)
   ![loading](../../images/xdebug-server.png)
