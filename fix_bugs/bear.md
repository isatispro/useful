
# bear 报错
``` shell
bear -- make
cd src && /Applications/Xcode.app/Contents/Developer/usr/bin/make all
    CC Makefile.dep
    CC adlist.o
wrapper: failed with: gRPC call failed: failed to connect to all addresses
make[1]: *** [adlist.o] Error 1
make: *** [all] Error 2
```

因为proxy导致，设置以下环境变量可解决
``` shell
export no_proxy=localhost,127.0.0.1
```

[github issues](https://github.com/rizsotto/Bear/issues/419)

