with modify of https://github.com/facebook/react-native/issues/28298 
```
int openNoInt(const char* name, int flags, mode_t mode) {
  ssize_t r;
  do {
    r = open(name, flags, mode);
  } while (r == -1 && errno == EINTR);
  return r;
}
```

and we download zip files only once.