1.)Biblioteci folosite impreuna cu versiunile lor

NumPy version: 1.26.4
scikit-learn version: 1.5.2
scikit-image version: 0.24.0
Matplotlib version: 3.8.4
OpenCV version: 4.10.0.84
Python version: 3.9.13
pip: 22.0.4

Jupyter - 1.1.1
Jupyter-server - 2.14.2
Notebook - 7.2.2

!!!Timpul de prelucrare este intre 30 de secunde si 2 minute pe imagine (in general aproximativ 5 ore)

2.)Cum se ruleaza codul:
############## Se ruleaza #######################
A.)Tot ce are un numar
1.)Task1 si Task2:
Tot ce are un numar in nume se ruleaza in ordinea numerelor. Adica 1_obtine_rezultate.ipynb, 2_dad_result.ipynb
3_deedee_result.ipynb, 4_dexter_result.ipynb, 5_mom_result.ipynb. Notebook-urile care au nume de personaj
fac predictiile pentru persoanje, iar 1_obtine_rezultate.ipynb pentru toate fetele. Daca memoria calculatorului permite 
notebookurile pot fi rulate in paralel.
In fiecare dintre aceste notebook-uri in ultima celula exista un test_img_path='./test_daria_custom/images/'.
Acesta se schimba cu calea catre fisierul de test. In rest, nu mai trebuie facuta nicio modificare, notebook-urile se
ruleaza integral.

2.) Task-ul bonus
Notebook-ul YOLO.ipynb contine codul ce face predictiile pentru YOLO. In prima celula se afla:
test_images_dir = Path("./validare/validare/") care trebuie schimbat cu fisierul unde se afla imaginile
de test. Toate predictiile se vor gasesc in folderul 351_Pirvulescu_Daria/task1_bonus respectiv
351_Pirvulescu_Daria/task2_bonus.

############## Nu se ruleaza #######################
B.)Tot ce nu are numar
Tot ce nu are numar reprezinta procesarea de date, extragere de descriptori si antrenarea de SVC.
Acestea nu se ruleaza si sunt doar o dovada a parcurgerii etapelor proiectului.
1.)Task1 si Task2:
-extarge_patch_poz.ipynb ia pozele din fisierul de antrenare si adnotarile si grupeaza fetele decupate pe forme
 geometrice diferite (patrat, dreptunghi si dreptunghi inalt) in functie de aspect ratio.

-descriptori.ipynb alcatuieste atat descriptorii pozitivi cat si cei negativi

-antreneaza.ipynb antreneaza cele 3+12 SVC uri cu kernel rbf

2.)Task Bonus
-YOLO_prepare_data.ipynb imi scrie datele de antrenare pentru YOLO in format suportat de acesta.


*************************
Daca se vrea rularea lor:
-extarge_patch_poz.ipynb
ultima celula primele 4 randuri reprezinta path-ul catre fisierele de antrenare se va schimba corespunzator
-descriptori.ipynb
pentru descriptorii negativi se schimba celula 6 primele 4 randuri cu path-ul catre folderul de imagini de antrenare
pentru descriptorii pozitivi trebuie rulat extarge_patch_poz.ipynb  inainte
-antreneaza.ipynb
trebuie rulate cele doua de sus pentru a rula antreneaza.ipynb

-YOLO_prepare_data.ipynb
primele 2 celule comentate reprezinta prelucarea datelor de validare; eu am ales sa las doar 20 de imagini
per validare de aceea daca se ruleaza trebuie modificate functiile apelate astfel
 scrie_img_pt_YOLO->for file in files[:20]:
 scrie_labels_pt_YOLO_task2->  # if img_name=='021.jpg':     return
ultima celula comentata reprezinta trainul pe care l-am facut pe kaggle si trebuie modificat calea catre data.yaml