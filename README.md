# Filius-Router

Obiettivo: creare una rete formata con Filius da due LAN collegate da un router che possano comunicare tra loro utilizzando un computer
come DHCP server per assegnare un indirizzo ip ad un nuovo possibile host emulato in questo caso da un portatile.

Strumenti utilizzati: router, due switch, 6 computer (numero che può variare).

Conoscenze teoriche: per permettere il collegamento di più computer tra di loro, mentre il router è l'apparecchio di rete
che permette il collegamento tra due reti in quanto possiede due schede di rete (NIC). 
Ogni rete avrà un'indirizzo ip diverso, ossia un numero formato da quattro ottetti da otto bit ciascuno che serveno per identificare 
il computer all'interno delle reti. Per permettere l'assegnazione di questi indirizzi si usa il servizio DHCP che consente di decidere se 
avviene in modo statico (impostata dall'amministratore) o dinamico (metodo che assegna automaticamente gli indirizzi ip agli host).
Per comnunicare tra due reti diffrenti collegate da un router che assume la funzione di default gateway ossia la via di default per
uscire dalla rete si specifica l'ip inerente alla rete presa in esame durante la configurazione degli host. 
La simulazione della rete avverà su filius un software tedesco open-source il quale permette la costruzione di reti medie con un 
approccio meno complesso di altri pacchetti software.

Procedimento:
Come prima cosa si dispongono i componenti utilizzati e si uniscono tra di loro con i cavi. Adesso bisogna assegnare gli indirizzi ip ai vari host e porre uno 
dei computer come DHCP cliccand sul dispositivo e successivamente cliccando sull'impostazione che lo permette. Qui avremo modo d configurare varie impostazioni che saranno poi applicate, nel nostro caso, al portatile che fungerà da host collegato in maniera dinamica. Bisognerà quindi scrivere l'ip del defaul gateway e il range di ip che potrà assegnare ai vai host il nostro DHCP server. Altre impostazioni configurabili sono il DNS server e la netmask che nella prova corrente non ci interessano.
questo procedimento è stato ripetuto anche nell'altra LAN. A questo punto si entra nella parte di simulazione in cui sarà possibile notare che i cavi di collegamento della rete si illuminano mettendo in "comunicazione" i dispositivi collegati. La prima prova serve per eseguire il ping ossia la segnalazione della presenza dell'host configurato tramite DHCP in modo dinamico partendo dalla macchina che fnge da DHCP server. Questo sarà possibile scaricando virtualmente sugli host delle nostre reti la command line, ossia il prompt dei comandi da cui facciamo partire l'istruzione di ping ( ping 'ip'). A questo punto si potrà vedere come tutti i cavi della rete si illuminano, questo avviene perchè il portocollo ARP ,utilizzato dalla funzione di ping, mand in broardcast la prima colta il ping in attesa di risposta dall'host chiamato. Il messaggio in broadcast passerà e verrà diffuso dallo switch che inizierà a popolare la sua MAC table. Per comunicare con un host dell'altra rete si digita sempre sulla commmand line ping 'ip dell'altra rete'. Quello che otteniamo è la visione di righe di codice che permettono di seguire il corretto invio dei pacchetti.

Conclusione: 
Inizialmente i lping tra reti diverse non avveniva perchè era stat dimmenticato di confiurare l'ip de l defaul gateway agli host.
