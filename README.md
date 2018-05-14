## Beauty Sublist3r 

Sublist3r是一个python工具，用于枚举使用OSINT的网站的子域。它有助于渗透测试人员和漏洞猎手收集并收集他们所针对的域名的子域名。Sublist3r使用Google，Yahoo，Bing，百度和Ask等许多搜索引擎来枚举子域名。Sublist3r还使用Netcraft，Virustotal，ThreatCrowd，DNSdumpster和ReverseDNS枚举子域。

[subbrute](https://github.com/beautyonly/subbrute)与Sublist3r集成以增加使用bruteforce和改进的单词表查找更多子域的可能性。功劳归功于Subbrute的作者TheRook。 

## Screenshots

![Sublist3r](http://www.secgeek.net/images/Sublist3r.png "Sublist3r in action")


## Installation

```
git clone https://github.com/beautyonly/Sublist3r.git
```

## Recommended Python Version:

Sublist3r currently supports **Python 2** and **Python 3**.

* The recommended version for Python 2 is **2.7.x**
* The recommened version for Python 3 is **3.4.x**

## Dependencies:

Sublist3r depends on the `requests`, `dnspython`, and `argparse` python modules.

These dependencies can be installed using the requirements file:

- Installation on Windows:
```
c:\python27\python.exe -m pip install -r requirements.txt
```
- Installation on Linux
```
sudo pip install -r requirements.txt
```

Alternatively, each module can be installed independently as shown below.

#### Requests Module (http://docs.python-requests.org/en/latest/)

- Install for Windows:
```
c:\python27\python.exe -m pip install requests
```

- Install for Ubuntu/Debian:
```
sudo apt-get install python-requests
```

- Install for Centos/Redhat:
```
sudo yum install python-requests
```

- Install using pip on Linux:
```
sudo pip install requests
```

#### dnspython Module (http://www.dnspython.org/)

- Install for Windows:
```
c:\python27\python.exe -m pip install dnspython
```

- Install for Ubuntu/Debian:
```
sudo apt-get install python-dnspython
```

- Install using pip:
```
sudo pip install dnspython
```

#### argparse Module

- Install for Ubuntu/Debian:
```
sudo apt-get install python-argparse
```

- Install for Centos/Redhat:
```
sudo yum install python-argparse
``` 

- Install using pip:
```
sudo pip install argparse
```

**for coloring in windows install the following libraries**
```
c:\python27\python.exe -m pip install win_unicode_console colorama
```

## Usage

Short Form    | Long Form     | Description
------------- | ------------- |-------------
-d            | --domain      | 列举子域名的域名
-b            | --bruteforce  | 启用subbrute bruteforce模块
-p            | --ports       | 根据特定的tcp端口扫描找到的子域
-v            | --verbose     | 启用详细模式并实时显示结果
-t            | --threads     | 用于subbrute bruteforce的线程数
-e            | --engines     | 指定一个以逗号分隔的搜索引擎列表
-o            | --output      | 将结果保存到文本文件
-h            | --help        | 显示帮助信息并退出

### Examples

* To list all the basic options and switches use -h switch:

```python sublist3r.py -h```

* To enumerate subdomains of specific domain:

``python sublist3r.py -d example.com``

* 要枚举特定域的子域并只显示具有开放端口80和443的子域 :

``python sublist3r.py -d example.com -p 80,443``

* 枚举特定域的子域并实时显示结果:

``python sublist3r.py -v -d example.com``

* 要枚举子域并启用bruteforce模块，请执行以下操作:

``python sublist3r.py -b -d example.com``

* 枚举子域名并使用特定引擎，例如Google，Yahoo和Virustotal引擎:

``python sublist3r.py -e google,yahoo,virustotal -d example.com``


## Using Sublist3r as a module in your python scripts

**Example**

```python
import sublist3r 
subdomains = sublist3r.main(domain, no_threads, savefile, ports, silent, verbose, enable_bruteforce, engines)
```
The main function will return a set of unique subdomains found by Sublist3r

**Function Usage:**
* **domain**: 您想要枚举子域的域.
* **savefile**: 将输出保存到文本文件中.
* **ports**: 指定要扫描的TCP端口的逗号分隔列表.
* **silent**: 设置sublist3r在执行过程中以无声模式工作（有助于在不需要太多噪音的情况下）.
* **verbose**: 实时显示找到的子域.
* **enable_bruteforce**: enable_bruteforce：启用bruteforce模块.
* **engines**: (可选）选择特定的引擎.

枚举Yahoo.com的子域的示例:
```python
import sublist3r 
subdomains = sublist3r.main('yahoo.com', 40, 'yahoo_subdomains.txt', ports= None, silent=False, verbose= False, enable_bruteforce= False, engines=None)
```

## License

Sublist3r is licensed under the GNU GPL license. take a look at the [LICENSE](https://github.com/aboul3la/Sublist3r/blob/master/LICENSE) for more information.


## Credits

* [TheRook](https://github.com/TheRook) - The bruteforce module was based on his script **subbrute**. 
* [Bitquark](https://github.com/bitquark) - The Subbrute's wordlist was based on his research **dnspop**. 

## Thanks

* Special Thanks to [Ibrahim Mosaad](https://twitter.com/ibrahim_mosaad) for his great contributions that helped in improving the tool.

## Version
**Current version is 1.0**
