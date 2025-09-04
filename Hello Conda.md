# Hello Conda

## 虚拟环境

### 创建

```bash
conda create -n env_name python=3.9 numpy pandas
```

### 激活

```bash
conda activate env_name
```

### 退出

```bash
conda deactivate
```

### 查看环境列表

```bash
conda env list
# or
conda info --envs
```

### 删除

```bash
conda remove -n env_name --all
```

### 复制环境

```bash
conda create -n new_env --clone old_env
```

### 导出环境

```bash
conda env export > env.yml
```

导出当前环境的配置到 `env.yml`

更推荐导出只包含用 `conda install` 显式安装的包，让 Conda 在安装时自动解决依赖关系。

### 导入环境

```bash
conda env create -f env.yml
```



## 包管理

### 安装包

```bash
conda install pkg_name
# or
conda install pkg_name=1.2
```

### 列出安装的包

```bash
conda list
```

### 更新包

```bash
conda update pkg_name
# or
conda update --all
```

### 卸载包

```bash
conda remove pkg_name
```

## 更新

```bash
conda update conda
```

