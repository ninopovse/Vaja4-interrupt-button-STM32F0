# Vaja4-interrupt-button-STM32F0

# 3. PROGRAMIRANJE V SW4:

b) Glede na vašo razvojno ploščo in razširitveno vezje s tipkami, izberite ustrezen digitalni vhod kot interrupt (GPIO_EXT...) in izhod za zeleno LED. Zapišite izbrana pina:
   Digitalni vhod kot interrupt(GPIO_EXT): PA0
   Izhod za zeleno LED: PC9

d) Znotraj te funkcije zapišite ukaz za vklop/izklop zelene LED (pomagajte si z metodo toggle):
   HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_9 );

e) Znotraj iste funkcije dodajte še zakasnitev, ki je potrebna, ko uporabimo mehanska tipkala/stikala: for(uint32_t i=0; i<10000; i++);
   Koliko znaša (v mili sekundah) zapisana zakasnitev? 500ms

f) V user code begin 3 - zanka while(1) - zapišite ukaz za utripanje modre LED (metoda toggle):
   HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_8 );

g) V to zanko dodajte ukaz za zakasnitev z funkcijo Delay iz knjižnice HAL, in sicer pol sekunde:
   HAL_Delay(500);

# 4. NALOŽITEV KODE IN OPAZOVANJE DELOVANJA NA STM32F0

b) Opazujte delovanje (utripanje modre LED). Kaj se zgodi, ko pritisnemo na modro tipko na STM32F0?
   Ko pritisnemo tipko se prižge zelena LED, modra LED pa še vedno neprestano utripa.

c) Ali pritisk na modro tipko vpliva na utripanje modre LED in zakaj?
   Ne, pritisk na modro tipko ne vpliva na utripanje modre LED, zato ker pritisk tipke ni povezan z modro LED.
   
   
Mikroprocesor je sporgramiran tako, da se ob pritisku modre tipke na STM32F0 prižge/ugasne zelena LED. Modra LED pa vedno utripa.    
   
