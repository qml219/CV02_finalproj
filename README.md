# CV02_finalproj
Leverage Knowledge Distillation for Polyp Classification 

Topic Description: 
  - This project experiments with standard knowledge distillation techniques, proposed by Hinton et al., 2015 in Distilling the Knowledge in a Neural Network. It applies KD to increase testing accuracy on the polyp dataset (gastrointestinal endoscopy images) for the task of classifying whether a polyp is pedunculated or sessile. 
  - This implementations diverts from the original paper by using the KL divergence instead of Cross Entropy as the measure for loss between student-teacher output.

Method: 
  - Baseline models from torchvision.models (ResNet50 and EfficentNet B4): https://pypi.org/project/torchvision/, pre-trained on IMAGENET 1K and fine-tuned on the polyp dataset
  - Customizing the models for binary classifcation
  - Cross Entropy Loss is used as loss criteria to output a probability distribution for distilling
  - Custom Distilling Training Loop on Student Model ResNet18
  - Trained on Google Colab with GPU A100, batch_size = 64, num_worker = 8

Result: 
  - Distilled Resnet18 outperforms both its raw version. Rather unexpectedly, it exceeds the teacher ResNet50, portraying the regularizing effects of distillation.

Testing Accuracy on class 0 of raw MobileNet 0.3571%
Testing Accuracy on class 0 of student MobileNet: 0.3333%
Testing Accuracy on class 1 of raw MobileNet: 0.9777%
Testing Accuracy on class 1 of student MobileNet: 0.9860%
Testing Accuracy of raw MobileNet: 0.9125%
Testing Accuracy of student MobileNet: 0.9175%
