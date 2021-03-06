# Zpy Docs Generator

Zpy Docs Generator - auto translate Python Library API to Zpy API, and generate Zpy Lib Docs 

Zpy Lib API is a Chinese mapping of the Python API

example
```json
{
    "name":"test",
    "zpy":"测试",
    "functions":[
        {
            "name":"threading_cleanup",
            "zpy":"线程清理"
        },
        {
            "name":"run_with_locale",
            "zpy":"运行与语言环境"
        },
    ],
    "args":[
        {
            "name":"cpython",
            "zpy":"cpython"
        },
        {
            "name":"captured_stdout",
            "zpy":"捕捉到stdout"
        },
    ]
}
```

## Quick Start

clone this repo
```shell
git clone https://github.com/louisyoungx/zpy-docs-generator.git
cd zpy-docs-generator
```

install dependences
```shell
pip install requests, scrapy, jieba, wordninja
```

download dictionary
```
wget https://resource.rocke.top/zpy/dictionary_lite.csv
mv dictionary_lite.csv dics
```

### Python Lib

generate python builtin lib docs
```shell
python3 main.py
```

the lib docs is in `libs/` directory
```shell
ls libs
```

### Third-party Lib

edit `config.py`
- change `URL`
- change `LIB_NAME`, exp:`requests-libs`

edit `lib.py`
- let `libs` in 19 line return list of url, exp: `['string.html', 'time.html']`

edit `module.py`
- change xpath expression of `name`, `methods`, `params` in 16, 17, 18 line

generate third-party lib docs
```shell
python3 main.py
```

the lib docs is in `YOUR-LIB-NAME` directory
```shell
ls requests-libs
```

### requests demo

```python
git checkout requests
```

generate requests lib docs
```shell
python3 main.py
```

the lib docs is in `requests-libs` directory
```shell
ls requests-libs
```