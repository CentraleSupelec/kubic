---
hide:
  - navigation
---

# Kubic - Kubernetes Infrastructure as Code

## Présentation

CentraleSupélec a basculé une partie de ses applications web sur une infrastructure Kubernetes chez un cloud provider (OVHCloud) en 2020, s’inscrivant ainsi dans la doctrine “[Cloud au centre](https://www.numerique.gouv.fr/services/cloud/doctrine/)” de l’état.

Il a fallu itérer au fil des projets car l’écosystème Kubernetes est vaste et évolue rapidement.

C’est pourquoi CentraleSupélec a développé Kubic et vous le propose en opensource :

- Il s’installe en 15 minutes
- Il s’appuie sur les services d’un cloud provider (OVHCloud ou Scaleway)
- Il vous facilite les montées de version

<br>

Kubic apporte les composants essentiels au bon fonctionnement du cluster :

- Un ingress controller : [Ingress-Nginx](https://kubernetes.github.io/ingress-nginx/)
- Un gestionnaire de certificats : [cert-manager](https://cert-manager.io/)
- Une stack de monitoring : [Prometheus](https://prometheus.io/) / [Grafana](https://grafana.com/)
- Un outil de déploiement continu : [ArgoCD](https://argo-cd.readthedocs.io/en/stable/)
- Un gestionnaire de secrets : [HashiCorp Vault](https://www.vaultproject.io/) et son [plugin ArgoCD](https://argocd-vault-plugin.readthedocs.io/en/stable/)
- Une solution de backups : [Velero](https://velero.io/)

Ce projet prend la forme d’une description Terraform, permettant d’appeler les API des cloud providers pour instancier un cluster kubernetes managé, puis d’y installer automatiquement via Helm les dépendances listées ci-dessus. Nous proposons aussi une documentation concise sur les différents cas d’usage de base (multi-tenant sur ArgoCD ou Vault, automatisation des backups, etc.)

La description du cluster étant totalement _as code_, cela offre la possibilité de redéployer son infrastructure sur un nouveau cluster afin par exemple d’y tester une montée de version ou réaliser un PRA.

Et comme la configuration est standardisée grâce à Terraform et Helm, elle ouvre également la possibilité de mutualiser les expertises et les bonnes pratiques entre les différents utilisateurs du projet.

La documentation de Kubic est disponible en ligne : <https://openfun.github.io/kubic/>, et le code source sur le Github de France Université Numérique : <https://github.com/openfun/kubic/>

## Webinaire DINUM

CentraleSupélec a présenté Kubic à l'un des webinaires organisés par la DINUM. Le support [est disponible au téléchargement](pdf/Kubic - Webinaire DINUM.pdf), et le replay visible [à ce lien](https://bbb-dinum-scalelite.visio.education.fr/playback/presentation/2.3/26f6fa253cf483b89bcb8a3c8b41ddbfab504abd-1695289280656), ou ci-dessous :

<iframe src="https://bbb-dinum-scalelite.visio.education.fr/playback/presentation/2.3/26f6fa253cf483b89bcb8a3c8b41ddbfab504abd-1695289280656" allowfullscreen style="width:100%; height:500px"></iframe>

## Carte Github

<p align="center">
    <a href="https://github.com/openfun/kubic"><img alt="Readme Card" src="https://github-readme-stats.vercel.app/api/pin/?username=openfun&repo=kubic" /></a>
</p>
