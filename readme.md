Git is a distributed version control system.

The second change.

The third change.





文档 DDD 相对于查询 QQQ 的 BM25 得分为：

BM25(D,Q)=∑t∈QIDF(t)⋅f(t,D)⋅(k1+1)f(t,D)+k1⋅(1−b+b⋅∣D∣avgDl)\text{BM25}(D,Q)=\sum_{t \in Q} \text{IDF}(t)\cdot \frac{f(t,D)\cdot (k_1+1)}{f(t,D)+k_1\cdot\left(1-b+b\cdot\frac{|D|}{\text{avgDl}}\right)}BM25(D,Q)=t∈Q∑IDF(t)⋅f(t,D)+k1⋅(1−b+b⋅avgDl∣D∣)f(t,D)⋅(k1+1)

其中：

- ttt：查询词
- f(t,D)f(t, D)f(t,D)：词 ttt 在文档中的出现次数（TF）
- ∣D∣|D|∣D∣：文档长度
- avgDl\text{avgDl}avgDl：语料库平均文档长度
- k1k_1k1 控制 TF 的饱和程度（通常取 1.2—2.0）
- bbb 控制长度归一化（通常取 0.75）
- IDF(t) 衡量词的稀有程度（越稀有权重越大）

BM25 在工程上通常不需要自己实现，因为搜索引擎都内置。