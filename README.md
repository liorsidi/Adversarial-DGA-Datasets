# Adversarial DGA Dataset


A collection of different adversarial attacks on Domain Generated Algorithms' (DGA) classifiers

The goal of sharing the dataset is to help the research community to come with a new defense mechanism against DGA adversarial attacks.

Each attack type contains 10,000 samples for evaluation and 2,000 samples for adversarial training.

We implemented the attacks based on author papers or code snippets they send us privately.

Please quote the following papers for using this repository:
- Lior Sidi, Asaf Nadler, and Asaf Shabtai. "MaskDGA: A black-box evasion technique against DGA classifiers and adversarial defenses."(2019).
- Lior Sidi, Yisroel Mirsky, Asaf Nadler, Yuval Elovici and Asaf Shabtai. "Helix: DGA Domain Embeddings for Tracking and Exploring Botnets" (2020).

## Attacks Data & Papers
- **DeepDGA**: Anderson, H. S., Woodbridge, J., & Filar, B. (2016, October). DeepDGA: Adversarially-tuned domain generation and detection. In Proceedings of the 2016 ACM Workshop on Artificial Intelligence and Security (pp. 13-21). ([paper](https://arxiv.org/abs/1610.01969)  / [data](https://github.com/liorsidi/Adversarial-DGA-Datasets/tree/master/DeepDGA))
- **CharBot**: Peck, J., Nie, C., Sivaguru, R., Grumer, C., Olumofin, F., Yu, B., ... & De Cock, M. (2019). CharBot: A simple and effective method for evading DGA classifiers. IEEE Access, 7, 91759-91771. ([paper](https://arxiv.org/abs/1905.01078) / [data](https://github.com/liorsidi/Adversarial-DGA-Datasets/tree/master/CharBot))
- **MaskDGA**: Sidi, L., Nadler, A., & Shabtai, A. (2019). MaskDGA: A black-box evasion technique against DGA classifiers and adversarial defenses. arXiv preprint arXiv:1902.08909. ([paper](https://arxiv.org/abs/1902.08909) / [data](https://github.com/liorsidi/Adversarial-DGA-Datasets/tree/master/MaskDGA))
- **Append**: A sequential adversarial attack that appends characters one after the other. ([data](https://github.com/liorsidi/Adversarial-DGA-Datasets/tree/master/AppendAttack))
- **Search**: An extension of MaskDGA, the attack keeps changing characters until the substitute model prediction changes. ([data](https://github.com/liorsidi/Adversarial-DGA-Datasets/tree/master/SearchAttack))
- **Random**: Randomly change the characters of a generated domain.([data](https://github.com/liorsidi/Adversarial-DGA-Datasets/tree/master/RandomAttack))


## More about the MaskDGA datasets
The dataset contains multiple files for each attacker's substitute model type (CNN/LSTM) and the threshold for character changes (25/50/75).

Each file contains more info on the attack, such as: 
- **url_original**: the original URL before the attack.
- **family_name**: the original DGA family of the URL.
- **url**: the URL after the attack.
- **sub_model_benign_prob**: the attacker substitute model confidence for benign.
- **maskDGA_iteration**: the model retraining phase, for evaluation, use the highest value (=4).






## Datasets unigram charachters distribution

### Adversarial attacks datasets
Available in this repository.

![DeepDGA](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/DeepDGA.png)
![CharBot](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/CharBot.png)
![MaskDGA_CNN_25](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/MaskDGA_CNN_25.png)
![MaskDGA_CNN_50](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/MaskDGA_CNN_50.png)
![MaskDGA_CNN_75](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/MaskDGA_CNN_75.png)
![MaskDGA_LSTM_50](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/MaskDGA_LSTM_50.png)
![AppendAttack](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/AppendAttack.png)
![SearchAttack](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/SearchAttack.png)
![Random](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/Random.png)

### Benign datasets 
Not available in this repository - need contact each owner separately.

![Alexa1Mil](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/Alexa1Mil.png)
![AmeritaDGA_benign](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/AmeritaDGA_benign.png)
![ISP_Benign](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/ISP_Benign.png)

### DGA datasets
Not available in this repository - need contact each owner separately.

![AmeritaDGA_DGA](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/AmeritaDGA_DGA.png)
![DGA_Archive](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/DGA_Archive.png)
![ISP_DGA](https://github.com/liorsidi/Adversarial-DGA-Datasets/blob/master/unigrams_distribution/ISP_DGA.png)

## Attacks evasion performance:

| Defense | No Attack | Charbot | DeepDGA | MaskDGA |
| ------ | ------ |------ |------ |------ |
| CNN (Invincea) |  0.96 | 0.66|0.85|0.50|
| CNN (Invincea) + Distillation |  0.96|0.66|0.79|0.49 |
| CNN (Invincea) + Charbot retrain |  0.93|0.64|0.68|0.50|
| CNN (Invincea) + DeepDGA retrain | 0.92|0.60|0.97|0.51|
| CNN (Invincea) + MaskDGA retrain | 0.92|0.62|0.72|0.95|
| Helix (AE Embeddings + KNN) |  0.87|0.65|0.79|0.73|

Architecture for Helix is available at: https://github.com/liorsidi/Helix
