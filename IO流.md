# I/O流

## FileInPutStream/FileOutPutStream

按照字节读取,一次读一个字节,所有类型文件都可以读,

```java
InputStresm in = new FileInputStream();
//创建一个流,建立连接

int count = in.read();
//读取文件字节
//当count=-1时,读取完毕

in.read("byte[]");
//表示往该数组输入数据

String(byte[]);
//转为字符串
```

## FileReader/FileWriter

按照字符串读取,

```java
FileReader reader = new FileReader();
reader.read(char[]);
//同理,向字符串数组写入数据

FileWriter writer = new FileWirter();
writer.wirte(char[]);
//这个char可以直接是字符串,直接写入文字

while( (count = reader.read(char[])) != -1 ){
  writer.write(char[], 0, count);
}//拷贝文件就是一边读一边写
```

## BufferedReader/BufferedWriter

缓冲流,需要接受流的参数,更像是是一个包装,包原来的FileReader包装起来,提供更多的方法

```java
BufferedReader br = new BufferedReader(_FileReader);
String firstLine = br.readLine();
//直接可以返回字符串

while((_string = _bufferedReader.readLine() != null){
  System.out.println(_string);
}//一个不错的遍历方法
      
InputStreamReader inputstreamreader = new InputStreamReader(_FileInputStram);
//通过InputStramReader可以把InputStream转换成字符流然后放入BufferedReader
```

