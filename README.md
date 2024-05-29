![Hello](docs/hello.svg)
### Hi there 👋
<!--
**yuqingc31/yuqingc31** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.


-->

I'm Yuqing, a master of computing and innovation student at UOA. 

My Medium articles: https://medium.com/@yuqingc31

:)

-   :hammer_and_pick: Java / C++ / C / python / HTML / CSS / SASS / JavaScript / TypeScript / React / Node.js / Wordpress
  
-   🧰  github / bitbucket / Jira

-   🖌️ figma / photoshop

----
#### :rocket: My Projects

Personal projects:
* [yuqingc31/JR](https://github.com/yuqingc31/JRbusinessProjects.git) - Projects from JR company - HTML, CSS, JavaScript, NodeJS, TypeScript, React
* [OfferRipple](https://github.com/yuqingc31/OfferRipple.git) - OfferRipple(Discount offer website) - HTML, CSS, JavaScript, NodeJS, React, TypeScript, MongoDB
* My personal page - yuqingc31.wordpress.com - WordPress

School's assignments (Do not copy):

* [yuqingc31/COMP SCI 2000 Computer-Systems-UOA](https://github.com/yuqingc31/Computer-System.git) - Computer Systems assignments/quizzes/exams/notes - HDL, c++
* [yuqingc31/ADSA-UOA](https://github.com/yuqingc31/ADSA.git) - Algorithm and Data Structure Analysis assignments - c++
* [yuqingc31/Computer-Vision-UOA](https://github.com/yuqingc31/Computer-Vision.git) - Computer Vision assignments - python numpy
* [yuqingc31/Operating-Systems](https://github.com/yuqingc31/Operating-Systems.git) - Operating Systems assignments - c, java
* [yuqingc31/CNA](https://github.com/yuqingc31/CNA.git) - Computer networking and applications - c, python
* [yuqingc31/MiningBigData](https://github.com/yuqingc31/MiningBigData.git) - Mining Big Data assignments - python
* [yuqingc31/MCI_Project](https://github.com/yuqingc31/MCI_Project.git) - Master of Computing and Innovation Project

---
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=yuqingc31&layout=compact)](https://github.com/anuraghazra/github-readme-stats)


### 数据表示为多项式

1. **将数据表示为多项式**：
   - 数据可以用多项式来表示。例如，一个二进制数据串可以看作是一个多项式的系数。例如，二进制数 `1001` 可以表示为多项式 \(1 \cdot x^3 + 0 \cdot x^2 + 0 \cdot x^1 + 1 \cdot x^0\)，也就是 \(x^3 + 1\)。

2. **将多项式转换为二进制数**：
   - 一旦我们有了多项式表示，我们可以将这个多项式转换回二进制数。例如 \(x^3 + 1\) 对应的二进制数就是 `1001`。

### CRC 示例解释

1. **消息作为多项式表示**：
   - 假设我们有一个消息 \(D(x)\)，其二进制表示是 `100101010`，我们可以把它看作一个多项式 \(D(x) = x^8 + x^5 + x^3 + x + 1\)。

2. **生成多项式**：
   - 使用生成多项式 \(G(x)\)，例如 `1101`，对应的多项式是 \(G(x) = x^3 + x^2 + 1\)。

3. **计算 CRC**：
   - 要计算 CRC，我们将消息多项式 \(D(x)\) 乘以 \(2^r\)（即将其左移 \(r\) 位，其中 \(r\) 是生成多项式的度数）。
   - 然后，对结果进行模 \(G(x)\) 的多项式除法，得到的余数就是 CRC 校验位 \(R\)。
   - 最后，将 \(R\) 附加到原始消息后面形成发送的数据。

### CRC 的实质

- **多项式除法**：CRC 校验的核心是多项式除法，通过将数据多项式除以生成多项式来检测错误。
- **二进制表示**：所有的多项式运算最终都可以用二进制表示进行，因为二进制数和多项式之间有直接的对应关系。

这个过程帮助我们确保数据在传输过程中没有出错，如果接收方用同样的生成多项式进行计算，应该得到零余数，如果不是零则表示数据传输过程中出现了错误。

### 具体例子

假设我们有一个消息 \(D(x) = 100101010\) 和生成多项式 \(G(x) = 1101\)，以下是详细的计算步骤：

1. **将消息多项式左移**：
   - 如果生成多项式的度数为3，那么我们将消息多项式 \(D(x)\) 乘以 \(2^3\)，即左移3位：\(100101010 \rightarrow 100101010000\)。

2. **进行多项式除法**：
   - 将左移后的消息多项式除以生成多项式 \(G(x)\)，得到余数 \(R\)。

3. **附加 CRC 校验位**：
   - 将余数 \(R\) 附加到消息 \(D(x)\) 的末尾，形成新的数据包。

### 使用 CRC 的原因

- **错误检测**：通过这个过程，发送方和接收方都可以检测数据传输过程中是否发生了错误。如果接收方计算出的余数不是零，则说明数据包在传输过程中发生了错误。
