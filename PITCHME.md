### Scalable funding of Bitcoin micropayment channel networks





---
## Introduction　
- micropayment channelの課題

  -スケーラビリティ
  
  -チャネル内で決済できる金額の上限




---


## Channel factory

![alt](mpay2.png)

     ３人が参加し、ペアのペイメントチャネルを作る。
---


## Allocation

![alt](mpay4.png)

       サブチャネルで資金が不足した場合、新しいAllocationを作成
---

##  Leaving a group

payment channel:ノードがクラッシュやオフライン
決済できない



同様にAllocationやCommitmentの更新ができなくなる。|

+++

アクティブな参加者で新しい共有アカウントを作る

![alt](mpay6.png) 
      
---

### Combining channel factories
     

![alt](mpay7.png)
      
  
+++

      グループが大きいほど、ブロックチェーンスペースは節約できる
      (オフチェーン決済の量が増える)
---      
  


##### The Cauchy-Schwarz Inequality


`\[
\left( \sum_{k=1}^n a_k b_k \right)^{\!\!2} \leq
 \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)
\]`



---
### slide 3
