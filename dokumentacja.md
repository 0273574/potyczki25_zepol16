Po pierwsze da się zauwazyc ze wersja ranchera nie jest aktualna więc ją zaktualizowaliśmy.

## Misja 1
Utworzenie projektu "szk-server"
![image](https://github.com/user-attachments/assets/f89adae4-5cfa-4ea1-aae0-cee90a7eb7a3)


Utworzenie namespace'u "ogloszenia-krytyczne"
![image](https://github.com/user-attachments/assets/30d448af-36d7-46a2-a77d-24f26183207e)


Tworzenie deploymentu z kontenerem nginx w najnowszej wersji, zwiększenie liczby kontenerow nginx
![image](https://github.com/user-attachments/assets/00fefbb4-a198-4793-b8ba-f5d2b3e0447c)

Użycie loadbalancera w celu umożliwienia odwołania się do usługi oraz zapewnieniu wysokiej dostepnosci suług
![image](https://github.com/user-attachments/assets/60807293-020e-483d-9341-6059ffed84c4)


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
![Screenshot 2025-05-16 at 12 45 27](https://github.com/user-attachments/assets/a8d7f42e-2fab-4827-9edd-ad57ec698bf8)

Ilośc podatności na wcześniejszej wersji rke2 -> 
  Znane podatności (CVE) dla RKE2 1.24.17+rke2r1
Według bazy CVE Details, wersja 1.24.17+rke2r1 posiada co najmniej jedną znaną podatność (CVE-2023-32186), która umożliwia atak typu Denial of Service na serwery RKE2. Szczegóły i zalecenia dotyczące zabezpieczenia klastra przed tą podatnością opisano w oficjalnych notatkach wydania RKE2.


Dodatkowo, w ekosystemie Kubernetes w wersjach poniżej 1.24.17 (czyli także w 1.24.17, jeśli nie zawiera backportu) występowały poważne luki dotyczące Kubelet na Windows (CVE-2023-3676, CVE-2023-3893, CVE-2023-3955), które pozwalały na zdalne wykonanie kodu z uprawnieniami SYSTEM oraz eskalację uprawnień. Wersja 1.24.17 jest już wolna od tych konkretnych podatności, ale wcześniejsze buildy były podatne.

Ilośc podatno
## Misja 5
![Screenshot 2025-05-16 at 12 34 12](https://github.com/user-attachments/assets/a4f0d076-95f0-446b-845a-b87d3e0ad339)
![Screenshot 2025-05-16 at 12 43 34](https://github.com/user-attachments/assets/42542068-d126-44f5-95ab-413e8057f6bc)

## Misja 6
Zostal zuploadowany yaml, z automatu nie ma stworzonego serwisu, więc jest odcięta jakakolwiek komunikacja.

## Misja 7

W pliku yaml znajduje się niepoprawna ścieżka  
    volumeMounts:
    - name: config-volume
      mountPath: /etc/konfiguracja

## Misja 8
Utworzenie rapid-response-agent
![image](https://github.com/user-attachments/assets/1aa736ab-39ad-4df8-9873-6811cc339609)

(klastr potyczki przestał odmawiać posłuszeństwa w tyn momencie)

dodanie do klastra rapid agenta
![image](https://github.com/user-attachments/assets/bc45cc8f-393e-41dc-a411-d7ad738a150f)

potem w zakładce project membership dodanie go do projekto "szk-server" w trybie read-only

utworzenie roli log-reader z opisanymi parametrami 

![image](https://github.com/user-attachments/assets/3604dc49-bf2b-4dc8-855b-a0b130e474b2)

