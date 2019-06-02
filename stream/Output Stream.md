> An output stream object is the target of information flow.
> 
> 输入流对象是信息流的目标。

### introduction
+ three most important output streams: ostream,ofstream,ostringstream.

+ the predefined ostream class object is used to accomplish the output standard devices: cout, cerr, clog

+ ofstream class supports disk file output. An ofstream class object can be constructed for an output-only disk file, ofstream object can be designated to receive binary or text data before or after opening a file. Many format options and member functions of ofstream object can be used, including all the functions in basic classes ios and ostream.

  ofstream类支持磁盘文件输出。 可以为仅能输出磁盘文件构造ofstream类对象，可以指定ofstream对象在打开文件之前或之后接收二进制或文本数据。 可以使用ofstream对象的许多格式选项和成员函数，包括基本类ios和ostream中的所有函数。

### Construct Output Object

+ ofstream myFile;
  
    myFile.open("filename",iosmode);

or

+ ofstream* pmyFile=new ofstream;
    
    pmyFile->open("filename",iosmode);


