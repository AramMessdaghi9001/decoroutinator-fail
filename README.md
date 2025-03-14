# Decoroutinator failing example

## Step 1
`./gradlew test` will succeed

## Step 2
`./gradlew build` will fail due to failing tests (as shadowJar plugin is involved)
```
> Task :app:test FAILED

MainTest > runTest() FAILED
    java.lang.NoClassDefFoundError at MainTest.kt:8
        Caused by: java.lang.ClassNotFoundException at MainTest.kt:8

1 test completed, 1 failed

FAILURE: Build failed with an exception.
```

## Step 3
`./gradlew shadowJar && java -jar app/build/libs/app-all.jar` will fail
```
Exception in thread "main" java.lang.NoClassDefFoundError: org/example/LibKt
        at org.example.MainKt.main(Main.kt:4)
        at org.example.MainKt.main(Main.kt)
Caused by: java.lang.ClassNotFoundException: org.example.LibKt
        at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:641)
        at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:188)
        at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:520)
        ... 2 more
```
