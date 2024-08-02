# api-language-detect 🚀

## Overview

**api-language-detect** provides ultra-fast and highly accurate language detection based on FastText, a library developed by Facebook. This package is 80x faster than traditional methods and offers 95% accuracy.

It supports Python versions 3.9 to 3.12.

> [!NOTE]  
> This library requires over 200MB of memory to use in low memory mode.

## Installation 💻

To install api-language-detect, you can use either `pip` or `pdm`:

### Using pip

```bash
pip install api-language-detect
```

### Using pdm

```bash
pdm add api-language-detect
```

## Usage 🖥️

For optimal performance and accuracy in language detection, use `detect(text, low_memory=False)` to load the larger model.

> The model will be downloaded to the `/tmp/fasttext-langdetect` directory upon first use.

### Native API (Recommended)

```python
from api_language_detect import detect, detect_multilingual

# Single language detection
print(detect("Hello, world!"))
# Output: {'lang': 'en', 'score': 0.1520957201719284}

print(detect("Привет, мир!")["lang"])
# Output: ru

# Multi-language detection
print(detect_multilingual("Hello, world!你好世界!Привет, мир!"))
# Output: [
#     {'lang': 'ru', 'score': 0.39008623361587524},
#     {'lang': 'zh', 'score': 0.18235979974269867},
# ]
```

### Convenient `detect_language` Function

```python
from api_language_detect import detect_language

# Single language detection
print(detect_language("Hello, world!"))
# Output: EN

print(detect_language("Привет, мир!"))
# Output: RU

print(detect_language("你好，世界！"))
# Output: ZH
```
