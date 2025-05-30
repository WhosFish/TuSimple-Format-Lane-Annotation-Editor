# TuSimple 车道线标注指南

本指南适用于使用本项目工具进行 TuSimple 格式的 2D 车道线标注工作。内容包括基本原则、实操经验及具体修改场景。

---

## 一、标注基本原则

- **最多标注 4 条车道线**  
  优先标注与自车中心最近的 4 条：  
  `Left-Left`, `Left`, `Right`, `Right-Right`。

- **起止位置**  
  起点/终点应尽可能覆盖全部参考线。靠近图像底部的区域可结合合理想象进行补全。

- **路边情况**  
  若可见车道线少于 4 条，可将路缘（如路肩、护栏）视作车道线进行标注。

- **分叉场景**  
  应标为 **两条车道线**：起点相同，终点不同。

- **合并场景**  
  应标为 **两条车道线**：终点相同，起点不同。

- **遮挡 / 模糊区域**  
  根据上下文合理推测车道线走向，进行补全。

---

## 二、标注实操建议

- 优先标注：起点、终点和关键转折点，使用**软件插值功能**自动补全中间点。
- 弧形车道线：应增加关键点，以提高拟合精度。
- 修改建议：**清空点重画**，而不是删除整条线，以保持线条在列表中的顺序与颜色。

---

## 三、何时应“修改”已有标注线

请在以下情况对已有标注线进行“重标”：

1. 标注线受路面阴影或图案误导，未正确沿实际车道线标注。
![标注线被地面沥青阴影所误导](https://github.com/WhosFish/TuSimple-Format-Lane-Annotation-Editor/blob/main/img/%E9%87%8D%E6%96%B0%E4%BF%AE%E8%AE%A2%20-%20%E5%9C%B0%E9%9D%A2%E9%98%B4%E5%BD%B1.png)
2. 标注线出现明显且不自然的折线。
![](https://github.com/WhosFish/TuSimple-Format-Lane-Annotation-Editor/blob/main/img/%E9%87%8D%E6%96%B0%E4%BF%AE%E6%AD%A3%20-%20%E8%BD%A6%E9%81%93%E4%B8%AD%E6%8A%98%E5%81%8F%E7%A6%BB.png)
3. 标注线发生明显偏折，明显偏离真实车道线。
![](https://github.com/WhosFish/TuSimple-Format-Lane-Annotation-Editor/blob/main/img/%E9%87%8D%E6%96%B0%E4%BF%AE%E6%AD%A3%20-%20%E4%B8%AD%E7%AB%AF%E6%8A%98%E7%BA%BF.png)
4. 标注线的起点或终点处偏离车道线。
![](https://github.com/WhosFish/TuSimple-Format-Lane-Annotation-Editor/blob/main/img/%E9%87%8D%E6%96%B0%E4%BF%AE%E6%AD%A3%20-%20%E8%BF%91%E7%AB%AF%E5%81%8F%E7%A6%BB.png)
![](https://github.com/WhosFish/TuSimple-Format-Lane-Annotation-Editor/blob/main/img/%E9%87%8D%E6%96%B0%E4%BF%AE%E6%AD%A3%20-%20%E6%9C%AB%E7%AB%AF%E5%81%8F%E7%A7%BB.png)
6. 错误忽略路口，将应连接的线错误分离。
![]()
---

## 四、何时应“删除”多余标注线

1. 有 5 条车道线被标注，应删除最外侧冗余线。
![]()
2. 某侧已标注超过两条车道线，且超过合理范围。
![]()
3. 道路边界无明显护栏/台阶/围栏，仅靠视觉猜测标注出的边缘线。
![]()
---

## 五、何时应“新增”遗漏标注线

1. 当前仅标注 3 条车道线，但边界处存在台阶、石墩等明显参照物，应补齐第 4 条。
2. 当前仅 3 条标注线，且边界处有围栏，应在围栏底部添加第 4 条车道线。

---

## 补充说明

- 本指南主要依据图像直观信息结合标注人员常识进行判断。
- 若存在特殊结构、复杂交汇区、暂未涵盖的情况，请提交 issue 或联系项目维护者。
