## MongoDB数据库说明

### 数据来源及基本信息

|     字段覆盖率          | ScienceDirect | arXiv   | SemanticScholar |
|---------------|---------------|---------|-----------------|
| title         | 100.00%       | 100.00% | 100.00%         |
| abstract      | 93.83%        | 100.00% | 83.38%          |
| authors       | 100.00%       | 100.00% | 99.99%          |
| doi           | 100.00%       | 40.80%  | 100.00%         |
| url           | 100.00%       | 100.00% | 45.12%          |
| year          | 100.00%       | 100.00% | 99.63%          |
| month         | 96.41%        | 100.00% | 86.71%          |
| type          | 100.00%       | 100.00% | 100.00%         |
| venue         | 100.00%       | 100.00% | 81.30%          |
| source        | 100.00%       | 16.00%  | 100.00%         |
| graph_url     | 68.20%        | 0.00%   | 53.90%          |
| graph_path    | 68.20%        | 0.00%   | 53.90%          |
| video_url     | 0.00%         | 0.00%   | 0.00%           |
| video_path    | 0.00%         | 0.00%   | 0.00%           |
| thumbnail_url | 0.00%         | 0.00%   | 0.00%           |
| pdf_url       | 100.00%       | 100.00% | 54.88%          |
| pdf_path      | 100.00%       | 100.00% | 54.88%          |
| latex_url     | 0.00%         | 100.00% | 0.00%           |
| latex_path    | 0.00%         | 100.00% | 0.00%           |
| ppt_url       | 0.00%         | 0.00%   | 0.00%           |
| ppt_path      | 0.00%         | 0.00%   | 0.00%           |
| inCitations   | 100.00%       | 0.00%   | 79.14%          |
| outCitations  | 0.00%         | 0.00%   | 98.17%          |
| 总记录数          | 19412         | 37695   | 296197          |

**这里有张图！！**


### 合并后数据信息
|               |  字段覆盖率  |
|---------------|---------|
| title         | 100.00% |
| abstract      | 90.68%  |
| authors       | 100.00% |
| doi           | 73.72%  |
| url           | 100.00% |
| year          | 99.82%  |
| month         | 92.66%  |
| type          | 100.00% |
| venue         | 90.50%  |
| source        | 72.05%  |
| graph_url     | 38.79%  |
| graph_path    | 38.79%  |
| video_url     | 0.00%   |
| video_path    | 0.00%   |
| thumbnail_url | 0.00%   |
| pdf_url       | 72.23%  |
| pdf_path      | 72.23%  |
| latex_url     | 32.45%  |
| latex_path    | 32.45%  |
| ppt_url       | 0.00%   |
| ppt_path      | 0.00%   |
| inCitations   | 89.59%  |
| outCitations  | 82.49%  |
| 合并后总记录数       | 116161  |

**这里有张图！！**


其中各数据源占比为

|   |ScienceDirect   |arXiv   |SemanticScholar   |
| ------------ | ------------ | ------------ | ------------ |
|记录数   |19259   |  37691 |59211   |
|占比   | 16.58%  |  32.45% |50.97%   |

**这里有张图！！**

### 合并操作


将数据导出为JSON格式存档：
`mongoexport -d database_name -c collection_name -o filename.json`

清空当前集合的数据：
`db.yourcollection.remove({})`

新建唯一索引：
`db.yourcollection.createIndex({public_no:1}, {unique:true})`

导入之前存档的JSON文件数据：
`mongoimport -d database_name -c collection_name --upsert filename.json`

用到的几个参数选项说明：-d 数据库名 -c 集合名 -o 导出后的目录及文件名 --upsert 会根据唯一索引去掉重复记录
依次对三个数据库执行导入操作即可
