# 爬虫实战
记录学习爬虫的过程
### 01 爬取一页贴吧的内容
涉及：re模块使用(findall)和csv文件写入
1. 半自动爬取，手动复制页面源代码，保存到tieba.txt文件中
2. 打开tieba.txt文件，用f.read()将读取的内容存储到一个字符串中
3. 正则表达式findall匹配楼层帖子的内容、发帖人名称、发帖时间
4. 将收集到的内容保存到csv文件中


### 02 利用requests模块发起网络请求
1. 明确网页请求的多种模式，如get/post
2. 格式 requests.get('网址').content.decode()  或者 requests.post('网址',data=data).content.decode()
3. decode函数的参数默认是utf-8,可以不填

### 03 多线程、搜索算法
1. 爬虫属于I/O密集型操作，使用多线程可以提高效率
2. 开启多线程的方式<br>
  1)导入库 `from multiprocessing.dummy import Pool`<br>
  2)定义函数fun，定义可迭代对象list<br>
  3)申请线程池pool = Pool(线程数量)<br>
  4)多线程工作result = pool.map(fun,list)<br>
3. 搜索算法，广度优先还是深度优先，依据于具体的问题而定

### 04 爬取小说
1. 首先找到一个不反爬虫的小说网站...(目前技术太菜了）
2. 然后找到目录，获取每一章节的link<br>
 1) 由于要爬取的小说章节较多，章节进行了分页放置 <br>
 2) 因此我们首先需要获得所有的目录页的link，在在这些目录页中获取所有章节的link <br>
 3) 获得章节的link后，读取章节内容，正则表达式解析出标题和正文返回<br>
 4) 访问频次太高会得不到章节内容，因此在读取一部分章节内容后会sleep <br>
3. 将所有章节内容写入文件存储
