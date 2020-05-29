# dataset

> 君思的数据集，赶快收藏吧

----

## 验证码数据集（原创）

> 

* [40w验证码数据集]() 

| name | 标签合计 | 总数合计 |
| :- | :- | :- |
| 训练集 | 1640 | 131200 |
| 验证集 | 1640 | 131200 |
| 测试集 | 1640 | 131200 |
| 标签 | | 82 |
| 统计 | | 393600 |

* [3w验证码轻量数据集]() 

| name | 标签合计 | 总数合计 |
| :- | :- | :- |
| 训练集 | 120 | 9840 |
| 验证集 | 120 | 9840 |
| 测试集 | 120 | 9840 |
| 标签 | | 82 |
| 统计 | | 29520 |

> 标签分类情况

```python
label = [
    '0', '1', '2', '3', '4', '5', '6', '7', '8', '9',
    'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v',
    'w', 'x', 'y', 'z',
    'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V',
    'W', 'X', 'Y', 'Z',
    '!', '@', '#', '$', '%', '^', '&', '*', '(', ')', '+', '-', '=', '[', '{', ']', '}', '<', '>', '?'
]
```

> ImageFolder方式数据集加载（PyTorch）

```python
data_url = '数据集PATH'

image_datasets = {
    x: datasets.ImageFolder(
            os.path.join(data_url, x),
            self.data_transforms[x]
        ) for x in ['train', 'val']
    }
data_loader_train = DataLoader(
    self.image_datasets['train'], batch_size=32,
    shuffle=True, num_workers=16, pin_memory=True
)
data_loader_val = DataLoader(
    self.image_datasets['val'], batch_size=32,
    shuffle=True, num_workers=16, pin_memory=True
)

dataloaders = {
    'train': data_loader_train,
    'val': data_loader_val,
}

```
