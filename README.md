# javac bug

Run:
```
mkdir bin
javac -sourcepath src src/org/example/Common.java src/org/example/impl/Common.java src/org/example/impl/Util.java -d bin
```

Java 8 succeeds, Java 9/10/11 fails:
```
src\org\example\impl\Util.java:7: error: cannot access Common
        System.out.println(Common.X);
                           ^
  bad source file: src\org\example\Common.java
    file does not contain class org.example.Common
    Please remove or make sure it appears in the correct subdirectory of the sourcepath.
1 error
```
