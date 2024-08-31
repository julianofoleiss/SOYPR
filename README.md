# SOYPR - Soybean Seed Defect Classification Database

Each fold contains images from seeds that were collected from the same region.

The filename format is XXXX_YYYY_ZZZZ_WWWW.png, where:

* XXXX is the defect id (0001 is intact, 0002 is cercospora, 0003 is greenish, 0004 is mechanical damage, 0005 is bug laceration, 0006 is dirty, 0007 is humidity damage)

* YYYY is the tray id

* ZZZZ is the number of the seed within the tray

* WWWW is the number of the image for that seed. There are three images per seed, so WWWW is 0001, 0002 or 0003.

# Baseline Results

## Classification of Seed Defect Type

The best F1-score without region-aware partitioning was 95.89% (+-0.3). In this case, seeds from the same regions were allowed to be in both training and testing sets. When enforcing region-aware partitioning, we achieved 85.06% (+-5). Both results were obtained with Vit-Base features and a SVM tuned with the RBF kernel. In both cases, we used three images per seed to make a final decision with the product rule. Without the fusion, considering each image from the each seed independently, the F1-score with region-aware partitioning was 74.74% (+-0.8).

## Intact vs Defective Seeds

The best result with region-aware partitioning was 99.32% (+-0.2) using Vit-Base features and a SVM tuned with the RBM kernel, making a final decision with the product rule. When each image from each seed was independently classified, the F1-score was 97% (+-0.8).

# Citation

If you use this dataset in research, please cite this paper:

'''
@INPROCEEDINGS {bertolini2024,
    author    = "Gabriel Mariano Lobato Pereira and Juliano Henrique Foleis and Alceu de Souza Britto Jr and Diego Bertolini",
    title     = "A Database for Soybean Seed Classification",
    booktitle = "Proceedings of the 37th SIBGRAPI - Conference on Graphics, Patterns and Images",
    year      = "2024",
    address   = "Manaus, Brazil",
    month     = "sep",
    publisher = "IEEE"
}
'''


