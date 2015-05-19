# tokens library

A Java library that keeps OAuth 2.0 service access tokens in memory for your usage.

## Usage

```java
AccessTokens tokens = Tokens.createAccessTokensWithUri(new URI("https://example.com/access_tokens"))
                            .manageToken("exampleRW")
                                .addScope("read")
                                .addScope("write")
                                .done()
                            .manageToken("exampleRO")
                                .addScope("read")
                                .done()
                            .start();

while (true) {
    final String token = tokens.get("exampleRO");
    System.out.println("RO token: " + token);

    Thread.sleep(1000);
}
```

## License

Copyright © 2015 Zalando SE

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   [http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
