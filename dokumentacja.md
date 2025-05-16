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
      mountPath: /etc/konfiguracja <- powinno się znaleźć: "/etc"

## Misja 8
Utworzenie rapid-response-agent
![image](https://github.com/user-attachments/assets/1aa736ab-39ad-4df8-9873-6811cc339609)

(klastr potyczki przestał odmawiać posłuszeństwa w tyn momencie)

dodanie do klastra rapid agenta
![image](https://github.com/user-attachments/assets/bc45cc8f-393e-41dc-a411-d7ad738a150f)

potem w zakładce project membership dodanie go do projekto "szk-server" w trybie read-only

utworzenie roli log-reader z opisanymi parametrami 

![image](https://github.com/user-attachments/assets/3604dc49-bf2b-4dc8-855b-a0b130e474b2)

## Misja Doomwar
1. nwcavoidingourlies  
2. nwlaveragingouryes  
3. nwcavertingourfear  
4. nwcavoringoutseeds  
5. nmcadvertingoreyes  
6. nwcavertingourmood  
7. nwcavertingourgaze  
8. nwcavertingourview  
9. nwcavertingourtime  
10. nwcavertingourmind  
11. nwcavertingourlife  
12. nwcavertingourhope  
13. nwcavertingourpath  
14. nwcavertingourpain  
15. nwcavertingourpast  
16. nwcavertingoursins  
17. nwcavertingourways  
18. nwcavertingourfeel  
19. nwcavertingourdebt  
20. nwcavertingourwork  
21. nwcavertingourhate  
22. nwcavertingourtone  
23. nwcavertingourvibe  
24. nwcavertingourrisk  
25. nwcavertingourluck  
26. nwcavertingourface  
27. nwcavertingourrole  
28. nwcavertingourturn  
29. nwcavertingourfear  
30. nwcavertingourview  
31. nwcavertingourzone  
32. nwcavertingourcore  
33. nwcavertingourgoal  
34. nwcavertingourneed  
35. nwcavertingoururge  
36. nwcavertingourlove  
37. nwcavertingourgift  
38. nwcavertingoururge  
39. nwcavertingourwill  
40. nwcavertingourcall  
41. nwcavertingourgods  
42. nwcavertingourdata  
43. nwcavertingourtask  
44. nwcavertingourrole  
45. nwcavertingourmove  
46. nwcavertingourplan  
47. nwcavertingourhome  
48. nwcavertingourland  
49. nwcavertingourbond  
50. nwcavertingourcrew  
51. nwcavertingourfire  
52. nwcavertingourzone  
53. nwcavertingourmask  
54. nwcavertingourview  
55. nwcavertingouredge  
56. nwcavertingourtrip  
57. nwcavertingourload  
58. nwcavertingourjobs  
59. nwcavertingoursite  
60. nwcavertingourtone  
61. nwcavertingourecho  
62. nwcavertingourlife  
63. nwcavertingourwars  
64. nwcavertingourbase  
65. nwcavertingourmaze  
66. nwcavertingourbias  
67. nwcavertingourquiz  
68. nwcavertingourbyte  
69. nwcavertingourvibe  
70. nwcavertingourfolk  
71. nwcavertingournews  
72. nwcavertingourjoke  
73. nwcavertingourluck  
74. nwcavertingourvoid  
75. nwcavertingourseed  
76. nwcavertingourtrap  
77. nwcavertingourleap  
78. nwcavertingourmark  
79. nwcavertingourspot  
80. nwcavertingourfile  
81. nwcavertingourlogs  
82. nwcavertingourfail  
83. nwcavertingourclue  
84. nwcavertingourrest  
85. nwcavertingourshot  
86. nwcavertingourcase  
87. nwcavertingourmaze  
88. nwcavertingourdark  
89. nwcavertingourpeak  
90. nwcavertingournote  
91. nwcavertingourchat  
92. nwcavertingourband  
93. nwcavertingourfear  
94. nwcavertingourhelp  
95. nwcavertingourneed  
96. nwcavertingourhope  
97. nwcavertingourturn  
98. nwcavertingourluck  
99. nwcavertingourview  
100. nwcavertingourgame  
