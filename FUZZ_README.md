1. Generate makefiles

```
auto/configure \
    --with-cc-opt='-DNGX_DEBUG_PALLOC=1' \
    --with-http_v2_module
```

2. Generate compilation database

```
bear -- make
```

3. Run fuzz test stub

```
cifuzz run fuzz --build-command "make -f objs/Makefile fuzzers"
```

4. Run spark
```
cifuzz spark --build-command "make -f cifuzz-spark/Makefile fuzzer" --build-dir . --build-file cifuzz-spark/Makefile

```
