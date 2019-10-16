#### Scalable funding of Bitcoin micropayment channel networks





---
#### Introduction　
- micropayment channelの課題

  -スケーラビリティ問題
  
  -チャネル内で決済できる金額の上限




---


#### Channel factory

![alt](mpay2.png)

     ３人が参加しペアのペイメントチャネルを作成
---


#### Allocationの効果
<img src="mpay8.png" width="400">



各MPCのキャパシティがオフチェーンで動的に変更

Blockchainに書き込む回数がへる。


+++
##### Allocationの更新
![alt](mpay4.png)

相対的ロックで最新のAllocationトランザクションを保証

参加者の総数を$p$とした場合、

$O(p^{2})$回の通信のオーバーヘッドが発生

しかしリーダーを置くことで$O(p)$まで減少できる。


---

##  Leaving a group

payment channel:

ノードがクラッシュやオフラインだと決済できない



同様にAllocationやCommitmentの更新ができなくなる。

+++

アクティブな参加者で新しいアカウントを作成

![alt](mpay6.png) 
      
---

### Combining channel factories
     

<img src="mpay7.png" width="400">
   
   グループが大きいほど、BCスペースは節約できる
   (オフチェーン決済の量が増える)   
  
+++

  <img src="mpay9.png" width="600">
---      
  


####  Evaluation 
  
 　evaluating the system
  
   with the used ECDSA signatures
   
   ECDSA signature:72bytes, 
   
   a public key:33 bytes.

+++
#### calculate

   p=number of parties and n=the number of subchannels. 
   
   The blockchain cost per subchannel:
   $$BC(p,n)=\frac{33\times2\times p +72 \times 2 \times p}{n}$$
    
   $$BC_{simple}=33\times2\times2+72\times2\times2=420$$

+++


p=20 parties and n=100 subchannelsとすると

the blockchain cost of each channel is 42, 

つまり、もともとの10%にまで削減

さらにより多いグループを作ればコストはより削減できる！

---

##### With Schnorr signatures
 
ed25519 curveに基づくBlockchain cost

a public key uses 32 bytes 

only one  signature 64 bytes

+++
### Schnorr signatures


$$BC_{schnorr}(p,n)=\frac{32\times(p+1) +64\times 2}{n}$$


$$BC_{simple,schnorr}=33\times3+64\times2=224$$


---
### Conclusion







