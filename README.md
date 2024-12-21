# adversarial-robustness

Core question to adversarial robustness is can we develop classifiers that are robust to test time perturbations of their inputs? These perturbations are caused by an adversary intent on fooling the classifier to misclassify. 
Taxonomy of adversarial attacks on the basis of threat model:
1. White box attacks - attacker has access to the model’s parameters
2. Black box attacks - attacker does not have access to model’s parameters and hence uses a different model or no model to generate adversarial examples. 
White Box attacks - 
* Fast Gradient Sign Method (FGSM) : computes an adversarial image by adding a pixel-wise perturbation of magnitude in the direction of the gradient. (I. J. Goodfellow, J. Shlens, and C. Szegedy, “Explaining and harnessing adversarial examples,” arXiv preprint arXiv:1412.6572, 2014. )

* Projected gradient descent
Iterate over gradient ascents on smaller step size and doesn’t consider constraints on amount of time and efforts. Proj{.} will project the updated adversarial sample into the epsilon neighbourhood and a valid range. 
* DeepFool [1]
* Carlini and Wagner attack [2]
* Jacobian based saliency map attack [3]
* Universal adversarial attack [4]
[1] : DeepFool: a simple and accurate method to fool deep neural networks, Moosavi-Dezfooli et al., 2016
[2] : Towards Evaluating the Robustness of Neural Networks, Carlini and Wagner, 2016
[3] : Maximal Jacobian-based Saliency Map Attack, Xu and Wiyatno, 2018
[4] : Universal adversarial perturbations, Moosavi-Dezfooli et al., 2017


<img width="392" alt="image" src="https://github.com/geetHonve/adversarial-robustness/assets/123307246/32afc5b6-ebf0-4095-ae3b-19b0b10e4ff5">

Original Image Activation (x):
   - You have an original image, let's call its activation value x. This activation value represents how the image affects a neural network or some other model.
Adversarial Image Activation (adv_x):
   - You want to create an adversarial image with a specific activation value, denoted as adv_x.
   - The goal is to make adv_x equal to R times the activation value of the original image x.
Epsilon (ε):
   - Epsilon is the degree of perturbation you introduce to the original image x to create the adversarial image adv_x.
   - Essentially, you're adding or subtracting a small amount to each pixel of the original image to change its activation value.

So, the task of this exploratory project is to find the right degree of perturbation (epsilon) to apply to the original image x so that its activation value becomes R times original activation.

* Original image - x
* Unit we are focussing on - unit
* Original image activation - x_act

* ![image](https://github.com/user-attachments/assets/a608f97d-13ff-4799-b3f4-920af7b07d1f)

* Adversarial image activation - adv_x_act
* Target ratio to reduce orig activation by - target_ratio
* Target activation - target_act = target_ratio * x_act
* Goal is : find epsilon where adv_x_act == target_act


