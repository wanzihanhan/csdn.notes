> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/zkchen0420/article/details/97921745?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522169880631816800185831282%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=169880631816800185831282&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-97921745-null-null.142^v96^pc_search_result_base2&utm_term=rdkit%20%E5%88%86%E5%AD%90%E6%8C%87%E7%BA%B9&spm=1018.2226.3001.4187)

基于 RDKit 获取分子指纹
---------------

分子指纹（化学指纹，Chemical Fingerprinting）：  
将化学分子的特征利用二进制表示，如 MDL 公司开发的 MACCSkeys 指纹。  
MACCSkeys 共有 166 个特征，但是 MACCSkeys 总长度为 167bits。  
第 0 位为[占位符](https://so.csdn.net/so/search?q=%E5%8D%A0%E4%BD%8D%E7%AC%A6&spm=1001.2101.3001.7020)，第 1~166 位为分子特征位。

具体操作见下

```
from rdkit import Chem
from rdkit.Chem import MACCSkeys

molecule = Chem.MolFromSmiles('') # 当分子为空值时，fingerprints全为0
fingerprints = MACCSkeys.GenMACCSKeys(molecule)
print(fingerprints) # result 1
print(len(fingerprints.ToBitString())) # result 2
print(fingerprints.ToBitString()) # result 3

```

运行结果如下：

```
[1] result 1 : 
<rdkit.DataStructs.cDataStructs.ExplicitBitVect object at 0x000001ECF1263F80>
[2] result 2 :
167
[3] result 3 :
00000000000000000000000000000000000000000000000000000000
00000000000000000000000000000000000000000000000000000000
0000000000000000000000000000000000000000000000000000000

```

**我们再以 3 - 戊酮为例：**

```
from rdkit import Chem
from rdkit.Chem import MACCSkeys

molecule = Chem.MolFromSmiles('CCC(=O)CC') # 3-戊酮
fingerprints = MACCSkeys.GenMACCSKeys(molecule)
print(fingerprints) # result 1
print(len(fingerprints.ToBitString())) # result 2
print(fingerprints.ToBitString()) # result 3

```

运行结果如下：

```
[1] result 1 : 
<rdkit.DataStructs.cDataStructs.ExplicitBitVect object at 0x000001ECF1249490>
[2] result 2 :
167
[3] result 3 :
000000000000000000000000000000000000000000000000000000000
000000000000000000000000000000000000000000000000000000000
10100000000000000010000000000000000100101100001000100

```

除了第 1 位，后面 2~167 位：每个 0 和 1 的具体含义我