---
title: Report di leasing cespite
description: Questo argomento elenca e descrive brevemente i report disponibili in Leasing cespite.
author: moaamer
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-27
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 085027c5cc823beec99779791ff471dceb4ec8fe
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814106"
---
# <a name="asset-leasing-reports"></a>Report di leasing cespite

[!include [banner](../includes/banner.md)]

Questo argomento elenca e descrive brevemente i report disponibili in Leasing cespite. La maggior parte dei rapporti viene visualizzata completando questi passaggi o passaggi molto simili, come indicato. 

- Per visualizzare la maggior parte dei report sui leasing di cespiti, vai a **Leasing cespiti > Richieste di informazioni e report > Report di leasing** e quindi seleziona un report da visualizzare. Per i report che richiedono un percorso di selezione diverso, i passaggi per aprire il report sono inclusi nella descrizione di quel report. 
- Quando si seleziona un report da stampare, si apre una pagina dei parametri che consente di filtrare le informazioni incluse nel report. Immetti i criteri di filtro e quindi seleziona **OK** per generare il report. Il report generato mostrerà le informazioni che rientrano nei filtri specificati.

## <a name="asset-movement"></a>Movimento cespite
Il report sul movimento del cespite funge da rapporto di rollforward per i saldi degli Asset Right of use per ogni leasing. Questo report consente di visualizzare le transazioni di asset di un leasing durante un periodo specificato. In questo report sono inclusi i seguenti campi. 

|     Campi del report                  |     Descrizione                                                                |
|------------------------------------|--------------------------------------------------------------------------------|
|     Data di inizio              |     La data di inizio della prima versione del leasing.                     |   
|     Termine del leasing                     |     Il termine del leasing della prima versione del leasing.                            |
|     Leasing a breve termine               |     Se il leasing è classificato come leasing a breve termine verrà visualizzato come **Sì**.         |
|     Leasing a valore basso                |     Se il leasing è classificato come leasing a valore basso verrà visualizzato come **Sì**.          |
|     Asset Right of use iniziale     |     Il valore originale dell'Asset Right of use dalla scrittura contabile di rilevazione iniziale.      |
|     Saldo iniziale              |     Il valore netto contabile dell'Asset Right of use alla **Data di inizio**.                         |
|     Spesa di ammortamento periodo    |     L'importo delle spese di ammortamento prese entro l'intervallo di date definito per il report.        |
|     Fondo di ammortamento       |     L'importo dell'ammortamento accumulato a partire dalla **Data di inizio**.                               |
|     Svalutazione                     |     L'importo dell'asset è stato ridotto entro l'intervallo di date definito per il report.               |
|     Modifiche                  |     L'importo delle rettifiche all'Asset Right of use tra i parametri di data.                            |
|     Valore contabile netto                 |     Il valore contabile netto finale dell'Asset Right of use, che è il netto dell'ammortamento accumulato a partire dalla **Data finale**.    |

## <a name="differences-report"></a>Report differenze
Il report sulle differenze mostra le differenze tra le informazioni caricate nel framework di importazione del leasing e le informazioni attualmente nel sistema. Ciò consente di confrontare cosa è stato rettificato, aggiornato o aggiunto tramite il framework di importazione in leasing.  

I valori nel report variano in base al leasing selezionato. Il report mostrerà solo i campi che differiscono da ciò che è attualmente nel sistema e da ciò che è nelle tabelle di staging. Il vecchio valore è ciò che è attualmente nel sistema o ciò che era precedentemente nel sistema, a seconda che il processo di importazione sia stato eseguito. Il nuovo valore mostra il valore che si trova nella tabella di staging che sostituirà il vecchio valore.

## <a name="five-years-undiscounted-payment-forecast"></a>Previsione pagamento non scontato cinque anni
Il report Previsione pagamento non scontato cinque anni mostra i pagamenti previsti per leasing non scontati da pagare nei prossimi cinque anni dalla data specificata nei parametri del report. In questo report sono inclusi i seguenti campi. 

|     Campi del report         |     Descrizione                                                                                       |
|-------------------------- |---------------------------------------------------------------------------------------------------    |
|     Descrizione leasing     |     La descrizione del leasing dall'intestazione del leasing.                                                      |
|     ID leasing              |     ID leasing univoco.                                                                              |
|     Prenota                  |     Il libro di leasing associato all'ID libro.                                                         |
|     Classificazione        |     La classificazione del leasing.                                                                  |
|     Livello di registrazione         |     Il livello in cui viene registrato questo leasing.                                                         |
|     Valuta              |     La valuta del leasing.                                                                        |
|     Correnti               |     La somma di tutti i canoni di leasing pagabili entro i successivi 12 mesi dalla data di reporting.          |
|     13-24 mesi          |     La somma di tutti i canoni di leasing pagabili tra 13 e 24 mesi dalla data di reporting.           |
|     25-36 mesi          |     La somma di tutti i canoni di leasing pagabili tra 25 e 36 mesi dalla data di reporting.           |
|     37-48 mesi          |     La somma di tutti i canoni di leasing pagabili tra 37 e 48 mesi dalla data di reporting.           |
|     49-60 mesi          |     La somma di tutti i canoni di leasing pagabili tra 49 e 60 mesi dalla data di reporting.           |
|     Successivo            |     La somma di tutti i canoni di leasing pagabili a partire da 61 mesi dalla data di reporting.              |

## <a name="gaap-cash-flows-report"></a>Report del flusso di GAAP
Il report di divulgazione GAAP soddisfa il requisito di divulgazione US GAAP specificato in 842-20-50-4 (g) (1). Per visualizzare questo report, vai a **Leasing cespite > Richieste di informazioni e report > Divulgazioni > GAAP - Flussi di cassa**. 

|     Campi del report                                 |     Descrizione                                                                                                                                               |
|------------------------------------------------   |-----------------------------------------------------------------------------  |
|     Data di inizio <br> Data di fine                        |     Definisce un intervallo di date utilizzato per limitare le informazioni incluse nel report.      |
|     Persona giuridica                                  |     La persona giuridica associata ai leasing.                                      |
|     Tipo di leasing                                    |     La classificazione del leasing come finanziario o operativo.           |
|     ID leasing                                      |     ID leasing univoco.                                                      |
|     Descrizione leasing                             |     La descrizione del leasing dall'intestazione del leasing.                              |
|     Libro di leasing                                    |     Il libro di leasing a cui si riferisce la linea.                        |
|     Livello di registrazione                                 |     Ciascun libro collegato a un cespite viene impostato per un particolare livello di registrazione con un obiettivo di ammortamento complessivo.                          |
|     Gruppo di leasing                                   |     Gruppo cui è associato il leasing.                                     |
|     Valuta                                      |     L'abbreviazioni per la valuta della transazione utilizzata. Tutti i report convertiranno la valuta delle transazioni nella valuta di dichiarazione.                      |
|     Leasing finanziario - Flussi di cassa operativi         |     La somma dei pagamenti variabili totali registrati e dei pagamenti di interessi totali registrati dal piano di ammortamento tra i parametri di data.        |
|     Leasing finanziario - Flussi di cassa finanziari           |     La somma dei pagamenti del capitale totale dal piano di ammortamento tra i parametri di data.       |
|     Leasing operativo - Flussi di cassa operativi       |     La somma di tutti i canoni di leasing registrati e dei pagamenti variabili registrati tra i parametri di data.            |

## <a name="lease-balances-forecast"></a>Previsione saldi leasing
La previsione saldi leasing elenca le informazioni direttamente dal piano di ammortamento delle passività e dal piano di ammortamento dei cespiti. Il report mostra gli importi previsti della passività prevista per il leasing e degli Asset Right of useper un periodo di tempo, comprese tutte le spese previste per tali leasing. In questo report sono inclusi i seguenti campi.

|     Campi del report                 |     Descrizione                                                                                                                                                                               |
|---------------------------------  |--------------------------------------------------------------------------------------------------------------------   |
|     Saldo iniziale             |     Il saldo iniziale nel piano di ammortamento del leasing per il periodo contenente la data di inizio del report.            |
|     Riconoscimento iniziale           |     Se la data di inizio del leasing rientra nell'intervallo di date definito per il report, in questa colonna verrà visualizzato il valore del conto obbligazione della registrazione contabile di rilevamento iniziale.      |
|     Pagamenti                      |     La somma dei canoni del leasing che rientrano nell'intervallo di date definito per il report.                               |
|     Interessi                      |     La somma degli interessi passivi del leasing che rientrano nell'intervallo di date definito per il report.                    |
|     Saldo finale                |     Il saldo passivo del leasing a partire dalla **Data finale**.                                                             |
|     Passività a breve termine          |     L'importo della passività a breve termine nel piano di ammortamento del leasing alla **Data finale**.                           |
|     Passività a lungo termine           |     L'importo della passività a lungo termine nel piano di ammortamento del leasing alla **Data finale**.                            |
|     Valore contabile netto iniziale      |     Il "Valore contabile netto iniziale" nel piano di ammortamento del cespite del leasing per il periodo contenente la data di inizio del report      |
|     Riconoscimento iniziale           |     Se la data di inizio del leasing rientra nell'intervallo tra i parametri di data del report, in questa colonna verrà visualizzato il valore del conto cespite della registrazione contabile di rilevamento iniziale.            |
|     Spesa di ammortamento          |     La somma delle spese di ammortamento del leasing che rientrano nell'intervallo di date definito per il report.                  |
|     Saldo finale                |     Il saldo del cespite del leasing a partire dalla **Data finale**.                                                              |
|     Rettifica capitale netto             |     Il saldo iniziale meno il valore contabile netto iniziale.                                                             |

## <a name="lease-commencements-report"></a>Report di inizio del leasing
Il report di inizio leasing mostra tutti i leasing che sono iniziati entro un intervallo di date specificato, inclusa la passività iniziale e i saldi degli Asset Right of use. In questo report sono inclusi i seguenti campi. 

|     Campi del report                 |     Descrizione                                                                                       |
|---------------------------------  |---------------------------------------------------------------------------------------------------    |
|     Data di inizio             |     La data della registrazione contabile di rilevamento che è stata registrata per quella versione di leasing.         |
|     Importo passività iniziale      |     L'importo della passività dalla registrazione contabile della rilevazione iniziale.                                  |
|     Importo cespite iniziale          |     L'importo del cespite dalla registrazione contabile della rilevazione iniziale.                                      |

## <a name="lease-modification-report"></a>Rapporto di modifica del leasing
Il report di modifica del leasing mostra tutti i leasing che sono stati modificati entro un intervallo di date specificato. Il report mostra anche l'utente che ha rettificato il leasing e l'importo totale della passività rettificato. In questo report sono inclusi i seguenti campi. 

|     Campi del report                 |     Descrizione           |
|---------------------------------  |-------------------------  |
|     Rettificato da                   |     Il nome utente della persona che ha modificato il leasing.                                |
|     Data di rettifica               |     La data in cui la registrazione contabile di rettifica è stata registrata.                        |
|     Rettifiche                   |     L'importo per qualsiasi registrazione contabile di rettifica registrata nel conto passività del leasing tra i parametri di data. I crediti appariranno positivi, mentre gli addebiti saranno negativi.       |
|     Importo profitti (perdite)            |     L'importo per qualsiasi registrazione contabile di rettifica registrata nel conto profitti/perdite del leasing tra i parametri di data. I crediti appariranno positivi, mentre gli addebiti saranno negativi.       |
|     Utili non distribuiti             |     L'importo per qualsiasi registrazione contabile di rettifica registrata nel conto utili non distribuiti del leasing tra i parametri di data.      |
|     Saldo finale passività      |     Il saldo passivo risultante a partire dalla data di rettifica del leasing.           |

## <a name="lease-movement-report"></a>Report movimenti leasing
Il report di movimento del leasing funge da report di rollforward per i saldi di obbligazione sul leasing per ogni leasing. Questo report consente all'utente di visualizzare le transazioni di passività di un leasing durante un periodo specificato.

|     Campi del report             |     Descrizione                                               |
|----------------------------   |-------------------------------------------------------------- |
|     Data di inizio         |     La data di inizio della prima versione del leasing.    |
|     Termine del leasing                |     Il termine del leasing della prima versione del leasing.           |
|     Pagamenti rimanenti        |     Il numero di pagamenti che non sono stati ancora registrati per il leasing.                       |
|     Saldo iniziale         |     La somma di tutte le transazioni che incidono sulla passività del leasing avvenute prima della data di inizio del report.             |
|     Riconoscimento iniziale       |     L'importo di qualsiasi transazione di rilevazione iniziale per il leasing registrato nell'intervallo di date definito per il report.     |
|     Pagamenti                  |     La somma delle transazioni di pagamento del leasing registrate all'interno dell'intervallo di date definito per il report. I valori in questa colonna appariranno come importi negativi poiché i pagamenti diminuiscono il saldo passivo del leasing.  |
|     Interessi                  |     La somma degli interessi maturati registrati a fronte del leasing all'interno dell'intervallo di date definito per il report.            |
|     Rettifiche               |     La somma delle transazioni di rettifica registrate del leasing che rientrano nell'intervallo di date definito per il report.                               |
|     Saldo finale            |     Il saldo di tutte le transazioni di passività del leasing che sono state registrate a partire dalla **Data finale** del report.                  |

## <a name="lease-transactions-report"></a>Report transazioni di leasing
La richiesta di transazioni di leasing mostra tutte le registrazioni contabili generate dal leasing di cespite. Ciascuna registrazione contabile è collegata all'ID del libro da cui è stata originata. Ciò consente di associare facilmente la registrazione contabile al leasing corrispondente. La richiesta di informazioni sulle transazioni di leasing funziona in modo simile alla pagina **Transazioni giustificativo** in Contabilità generale.

## <a name="weighted-average-discount-rate-report"></a>Report sul tasso di sconto medio ponderato
Il report sul tasso di sconto medio ponderato soddisfa i requisiti di divulgazione dei GAAP US specificati in ASC 842-20-50-4 (g) (4) per un tasso di sconto medio ponderato. Per visualizzare questo report, vai a **Leasing cespite > Richieste di informazioni e report > Divulgazioni > Report sul tasso di sconto medio ponderato**. In questo report sono inclusi i seguenti campi. 

|     Campi del report                     |     Descrizione                                                           |
|------------------------------------   |------------------------------------------------------------------------   |
|     In data                        |     Questo report includerà tutti i leasing che sono iniziati il o prima del parametro di data **A partire da**. Questo report dovrebbe essere eseguito a partire dall'ultimo giorno del periodo da divulgare.      |
|     Persona giuridica                      |     La persona giuridica associata al leasing.                           |
|     ID leasing                          |     ID leasing univoco.                                                  |
|     Descrizione leasing                 |     La descrizione del leasing dall'intestazione del leasing.                          |
|     Prenota                              |     Il tipo di libro specifico del leasing visualizzato.                                                                                                                                            |
|     Livello di registrazione                     |     Ciascun libro collegato a un cespite viene impostato per un particolare livello di registrazione con un obiettivo di ammortamento complessivo.      |
|     Gruppo di leasing                       |     Gruppo cui appartiene il leasing.                                 |
|     Tasso di sconto                     |     Il tasso utilizzato per i canoni di leasing scontati.                             |
|     Valuta                          |     L'abbreviazioni per la valuta della transazione utilizzata. Tutti i report convertiranno la valuta delle transazioni nella valuta di dichiarazione.  |
|     Canoni di leasing rimanenti          |     L'importo totale dei canoni di leasing non pagati dal programma di pagamento rimanente dalla data **A partire da**.            |
|     Pagamenti ponderati rimanenti       |     I canoni di leasing rimanenti moltiplicati per il tasso di sconto utilizzato.   |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]