# DB

*长期储存在计算机内、有组织的、可共享的大量数据的集合*
# DBS

*数据库系统是由数据库、数据库管理系统（及其应用开发工具）、应用程序和数据库管理员组成的存储、管理、处理和维护数据的系统*

## 数据库系统特点

1. 数据结构化
* 数据库系统与文件系统的本质区别
2. 数据的共享性高、冗余度低且易扩充
* 数据共享可以大大减少数据冗余，节约存储空间。还能避免数据之间不相容性和不一致性
3. 数据独立性高
  * 数据独立性包括数据的物理独立性和逻辑独立性
  * 物理独立性是指用户的应用程序与数据库中数据的物理存储是相互独立的
  * 逻辑独立性是指用户的应用程序与数据库的逻辑结构是相互独立的

4. 数据有数据库管理系统统一管理和控制
* 数据的安全性保护
* 数据的完整性检查
* 并发控制
* 数据恢复

# DBMS

*数据库管理系统是位于用户与操作系统之间的一层数据管理软件*

## 主要功能

1. 数据定义
2. 数据组织、存储和管理
3. 数据操纵
4. 数据库的事物管理和运行管理
5. 数据库的建立和维护
6. 其他

# 数据模型

*数据模型由数据结构、数据操作、数据的完整性约束条件三部分组成*

## 概念模型

* 按照用户的观点来对数据化和信息建模，主要用于数据库设计

## 逻辑模型和物理模型
### 逻辑模型
* 层次模型
* 网状模型
* 关系模型
* 面向对象数据模型
* 对象关系数据模型
* 半结构化数据模型

### 物理模型

对数据最底层的抽象，它描述数据在系统内部的表示方式和存取方式，或在磁盘或磁带上的存储方式和存取方法，是面向计算机系统的

# 数据库设计的主要阶段和任务

1. 需求分析
2. 概念设计分析
3. 逻辑结构分析
4. 物理结构分析
5. 数据库实施
6. 数据库运行和维护

# 数据库模式

## 数据库三级模式系统

### 模式

模式也称逻辑模式，是数据库中全体数据的逻辑结构和特征的描述，是所有用户的公共视图

### 外模式

外模式也称子模式或用户模式，它是数据库用户所能看见和使用的局部数据的逻辑结构和特征的描述，是数据库用户的数据视图，是与某一应用有关的数据的逻辑表示

### 内模式

内模式也称存储模式，一个数据库只有一个内模式。它是数据物理结构和存储方式的描述，是数据在数据库内部的组织方式

## 数据库的二级映像功能和数据独立性

### 外模式/模式映像

当模式改变时，由数据库管理员对各个外模式/模式的映像做出相应改变，可以使外模式保持不变。应用程序是依据数据的外模式编写的，从而应用程序不必修改，保证了数据的逻辑独立性，简称数据的逻辑独立性

### 模式/内模式映像

当数据库存储结构改变时，由数据库管理员对各个模式/内模式的映像做出相应改变，可以使模式保持不变，从而应用程序也不必改变。保证了数据与程序的物理独立性，简称物理独立性

# 范式

## 2NF

每一个非主属性完全函数依赖于任何一个候选码

## 3NF

每一个非主属性既不传递依赖于码，也不部分依赖于码

## BCNF

每一个决定因素都包含码

# 关系模式的分解

## 模式分解的三个定义 

1. 分解具有无损连接性
2. 分解要保持函数依赖
3. 分解既要1也要2