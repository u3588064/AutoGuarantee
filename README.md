# 保函要素抽取项目

## 项目概述

本项目旨在从保函文本中抽取关键要素，以便于法律和金融专业人士进行分析和处理。项目使用自然语言处理技术，从保函文本中提取特定要素，并以JSON格式输出结果。

## 项目结构

```
保函要素抽取项目/
│
├── data/
│   ├── sample_guarantee.txt       # 示例保函文本
│   └── ...                       # 其他保函文本
│
├── src/
│   ├── extractor.py              # 要素抽取脚本
│   └── ...                       # 其他源代码文件
│
├── tests/
│   ├── test_extractor.py         # 单元测试
│   └── ...                       # 其他测试文件
│
├── README.md                     # 项目说明文档
├── requirements.txt               # 项目依赖
└── ...                           # 其他配置文件
```

## 要素列表

项目目前支持抽取以下要素：

1. 担保人的SWIFT标识代码
2. 开立日期
3. 保函种类
4. 保函编号
5. 担保人的名称
6. 保函开立地址
7. 申请人的名称
8. 申请人的地址
9. 受益人的名称
10. 受益人的地址
11. 基础合同名称
12. 基础合同编号
13. 基础合同货物描述
14. 保函的金额
15. 保函的币种

## 使用方法

1. 克隆项目仓库：
    ```bash
    git clone https://github.com/u3588064/AutoGuarantee.git
    cd 保函要素抽取项目
    ```

2. 安装项目依赖：
    ```bash
    pip install -r requirements.txt
    ```

3. 运行要素抽取脚本：
    ```bash
    python src/extractor.py data/sample_guarantee.txt
    ```

4. 查看输出结果：
    脚本会在终端输出抽取的要素，以JSON格式展示。

## 示例

输出结果：
```json
{
  "担保人的SWIFT标识代码": "",
  "开立日期": "December 7, 2023",
  "保函种类": ["Performance Guarantee","Advance Payment Guarantee"],
  "保函编号": "GC1234567",
  "担保人的名称": "Bank of China Ltd, ABC Branch",
  "保函开立地址": "No.1 N Road, Xi Province, P. R. China",
  "申请人的名称": "GUANGDONG GX GROUP MACHINE CO., LTD",
  "申请人的地址": "NO.18 E ROAD, CHINA",
  "受益人的名称": "Machine Shopping Department",
  "受益人的地址": "Q.X.TOY 101 HUAYUAN, Korea",
  "基础合同名称": "Supply Contract",
  "基础合同编号": "AK/123/2023/09",
  "基础合同货物描述": "Supply of Toy bags",
  "保函的金额": 1,123.00,
  "保函的币种": "USD"
}
{
 "保函种类": ["Performance Guarantee","Advance Payment Guarantee"]
}
```

## 贡献

欢迎对本项目进行贡献。如果您有任何建议或发现任何问题，请提交Issue或Pull Request。

## 许可证

本项目采用MIT许可证，详见LICENSE文件。

## 联系方式

如果您有任何问题或需要进一步的信息，请联系项目维护者：[u3588064@connect.hku.hk](mailto:u3588064@connect.hku.hk)。

![qrcode_for_gh_643efb7db5bc_344(1)](https://github.com/u3588064/LLMemory/assets/53069671/8bb26c0f-4cab-438b-9f8c-16b1c26b3587)
