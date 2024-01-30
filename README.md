# Projet Web

Ce projet est un exemple de mise en place d'un service mesh avec Istio, l'intégration de microservices, et la mise en place de fonctionnalités telles que  la surveillance avec Kiali et Grafana.

## Prérequis
- **Système d'exploitation :** Windows
- **Logiciels :** Docker, Minikube, Istio

## Installation et Configuration
1. Installez Istio en suivant les instructions : https://istio.io/latest/docs/setup/getting-started/
2. Lancer Docker
3. Lancer Minikube : `minikube start`
4. Récuperez le dépot : `git clone https://github.com/charroux/servicemesh.git`
5. Se déplacer dans le répertoire servicemesh : `cd /home/servicemesh`
6. Modifier le fichier infrastruture.yaml et appliquez la configuration de l'infrastructure : `kubectl apply -f infrastructure.yaml`
7. Modifier le fichier microservices.yaml et Appliquez la configuration des microservices : `kubectl apply -f microservices.yaml`

## Utilisation
1. Accès à la passerelle Ingress avec la commande suivante : `.\ingress-forward.sh` puis `kubectl -n istio-system port-forward deployment/istio-ingressgateway 31380:8080`
2. Allez sur un navigateur web : `http://localhost:31380/myservice/`

## Surveillance
1. Pour accéder au tableau de bord Kiali : `kubectl -n istio-system port-forward deployment/kiali 20001:20001`
2. Allez sur le navigateur web : `http://localhost:20001/`

<img width="745" alt="image" src="https://github.com/BATHILYMoussa/kubernetes-minikube/assets/114112293/81cce594-03c5-42b7-ba16-a507def445a9">

# Monitoring avec Grafana
1. Pour accéder au tableau de bord Grafana : `kubectl -n istio-system port-forward deployment/grafana 3000:3000`
2. Allez sur la navigateur web : `http://localhost:3000/`

<img width="469" alt="image" src="https://github.com/BATHILYMoussa/kubernetes-minikube/assets/114112293/35f4dfb2-eb73-4d77-a414-11ea0ff765bb">



