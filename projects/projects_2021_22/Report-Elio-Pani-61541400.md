# Open Source Contribution Project

Author: Elio Pani

NOMA: 61541400

Year: 2021

Selected project: https://github.com/pytorch/pytorch

*Pull Request :* [Pull Reaquest #43102](https://github.com/pytorch/pytorch/pull/43102)

#About the project

While working on a project, I was using a lot PyTorch, it is an open source machine learning library based on the Torch library, used for applications such as computer vision and natural language processing, primarily developed by Facebook's AI Research lab. I saw that there was an issue in the documentation when comparing it to the result I got. As I learned to use more and more Pytorch, I thought it was a good idea to learn more about it's world and the people behind. It's a highly used application so I know I would learn a lot.


# About the issue <span style='font-size:8pt;'>*(2021/09/19)*</span>

Pour de la classification d’image en utilisant plusieurs gpus (2). 
 
En deep learning par defaut les calculs sont faits avec des float32 (32 bits pour chaque nombre). Pytorch propose “AMP” (Automatic Mixed Precision) qui mixe les calculs entre float16 et float32 (Plus rapide, plus léger).

Pour plusieurs GPU tu utilises “DataParallel” de Pytorch qui permet de paralléliser les calculs sur plusieurs gpu.
AMP et DataParallel ensemble ne fonctionnent pas directement (selon la doc). Dans les faits pourtant si. Tu as donc regardé les issues reliées à ton problème et à trouver qu’en fait le code avait été mis à jour pour résoudre ce problème, mais pas la doc.

Quand j’ai voulu utiliser DataParallel avec AMP j’ai été voir dans la doc le fonctionnement et quand j’ai comparé mes logs avec les informations de la docs, je me suis rendu compte qu’elle n’était pas à jour.De plus, en creusant un peu, j’ai vu un des contributeur qui avait commenté le faite que le code avait bien été modifié mais que la doc était encore celle pour l’ancien code. Il fallait rajouter des lignes de codes pour que ça fonctionne dans la version précédente alors que le code actuel lui ne demande pas. J’ai donc modifié la doc pour qu’elle soit en accord avec ce que le code fait

# About the process 

