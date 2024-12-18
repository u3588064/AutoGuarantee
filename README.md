# 保函业务自动化项目

## 项目概述

本项目旨在从保函文本中抽取要素、切分条款、提示要点、录制系统，以便于法律和金融专业人士进行分析和处理。项目使用自然语言处理技术，从保函文本中提取特定要素，并以JSON格式输出结果。

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
│   ├── clause_splitter.py        # 条款分割脚本
│   ├── key_points.py             # 要点提示脚本
│   ├── format.py                 # 格式处理脚本
│   └── ...                       # 其他源代码文件
│
├── tests/
│   ├── test_extractor.py         # 要素抽取单元测试
│   ├── test_clause_splitter.py   # 条款分割单元测试
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

## 条款分割

项目支持按以下类别切分条款：

    需提交的支持索赔的单据
    需提交单据的语言
    交单形式
    交单地点
    生效条款
    失效条款
    费用的承担方
    担保人的承诺
    索赔的提交要求
    索赔的时间和地点要求
    适用规则
    适用法律
    司法管辖地


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
输入文本：
```
Performance Guarantee

Issue date: December 7, 2023
No.: XX1234567

To:Machine Shopping Department (hereinafter called 'the Beneficiary')
Add:Q.X.TOY 101 HUAYUAN, Korea

…… (SEE Full Text in the repository)

This performance guarantee shall be valid from its issuance and remian valid until August 35, 2025 (expiry date). Any demand in respect of this guarantee should reach us at our counter not later than the close of our Business hours on the above expiry date.

This performance guarantee is only personnel to you and is not assignable or transferable.

This guaranttee is subject to the Uniform Rules for Demand Guarantees, ICC Publication No.758.

```

要素抽取结果：
```json
{
  "担保人的SWIFT标识代码": "",
  "开立日期": "December 7, 2023",
  "保函种类": ["Performance Guarantee","Advance Payment Guarantee"],
  "保函编号": "XX1234567",
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

条款切分结果：
```
{
  "需提交的支持索赔的单据": null,
  "需提交单据的语言": null,
  "交单形式": "any such demand in original should be presented to us through your Banker confirmation that the signatures thereon are authentic and legally binding upon you.",
  "交单地点": "our counter",
  "生效条款": "This performance guarantee shall be valid from its issuance",
  "失效条款": "This performance guarantee shall ... remain valid until August 35, 2025 (expiry date).",
  "费用的承担方": null,
  "担保人的承诺": "we undertake to pay you unconditionally and independently, upon our receipt of your first written demand in original paper form declaring the seller fails to perform its obligations under the Contract and specifying in which respect the seller is in failure.",
  "索赔的提交要求": "your first written demand in original paper form declaring the seller fails to perform its obligations under the Contract and specifying in which respect the seller is in failure.",
  "索赔的时间和地点要求": "Any demand in respect of this guarantee should reach us at our counter not later than the close of our Business hours on the above expiry date.",
  "适用规则": "This guaranttee is subject to the Uniform Rules for Demand Guarantees, ICC Publication No.758.",
  "适用法律": null,
  "司法管辖地": null
}
```

## 贡献

欢迎对本项目进行贡献。如果您有任何建议或发现任何问题，请提交Issue或Pull Request。

## 许可证

本项目采用MIT许可证，详见LICENSE文件。

## 联系方式

如果您有任何问题或需要进一步的信息，请联系项目维护者：[u3588064@connect.hku.hk](mailto:u3588064@connect.hku.hk)。

![qrcode_for_gh_643efb7db5bc_344(1)](https://github.com/u3588064/LLMemory/assets/53069671/8bb26c0f-4cab-438b-9f8c-16b1c26b3587)
