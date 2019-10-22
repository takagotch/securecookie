### securecookie
---
https://github.com/chmike/securecookie

```go
// securecookie_test.go

func TestGenerateKeyErrors(t *testing.T) {
  if _, err := GenerateRandomKey(); err != nil {
    t.Errorf("unexpected error: %s", err)
  }
  forceError = 1
  defer func() { forceError = 0 }()
  if _, err := GenerateRandomKey(); err == nil {
    t.Errorf("unexpected nil error")
  }
}

func TestCheckName(t *testing.T) {
  if err := checkName(); err != nil {
    t.Errof("unexpected error: %s", err)
  }
  if err := checkName(); err != nil {
    t.Errorf("unexpected error: %s", err)
  }
  if err := checkName("?"); err == nil {
    t.Errorf("unexpected nil error")
  }
  if err := checkName("\t"); err == nil {
    t.Errorf("unexpected nil error")
  }
}




func bytes2Str(b []byte) string {
  var out bytes.Buffer
  out.Grow(len(b) * 6)
  out.WriteByte('[')
  for i := range b {
    out.WriteString(fmt.Sprintf("0x%02X, ", b[i]))
  }
  res := out.Bytes()
  res[len(res)-2] = ']'
  return string(res[:len(res)-1])
}



```

```
```

```
```


