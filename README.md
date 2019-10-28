# STM32F7HTTPS

This is a simple HTTPS Client for the STM32F7 MCU by ST.
For some reasons there is no sample mbedtls client/server project included for this Controller hence this project.
Tested with the STM32F746NG Discovery Kit (no hardware acceleration :( ).
Basic Features:

- mbedtls
- threaded by freertos
- list of ca's
- simple https GET request
- Lcd Display Log

# IDE

I used the ST System Workbench (just import the SW4STM32 Directory) but you can import it with a variety of Editors

# Usage

1. Set up simple https server
```
openssl req -newkey rsa:2048 -new -nodes -x509 -days 3650 -keyout key.pem -out cert.pem
echo "success!!" > test.html
openssl s_server -key key.pem -cert cert.pem -accept 44330 -WWW
```

2. adjust main.h

replace SERVER_NAME with your IP address

3. Compile and Flash your MCU
