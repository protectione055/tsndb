## 1. 代码描述
Actually, the codebase mainly consists of two parts. The first part is the management of timeseries (indexes and in-memory data samples), and they are in folders except for leveldb. The second part is the management of the persistent data samples (I derive time-partitioned lsm tree based on LevelDB), which is contained in folder leveldb. For each folder, the main contents are as follows:

**base:** basic helper functions for the codebase

**block:** interfaces for chunk reader/writer, and index reader/writer

**chunk:** compression of a set of data points into a chunk

**cloud:** the AWS S3 wrapper for file operations on S3

**db:** the tsdb object (in charge of everything)

**head:** management of in-memory data (indexes and in-memory data samples), this is important

**index:** mainly are different kinds of posting lists

**label:** tags

**leveldb:** time-partitioned LSM tree

**querier:** the querier for all data, which has a global view (this is deprecated), the current querier is in leveldb/db/db_querier.h

Besides, you can read the blogs of Prometheus for some basic concepts.


## 2. 使用Github进行协作

### 2.1 从远端仓库获取项目
```
git clone https://github.com/protectione055/tsndb.git
```

### 2.2 git协作流程
开始新的工作前确保当前是最新版本：  
```
git pull
```

修改完毕后将代码提交到远端仓库：  
```
git add .
git commit -m "（描述修改内容）"
git push
```

### 2.3 注意事项
待续
