Po pierwsze da się zauwazyc ze wersja ranchera nie jest aktualna więc ją zaktualizowaliśmy.

## Misja 1




## Misja 3
  Dodanie repozytorium do aplikacji:
  Wybieramy cluster, przechodzimy do "Apps", wybieramy repozytoria i klikamy:
  ![Screenshot 2025-05-16 at 11 30 44](https://github.com/user-attachments/assets/08cefac9-338c-4b7c-b3dc-c60cd094ffa9)
  ![Screenshot 2025-05-16 at 11 32 09](https://github.com/user-attachments/assets/a5048d48-fe12-44f8-a00f-c2cce6188d3f)

  Dodanie gry:
  -- apps-charts i wyszukujemy tetris
![Screenshot 2025-05-16 at 11 35 22](https://github.com/user-attachments/assets/fc7617fe-4b4a-406b-aabf-ccba79b6bb6d)
i gra jest dostepna pod linkiem
https://rancher.193.187.67.113.sslip.io/k8s/clusters/c-m-fjqvk7f6/api/v1/namespaces/default/services/http:gramisja3-tetris:80/proxy/

## Misja 4
Instalacja NeuVector, za pomocą Apps na klastrze **potyczki**.
AUTOSCAN ->
![Screenshot 2025-05-16 at 12 32 45](https://github.com/user-attachments/assets/81bc4411-dda1-4c8c-b83f-d2aa1140ec24)

Logowanie sie do NeuVector ->
  NODE_PORT=$(kubectl get --namespace cattle-neuvector-system -o jsonpath="{.spec.ports[0].nodePort}" services neuvector-service-webui)
  NODE_IP=$(kubectl get nodes --namespace cattle-neuvector-system -o jsonpath="{.items[0].status.addresses[0].address}") 
  echo https://$NODE_IP:$NODE_PORT

Żadne podatnosci nie zostaly wykryte przez NeuVector, gdyz na poczatku wykonywania zadań został cały cluster zaktualizowany 
![Screenshot 2025-05-16 at 12 24 50](https://github.com/user-attachments/assets/079096c0-fa22-4c8e-aba0-d799668c9b97)

Ilośc podatności na wcześniejszej wersji rke2 -> 
  Znane podatności (CVE) dla RKE2 1.24.17+rke2r1
Według bazy CVE Details, wersja 1.24.17+rke2r1 posiada co najmniej jedną znaną podatność (CVE-2023-32186), która umożliwia atak typu Denial of Service na serwery RKE2. Szczegóły i zalecenia dotyczące zabezpieczenia klastra przed tą podatnością opisano w oficjalnych notatkach wydania RKE2.


Dodatkowo, w ekosystemie Kubernetes w wersjach poniżej 1.24.17 (czyli także w 1.24.17, jeśli nie zawiera backportu) występowały poważne luki dotyczące Kubelet na Windows (CVE-2023-3676, CVE-2023-3893, CVE-2023-3955), które pozwalały na zdalne wykonanie kodu z uprawnieniami SYSTEM oraz eskalację uprawnień. Wersja 1.24.17 jest już wolna od tych konkretnych podatności, ale wcześniejsze buildy były podatne.

Ilośc podatno
## Misja 5
Rozwiązanie ollamy z najwyższą wersją podatności to ollama/ollama:0.1.1, zawiera ono 40 różnych podatności bezpieczeństwa
![Screenshot 2025-05-16 at 12 34 12](https://github.com/user-attachments/assets/a4f0d076-95f0-446b-845a-b87d3e0ad339)

