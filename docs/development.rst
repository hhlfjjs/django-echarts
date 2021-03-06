项目开发
=========

pyecharts接口
--------------

django-echarts 基于 `pyecharts API`_ 整合开发。

.. _`pyecharts API`: https://github.com/pyecharts/pyecharts/blob/master/docs/zh-cn/doc_api.md

由于 Python 语言的"Duck Type" 特性，django-echarts 并不会直接引入 `pyecharts.base.Base` 或 `pyecharts.custom.page.Page` 等实际图表类，而是仅使用其接口。

FAQ
-----

**Q: django-echarts 运行环境要求是什么？**

A: 目前 django-echarts 运行环境要求如下：

- Python3.5+
- Django 1.11 LTS 和 Django 2.0

**Q: django_echarts 对于 pyecharts 有什么改造？**

A：首先需要明确的一点的是： django-echarts 仅使用了 pyecharts 当中的图表构建模块。对 pyecharts 的运行环境和功能特性作了一定的调整，包括：

- jshost 不支持对象级别设置
- javascript 标签渲染不支持内部嵌入方式

需要注意的是： pyecharts v0.3.2 之后 ，jshost 也不支持对象级别设置了，可以使用 `pyecharts.configure` 或者 `pyecharts.online` 函数进行全局设置。

**Q: 本地部署无法引用 echarts.js 文件 ？**

A: 为了节省资源和提高加载效率，在 pyecharts 中 依赖文件 echarts 实际引用的是 echarts.min.js ，因此可以使用其压缩版本文件 echarts.min.js 代替， 请确保文件名是 echarts.min.js 。

**Q：我的Django项目是采用 jinja2 模板引擎，该如何整合？**

A: django-echarts 是一个 django + pyecharts 的整合解决方案，因此在django中使用jinja2模板引擎不在该项目的问题领域之内。可参考 pyecharts 项目的相关文档。

开源协议
---------

django-echarts 基于 MIT 开源协议。

.. code-block:: none

    MIT License

    Copyright (c) 2017-2018

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.
