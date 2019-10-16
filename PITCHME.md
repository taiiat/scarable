#### Scalable funding of Bitcoin micropayment channel networks





---
#### Introduction　
- micropayment channelの課題

  -スケーラビリティ
  
  -チャネル内で決済できる金額の上限




---


#### Channel factory

![alt](mpay2.png)

     ３人が参加し、ペアのペイメントチャネルを作る。
---


#### Allocation

![alt](mpay4.png)

       サブチャネルで資金が不足した場合、新しいAllocationを作成
---
##### Allocationの更新



---

##  Leaving a group

payment channel:ノードがクラッシュやオフライン
決済できない



同様にAllocationやCommitmentの更新ができなくなる。

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
  


####  Evaluation 
  
  ESDCAに基づいたBlockchain　cost
   
   ECDSA signature constitutes 72 bytes, 
   
   a public key 33 bytes.

+++
$$BC(p,n)=\frac{33\times2\times p +72 \times 2 \times p}{n}$$

$$BC_{simple}=33\times2\times2+72\times2\times2=420$$

+++

p=20 parties and n=100 subchannels,

the blockchain cost of each channel is 42, 

つまり、もともとの10%にまで削減

さらにより多いグループを作ればコストはより削減できる！

---

##### With Schnorr signatures
 
ed25519 curveに基づくBlockchain cost

a public key uses 32 bytes 

only one  signature 64 bytes

+++
Schnorr signatures


$$BC_{schnorr}(p,n)=\frac{32\times(p+1) +64\times 2}{n}$$


$$BC_{simple,schnorr}=33\times3+64\times2=224$$


---
###






