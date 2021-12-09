# 強化学習による迷路の探索
迷路の自動探索を行うエージェントをTD学習法で訓練する。
例題迷路である。 Sは初期位置、 Gはゴールである。
![image text](https://github.com/KKK12321/Reinforcement-Learning/blob/main/%E4%BE%8B%E9%A1%8C%E8%BF%B7%E8%B7%AF.png)

方法：Q-学習法 & epsilon-greedy TD(0)
# 1.epsilon-greedy TD(0)学習法のアルゴリズム概要
![image text](https://github.com/KKK12321/Reinforcement-Learning/blob/main/TD%E5%AD%A6%E7%BF%92%E6%B3%95%E3%82%A2%E3%83%AB%E3%82%B3%E3%82%99%E3%83%AA%E3%82%B9%E3%82%99%E3%83%A0.png)
# 2.Q-学習法のアルゴリズム概要
Q学習法の価値更新関数は以下の通りである：
![image text](https://github.com/KKK12321/Reinforcement-Learning/blob/main/q%E5%AD%A6%E7%BF%92%E6%B3%95%E3%81%AE%E4%BE%A1%E5%80%A4%E6%9B%B4%E6%96%B0%E9%96%A2%E6%95%B0.png)
この式からわかる通り（赤線部分）、Q学習では遷移先状態𝑠′の最大Q値𝑚𝑎𝑥𝑎′𝑄(𝑠,𝑎′)を使って学習するのが主な特徴となる。
つまり、遷移した先の状態の最も良いところだけを利用します。 そのため楽観的な手法と言われる。
ちなみに　𝑟+𝛾max𝑎′𝑄(𝑠′,𝑎′)−𝑄(𝑠,𝑎)　をTD誤差といい、 Q学習ではこの誤差を小さくするように学習していく。
𝛼は学習率といい0〜1の間の値をとるパラメータです。 TD誤差をどれだけ反映させるかを決定する。
𝛾は割引率といい、遷移先の最大Q値をどれだけ利用するかを決めるパラメータである。
Q-学習法のアルゴリズム:
![image text](https://github.com/KKK12321/Reinforcement-Learning/blob/main/Q%E5%AD%A6%E7%BF%92%E6%B3%95%E3%81%AE%E3%82%A2%E3%83%AB%E3%82%B3%E3%82%99%E3%83%AA%E3%82%B9%E3%82%99%E3%83%A0.png)
