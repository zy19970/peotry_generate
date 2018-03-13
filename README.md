# 基于循环神经网络(RNN)的古诗生成器

项目基于循环神经网络，使用tensorflow 1.4实现。训练数据为四万多首古诗，

训练完成后，能随机生成古诗。

-----------------

## 使用说明

**1.预处理数据**

古诗文件不能够直接使用，需要生成词汇表，将古诗文件转换成向量。

```
python process_data.py
```

**2.训练模型**

使用1中生成的文件训练神经网络。

```
python train.py
```

**3.生成古诗**

当模型训练完成之后，可以尝试生成古诗。输入以下命令可以进行生成，至于质量嘛...emmmm，凑合吧

```
python eval.py
```

结果示例：

> 树阴飞尽水三依，谩自为能厚景奇。
莫怪仙舟欲西望，楚人今此惜春风。

> 岩外前苗点有泉，紫崖烟霭碧芊芊。
似僧月明秋更好，一踪颜事欲犹伤？

**4.生成藏头诗**

模型做的比较小，训练数据也不足，在生成藏头诗上的表现不是很好。往往要生成很多次生成一个满意的= =娱乐功能。

使用该功能要修改代码(等闲了我将它改成命令行功能，就不用改代码了)，将`eval.py`中以下代码：

```python
if __name__ == '__main__':
    # generate_acrostic(u'天空')
    generate_poem()
```

改成

```python
if __name__ == '__main__':
    generate_acrostic(u'天空')
    # generate_poem()
```

然后运行即可。

```
python eval.py
```

结果示例：

> 天序曾柏乌倾鱼，空老桐歌尘翁红。

