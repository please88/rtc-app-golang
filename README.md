# rtc-app-golang

Golang AppServer for RTC.

You could also write AppServer by following languages:

* Golang: https://github.com/winlinvip/rtc-app-golang
* Java: https://github.com/winlinvip/rtc-app-java
* Python: https://github.com/winlinvip/rtc-app-python
* C#: https://github.com/winlinvip/rtc-app-csharp
* Nodejs: https://github.com/winlinvip/rtc-app-nodejs
* PHP: https://github.com/winlinvip/rtc-app-php

For RTC deverloper:

* RTC [workflow](https://help.aliyun.com/document_detail/74889.html).
* RTC [token generation](https://help.aliyun.com/document_detail/74890.html).

Use OpenAPI to create channel:

* Golang: https://help.aliyun.com/document_detail/74890.html#channel-golang
* Java: https://help.aliyun.com/document_detail/74890.html#channel-java
* Python: https://help.aliyun.com/document_detail/74890.html#channel-python
* C#: https://help.aliyun.com/document_detail/74890.html#channel-csharp
* Nodejs: https://help.aliyun.com/document_detail/74890.html#channel-nodejs
* PHP: https://help.aliyun.com/document_detail/74890.html#channel-php

Token generation algorithm:

* Golang: https://help.aliyun.com/document_detail/74890.html#token-golang
* Java: https://help.aliyun.com/document_detail/74890.html#token-java
* Python: https://help.aliyun.com/document_detail/74890.html#token-python
* C#: https://help.aliyun.com/document_detail/74890.html#token-csharp
* Nodejs: https://help.aliyun.com/document_detail/74890.html#token-nodejs
* PHP: https://help.aliyun.com/document_detail/74890.html#token-php

## Usage

1. Generate AK from [here](https://usercenter.console.aliyun.com/#/manage/ak):

```
AccessKeyID: OGAEkdiL62AkwSgs
AccessKeySecret: 4JaIs4SG4dLwPsQSwGAHzeOQKxO6iw
```

2. Create APP from [here](https://rtc.console.aliyun.com/#/manage):

```
AppID: iwo5l81k
```

3. Setup Golang enviroment, click [here](https://blog.csdn.net/win_lin/article/details/48265493).

4. Start AppServer, **use your information**:

```
go get -d github.com/winlinvip/rtc-app-golang &&
cd $GOPATH/src/github.com/winlinvip/rtc-app-golang &&
go run main.go --listen=8080 --access-key-id=OGAEkdiL62AkwSgs \
	--access-key-secret=4JaIs4SG4dLwPsQSwGAHzeOQKxO6iw --appid=iwo5l81k \
	--gslb=https://rgslb.rtc.aliyuncs.com
```

5. Verify  your AppServer by [here](http://ossrs.net/talks/ng_index.html#/rtc-check?schema=http&host=127.0.0.1&port=8080&path=/app/v1/login&room=1237&user=jzufp&password=12345678) or [verify token](http://ossrs.net/talks/ng_index.html#/token-check).

![AppServer Success](https://github.com/winlinvip/rtc-app-golang/raw/master/images/app-ok.png)

![AppServer Failed](https://github.com/winlinvip/rtc-app-golang/raw/master/images/app-failed.png)

![AppServer Error Recovered](https://github.com/winlinvip/rtc-app-golang/raw/master/images/app-recovered.png)

> Remark: You can setup client native SDK by `http://30.2.228.19:8080/app/v1`.

> Remark: Please use your AppServer IP instead by `ifconfig eth0`.

## History

* [2822108](https://github.com/winlinvip/rtc-app-golang/commit/2822108caafe03872e14b022deac4302fb16b6c9), Update SessionID generation algorithm.
* [a1b5c9d](https://github.com/winlinvip/rtc-app-golang/commit/a1b5c9de0edd2ef23e3874ee9c1f9a737c3afa01), Use HTTP, x3 times faster than HTTPS.
* [8e2761c](https://github.com/winlinvip/rtc-app-golang/commit/8e2761cd5e57ba87c10b73f0a2c49494090bb259), [19c59e3](https://github.com/winlinvip/rtc-app-golang/commit/19c59e382102de5aff6092615e98381574b2b63a), Set endpoint to get correct error.
* [f41b7cd](https://github.com/winlinvip/rtc-app-golang/commit/f41b7cd8e0ae5a945b09292b6bbeb0d335f413c8), Log the request id and cost in ms.
* [4b256ca](https://github.com/winlinvip/rtc-app-golang/commit/4b256caaee03c1c80dc29855bb065acbf153f88d), Support recover for some OpenAPI error.
* Support create channel and sign user token.
