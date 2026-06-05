# 常用激活函数。

<img width="1561" height="936" alt="image" src="https://github.com/user-attachments/assets/d095c870-3f46-43e6-b641-c3683562c1c8" />

### sigmiod为什么适合分类任务？因为他把输入压缩到了0到1之间，

### 反向传播时sigmiod会出现梯度消失。sigmiod的导数最大只有0.25.反向传播时：神经网络更新参数依赖梯度。梯度大：学习快。梯度小：学习慢

### 梯度接近0：几乎学不动。除此之外，sigmiod的值永远为正数，反向传播时会导致参数更新方向容易比较偏，不够平衡，所以收敛会慢。

###  为什么现在CNN几乎不用Sigmoid？因为后来发现relu更好，

<img width="1456" height="936" alt="image" src="https://github.com/user-attachments/assets/df56ee07-dd12-4703-8a97-f0c49013b54c" />

###  Tahn（双曲正切激活函数）解决了sigmiod只有正值的情况，所以收敛会更快。

### 它的导数最大值为1，因此传播梯度的能力更强。

##  需要注意的是 以上两个激活函数基本不会出现神经元死亡。它们的梯度最低是趋近于0而不是等于0。

<img width="1592" height="940" alt="image" src="https://github.com/user-attachments/assets/065700ef-a135-4e92-be72-f2fe1532b7a5" />

### 为什么ReLU能解决梯度消失？先回忆Sigmoid。Sigmoid两边会变平：变平意味着导数≈0。而ReLU呢？

### 右边永远是：导数=1所以对于正区间：1 × 1 × 1 × 1还是：1

### 为什么会出现神经元死亡？假设某个神经元：z=wx+b，计算出来一直是：-3，经过ReLU：0下一次：-5输出：0再下一次：-10输出：0于是：永远输出0看导数：x<0，导数=0，反向传播：梯度=0，参数更新：0

### 为什么课件圈了 W、b？因为决定神经元是否死亡的关键就是：z=wx+b。如果权重更新后：wx+b<0对于所有样本都成立。那么：永远进入ReLU左边区域。输出：永远是0。导数：永远是0，神经元死亡。

<img width="1264" height="1031" alt="image" src="https://github.com/user-attachments/assets/4cffaa50-a544-42f4-9b99-c84419924967" />

<img width="1167" height="435" alt="image" src="https://github.com/user-attachments/assets/90936f3f-83e9-47cb-a086-58c187b39543" />

<img width="1207" height="787" alt="image" src="https://github.com/user-attachments/assets/81098705-f494-44c9-943a-891b88a5b043" />

<img width="1557" height="931" alt="image" src="https://github.com/user-attachments/assets/e1e0260d-204d-4efa-b9e5-9e3604cf36b0" />

### Leaky ReLU：负数导数＝a=0.01但不是：0。所以：梯度还能传回去神经元还能继续学习。

#### 两边处理方式不同。

<img width="1257" height="1189" alt="image" src="https://github.com/user-attachments/assets/f4d6b7d9-982c-4e4c-bdb6-e0b832fc3df4" />

<img width="1210" height="818" alt="image" src="https://github.com/user-attachments/assets/30089dc2-f967-4cac-b935-4c8167f7870f" />

# 前向传播

<img width="1635" height="750" alt="image" src="https://github.com/user-attachments/assets/b1e41597-f4df-4be7-9df9-441e7e69dcd7" />


## 先说一个结论：前向传播（Forward Propagation）其实就是神经网络的“预测过程”。你训练好的模型拿到一张图片：

## 猫经过网络：输入↓计算↓输出，最后得到：猫：0.95狗：0.05

## 这一整套从输入到输出的计算过程，就是前向传播。

# 损失函数

<img width="1675" height="869" alt="image" src="https://github.com/user-attachments/assets/a004102e-3679-4803-8f0b-66e437be2427" />

<img width="1183" height="520" alt="image" src="https://github.com/user-attachments/assets/e63907f6-c314-46b6-8fbb-93a5492f5f6b" />

<img width="1167" height="636" alt="image" src="https://github.com/user-attachments/assets/53a09aea-07bb-434d-9576-81ca92499b63" />

<img width="1186" height="442" alt="image" src="https://github.com/user-attachments/assets/c4c5c1a2-17ca-4237-bb57-5e25eac6b87b" />

<img width="1197" height="714" alt="image" src="https://github.com/user-attachments/assets/f62de1c0-fe74-45e1-b0cf-5758876ad150" />

<img width="1221" height="1116" alt="image" src="https://github.com/user-attachments/assets/d783ca7a-b783-4380-8031-6a0ef1fe0ad2" />

<img width="1181" height="1103" alt="image" src="https://github.com/user-attachments/assets/09871596-0c08-4776-85e8-a1b8418e7c02" />



