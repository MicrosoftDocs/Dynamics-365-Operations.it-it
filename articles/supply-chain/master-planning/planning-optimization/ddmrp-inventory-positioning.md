---
title: Posizionamento delle scorte
description: Questo articolo fornisce informazioni sul posizionamento delle scorte strategiche, che prevede l'identificazione dei punti di disaccoppiamento nella supply chain, dove è possibile creare scorte disponibili per abbreviare i lead time e limitare l'impatto di eventi imprevisti sulla supply chain.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ReqGroup, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: bec36b5b51b937782afdb78d7009a58dcd0942f0
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186735"
---
# <a name="inventory-positioning"></a>Posizionamento delle scorte

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Il posizionamento delle scorte strategiche prevede l'identificazione dei punti di disaccoppiamento nella supply chain, dove è possibile creare scorte disponibili. Questo approccio viene usato principalmente per abbreviare i lead time e ridurre l'impatto di eventi imprevisti sulla supply chain. Permette di mitigare il cosiddetto "effetto frusta", perché la variabilità della domanda non si ripercuote su tutta la supply chain. (L'*effetto frusta* si riferisce al modo in cui minime fluttuazioni della domanda a livello di vendita al dettaglio possono causare progressivamente fluttuazioni di entità maggiore a livello di vendita all'ingrosso, distributore, produttore e fornitore di materie prime.)

Il posizionamento delle scorte è il primo passaggio di Demand Driven Materials Resource Planning (DDMRP).

## <a name="inventory-positioning-for-manufacturing"></a>Posizionamento delle scorte per la produzione

In questa sezione è riportato un esempio che mostra come prendere decisioni sul posizionamento delle scorte se si fabbrica un tipico prodotto cuscino. Il cuscino prevede una distinta base a più livelli, come mostrato nella figura seguente.

![Esempio di distinta base a più livelli per un prodotto cuscino.](media/ddmrp-bom-example.png "Esempio di distinta base a più livelli per un prodotto cuscino")

### <a name="choose-your-decoupling-points"></a>Scegliere il punto di disaccoppiamento

Quando si sceglie dove posizionare i punti di disaccoppiamento, occorre prendere in considerazione i seguenti aspetti di ogni articolo nella distinta base come criteri:

- Variabilità esterna
- Sfruttamento e flessibilità delle scorte
- Protezione delle operazioni critiche
- Tempo di tolleranza del cliente
- Orizzonte di visibilità degli ordini di vendita
- Lead time potenziale del mercato

Nell'esempio dei cuscini, si potrebbe posizionare il primo punto di disaccoppiamento a livello di *traverse di schiuma* per i seguenti motivi:

- Il materiale usato per le traverse di schiuma è difficile da reperire e la disponibilità è volatile. Pertanto, il criterio *variabilità esterna* è soddisfatto.
- Le traverse di schiuma possono essere tagliate in svariate forme e dimensioni per creare inserti in schiuma per altri prodotti fabbricati, oltre ai cuscini. Pertanto, il criterio *sfruttamento e flessibilità delle scorte* è soddisfatto.

Si potrebbe quindi posizionare il successivo punto di disaccoppiamento a livello di *kit di tessuto*, ovvero il tessuto pre-tagliato per il cuscino. Si potrebbe scegliere questo punto in ragione del fatto che si dispone di un unico macchinario per il taglio del tessuto. Pertanto, il criterio *protezione dell'operazione critica* è soddisfatto.

Infine, si potrebbe posizionare l'ultimo punto di disaccoppiamento a livello di articolo cuscino finito. Si potrebbe scegliere questo punto perché il *tempo di tolleranza del cliente* per le vendite è molto basso e perché l'*orizzonte di visibilità degli ordini di vendita* è alquanto breve. Di conseguenza, si vuole avere la certezza di avere scorte disponibili per soddisfare gli ordini in arrivo. È anche possibile impostare un prezzo più alto mantenendo il lead time breve, ed è ciò cui fa riferimento il criterio *lead time potenziale del mercato*.

In base a questa analisi, l'immagine seguente mostra l'aspetto della distinta base del cuscino. I simboli gialli delle scorte evidenziano i punti di disaccoppiamento.

![Distinta base di esempio con i punti di disaccoppiamento evidenziati.](media/ddmrp-bom-decoupling-example.png "Distinta base di esempio con i punti di disaccoppiamento evidenziati")

### <a name="calculate-your-decoupled-lead-time"></a>Calcolare il lead time disaccoppiato

Questa sezione mostra come calcolare i nuovi lead time dopo aver introdotto i punti di disaccoppiamento.

Nell'immagine seguente per l'esempio del cuscino iniziato nella precedente sezione, i lead time sono mostrati in riquadri grigi in alto a sinistra di ciascun componente della distinta base. I riquadri con un contorno rosso indicano gli articoli che determinano il lead time cumulativo (la somma dei lead time più lunghi a ogni livello della distinta base). Il lead time è di 21 giorni quando si inizia da zero.

![Distinta base di esempio con lead time.](media/ddmrp-bom-lead-times-example.png "Distinta base di esempio con lead time")

Tuttavia, se si applicano i punti di disaccoppiamento scelti in precedenza, gli articoli disaccoppiati saranno sempre in magazzino. Pertanto, avranno un lead time pari a 0 (zero). Il nuovo lead time per il cuscino è ora di soli cinque giorni: due giorni per acquistare il filo e tre giorni per produrre il cuscino. Questo lead time è noto come *lead time disaccoppiato*.

![Esempio di lead time disaccoppiato.](media/ddmrp-bom-decoupled-lead-time-example.png "Esempio di lead time disaccoppiato")

## <a name="strategic-inventory-positioning-in-a-retail-model"></a>Posizionamento delle scorte strategiche in un modello di vendita al dettaglio

Poiché i rivenditori hanno in magazzino solo i prodotti finiti, le distinte base non sono un problema. Tuttavia, i rivenditori possono usare DDMRP impostando un posizionamento delle scorte strategico e livelli di buffer basati sulle posizioni di magazzinaggio nella rete di distribuzione.

Nella figura seguente viene illustrato un esempio di una società con un centro di distribuzione a Seattle e punti vendita a Boston, Atlanta e Portland.

![Punti di disaccoppiamento basati sulla posizione in un modello di vendita al dettaglio.](media/ddmrp-retail-decoupl-points-example.png "Punti di disaccoppiamento basati sulla posizione in un modello di vendita al dettaglio")

Si potrebbe decidere che il tempo di trasferimento per spostare un prodotto coperta tra il centro di distribuzione e i punti vendita viola il *tempo di tolleranza del cliente*, perché i clienti si aspettano che le coperte siano disponibili al momento della loro visita in negozio. In questo caso, si imposterà un punto di disaccoppiamento per l'articolo coperta a livello di ognuno dei tre punti vendita. Ogni punto vendita avrà livelli di buffer diversi, basati su lead time, pattern di domanda e così via.

## <a name="implement-inventory-positioning-in-dynamics-365-supply-chain-management"></a>Implementare il posizionamento delle scorte in Dynamics 365 Supply Chain Management

Questa sezione descrive come implementare la strategia di posizionamento delle scorte in Microsoft Dynamics 365 Supply Chain Management.

### <a name="set-up-item-coverage-groups-that-create-decoupling-points"></a>Impostare gruppi di copertura degli articoli che creano punti di disaccoppiamento

Gli articoli diventano punti di disaccoppiamento quando appartengono a un gruppo di copertura configurato con un valore **Codice di copertura** di *Punto di disaccoppiamento*. Pertanto, il primo passaggio nel processo di impostazione id DDMRP è decidere quali gruppi di copertura implementare per la strategia DDMRP, per poi crearli attenendosi alla seguente procedura.

1. Andare a **Pianificazione generale \> Impostazioni \> Copertura \> Gruppi di copertura**.
1. Nel riquadro Azioni selezionare **Nuovo** per creare un gruppo di copertura.
1. Immettere le informazioni che identificano il gruppo di copertura, quindi selezionare il calendario da usare.
1. Nella scheda **Generale** impostare il campo **Codice di copertura** su *Punto di disaccoppiamento*. Questa impostazione farà sì che tutti gli articoli che appartengono a questo gruppo di copertura verranno trattati come punti di disaccoppiamento per DDMRP. Inoltre, abilita tutte le impostazioni DDMRP per questo gruppo, come descritto più avanti in questa procedura.
1. Nella sezione **Parametri DDMRP** della scheda **Altro** impostare i seguenti campi:

    - **Fattore di lead time**: specificare un fattore (come valore decimale compreso tra 0 e 1) per controllare l'impatto dei lead time quando i livelli delle scorte minimo e massimo vengono calcolati per gli articoli in questo gruppo di copertura. In generale, maggiore è il lead time di un articolo, minore deve essere il relativo fattore di lead time. Un fattore di lead time minore produce livelli delle scorte minimo e massimo più bassi, causando quindi ordini di dimensioni ridotte e più frequenti. La metodologia DDMRP consiglia di adottare un valore compreso tra 0,20 e 0,40 per gli articoli con lead time più lunghi, tra 0,41 e 0,60 per gli articoli con lead time medi e tra 0,61 e 1 per gli articoli con lead time brevi. Per ulteriori informazioni, vedere [Profilo e livelli di buffer](ddmrp-buffer-profile-and-levels.md).
    - **Fattore di variabilità**: specificare un fattore (come valore decimale compreso tra 0 e 1) per controllare l'impatto della variazione della domanda quando i livelli delle scorte vengono calcolati per gli articoli in questo gruppo di copertura. In generale, più variabile è la domanda per un articolo, più elevato sarà il relativo fattore di variabilità. Un fattore di variabilità superiore produce un livello delle scorte minimo più elevato. La metodologia DDMRP consiglia di adottare un valore compreso tra 0,00 e 0,40 per gli articoli con bassa variabilità, tra 0,41 e 0,60 per gli articoli con variabilità media e tra 0,61 e 1 per gli articoli con variabilità elevata. Per ulteriori informazioni, vedere [Profilo e livelli di buffer](ddmrp-buffer-profile-and-levels.md).
    - **Periodo minimo, massimo e punto di riordino**: specificare con quale frequenza calcolare i valori di buffer (*Giornaliero* o *Settimanale*).

1. Nella sezione **Utilizzo giornaliero medio** della scheda **Altro** impostare i seguenti campi:

    - **Utilizzo giornaliero medio basato su**: selezionare su quali periodi di tempo dovrà essere basato l'utilizzo giornaliero medio (ADU). Selezionare uno dei seguenti valori:

        - *Passato*: prende in esame soltanto l'utilizzo passato per il numero di giorni specificato nel campo **Periodo passato (giorni)**. L'ADU viene calcolato come domanda totale per un articolo durante il periodo di calcolo (in unità di scorte) diviso per il numero di giorni nel periodo di calcolo.
        - *Futuro*: prende in esame soltanto l'utilizzo futuro previsto (incluse le previsioni) per il numero di giorni specificato nel campo **Periodo futuro (giorni)**. L'ADU viene calcolato come domanda totale per un articolo durante il periodo di calcolo (in unità di scorte) diviso per il numero di giorni nel periodo di calcolo. 
        - *Misto*: prende in esame sia l'utilizzo passato che quello futuro. Si applicano tutte le impostazioni per i campi **Periodo passato (giorni)** e **Periodo futuro (giorni)**, nonché le opzioni per l'uso misto. 

            *ADU misto* = (\[*Ponderazione passato* × *ADU passato*\] + \[*Ponderazione futuro* × *ADU futuro*\]) ÷ (*Ponderazione passato* + *Ponderazione futuro*)

    - **Periodo passato (giorni)**: immettere il numero di giorni passati (inclusa la data odierna) che il sistema deve prendere in considerazione ai fini del calcolo dell'ADU degli articoli in questo gruppo di copertura. Questa impostazione si applica solo quando il campo **Utilizzo giornaliero medio basato su** è impostato su *Passato* o *Misto*.
    - **Periodo futuro (giorni)**: immettere il numero di giorni futuri (a partire dalla data odierna e fino al giorno specificato) che il sistema deve prendere in considerazione ai fini del calcolo dell'ADU degli articoli in questo gruppo di copertura. Questa impostazione si applica solo quando il campo **Utilizzo giornaliero medio basato su** è impostato su *Futuro* o *Misto*.
    - **Peso relativo del periodo passato per l'utilizzo giornaliero medio misto**: immettere il peso (sotto forma di percentuale) da applicare al periodo passato quando viene calcolato l'ADU misto. Questa impostazione si applica solo quando il campo **Utilizzo giornaliero medio basato su** è impostato su *Misto*.
    - **Peso relativo del periodo futuro per l'utilizzo giornaliero medio misto**: immettere il peso (sotto forma di percentuale) da applicare al periodo futuro quando viene calcolato l'ADU misto. Questa impostazione si applica solo quando il campo **Utilizzo giornaliero medio basato su** è impostato su *Misto*.

1. Per tutte le altre schede e gli altri campi, immettere le impostazioni dettagliate usate per calcolare i requisiti per gli articoli collegati a questo gruppo di copertura.

### <a name="set-an-item-as-a-decoupling-point"></a>Impostare un articolo come punto di disaccoppiamento

Attenersi alla seguente procedura per impostare un articolo come punto di disaccoppiamento.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Trovare e selezionare un articolo rilasciato da impostare per DDMRP.
1. Nella scheda **Piano** del riquadro Azioni selezionare **Copertura articolo**.
1. Nella pagina **Copertura articolo** potrebbero essere già elencati diversi record di copertura articolo, ognuno dei quali si applica a una diversa combinazione di magazzinaggio e dimensioni del prodotto. È possibile selezionare un record di copertura articolo esistente applicabile alle dimensioni, laddove si voglia creare un punto di disaccoppiamento. In alternativa, è possibile selezionare **Nuovo** nel riquadro Azioni per creare un nuovo record di copertura.
1. Impostare il record di copertura articolo normalmente. Come minimo, è necessario specificare il sito e il magazzino cui verrà applicato il punto di disaccoppiamento.
1. Mentre il record appropriato è ancora selezionato, selezionare la scheda **Generale**.
1. Selezionare la casella di controllo **Usa impostazioni specifiche**.
1. Impostare il campo **Gruppo di copertura** su un gruppo di copertura impostato per creare punti di disaccoppiamento (come descritto nella sezione precedente).
1. L'articolo è ora configurato come punto di disaccoppiamento. In genere, quando si usa DDMRP, si configureranno anche le impostazioni che incidono sulle dimensioni del buffer e sulla quantità da riordinare. È comunque possibile completare la configurazione in un successivo momento. Per ulteriori informazioni sulle impostazioni, vedere [Impostare i buffer per un articolo punto di disaccoppiamento](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

> [!NOTE]
> Per pianificare gli articoli che non sono punti di disaccoppiamento, attenersi alla seguente procedura seguita quando si utilizza la pianificazione dei fabbisogni di materiali standard (MRP).
