# 爬虫实战\n
记录学习爬虫的过程\n
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
4. 
