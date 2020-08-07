# Adversarial-DGA-Datasets
A collection of different adversarial attacks on Domain Generated Algorithms' (DGA) classifiers

The goal of sharing the dataset is to help the research community to come with new defense mechanism against DGA adversarial attacks.

Each attack type contains 10,000 samples for evaluation and 2,000 samples for adversarial training.

We implemented the attacks based on autohr papers or code sinppets they send us privatly.


## Attacks Data & Papers
- **DeepDGA**: Anderson, H. S., Woodbridge, J., & Filar, B. (2016, October). DeepDGA: Adversarially-tuned domain generation and detection. In Proceedings of the 2016 ACM Workshop on Artificial Intelligence and Security (pp. 13-21). ([paper](https://arxiv.org/abs/1610.01969)  / [data](https://github.com/liorsidi/Adversarial-DGA-Datasets/tree/master/DeepDGA))
- **CharBot**: Peck, J., Nie, C., Sivaguru, R., Grumer, C., Olumofin, F., Yu, B., ... & De Cock, M. (2019). CharBot: A simple and effective method for evading DGA classifiers. IEEE Access, 7, 91759-91771. ([paper](https://arxiv.org/abs/1905.01078) / [data](https://github.com/liorsidi/Adversarial-DGA-Datasets/tree/master/CharBot))
- **MaskDGA**: Sidi, L., Nadler, A., & Shabtai, A. (2019). MaskDGA: A black-box evasion technique against DGA classifiers and adversarial defenses. arXiv preprint arXiv:1902.08909. ([paper](https://arxiv.org/abs/1902.08909) / [data](https://github.com/liorsidi/Adversarial-DGA-Datasets/tree/master/MaskDGA))
- **Append**: Sequential adversarial attack that append charachers one after the other. ([data](https://github.com/liorsidi/Adversarial-DGA-Datasets/tree/master/AppendAttack))
- **Search**: An extension of MaskDGA, it keep changing charachters up untull the subsitut model prediction changes. ([data](https://github.com/liorsidi/Adversarial-DGA-Datasets/tree/master/SearchAttack))
- **Random**: Randomally change the charachters regardless the attack. ([data](https://github.com/liorsidi/Adversarial-DGA-Datasets/tree/master/RandomAttack))


## More about the MaskDGA datasets
The dataset contains multiple files for each attacker's subsitute model type (CNN/LSTM) and threshold for charachter changes (25/50/75).

Each file contains more info on the attack such as: 
- **url_original**: the original url before the attack.
- **family_name**: the original DGA family of the url.
- **url**: the url after the attack.
- **sub_model_benign_prob**: the attacker subsitute model confidence for benign.
- **maskDGA_iteration**: the model retraining phase, for evaluation use the highest value (=4).


## Comperisson of attacks charachters distribution to other datasets


## Attacks evasion performance:

| Defense | Charbot | DeepDGA | MaskDGA |
| ------ | ------ |------ |------ |
| CNN (Invincea) |  0.96 | 0.66|0.85|0.50|
| CNN (Invincea) + Distillation |  0.96|0.66|0.79|0.49 |
| CNN (Invincea) + Charbot retrain |  0.93|0.64|0.68|0.50|
| CNN (Invincea) + DeepDGA retrain | 0.92|0.60|0.97|0.51|
| CNN (Invincea) + MaskDGA retrain | 0.92|0.62|0.72|0.95|
| Helix (AE Embeddings + KNN) |  0.87|0.65|0.79|0.73|
