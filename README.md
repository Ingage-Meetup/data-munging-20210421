# Data Munging Kata

## Description
[Blah blah blah, yada yada yada](http://codekata.com/kata/kata04-data-munging/)

## Reading a File
In order to give everyone a quick start, here are code snippets for reading a file in various languages.

### C#
```c#
// Need example code here
```

### JavaScript (NodeJS)
```javascript
var fileName = 'weather.dat';
var lines = require('fs')
                .readFileSync(fileName, 'utf-8') // Read the entire file as a string (not recommended for very large files, but fine here...)
                .split('\n'); // Split the string on carriage returns, resulting in an array with an entry per line
for (var line of lines) {
    var columns = line.split(/(\s+)/); // Split line on whitespace, to get columns
    // Do stuff with columns array...
} 
```

### Java
```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

...
String fileName = "weather.dat";
BufferedReader br = null;
try {
    br = new BufferedReader(new FileReader(fileName));
    String line = null;
    while (line = br.readLine() != null) {
        String[] columns = line.split("\\s+"); // Split line on whitespace, to get columns
        // Do stuff with columns array...
    }
} catch (IOException e) {
    e.printStackTrace();
} finally {
    br.close();
}
```

### Kotlin
```kotlin
var fileName = "weather.dat"
File(fileName).forEachLine {
    var columns = it.split("\\s+") // Split line on whitespace, to get columns
    // Do stuff with columns array...
}
```

### Python
```python
# Need example here
```