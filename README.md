# Zahid_LWC_Thesis

This repository uses X3DH protocol for asymmetric encryption and Ascon for symmetric encryption. The X3DH protocol uses NIST SECP curves instead of the original ED25519 curves because of the variety of SHA versions that can be used. 

Requirements to run this repo:
1. Machine running any Linux distro
2. K3s installed
3. Docker installed (Docker buildx installed)

Clone this repository into your local machine:
1. bash create-deployment.sh
2. RUN kubectl get pods
3. RUN kubectl logs pod_name
4. See output

