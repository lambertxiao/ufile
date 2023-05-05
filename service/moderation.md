# 内容审核服务

## 概览

对象存储提供内容审核功能，可以对存储在US3中的图片进行违禁内容识别，识别的场景包括涉黄、涉恐、涉政。

详细介绍见[UDI数据智能文档](https://docs.ucloud.cn/udi/introduction/functions)

## 操作步骤

1. 登陆UDI管理控制台。
![image](/images/udi控制台首页.png)

2. 单击“创建任务”，选择对应的基础和审核设置，各参数说明请参见参数说明表
![image](/images/udi创建任务.png)

3. 配置各项参数后，单击“立即创建”即为任务创建完成。其中首次使用UDI的存储空间需进行授权确认。
![image](/images/udi授权确认页.png)

4. 已创建的内容审核任务支持“查看结果”、“任务详情”、“暂停”和“删除”操作。

    1）查看结果：单击对应任务的“查看结果”，该页面展示审核异常的详细记录，分别标签异常图片的审核类型和结果，同时也支持对异常图片的迁移、删除和忽略操作。
  ![image](/images/udi查看结果.png)
  
    2）任务详情：单击对应任务的“任务详情”，该页面展示其基础信息和审核信息。
  ![image](/images/udi任务详情.png)
  
    3）暂停：支持暂停和启动“进行中”的任务状态。
  
    4）删除：支持删除单个任务和批量删除多个任务。
  
## 参数说明表

| 参   数  | 说明                                                         |
| :------- | :----------------------------------------------------------- |
| 地域     | 目前开放地域是华北一、上海二、台北。其他地域有开通需求，请联系技术支持。 |
| 存储空间 | US3对象存储空间（简称存储空间）是文件的组织管理单位，一个文件必然隶属于某个空间中。<br>用户可以选择在US3已创建的存储空间，或者单击“新建存储空间”跳转至US3对象存储完成创建。 |
| 任务类型 | - 增量审核：针对该审核任务创建完成后，新上传至该存储空间的图片进行审核；<br>- 存量审核：针对已存储在该存储空间的图片进行审核。 |
| 审核内容 | 目前仅支持图片审核。                                         |
| 规则范围 | - 所有文件：针对US3存储空间中上传的所有图片进行处理；<br>- 部分文件：针对US3存储空间中上传的文件名以指定`前缀` 的图片进行处理。 |
| 图片格式 | 目前仅支持的图片格式为：JPG、PNG、JPEG。<br>必选项，至少需要选择一项。 |
| 审核类型 | 涉黄/涉政/涉暴恐。<br>必选项，至少需要选择一项，且每种类型单独计费。 |
| 违规处理 | - 不处理：则审核结果会展示在结果页面中，由用户决定如何处理；<br>- 迁移文件至：审核的违规图片会被移动到选择的US3存储空间的指定前缀下。 |
| 任务名称 | 支持输入长度为1-63位字符，支持中英文、数字以及- _            |
  
## 开放地域
其他地域有开通需求，请联系技术支持。
- 华北一
- 上海二
- 台北


## 计费规则
图片内容审核的计费场景共3个（涉黄、涉政、涉暴恐），支持后付费模式，检测多个场景时会累积计费，后付费按照当日计费场景累计扫描量对应的档位阶梯计费。

### 后付费定价

| 当日总扫描量 | 单价（元/千张） |
| :----------- | :-------------- |
| >0           | 1.5             |
| >5000        | 1.43            |
| >50000       | 1.36            |
| >130000      | 1.25            |
| >260000      | 1.20            |
| >850000      | 1.15            |


> 1. 图片内容审核有多种类型，每种类型单独计费。如使用了涉黄、涉政，则上传1张图片后会计入2次计费；
>
> 2. 数据智能UDI提供每月2000张的免费使用额度。