# TaxoCompl
论文代码仓库

#代码问题
由于中国网络问题，只能本地加载,先下载好token放在本地不然可能会加载出问题

[INFO|tokenization_auto.py:458] 2023-03-13 11:33:37,906 >> Could not locate the tokenizer configuration file, will try to use the model config instead.

```
checkpoint = "./roberta-base"
tokenizer = AutoTokenizer.from_pretrained("roberta-base")
tokenizer.save_pretrained("./checkpooint/token/roberta-base")
```

并发  
In distributed training, the load_dataset function guarantee that only one local process can concurrently
