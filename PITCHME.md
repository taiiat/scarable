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

(相対的ロック)

最新のAllocationトランザクションを保証

+++

参加者の総数を$p$とした場合、

$O(p^{2})$回の通信のオーバーヘッドが発生

しかしリーダーを置くことで$O(p)$まで減少できる。


---

###  Leaving a group

payment channel:

ノードがクラッシュやオフラインだと決済不可



同様にAllocationやCommitmentの更新も不可。

+++

アクティブな参加者で新しいアカウントを作成

![alt](mpay6.png) 
      
---
#### Including a cold & hot wallet in a channel

 
<img src="mpay13.png" width="600">

coldから資金を引っ張りたいとき

Allocationのときのみグループ内でcoldをオンライン

---

### Combining channel factories
     

<img src="mpay7.png" width="400">
   
   グループが大きいほど、BCスペースを節約
   
   (オフチェーン決済の量が増える)   
  
+++

  <img src="mpay9.png" width="600">
  
  共通のノードの役割は新たなビジネスになる可能性

---      
  


###  Evaluation of Channel Factory 

evaluating the system with the used ECDSA signatures
   
   ECDSA signature :72bytes, 
   
   a public key :33 bytes.

   p=number of parties 
   
   n=the number of subchannels
   
   
   
+++
   #### The blockchain cost per subchannel
   
   $$BC(p,n)=\frac{33\times2\times p +72 \times 2 \times p}{n}=210\times \frac{p}{n}$$
    
   
   $$BC_{simple}=33\times2\times2+72\times2\times2=420$$

+++
### More concrete

p=20 parties　n=100 subchannels

the blockchain cost of each channel:42 bytes

もともとの420の10%にまで削減

より多いグループだとコストはさらに削減！

---

### With Schnorr signatures
 
ed25519 curveに基づくBlockchain cost

a public key uses 32 bytes 

only one  signature 64 bytes

Signature for hock and settle

Pub key for each output and

Public key combined with Signature

+++
### Schnorr signatures

signature for hock and settlemrnt=2

Pub key for each output and 


Pub key combined with signature   


$$BC_{schnorr}(p,n)=\frac{32\times(p+1) +64\times 2}{n}$$


$$BC_{simple,schnorr}=33\times3+64\times2=224$$


---
### Conclusion

より多く効率的にMPCの取引可能

ただし

直接の取引相手ではない第三者によって

チャネルが閉じられるリスクが生じる








