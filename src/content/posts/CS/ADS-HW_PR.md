---
title: ZJU ADS HW and Project
published: 2024-10-26
description: 一些造福后人的东西
tags: [note,ads,CS,]
category: CS
draft: false
---
# Introduction

一个(不完全的)作业回归+项目展示，隐去相关违反诚信守则内容，请勿抄袭，此外假设内容有误敬请在discussion刊误。

# HW

看这个吧，我后面有复习了再修正

# Project

private 项目 （尚未公开）

- [ ] Must-work

  - [ ] Project-3 Recover the Design
    - [X] code 😍(zzw4257)
      - [X] test 😍(WangHX)
    - [ ] report 😍(Valkqs)
    - [ ] presentation
    - [X] bonus reference
  - [ ] Project-7 Skip Lists
    - [ ] code 😍(Valkqs)
    - [ ] report
    - [ ] *presentation
    - [X] bonus reference
- [ ] Optional-work

  - [ ] Project-1Roll Your Own Mini Search Engine
  - [X] Project-2 Shortest Path Algorithm with Heap 😍(WangHX)

    - [X] bonus reference
    - [X] code 😍(WangHX)
    - [X] report😍(zzw4257+WangHX)
  - [ ] Project-4 Red-black Tree 😍(zzw4257)

    - [X] idea : in `/idea/project4-ans.md` 😍(zzw4257)
    - [X] code 😍(zzw4257)
    - [X] report 😍(zzw4257)
    - [ ] presentation
  - [ ] Project-5 Shopping With Coupons
  - [ ] Project-6 Texture Packing
  - [ ] Project-8 MapReduce

    - [X] bonus reference:`/reference/MapReduce`

## Project1（没做）

比较好的参考，虽然我觉得纯粹简单问题复杂化

[bowling233/ZJU-ADS-2024-Lab1: 基于自适应基数树的高性能文本倒排索引——浙江大学《高级数据结构与算法》课程实验一：Roll Your Own Mini Search Engine
](https://github.com/bowling233/ZJU-ADS-2024-Lab1)

### 项目背景

本项目旨在设计和实现一个高性能的文本倒排索引系统，以提升文本检索的效率。倒排索引是一种将词项映射到包含该词项的文档列表的数据结构，广泛应用于信息检索领域。

### 项目目标

* **处理数据集** ：使用“莎士比亚全集”作为数据集进行实验。
* **词干提取** ：实现词干提取功能，以解决词形变化带来的检索问题。
* **倒排索引** ：创建一个包含词干提取的倒排索引，排除已识别的停用词。
* **查询程序** ：编写一个查询程序，接受用户输入的词或短语，并返回包含该词的文档ID。

### 项目任务

1. **词频统计** ：对莎士比亚文集进行词频统计，并识别停用词。
2. **倒排索引构建** ：基于识别的词干和排除的停用词，构建倒排索引。
3. **查询处理** ：开发查询程序，实现用户查询词的检索功能。
4. **性能测试** ：进行测试，展示查询阈值对结果的影响。

### 评分政策

* **编程** ：实现词频统计（1分）、索引生成（5分）和查询处理（3分）程序，并添加充分注释。
* **测试** ：设计倒排索引正确性测试（2分）和查询阈值测试（2分），并编写分析和评论（3分）。额外加分项：考虑处理500,000个文件和4亿个不同词的情况（+2分）。
* **文档** ：撰写第1章（1分）、第2章（2分）和完整的项目报告（1分）。

### 项目结构

* **第1章 简介** ：介绍项目背景和词干提取模块。
* **第2章 数据结构和算法说明** ：详细说明基于 `std::map`的简单实现、自适应基数树（ART）等二叉搜索树的倒排索引设计、搜索引擎设计等。
* **第3章 性能测试与分析** ：展示使用不同数据集的性能测试结果。
* **第4章 思考与展望** ：讨论内存利用率优化、长键测试和ART树的应用前景。

## Project2（code+report)

> 堆优化最短路

没任何好说的，斐波纳契堆看我的ADS的数据结构部分笔记

## Project3（code+report+presentation）

> 回溯剪枝求解围栏恢复问题

整体两个

# Final Review
