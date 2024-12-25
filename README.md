# AI-imageGenerate
一种生成ai图片的解决方案，爬取某ai生图网站的api。仅供娱乐，请勿用于商业用途。

# 项目文档

## 加密算法

所有的模型都包括加密 API-Key 算法。这只是一个字符串拼接的过程，逻辑较为简单。

### 代码实现

以下是加密算法的代码示例：

```javascript
var myrandomstr = Math.round((Math.random() * 100000000000)) + "";
var myhashfunction = function() {
    for (var a = [], b = 0; 64 > b; )
        a[b] = 0 | 4294967296 * Math.sin(++b % Math.PI);
    return function(c) {
        var d, e, f, g = [d = 1732584193, e = 4023233417, ~d, ~e], h = [], l = unescape(encodeURI(c)) + "\u0080", k = l.length;
        c = --k / 4 + 2 | 15;
        for (h[--c] = 8 * k; ~k; )
            h[k >> 2] |= l.charCodeAt(k) << 8 * k--;
        for (b = l = 0; b < c; b += 16) {
            for (k = g; 64 > l; k = [f = k[3], d + ((f = k[0] + [d & e | ~d & f, f & d | ~f & e, d ^ e ^ f, e ^ (d | ~f)][k = l >> 4] + a[l] + ~~h[b | [l, 5 * l + 1, 3 * l + 5, 7 * l][k] & 15]) << (k = [7, 12, 17, 22, 5, 9, 14, 20, 4, 11, 16, 23, 6, 10, 15, 21][4 * k + l++ % 4]) | f >>> -k), d, e])
                d = k[1] | 0,
                e = k[2];
            for (l = 4; l; )
                g[--l] += k[l]
        }
        for (c = ""; 32 > l; )
            c += (g[l >> 3] >> 4 * (1 ^ l++) & 15).toString(16);
        return c.split("").reverse().join("")
    }
}();
var tryitApiKey = 'tryit-' + myrandomstr + '-' + myhashfunction(navigator.userAgent + myhashfunction(navigator.userAgent + myhashfunction(navigator.userAgent + myrandomstr + 'i_am_a_smelly_hacker_yes_i_am')));
```

## 默认 Text2Img 模型

### 支持的图像尺寸

- 832x448
- 768x576
- 640x640
- 576x768
- 448x832

### 请求参数

请求的 `formData` 包括以下字段：

- **text**: 图像生成的描述内容（即 prompt）。
- **width**: 图像宽度（支持的尺寸见上）。
- **height**: 图像高度（支持的尺寸见上）。
- **image_generator_version**: 图像生成的清晰度，支持两种类型：`standard` 和 `hd`。
- **use_old_model**: 固定为 `false`。
- **quality**: 决定是否追求质量（默认为 `true`）。
- **genius_preference**: 偏好设置（默认为 `classic`）。

## Fantasy-World-Generator 模型

### 参数说明

该模型的请求参数与 Text2Img 模型完全相同，包含以下 7 个字段：

- **text**
- **width**
- **height**
- **image_generator_version**
- **use_old_model**
- **quality**
- **genius_preference**

## Cute-Creature-Generator 模型

### 参数说明

同样地，该模型的请求参数也与 Text2Img 模型一致，包含以下 7 个字段：

- **text**
- **width**
- **height**
- **image_generator_version**
- **use_old_model**
- **quality**
- **genius_preference**

------


