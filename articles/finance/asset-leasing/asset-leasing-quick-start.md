---
title: Attività iniziali per il leasing di cespiti
description: Questo argomento descrive la funzionalità Leasing di cespiti, illustra i passaggi per la creazione di un leasing di cespiti e visualizza le informazioni per tali leasing.
author: moaamer
manager: Ann Beebe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-09-24
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b4f1bdf74dc5319f0b3ba145969b064ad33d5010
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229600"
---
# <a name="asset-leasing-get-started"></a>Attività iniziali per il leasing di cespiti

[!include [banner](../includes/banner.md)]

Questo argomento descrive la funzionalità Leasing di cespiti, illustra i passaggi per la creazione di un leasing di cespiti e visualizza le informazioni per tali leasing. Definisce anche la terminologia utilizzata nell'interfaccia utente e nella documentazione. Leasing di cespiti è una funzionalità avanzata per la gestione, il monitoraggio e l'automazione di transazioni finanziarie per cespiti in leasing in Microsoft Dynamics 365 Finance. Leasing di cespiti è conforme agli standard contabili internazionali (IFRS 16) e agli standard GAAP statunitensi (ASC 842). Leasing di cespiti acquisisce ed elabora informazioni sui leasing e consente la generazione di scritture contabili durante il ciclo di vita del leasing, dalla rilevazione iniziale alle scritture contabili mensili fino alla riduzione del valore e alla risoluzione del leasing. Leasing di cespiti si integra perfettamente con altri componenti di Dynamics 365 Finance, tra cui Cespiti, Contabilità fornitori e Contabilità generale.

Per ulteriori informazioni sugli standard contabili, consulta la documentazione di IFRS 16 e US GAAP ASC 842.

## <a name="asset-leasing-elements"></a>Elementi di leasing di cespiti
Il diagramma seguente mostra gli elementi principali del processo aziendale per i leasing.

[![Elementi di leasing di cespiti](./media/overview-01.png)](./media/overview-01.png)

Un cespite in leasing contiene i seguenti componenti principali:

- **Contratto di leasing** - Il locatore possiede il cespite e concorda con il conduttore cedere in leasing un cespite per un periodo specifico in cambio di canoni di leasing periodici. Oltre al contratto legale tra il locatore e il conduttore, il contratto di leasing acquisisce decisioni gestionali come la probabilità di esercitare un'opzione di rinnovo e il trasferimento della proprietà.

- **Calcolo e classificazione del leasing per standard contabile** - Il calcolo e la classificazione del leasing identificano lo standard contabile che sarà applicato nella valutazione iniziale e successiva, nonché il test di classificazione che determina quale sarà la tipologia del leasing. Un leasing può essere un leasing finanziario, un leasing operativo, un leasing a breve termine o un leasing a valore basso. Il sistema calcola inoltre il valore attuale dei canoni di leasing minimi futuri ai fini della valutazione e della classificazione.

- **Transazioni di leasing** - Il leasing di cespiti supporta la rilevazione iniziale dell'asset Right of use per leasing nello stato patrimoniale, nonché la successiva valutazione sia per i leasing in bilancio che fuori bilancio. La transazione di rilevazione iniziale misura il valore attuale dei canoni di leasing minimi futuri. Questi dati vengono utilizzati per determinare il valore dell'asset Right of use e dell'obbligazione sul leasing, che influiscono sullo stato patrimoniale dell'organizzazione. La successiva valutazione delle transazioni di leasing mensili comporta l'accumulo di interessi sull'obbligazione sul leasing, che aumenta tale obbligazione. Valuta anche l'accumulo dei canoni di leasing che riducono l'obbligazione sul leasing e che saranno successivamente corrisposti al locatore. La valutazione include anche l'ammortamento dell'asset Right of use.

  Per i leasing fuori bilancio, il sistema calcola il costo del leasing a quote costanti sul valore meno elevato: la vita economica del cespite o il termine del leasing. Le rettifiche del leasing misurano le modifiche del contratto come l'estensione o l'espansione del leasing e la transazione di riduzione di valore che utilizza l'asset Right of use per costi non recuperabili.

  Il leasing di asset si integra con la contabilità generale per garantire che tutte le transazioni di leasing registrate aggiornino il piano dei conti. Il leasing di cespiti si integra con la contabilità fornitori per tenere traccia delle fatture del locatore in Contabilità fornitori e dedurne i pagamenti futuri. L'integrazione con Cespiti consente di tenere traccia dei leasing nel registro delle immobilizzazioni e di registrare le transazioni asset Right of use, inclusi la rilevazione iniziale, l'ammortamento e la riduzione di valore del cespite in Cespiti.   

## <a name="asset-leasing-components"></a>Componenti del leasing di cespiti 
Il leasing di cespiti mappa le informazioni sul leasing, gli scadenziari pagamento, le date di inizio e fine e la frequenza dei pagamenti. Inoltre, automatizza i calcoli per il valore attuale, i canoni di leasing mensili, gli interessi e l'ammortamento del leasing. Il sistema esegue test di classificazione dei leasing, a seconda della configurazione. Il sistema crea e registra anche le transazioni di leasing corrispondenti, che si basano sul framework definito dallo standard contabile che stai seguendo.

Il diagramma seguente mostra il libro di leasing, il leasing, lo scadenziario pagamenti calcolato, i test di classificazione per leasing e libri di leasing e le relative transazioni contabili.

[![Leasing, libro di leasing e scadenziario pagamento](./media/overview-02.png)](./media/overview-02.png)

- **Libro di leasing** - Il libro di leasing include tutte le informazioni sui contratti di leasing come i termini del leasing, il valore equo e i canoni di leasing. Include anche lo standard contabile che stai seguendo, il tipo di leasing e le soglie considerate nel test di classificazione del leasing. Il libro di leasing contiene anche le transazioni di leasing registrate nella contabilità generale. 
  
- **Leasing** - Il leasing contiene le informazioni sul leasing di cespiti che rappresentano le fondamenta del leasing di cespiti. L'origine delle informazioni sul leasing è il contratto di leasing e la decisione gestionale, che vengono eseguiti al di fuori di Dynamics 365 Finance. Il valore equo del cespite è il prezzo che sarebbe pagato per un cespite in una transazione alla data di valutazione. Questo valore potrebbe dipendere dal tipo di cespite, dalle condizioni di mercato e da altri criteri che possono essere presi in considerazione nella valutazione. Il valore equo del cespite sarà preso in considerazione nell'equazione del test di classificazione.

- **Vita utile del cespite** - Rappresenta i periodi rimanenti della vita utile di un cespite, dalla data di inizio del leasing. La vita utile di un cespite sarà preso in considerazione nell'equazione del test di classificazione. Differisce dalla vita utile definita in Cespiti.

- **Tasso incrementale di prestito** - Questo è il tasso di interesse che verrà utilizzato per calcolare il valore attuale. Il sistema utilizzerà il tasso implicito se definito nei dati del leasing per calcolare il valore attuale dei canoni di leasing. Se il tasso implicito non è definito, il sistema utilizzerà il tasso incrementale di prestito.

- **Tipo di annualità** - Si tratta del canone di leasing dovuto all'inizio del periodo di pagamento o alla fine del periodo. Può essere un pagamento anticipato o una annualità dovuta (all'inizio del periodo di pagamento del leasing) o un'annualità ordinaria (alla fine del periodo di pagamento del leasing).

  Il primo mese sarà considerato come il periodo numero zero per il pagamento anticipato; il primo mese sarà considerato come il periodo uno per gli arretrati di pagamento.

- **Intervallo interessi composti** - Rappresenta il numero di periodi in cui gli interessi sono accumulati per anno. Può essere mensile (12 periodi all'anno), trimestrale (4 periodi all'anno), semestrale (2 periodi all'anno) o annuale (1 periodo all'anno). Il numero di periodi sarà considerato nel calcolo del valore attuale.

- **Data di inizio** - La data in cui il locatore rende il cespite disponibile per l'uso da parte del conduttore. Tutti i calcoli e le transazioni di leasing saranno basati sulla data di inizio. La data di inizio dovrebbe essere all'inizio di un periodo (primo del mese) per garantire l'accuratezza dei calcoli successivi. Puoi usare il campo **Data della firma del contratto** per inserire la data effettiva in cui è stato firmato il contratto.

- **Termine del leasing** - La durata del periodo di leasing in mesi.

> [!NOTE] 
> La definizione del termine del leasing si basa sul numero di periodi, o intervalli, nelle righe dello scadenzario pagamenti. Il numero di intervalli definito verrà convertito in mesi.

- **Riga scadenziario pagamenti** - Acquisisce i pagamenti dei canoni di leasing per periodo. Specifica inoltre se un periodo di rinnovo sarà esercitato e incluso nella valutazione iniziale dell'asset Right of use e dell'obbligazione sul leasing. Puoi definire la data di inizio dei pagamenti dovuti per il leasing e gli intervalli di periodo che rappresentano la durata del leasing, che possono essere giorni, mesi o anni.

- **Frequenza pagamenti** - Indica se il pagamento è mensile, trimestrale, semestrale o annuale. La data di fine viene calcolata automaticamente in base alla data di inizio e al numero di periodi immessi.

- **Scadenziario pagamenti** - È il valore attuale calcolato, sulla base del periodo di tempo coperto dai canoni di leasing, l'importo dei pagamenti, i periodi di interessi composti e il tipo di annualità.

- **Periodi** - Sono i periodi di leasing che riflettono il tipo di interessi composti interni e di annualità. L'intervallo di interessi composti determina come verranno suddivisi i periodi. Puoi impostare i seguenti intervalli di interessi composti:

  - Mensile, 12 periodi all'anno
  - Trimestrale, 4 periodi all'anno
  - Semi-annuale, 2 periodi all'anno
  - Annuale, 1 periodo all'anno

Il primo periodo inizierà con il periodo zero, se il tipo di annualità è Annualità dovuta. Altrimenti il primo periodo inizierà con uno, se il tipo di annualità è Arretrati di pagamento.

- **Mesi** - Indica il numero di mesi di calendario per la durata del leasing. L'importo del pagamento è l'importo dovuto come definito in Frequenza pagamenti. Il valore attuale calcolato è il canone di leasing basato sul valore attuale per periodo, gli intervalli di interessi composti e il tasso incrementale di prestito.

> [!NOTE] 
> Il valore attuale è calcolato sulla base dell'equazione del flusso di cassa scontato.

- **Libri** - È la configurazione preconfigurata che verrà associata a ogni leasing. Il libro definisce lo standard contabile applicato, i tipi di leasing e la soglia utilizzata come base per i test di classificazione. I test di classificazione vengono utilizzati per specificare automaticamente il tipo di leasing.

- **Framework di contabilità** - Mostra lo standard contabile selezionato, ovvero IFRS 16 e ASC 842, che stai supportando. Lo standard contabile è indicato nel libro associato al leasing. Lo standard contabile determinerà i conti CoGe specificati nel profilo di registrazione.

- **Tipi di leasing** - Indica quale dei due tipi di leasing verrà utilizzato, sia un leasing finanziario sia un leasing operativo. Con un leasing finanziario, i rischi e i vantaggi correlati al cespite in leasing vengono trasferiti al conduttore. Con un leasing operativo, i rischi e i vantaggi correlati al cespite in leasing rimangono al locatore. Una terza opzione è un'identificazione automatizzata del tipo di leasing, finanziario o operativo, in base alle soglie definite nel libro. Tale identificazione automatica viene eseguita durante il test di riclassificazione del leasing.

- **Soglie** - Utilizzato nei test di classificazione del leasing per determinare se il cespite è classificato come uno degli elementi seguenti:

  - **Termine del leasing** - È la percentuale della vita utile da utilizzare nel test di classificazione. Il sistema classificherà il leasing come finanziario se il tipo di leasing è impostato su Automatico e se il termine del leasing sulla vita utile del cespite è maggiore o uguale alla percentuale qui definita.

  - **Valore attuale** - È la percentuale del valore equo del cespite da utilizzare nel test di classificazione. Il sistema classificherà il leasing come finanziario se il tipo di leasing è impostato su Automatico e se il valore attuale dei canoni di leasing futuri sul valore equo del cespite è maggiore o uguale alla percentuale qui definita.

  - **Leasing a breve termine** - Se il termine del leasing è inferiore o uguale al valore definito, il leasing sarà classificato come leasing a breve termine.

  - **Valore ridotto** - Se il valore equo del cespite è inferiore o uguale al valore definito, il leasing sarà classificato come leasing a valore ridotto.

  - **Classificazione e transazioni del leasing** - La classificazione del leasing è un processo automatizzato per classificare i leasing in base alle soglie definite nei libri oltre che ad altri criteri di test di classificazione per identificare se il leasing è un leasing finanziario, operativo, a breve termine o a valore ridotto. È utilizzata anche per identificare se viene seguito il processo di passività sui contratti.

I test di classificazione includono il trasferimento di proprietà, l'opzione di acquisto, il termine del leasing, il valore attuale e l'asset unico. Il diagramma seguente illustra i test di classificazione dei leasing.

[![Test di classificazione dei leasing](./media/overview-03.png)](./media/overview-03.png)

Ogni tipo di leasing gestisce la contabilità in modo diverso per diverse transazioni di leasing. Le transazioni includono la rilevazione iniziale, gli interessi passivi, il canone di leasing dovuto e l'ammortamento del leasing. Si basano sugli standard contabili che stai seguendo (IFRS 16 o ASC 842). I conti CoGe sono definiti nel profilo di registrazione del leasing per ogni tipo di transazione e framework di contabilità.

## <a name="asset-leasing-transactions"></a>Transazioni del leasing di cespiti

#### <a name="initial-recognition"></a>Rilevazione iniziale 
La rilevazione iniziale di un cespite in leasing utilizza il valore attuale calcolato di modo che possa essere riportato nello stato patrimoniale. La relativa voce contabile viene generata automaticamente. Questa transazione addebita il conto asset Right of use e accredita il conto obbligazione sul leasing operativo come segue. Se un cespite è associato al leasing, la voce di rilevazione iniziale si rifletterà come un'acquisizione di cespite. In questo scenario, devi definire un profilo di registrazione cespiti da registrare nel conto asset Right of use. 

> [!NOTE]
> I leasing operativi sono supportati solo da US GAAP ASC 842.

|     Tipo                                          |     Dare                     |     Avere                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Leasing operativa secondo US GAAP              |     Asset Right of use      |     Obbligazione sul leasing operativo       |
|     Leasing finanziario secondo IFRS e US GAAP        |     Asset Right of use      |     Obbligazione sul leasing operativo       |

#### <a name="lease-liability-amortization-interest-expense"></a>Ammortamento dell'obbligazione sul leasing (interessi passivi) 
Gli interessi di un leasing vengono riconosciuti calcolando gli interessi per il saldo iniziale del leasing, il canone di leasing del periodo, il tasso di interesse debitore e i periodi di intervallo di interessi composti per anno. L'importo degli interessi aumenta il conto obbligazione sul leasing operativo accreditandolo, cosa che si rifletterà sullo stato patrimoniale dell'organizzazione. La transazione include anche una voce di addebito al conto interessi passivi, che viene riflessa nel rendiconto profitti e perdite per leasing finanziari e nel conto spese per leasing operativi.

|     Tipo                                          |     Dare                     |     Avere                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Voce dell'obbligazione sul leasing operativo secondo US GAAP ASC 842    |     Interessi passivi          |     Obbligazione sul leasing operativo         |
|     Voce dell'obbligazione sul leasing finanziario secondo IFRS e US GAAP      |     Interessi passivi          |     Obbligazione sul leasing finanziario           |

#### <a name="accrued-lease-payment"></a>Canone di leasing maturato
Un canone di leasing maturato viene riconosciuto come canone di leasing futuro che deve essere elaborato come transazione di pagamento da conti bancari o di cassa. Il canone di leasing dovuto riduce l'obbligazione sul leasing addebitando il conto obbligazione sul leasing della contabilità ausiliaria del fornitore nel caso in cui il locatore sia definito come fornitore, oppure registrando la parte in Avere su un conto CoGe degli effetti passivi, il pagamento verrà eseguito nei confronti del fornitore o degli effetti passivi.

|     Tipo                                          |     Dare                     |     Avere                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Leasing operativa secondo US GAAP              |  Obbligazione sul leasing operativo    |   Responsabilità del fornitore (contabilità ausiliaria)/Effetti passivi  |
|     Leasing finanziario secondo IFRS e US GAAP        |  Obbligazione sul leasing finanziario      |   Responsabilità del fornitore (contabilità ausiliaria)/Effetti passivi  |

#### <a name="asset-depreciation"></a>Ammortamento dei cespiti
L'asset Right of use viene ammortizzato in base al valore inferiore: la vita utile del cespite o il termine del leasing. Il metodo per calcolare l'ammortamento secondo gli standard US GAAP (ASC 842) si basa sulla differenza tra il costo del leasing a quote costanti e l'importo degli interessi. Gli interessi sui leasing finanziari sono calcolati utilizzando un metodo a quote costanti standard. L'ammortamento del leasing incide sul rendiconto profitti e perdite addebitando gli interessi passivi. Lo stato patrimoniale è influenzato dall'accreditamento del conto asset Right of use accumulato per i leasing finanziari. Per i leasing operativi, l'ammortamento viene accreditato sul conto spese di leasing. Se il leasing è collegato a un cespite, le transazioni di ammortamento verranno eseguite solo dal modulo Cespiti. 

|     Tipo                                          |     Dare                     |     Avere                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Leasing operativa secondo US GAAP              |  Costo di leasing                |   Ammortamento accumulato dell'asset Right of use     |
|     Leasing finanziario secondo IFRS e US GAAP        |   Ammortamento delle spese dell'asset Right of use   |   Ammortamento accumulato dell'asset Right of use    |

#### <a name="short-term-lease"></a>Leasing a breve termine
Un leasing a breve termine viene riconosciuto come spesa che inciderà sul conto economico di un'organizzazione. Il canone di leasing dovuto generato viene addebitato sul conto spese di leasing e accreditato sul conto CoGe secondario del fornitore o degli effetti passivi.

|     Tipo                                          |     Dare                     |     Avere                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Voce del leasing a breve termine secondo IFRS e US GAAP     |  Costo di leasing                |   Responsabilità del fornitore (contabilità ausiliaria)/Effetti passivi  |

#### <a name="low-value-lease"></a>Leasing a valore ridotto
Un leasing a valore ridotto viene riconosciuto come spesa che inciderà sul conto economico di un'organizzazione. Il canone di leasing dovuto generato viene addebitato sul conto spese di leasing e accreditato sul conto CoGe secondario del fornitore o degli effetti passivi.

|     Tipo                                          |     Dare                     |     Avere                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Voce del leasing a valore ridotto secondo IFRS e US GAAP      |  Costo di leasing                |   Responsabilità del fornitore (contabilità ausiliaria)/Effetti passivi  |


#### <a name="index-revaluation"></a>Rivalutazione dell'indicizzazione
È il conto di leasing di cespiti per canoni di leasing variabili misurati da un tasso di indicizzazione. Le variazioni nei canoni di leasing dovute alle fluttuazioni del tasso di indicizzazione costituiscono una rettifica del leasing secondo IFRS 16. L'obbligazione sul leasing e gli asset Right of use saranno rettificati per tenere conto dei nuovi pagamenti. 

|     Tipo                                          |     Dare                             |     Avere                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Voce di rivalutazione dell'indicizzazione secondo IFRS in caso di aumento  |  Asset Right of use       |   Obbligazione sul leasing operativo |
|   Voce di rivalutazione dell'indicizzazione secondo IFRS in caso di riduzione  |  Obbligazione sul leasing operativo  |   Asset Right of use      |

Quando i pagamenti cambiano a causa di una variazione del tasso di indicizzazione, verranno modificati solo i pagamenti variabili a meno che non vi siano ulteriori modifiche ai flussi di cassa, come una modifica dei termini del leasing relativi ai tassi di interesse secondo US GAAP ASC 842.

#### <a name="lease-adjustment"></a>Rettifica del leasing
Il leasing di cespiti consente di rettificare i leasing se i termini del leasing vengono modificati, il leasing viene prolungato o se vi sono circostanze aggiuntive in cui un leasing richiede una rettifica. Le rettifiche del leasing vengono registrate per aumentare o diminuire l'asset Right of use e l'obbligazione sul leasing. Il processo di rettifica prende in considerazione il riporto dei saldi finali dell'ammortamento delle passività e del saldo cespiti alla data della rettifica. Quando un leasing è collegato a un cespite, la rettifica del Right of use verrà registrata utilizzando l'ID assegnato in Cespiti. 

|     Tipo                                          |     Dare                             |     Avere                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Voce di rettifica del leasing per IFRS e US GAAP in caso di aumento     |  Asset Right of use       |   Obbligazione sul leasing operativo |
|   Voce di rettifica del leasing per IFRS e US GAAP in caso di riduzione     |  Obbligazione sul leasing operativo  |   Asset Right of use      |


#### <a name="lease-impairment"></a>Riduzione del valore del leasing
Rappresenta il riporto della riduzione del saldo dell'asset Right of use. Identifica l'importo della riduzione del valore, la data della transazione e i periodi rimanenti. L'asset Right of use rimanente sarà ammortizzato a quote costanti. La logica di riduzione del valore del leasing prende in considerazione il valore di riporto del cespite indicato nel piano di ammortamento del cespite.  

|     Tipo                                          |     Dare                             |     Avere                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Voce della riduzione del valore per IFRS e US GAAP           |  Spesa di riduzione del valore                   |    Asset Right of use     |

>[!NOTE]
> Se il leasing è collegato a un cespite, la riduzione del valore del leasing deve essere registrata in Cespiti perché l'ammortamento del cespite viene eseguito nel modulo Cespiti.

**Doppia valuta** - Le transazioni di leasing possono essere registrate in una valuta diversa da quella contabile e di dichiarazione. Il tasso di cambio della valuta è definito nella contabilità generale alla data di inizio. Puoi modificare i tassi di cambio impostando il campo **Tasso fisso** su **Sì** quando crei il leasing. Quando immetti transazioni di leasing, la rilevazione iniziale e le successive transazioni di ammortamento utilizzeranno il tasso di cambio alla data di inizio. Le transazioni interessi e di pagamento successive utilizzeranno il tasso di cambio attivo corrente. 

## <a name="create-an-asset-lease"></a>Creare un leasing di cespiti
Completa i passaggi seguenti per creare un nuovo leasing. 

1. Per utilizzare la funzionalità **Leasing di cespiti**, devi abilitarla nell'area di lavoro **Gestione funzionalità**. Nell'area di lavoro **Gestione funzionalità**, seleziona **Tutto** in modo che tutte le funzionalità siano elencate nella pagina. Seleziona **Leasing di cespiti**, quindi seleziona **Abilita adesso**.
2. Vai a **Leasing di cespiti > Comune> Riepilogo leasing**. Imposta i campi necessari nella Scheda dettaglio **Generale**: 
   - **Dettagli del leasing**
   - **Vita utile del cespite (mesi)**
   - **Gruppo di leasing**
   - **Tasso incrementale di prestito (%)**
   - **Intervallo interessi composti**
   - **Tipo di annualità**
   - **Valuta**
   - **Data di inizio**

3. Accedi alla Scheda dettaglio **Righe scadenzario pagamenti** e immetti una riga di pagamento, quindi seleziona **Crea scadenziario**.

4. Selezionare **Libri**. 

5. Accedi alla Scheda dettaglio **Generale**. Vengono calcolati i valori di **Asset Right of use iniziale** e **Obbligazione sul leasing**. 

6. Vai alla Scheda dettaglio **Test di classificazione leasing** per controllare il valore nel campo **Tipo di leasing**. 

   Il **Tipo di leasing** automatico viene classificato in base ai criteri definiti nella pagina **Libri**.

7.  Vai a **Scadenziario pagamenti** sotto la sezione **Funzione**.  

   La pagina **Scadenziario pagamenti** elenca gli scadenziari di pagamento futuri per un ID leasing. Seleziona **Conferma scadenziario** per poter registrare le transazioni di **rilevazione iniziale**. 

[![Funzione Rilevazione iniziale](./media/overview-13.png)](./media/overview-13.png)

8. Seleziona **Rilevazione iniziale** per creare un giornale di registrazione di riconoscimento iniziale. 

9. Seleziona **Giornali di registrazione di leasing di cespiti** per registrare la transazione di rilevazione iniziale. 

   Nello scadenzario dei pagamenti puoi aprire una pagina dettagliata che elenca le transazioni dell'asset Right of use. 
 
   Il **piano di ammortamento dell'obbligazione sul leasing** mostra l'importo degli interessi calcolato per ogni periodo.
   
10. Crea il giornale di registrazione e seleziona **Giornali di registrazione leasing di cespiti**. Il **piano di ammortamento dell'obbligazione sul leasing** viene visualizzato anche nelle transazioni interessi.

   Nella pagina **Piano di ammortamento cespite** sono visualizzate le transazioni di ammortamento per l'ID leasing selezionato. 

   [![Pagina Transazioni asset ROU](./media/overview-20.png)](./media/overview-20.png)

   Nella pagina **Transazioni asset ROU** sono elencati la rilevazione iniziale, l'ammortamento accumulato e il saldo cespiti. 

   Nella pagina **Transazioni di obbligazione sul leasing** sono visualizzati la rilevazione iniziale, il pagamento degli interessi del leasing, il canone di leasing e il saldo dell'obbligazione sul leasing. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]