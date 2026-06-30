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

# Implementare
Inainte de a incepe proiectul, am facut o recapitulare a notiunilor studiate la CID si am urmarit videoclipurile 
din ECE 3300.

Am inceput prin a defini semnalele de intrare pentru contorul de 16 biti, ce vor fi sincronizate
dupa frontul pozitiv de ceas (clk) pentru o funtionare corecta si precisa
-inc (butonul pentru incrementare)
-dec (butonul pentru decrementare)
-reset ( butonul pentru reset)
precum si cele de iesire 
-out[15:0] ( 16 led-uri , un led reprezentand un bit al valorii contorului)
-value[15:0] (registru ce retine valoarea curenta si afisata pe leduri)

Am realizat un debouncer pentru fiecare buton deoarece butoanele produc oscilatii ale semnalului ce pot fi interpretate 
ca apasare repetata ( ECE3300:55 ).

A fost necesara adaugarea modului edge_det. Acesta transforma apasarea unui buton 
intr-un impuls de exact un ciclu de ceas prin detectarea frontului crescator.



Am inceput sa schitez o schema a FSM-ului ce ar putea realiza operatiile de incrementare ,decrementare si reset:
<img width="653" height="410" alt="image" src="https://github.com/user-attachments/assets/5675a09a-66a8-4fff-ba89-3a4f7396f295" />




Probleme aparute:

1.Daca incrementez un numar maxim,trebuie sa se reseteze 

2.Daca decrementez 0 sa rezulte numarul maxim

Aceste aspecte le-am studiat, intelegand acum notiunea de overflow.

3.Ce se intampla daca tin apasat un buton? - m-am documentat despre implementarea
unui edge detector

