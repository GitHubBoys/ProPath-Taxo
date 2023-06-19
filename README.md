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
In distributed training, the .from_pretrained methods guarantee that only one local process can concurrently. 
```
--per_device_train_batch_size 16 \ 暂时不用
```
```
 # 这里将Dataset文件中的map方法属性修改，因为每次加载都会有进度条
disable_tqdm = not logging.is_progress_bar_enabled()
disable_tqdm = True
negative_dataset = Dataset.from_list(negtive_sequence)
```

#文件
```
读取childs，供sibling比较使用
mag_cs_read_childs.py
#读取path、生成格式数据集等
mag_cs_read_allNode.py
#beam-search链接预测
TaxoComp_link_prediction_beam_search.py
#三元组分类任务
TaxoComp.py
#数据集不同拆分
mag_cs_t_v_t.py    jsonl\text
mag_cs_t_v_t_tsv.py
mag_cs_t_v_t_csv.py

#读取数据集，并非只是叶子节点
mag_cs_read_dataset_norm.py
#正常数据集
mag_cs_dataset_no_prompt.jsonl
mag_cs_dataset_norm.jsonl
#41008148下节点数据集
mag_cs_dataset_no_prompt_41008148.jsonl
mag_cs_dataset_41008148.jsonl
#读取embedding
mag_cs_read_instructor_large_embedding.py
#每一个节点加入隔1层正样本
mag_cs_read_dataset_norm_other_positive.py
```
