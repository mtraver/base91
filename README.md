# base91
A Go implementation of base91 encoding with an interface as close as possible to that of the standard library's `encoding/base64` (https://golang.org/pkg/encoding/base64).

The `encoding/base64` `Encoding` type and this package's `Encoding` type both satisfy this interface:

```go
type BaseNEncoding interface {
  Decode(dst, src []byte) (int, error)
  DecodeString(s string) ([]byte, error)
  DecodedLen(n int) int
  
  // The signature of Encode is different in this package and
  // encoding/base64: this package returns the number of bytes
  // written because the encoded length cannot be known from just
  // the number of bytes to encode, whereas it can with base64.
  // Encode(dst, src []byte)
  
  EncodeToString(src []byte) string
  EncodedLen(n int) int
}
```
