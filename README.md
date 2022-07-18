# noise_and_perturbation
CIFAR10 데이터셋에 Negative noise, Gaussian Noise, Gaussian blur, Salt and Pepper noise를 추가하는 방법과,
Adversarial attack 기법 중 FGSM (Fast gradient Signed Method) 기법으로 Adversarial example을 생성하는 방법을 구현하였다.

각 noise의 세기에 따라 딥러닝 모델(Resnet18)의 정확도가 얼마나 감소하는지를 확인하였다.

특히, 기존의 one-hot encoding 방법과 
논문 "Construction of Error Correcting Output Codes for Robust Deep Neural Networks Based on Label Grouping Scheme"에서 제시한 multi-hot encoding 방법이
노이즈의 세기에 얼마나 강인한지를 측정하였다.

DataSample/NoisyData.ipynb : 각종 노이즈를 생성하고 생성된 노이즈를 표시한다.
DataSample/FGSM.ipynb : 학습된 모델를 공격하는 FGSM 이미지를 생성하고 생성된 이미지를 표시한다.
Resnet18(OneHotEncoding).ipynb : 기존의 one-hot encoding 기법으로 Resnet18을 학습하고 학습된 모델을 TrainedModel/Resnet18(OneHotEncoding).pt로 저장
Resnet18(ECOC).ipynb : 논문에서 제시한 ECOC 기반 multi-hot encoding 기법으로 Resnet18을 학습하고 학습된 모델을 TrainedModel/Resnet18(ECOC).pt로 저장
Accuracy(OneHotEncoding).ipynb : 각 노이즈의 세기에 따른 모델의 정확도를 측정한 다음 그 결과를 result 폴더에 저장
Accuracy(ECOC).ipynb : 각 노이즈의 세기에 따른 모델의 정확도를 측정한 다음 그 결과를 result 폴더에 저장
result.ipynb : 각 노이즈의 세기에 따른 두 기법으로 학습된 모델의 정확도 변화를 비교하는 그래프를 표시
