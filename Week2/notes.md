# Week2 linux and introduction II
## Linux introduction
- shell -- 直接输入命令  bash
- 使用脚本，使用通配符、自动补全、...
- --help或man命令查看帮助
- pwd 查看当前文件夹     ls 查看目录   tree ./可读性更强 
    cd 切换目录     touch 创建文件    mkdir 创建目录
    cp 复制粘贴     rm 删除     cat 读文件    wc 查看文件信息
    less 滚动查看    cut sed 切取   grep 筛选    sort 排序
    uniq 去重复    diff 对比两个文件
- 管道 | 和重定向 >（覆盖） >>（追加）
- gzip 压缩为gz   gunzip 解压缩    tar 压缩为tar
- chmod xxx 设置权限（1-7）
  
## Introduction II
physics - liguistics - bioinformatics
image $\leftrightarrow$ text -- correspond to same latent space
### 1-dimension: regular grammar - HMM
non-terminal(variable)(verb) + production rule + terminal(run)
same in nucleotide sequence (derivation path = parsing = sequence) （序列即为生成的过程）
HMM -- a chain of probability, used in gene finder/gene families
### 2-dimension: context-free grammar - SCFG
RNA pairing -- trans-pairs between 2 molecules, cis-pairs in 1 molecule
describe by pairs and loops(derivation path = parsing tree = sequence)
### 3-dimension: context-sensitive grammar - linear bounded automata
3D structure -- need considering long-distance interactions, context sensitive (self attention transformer)
### higher dimension: unrestricted grammar - turing machines & recursively enumerable sets
multi-omics -- ai for precise treatment