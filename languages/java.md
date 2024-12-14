# Java

## try catch with `AutoCloseable`

```java

try(
// AutoCloseable here
) {

} catch(Expression e) {

}

```

## Examples of stream


|                Input                   |                Output                    |
|:--------------------------------------:|:----------------------------------------:|
|            `FileInputStream`           |            `FileOutputStream`            | 
|            `BiteArrayInputStream`      |            `BiteArrayOutputStream`       |
|            `BufferedInputStream`       |            `BufferedOutputStream`        | 
|            `DataInputStream`           |            `DataOutputStream`            | 
|            `ObjectInputStream`         |            `ObjectOutputStream`          | 
|            `PipedInputStream`          |            `PipedOutputStream`           | 
|            `GzipInputStream`           |            `GzipOutputStream`            | 
|            `SequenceInputStream`       |            `SequenceOutputStream`        | 
|            `AudioInputStream`          |            `AudioOutputStream`           | 


## Useful class

- `FileReader`
- `Scanner`
- `PrintWriter`
- `BufferedReader`

Use buffer with a file : `FileReader`->`BufferedReader`->`Scanner`


## Protected, public private


