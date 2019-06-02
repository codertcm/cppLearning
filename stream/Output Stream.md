> An output stream object is the target of information flow.
> 
> 输入流对象是信息流的目标。

### 介绍 introduction
+ three most important output streams: ostream,ofstream,ostringstream.

+ the predefined ostream class object is used to accomplish the output standard devices: cout, cerr, clog

+ ofstream class supports disk file output. An ofstream class object can be constructed for an output-only disk file, ofstream object can be designated to receive binary or text data before or after opening a file. Many format options and member functions of ofstream object can be used, including all the functions in basic classes ios and ostream.

  ofstream类支持磁盘文件输出。 可以为仅能输出磁盘文件构造ofstream类对象，可以指定ofstream对象在打开文件之前或之后接收二进制或文本数据。 可以使用ofstream对象的许多格式选项和成员函数，包括基本类ios和ostream中的所有函数。

### 构造函数 Construct Output Object

+ ofstream myFile;
  
    myFile.open("filename",iosmode);

or

+ ofstream* pmyFile=new ofstream;
    
    pmyFile->open("filename",iosmode);



### 打开模式 open model
label       | function| 
|-----      |----   |
|ios::app   |从后面添加 |
|ios::ate   |打开并找到文件尾 |
|ios::binary|二进制模式 I/O (与文本模式相对) |
|ios::in    |只读打开 |
|ios::out   |写打开   | 
|ios::trunc |将文件截为 0 长度 | 

可以使用位域作用符OR组合这些标志

+ ofstream logfile("login.dat", ios::binary | ios::app);           //向现有文件中添加二进制数据

+ std::fstream test("hahahah",ios::in | ios::out | ios::trunc);    //读、写、将文件设定为空


###  错误处理函数 Error handing Function

| function | effect ans return value |
| ----     | ---- |
| bad      | if an error appeared and cannot be recovered, then return a non-0 value.|
| fail     | if an error that cannot be recovered or an expected condition appeared, for example, a conversion error or cannot find file, then return a non-0 value. Error label will deleted after call clear using zero parameter.|
| good     | if all the error labels and file ending labels have be cleared , then return a non-0 value. |
| eof      | meet the file ending condition, return a non-0 value. |
| clear    | set the state of internal errors, if call by default parameters , then clear all the error digits|
| rdstate  | return the current error state.  |


