使用Pod导入

pod 'BHLogFactory', '~> 1.1.0'

> 提示： 利用`Runtime`, 无需导入如何头文件到项目中;

-------------------

简介

>  BHLogFactory 是为了处理控制台打印的中文被unicode编码 。产生类似于 `U7ea2\U5305\U96e8\U6d3b\U52a8`的unicode编码 , 不利于开发的调试 ;  所以, 使用这个工具, 可以将我们不易识别的unicode编码转换为具备可读性的中文.
>  

实现原理: 分别对`NSArray`和`NSDictionary`方法进行类别方法重写,  如下
```
// NSArray (Log)
- (NSString *)debugDescription;
- (NSString *)description;
- (NSString *)descriptionWithLocale:(id)locale;

// NSDictionary (Log)
- (NSString *)debugDescription;
- (NSString *)description;
- (NSString *)descriptionWithLocale:(id)locale
```

```
使用前:
{ "create_time" = "2018-08-21 15:03:01";
  "week_time" = "08-21 \U661f\U671f\U4e8c";
}
-------------------
使用后:
{ "create_time" = "2018-08-21 15:03:01";
  "week_time" = "08-21 星期二";
}
```

交流与建议
- GitHub：<https://github.com/BaHui>
- 邮  箱：<qiaobahuiyouxiang@163.com>

