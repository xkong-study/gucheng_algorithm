---

# §7 杂项题型整理

---
<img width="359" alt="Screenshot 2025-04-14 at 19 44 57" src="https://github.com/user-attachments/assets/283987f2-372b-4d7e-9970-6ee664499740" />

<img width="330" alt="Screenshot 2025-04-14 at 20 09 54" src="https://github.com/user-attachments/assets/08962cc8-19ba-4409-a27f-a0d365df9839" />

1.检测在不在环上是 x = kn-m的证明
2.证明 n-x=m

## §7.6 Floyd 判圈（判环证明）

### 🌀 基本模型

- 给定一个函数 \( f(x) \)，不断执行：`x = f(x)`，最终可能进入循环。
- 判圈算法使用两个指针：
  - `slow = f(x)` 每次走一步
  - `fast = f(f(x))` 每次走两步

<img width="603" alt="Screenshot 2025-04-14 at 19 45 14" src="https://github.com/user-attachments/assets/5ccbb84e-2980-49c1-8c9d-d32c9cad146e" />

<img width="537" alt="Screenshot 2025-04-14 at 19 45 21" src="https://github.com/user-attachments/assets/2b399668-7abb-4ae8-ac30-250b8e60f7be" />
