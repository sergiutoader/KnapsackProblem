Titlul proiectului: Paralelizarea unui algoritm genetic pentru problema rucsacului 

Scurta descriere: 
  In cadrul acestui proiect, vom paraleliza folosind MPI si OpenMP un paralel genetic folosit pentru a rezolva problema rucsacului (Knapsack Problem). 
  Vom incerca sa rezolvam varianta 0-1 a problemei rucsacului. Acesta este un exemplu clasic de problema de optimizare care se poate reprezenta facil ca un algoritm   genetic. In problema rucsacului, se da o multime de obiecte definite printr-o greutate si un profit, precum si un rucsac care poate sustine o greutate maxima       data. Scopul problemei este de a gasi combinat,a de obiecte care pot fi adaugate ın rucsac fara a depasi greutatea maxima a acestuia, si care aduc profit maxim.     In cazul variantei 0-1 a acestei probleme, se presupune ca putem plasa maxim un singur obiect de un anumit tip in rucsac. 

Implementarea folosind algoritmi genetici: 

- Reprezentarea unui individ si generatia initiala 
    Un individ este format dintr-un numar de cromozomi egal cu numarul de obiecte care pot fi adaugate in rucsac, cromozomul i avand valoarea 1 daca obiectul cu         indexul i se afla in rucsac, sau 0 altfel. Setul initial de indivizi poate fi generat aleator, dar o varianta mai eficienta ar putea presupune ca acesta este       format din toti indivizii care contin cate un singur obiect in rucsac. Astfel, daca exista N obiecte care pot fi pusein rucsac, vor exista N indivizi in             generatia initiala, fiecare din ei avand un singur cromozom cu valoarea 1, si restul 0. 

- Selectia
    Functia de fitness se poate calcula ca suma profiturilor obiectelor din rucsac, adica a obiectelor corespunzatoare cromozomilor cu valoarea 1 ai unui individ.       Daca greutatea obiectelor din sac depaseste greutatea maxima permisa, functia de fitness va avea valoarea 0. 
    Vom considera primii 30% din indivizii din generatia curenta (din punct de vedere al functiei de fitness) vor fi pastrati si la generatia urmatoare. 

- Crossover
    In cadrul rezolvarii problemei rucsacului din aceasta tema, vom folosi crossover intr-un punct pentru a genera cate doi copii din cate doi parinti. 

- Mutatia
    In cadrul proiectului, vom utiliza doua variante de mutatie bit string. Prima varianta se va aplica pe primii 20% din indivizii generatiei curente (ordonati         dupa valorile functiei de fitness) si presupune inversarea primilor 40% din cromozomii unui individ cu un pas pentru indivizii cu index par, respectiv               inversarea ultimilor 80% din cromozomii unui individ pentru indivizii cu index impar, cu acelasi pas. 
    A doua varianta de mutatie bit string se aplica pe urmatorii 20% din indivizii generatiei curente si presupune inversarea tuturor cromozomilor unui individ, cu     acelasi pas. 

- Terminarea
    Pentru a pastra determinismul rularii algoritmului, programul se va termina dupa un numar fix de generatii dat ca input la rulare. 



Echipa este formata din: 

• Onea Roxana-Diana, 343C4

• Toader Sergiu-Cristian, 344C1

Nume asistent: Cosmin-Gabriel Samoila
