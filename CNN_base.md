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

<img width="1214" height="1074" alt="image" src="https://github.com/user-attachments/assets/d44ed8c9-3f9a-4292-8b30-01b3a546f334" />

# 梯度下降

<img width="1517" height="728" alt="image" src="https://github.com/user-attachments/assets/1eecf990-d5d4-4037-a208-8c6dba120909" />


<img width="1315" height="635" alt="image" src="https://github.com/user-attachments/assets/ee5569fd-26d3-4d0e-b637-e8b6ddbe491f" />

<img width="1212" height="742" alt="image" src="https://github.com/user-attachments/assets/e43303dc-6b96-4011-b9b1-ffdf74633555" />

<img width="1204" height="797" alt="image" src="https://github.com/user-attachments/assets/51776806-352b-4946-90ff-60280d36e623" />

<img width="1228" height="802" alt="image" src="https://github.com/user-attachments/assets/745657a0-6de9-4e73-a0d7-8fd7305cd84e" />

<img width="1227" height="249" alt="image" src="https://github.com/user-attachments/assets/e7b368dc-c53c-4bb4-8703-c4dd2cec8326" />

<img width="1207" height="1124" alt="image" src="https://github.com/user-attachments/assets/65e56988-a420-4012-a04c-7265a053c6ad" />

<img width="1201" height="960" alt="image" src="https://github.com/user-attachments/assets/c70f3ba3-4d3c-440e-8b2a-fa51b98c114a" />

<img width="1219" height="812" alt="image" src="https://github.com/user-attachments/assets/6c2ccb26-5d8a-4f45-877d-f496308e5826" />

<img width="1183" height="694" alt="image" src="https://github.com/user-attachments/assets/1a690f61-d81c-4cfe-9781-1b409e3851b5" />

<img width="1168" height="723" alt="image" src="https://github.com/user-attachments/assets/8939a0ec-f2e1-4dce-965e-3e78ad532913" />

<img width="1200" height="829" alt="image" src="https://github.com/user-attachments/assets/95b477a0-c359-49a4-ab2f-146333f735e7" />

## 理解了这些，再进一步解释公式

<img width="1188" height="874" alt="image" src="https://github.com/user-attachments/assets/8fbab7ad-8561-4d11-9ecc-ae6ca7c30db3" />

<img width="1233" height="952" alt="image" src="https://github.com/user-attachments/assets/c1340456-bdd4-4eec-8d92-8801e98d212e" />

<img width="397" height="259" alt="image" src="https://github.com/user-attachments/assets/478ecd41-c5dd-4ee0-bf10-bb28a6e4710b" />

<img width="1209" height="720" alt="image" src="https://github.com/user-attachments/assets/dda390ff-8820-4752-b1c5-4891211d6776" />

<img width="1194" height="180" alt="image" src="https://github.com/user-attachments/assets/8aa0e0c6-02d7-4e37-ba00-05517b03f2a3" />

<img width="1237" height="858" alt="image" src="https://github.com/user-attachments/assets/185ad047-0180-4844-9411-c7e57635bda3" />

<img width="1181" height="1168" alt="image" src="https://github.com/user-attachments/assets/a3d7d74f-a849-463f-b501-9de92c229b40" />

<img width="1236" height="1140" alt="image" src="https://github.com/user-attachments/assets/aae84e42-bc67-418e-bd16-c0f37754bcbc" />

<img width="1187" height="1006" alt="image" src="https://github.com/user-attachments/assets/dc077d5b-61a5-4a20-8406-32aa6b11cf3c" />

<img width="1281" height="1003" alt="image" src="https://github.com/user-attachments/assets/a76278e9-60aa-4f1f-a560-4676147a5c55" />

<img width="1283" height="509" alt="image" src="https://github.com/user-attachments/assets/00c9e3dc-cc32-4e51-9ced-42db101032ee" />

<img width="1181" height="581" alt="image" src="https://github.com/user-attachments/assets/304a5d00-cc15-4cbe-a736-7e8d22019c04" />

# 本章问答

<img width="1190" height="366" alt="image" src="https://github.com/user-attachments/assets/06ef65db-32d0-4dc6-8392-0beb0a07bfe9" />

<img width="1203" height="169" alt="image" src="https://github.com/user-attachments/assets/b7fca6a4-5f29-4582-8170-646f11ad5d3a" />

<img width="854" height="271" alt="image" src="https://github.com/user-attachments/assets/a4679aeb-3773-4503-8a7d-76e3369ef874" />

<img width="1183" height="529" alt="image" src="https://github.com/user-attachments/assets/9f63aec7-6cd8-4b4e-801d-ae4507146230" />

<img width="674" height="1054" alt="image" src="https://github.com/user-attachments/assets/291d8381-6713-4e98-a422-d6f19caf71f6" />

<img width="387" height="279" alt="image" src="https://github.com/user-attachments/assets/15af1d00-94f1-4f11-99b6-b1923afd923c" />

<img width="735" height="829" alt="image" src="https://github.com/user-attachments/assets/63a18415-1456-4a3d-8f53-ab984c7e7664" />

<img width="820" height="314" alt="image" src="https://github.com/user-attachments/assets/abbf16cd-6b02-4010-92a1-492fe8eb9549" />

<img width="1188" height="687" alt="image" src="https://github.com/user-attachments/assets/da82fb6e-2624-4e92-a920-f9635e4b53df" />

<img width="1261" height="678" alt="image" src="https://github.com/user-attachments/assets/3b468089-961c-4fba-bb95-d06fbd55a2e5" />

<img width="1200" height="718" alt="image" src="https://github.com/user-attachments/assets/baec8e7f-3582-43aa-8bb0-bbfe3f61d996" />

<img width="1209" height="602" alt="image" src="https://github.com/user-attachments/assets/471ae518-8fba-492c-8c64-cb83f569017f" />

<img width="1287" height="860" alt="image" src="https://github.com/user-attachments/assets/b8ba6caf-7cb5-4e48-ae5f-70eca9018eab" />

<img width="953" height="398" alt="image" src="https://github.com/user-attachments/assets/d87ab49a-7dcc-4e04-8b35-a4fae5943250" />

<img width="404" height="380" alt="image" src="https://github.com/user-attachments/assets/2f17eafb-0c19-4d30-badd-e45c3c3086b8" />

# 以下是学习过程中启发比较大的问答讲解，害怕以后找不到所以先贴上来。自己练习后再看。

<img width="1279" height="1272" alt="image" src="https://github.com/user-attachments/assets/0fa13738-96b9-466c-b2fd-eec15c3dffd1" />

<img width="1239" height="997" alt="image" src="https://github.com/user-attachments/assets/36651700-8614-44f7-a5f9-d7c8f68f2ed6" />

<img width="1283" height="787" alt="image" src="https://github.com/user-attachments/assets/dabe3d48-b0e6-46fb-ada4-d73b1e4a9b64" />

<img width="1234" height="819" alt="image" src="https://github.com/user-attachments/assets/1d2008b1-4b56-4b3c-83fd-29b438c9f5ea" />

<img width="1267" height="786" alt="image" src="https://github.com/user-attachments/assets/20570ffe-bdf2-4769-95fb-479d476520c0" />

<img width="1211" height="766" alt="image" src="https://github.com/user-attachments/assets/e93b630c-f4ff-4732-828c-e21ff2b4dace" />

<img width="1189" height="517" alt="image" src="https://github.com/user-attachments/assets/93ed2e47-c46e-45f5-a539-e44fcb04e715" />
