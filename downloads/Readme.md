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

windows build with MAX_PATH 260 limitation can read this for help:
```
https://www.howtogeek.com/266621/how-to-make-windows-10-accept-file-paths-over-260-characters/
```