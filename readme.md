# 单词表朗读音频文件生成

## 功能
根据单词表，生成相应的单词音频朗诵文件
默认的格式：单词表csv，生成mp3文件，每个单词朗诵3遍
具体的参数可以自行修改，音频朗读源自有道

## 目录及文件说明

wordlist: 单词表

mp3list_en：生成的英音文件

mp3list_us: 生成的美音文件

Speech_EN:下载的所有单词的英音文件

Speech_US:下载的所有单词的美音文件



## 使用说明

本地git：
> git clone https://github.com/sijing233/English-list.git

可以直接运行

可修改参数,main.py中：

1、修改英音、美音

（1）修改第7行：type=0是美音，type=1是英音
~~~
  def __init__(self, type=1, word='hellow'):
~~~
（2）修改第101行，Speech_EN是英音，Speech_US是美音
~~~
  wordmp3=AudioSegment.from_mp3('./Speech_EN/'+word[0]+'.mp3')*3
~~~
（3）修改最后一行，mp3list_en是英音，mp3list_us是美音
~~~
  without_the_middle.export("./mp3list_en/A1st.mp3", format="mp3")
~~~

2、修改片头音乐

（1）将喜欢的音乐下载后，放到项目的根目录中

（2）修改第95行开始的代码

~~~python
  begin = AudioSegment.from_mp3('If-I-were-a-Bird.mp3') #先替换音乐文件名
  four_seconds = 2 * 1000 #选取音乐文件的前多少秒，或是后多少秒，或是中间的某一段
  without_the_middle = begin[:four_seconds] #截取音乐
~~~
