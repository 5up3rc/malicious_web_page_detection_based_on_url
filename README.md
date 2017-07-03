# malicious_web_page_detection_based_on_url
##基于url特征的轻量级的恶意页面检测
#程序说明：
__Author__:沂水寒城
功能：使用url数据建立起恶意网站的检测模型
输入：第一行为标题，接下来每一行均为一个样本即一个url抽取的得到的向量
输出：模型的预测结果


#数据说明：
训练数据的集合为：all_train.txt
测试数据的集合为：all_test.txt
其中正例样本标签为0，负例样本标签为1
使用的数据中均为12维特征向量加1维的标签（共13维）


#特征说明：
特征文件一共分为两类，第一类一共12维特征也即程序中使用的数据；第二类是实现一篇去年会议上的一篇恶意网站检测的论文的方法一共16维特征
##第一类特征为：
len_procotol2path,ip_exist,len_hostname,www_exist,TLD_exist,SLD_decimal,TLD_decimal,len_path,num_directory_max,path_exist_date,path_exist_hex, label
##第二类特征为：
len_procotol2path,ip_exist,len_hostname,www_exist,TLD_exist,SLD_decimal,TLD_decimal,len_path,num_directory_max,path_exist_date,path_exist_hex,url_sign, url_dot, url_length, url_number_length, red_keyword, label
##第一类特征文件为：
urlresult2.txt
##第二类特征文件为：
urlresult.txt


#模型说明：
第一个函数为读取特征数据的函数
接下来每一个函数均为一个模型，可以依旧自己的不同需要来使用
model文件夹下面存储的是模型文件，每个训练和测试的模型均可以仿照SVM的模型持久化方法进行存储，避免每次测试都要训练


#结果说明：
RESULT文件中存放的是程序运行的结果
result.xlsx中存放的是一些模型的数据记录以及直方图表
