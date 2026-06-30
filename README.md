# Tema---Contor_Binar
Proiect FPGA — Contor Binar cu 3 Butoane  

Cerințele proiectului:
Implementați pe placa de dezvoltare FPGA un contor binar pe 16 biți, afișat pe 16 LED-uri, controlat prin
3 butoane:

• Buton 1 — Incrementare: la fiecare apăsare, valoarea binară afișată pe LED-uri se incrementează
cu 1.

• Buton 2 — Decrementare: la fiecare apăsare, valoarea binară afișată pe LED-uri se decrementează
cu 1.

• Buton 3 — Reset: readuce valoarea contorului la 0 (toate LED-urile stinse).

Inainte de a incepe proiectul, am facut o recapitulare a notiunilor studiate la CID si am urmarit videoclipurile 

Am inceput sa schitez o schema a FSM-ului ce ar putea realiza operatiile de incrementare ,decrementare si reset:
<img width="653" height="410" alt="image" src="https://github.com/user-attachments/assets/5675a09a-66a8-4fff-ba89-3a4f7396f295" />

Am realizat un debouncer pentru fiecare buton de inc, dec si reset deoarece butoanele produc oscilatii ale semnalului ce pot fi intertpretate 
gresit.


Probleme aparute:

1.Daca incrementez un numar maxim,trebuie sa se reseteze 

2.Daca decrementez 0 sa rezulte numarul maxim

Aceste aspecte le-am studiat, intelegand acum notiunea de overflow.

3.Ce se intampla daca tin apasat un buton? - m-am documentat despre implementarea
unui edge detector

