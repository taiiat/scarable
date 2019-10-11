### Scalable funding of Bitcoin micropayment channel networks





---
### Introduction　
- micropayment channelの課題

  -スケーラビリティ
  
  -チャネル内で決済できる金額の上限




---


### Channel factory

![alt](mpay2.png)

     ３人が参加し、ペアのペイメントチャネルを作っている。
---


### Allocation

![alt](mpay4.png)

       サブチャネルで資金が不足した場合、新しいAllocation TXを作成
---


###  Leaving a group
      相手のノードがクラッシュしたりオフラインとなったままでは決済ができない
![alt](mpay6.png)
       
       まだアクティブな参加者が集まって新しい共有アカウントを作る方法がある。
 
      
---

### Combining channel factories
     

![alt](mpay7.png)
      
      グループが大きいほど、ブロックチェーンスペースは節約できる
      (オフチェーン決済の量が増える)
  
+++

### Evaluation
