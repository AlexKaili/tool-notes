# conda
![conda](./images/conda_logo.svg)

> `conda`是一个开源的包管理器和环境管理器，用于安装多个版本的包和Python解释器，并能够在这些不同的环境之间切换。下面是一些常用的`conda`命令和使用方法。

## 1. 安装和更新conda

- **安装：** 通常，我们通过安装Anaconda或Miniconda来获取`conda`。Anaconda包含了conda、Python和常用的科学计算包；Miniconda则更为轻量级，仅包含了conda和Python。
- **更新：**

  ```sh
  conda update conda
  ```

## 2. 管理环境

- **创建环境：**

  ```sh
  conda create --name myenv python=3.8
  ```

  这里`myenv`是你的环境名称，`3.8`是Python的版本。
  
- **激活环境：**

  ```sh
  conda activate myenv
  ```
  
- **退出环境：**

  ```sh
  conda deactivate
  ```
  
- **列出所有环境：**

  ```sh
  conda env list
  conda info --envs
  ```

- **重命名环境名：**

    ```sh
    # 将 py3 重命名为 torch
    conda create -n torch --clone py3
    ```

- **删除环境：**

  ```sh
  conda env remove --name myenv
  conda env remove -n env_name
  conda remove -n env_name --all
  ```

## 3. 管理包

- **安装包：**

  ```sh
  conda install package_name
  ```

  你可以指定包的版本，例如：

  ```sh
  conda install numpy=1.18
  ```
  
- **更新包：**

  ```sh
  conda update package_name
  ```
  
- **卸载包：**

  ```sh
  conda remove package_name
  ```
  
- **列出环境中的包：**

  ```sh
  conda list
  ```

## 4. 管理Python版本

- 当你创建一个新的环境时，可以指定Python的版本。例如，要创建一个名为`myenv`的环境并在其中安装Python 3.7，你可以使用以下命令：

  ```sh
  conda create --name myenv python=3.7
  ```

## 5. 其他

- **清理缓存：**

  ```sh
  conda clean --all
  ```

  这个命令将清除不需要的包和缓存，可能会释放一些磁盘空间。

- **查找包：**

  ```sh
  conda search package_name
  ```

  通过这个命令，你可以找到可用的包和它们的版本。

## 6. Conda配置和帮助

- **配置conda：**

  ```sh
  conda config --set auto_activate_base False
  ```

  这个例子将避免conda每次启动时自动激活基础环境。

- **获取帮助：**

  ```sh
  conda --help
  ```

  或者

  ```sh
  conda command --help
  ```

  这将显示关于conda或其子命令的帮助信息。

## 7. Conda渠道

- **添加渠道：**

  ```sh
  conda config --add channels channel_name
  ```

Conda的清华镜像源可以加快软件包的下载速度，特别是对于身处中国大陆的用户来说。你可以按照以下步骤添加清华镜像源为Conda的默认渠道。

### 7.1 添加清华镜像源

1. **添加conda-forge和bioconda渠道**

   ```sh
   conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
   conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
   ```

2. **设置清华Anaconda仓库镜像**

   ```sh
   conda config --set show_channel_urls yes
   conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
   ```

3. **设置搜索时显示渠道地址**

   ```sh
   conda config --set show_channel_urls yes
   ```

### 7.2 设置渠道优先级

如果你希望清华镜像源拥有更高的优先级，你可以按照以下步骤设置：

```sh
conda config --set channel_priority strict
```

### 7.3 查看当前渠道列表

要查看当前的渠道列表和优先级，你可以使用以下命令：

```sh
conda config --show channels
```

### 7.4 移除清华镜像源

如果你以后想要移除清华镜像源，可以编辑`~/.condarc`文件，或者使用`conda config --remove channels URL`来移除相应的渠道。

### 注意

- 在某些情况下，清华镜像可能不是最新的，这时候可以考虑使用其他的镜像源，或者直接使用官方的Anaconda仓库。

- 在使用清华镜像源（或其他镜像源）时，请遵守相关的使用规定，并确保知道镜像源的可靠性和安全性。

## 8.在conda环境内使用 pip安装

在`conda`环境中使用`pip`进行包安装是完全可行的，实际上，`conda`和`pip`可以很好地协同工作。但是，尽可能使用`conda`来安装包是一个好习惯，因为`conda`可以更好地管理包的依赖关系。
尽管在anaconda下我们可以很方便的使用conda install来安装我们需要的依赖，但是anaconda本身只提供部分包，远没有pip提供的包多，如果在`conda`中找不到所需的包，可以考虑使用`pip`作为备选方案。

以下是在`conda`环境中使用`pip`安装包的一些步骤：

### 1. 激活你的conda环境

首先，你需要激活你想在其中安装包的conda环境：

```sh
conda activate myenv
```

这里`myenv`是你的环境名。

### 2. 使用pip安装包

在激活了环境之后，你可以使用`pip`来安装包：

```sh
pip install package_name
```

这里`package_name`是你想安装的包名。

### 注意事项

- **优先考虑Conda**
  - 尽管`pip`和`conda`可以在大多数情况下一起使用，但最好尽量使用`conda`来安装软件包，因为`conda`更擅长解决依赖关系和环境隔离。

- **避免混合使用**
  - 在一个环境中混合使用`pip`和`conda`可能会导致依赖关系的混乱。因此，尽量避免在同一环境中混用它们，除非必要。

- **安装pip**
  - 新创建的conda环境中可能不会自动包含`pip`。如果你在一个新的conda环境中找不到`pip`，可以先用`conda`安装`pip`：

    ```sh
    conda install pip
    ```

- **使用`pip freeze`**
  - 如果你在`conda`环境中使用`pip`安装了很多包，可以使用`pip freeze > requirements.txt`来记录这些包的列表，以便未来重新创建这个环境。
- **安装特定版本的包**
  - conda用“=”，pip用“==”

总之，尽管`conda`是首选，但在`conda`环境中使用`pip`是可以的，只需注意管理依赖关系，以避免潜在的冲突。
