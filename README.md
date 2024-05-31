## CV02_finalproj: Leverage Knowledge Distillation for Polyp Classification 
#### Advisors: Thao Dao, Tan-Cong Nguyen
#### Quan Le

**Topic Description:**
  - This project experiments with standard knowledge distillation techniques, proposed by Hinton et al., 2015 in Distilling the Knowledge in a Neural Network. It applies KD to increase testing accuracy on the polyp dataset (gastrointestinal endoscopy images) for the task of classifying whether a polyp is pedunculated or sessile. 
  - This implementations diverts from the original paper by using the KL divergence instead of Cross Entropy as the measure for loss between student-teacher output.

**Method**: 
  - Baseline models from torchvision.models (ResNet50 and EfficentNet B4): https://pypi.org/project/torchvision/, pre-trained on IMAGENET 1K and fine-tuned on the polyp dataset
  - Customizing the models for binary classifcation
  - Cross Entropy Loss is used as loss criteria to output a probability distribution for distilling
  - Custom Distilling Training Loop on Student Model ResNet18
  - Trained on Google Colab with GPU A100, batch_size = 64, num_worker = 8

**Result**: 
  - Distilled Resnet18 outperforms both its raw version. Rather unexpectedly, it exceeds the teacher ResNet50, portraying the regularizing effects of distillation.

**See slides for more details on results**
**The experiment cannot be replicated simply using the colab notebook, due to the data not being present on colab's VM. To replicate, extract the zip file at: https://drive.google.com/file/d/1xMHYAJ-GfjkA9Z6tf3tKa0laZfLeunWm/view?usp=drive_link to the same directory as this README. 

**Links:**
  - Github: https://github.com/qml219/CV02_finalproj
  - Colab: https://colab.research.google.com/drive/1RZKoph-gnbYn_HZfAgXKR5YxTY70eq5X?usp=sharing
  - Google Slides: https://docs.google.com/presentation/d/1vXWizKV8lCVZAvkorLxjZhbAwZ-OmJxwRXk0hGCFGGw/edit?usp=sharing
