---
title: Funzionalità del controllo griglia
description: Questo argomento descrive diverse potenti funzionalità del controllo griglia. La nuova funzionalità Griglia deve essere abilitata per avere accesso a queste funzionalità.
author: jasongre
manager: AnnBe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7136edba828bf97b6e0c8d2a698b884640d680e5
ms.sourcegitcommit: 880f617d1d6e95eccbed762c7ea04398553c2ec0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036267"
---
# <a name="grid-capabilities"></a>Funzionalità del controllo griglia

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Il nuovo controllo griglia offre una serie di funzionalità utili e potenti che possono essere utilizzate per migliorare la produttività degli utenti, creare viste più interessanti dei dati e ottenere informazioni dettagliate significative sui dati. In questo articolo vengono illustrate le seguenti funzionalità: 

-  Calcolare i totali
-  Raggruppare i dati
-  Digitare prima del sistema
-  Valutare espressioni matematiche 

## <a name="calculating-totals"></a>Calcolare i totali
Nelle app Finance and Operations, gli utenti hanno la possibilità di vedere i totali nella parte inferiore delle colonne numeriche nelle griglie. Questi totali sono visualizzati in una sezione a piè di pagina nella parte inferiore della griglia. 

### <a name="showing-the-grid-footer"></a>Visualizzare il piè di pagina della griglia
C'è un'area per i piè di pagina nella parte inferiore di ogni griglia tabulare nelle app Finance and Operations. Il piè di pagina può mostrare informazioni preziose correlate ai dati visualizzati nella griglia. Di seguito sono riportati alcuni esempi di queste informazioni:

- Il numero di righe selezionate nella tabella (quando è selezionato più di un record)
- I totali complessivi nella parte inferiore delle colonne numeriche configurate
- Il numero di righe nel set di dati 

Questo piè di pagina è nascosto per impostazione predefinita, ma può essere attivato facilmente. Per visualizzare il piè di pagina per una griglia, fare clic con il tasto destro del mouse sull'intestazione di una colonna nella griglia e selezionare l'opzione **Mostra piè di pagina**. Una volta attivato il piè di pagina per una particolare griglia, tale impostazione verrà ricordata fino a che l'utente sceglie di nascondere il piè di pagina, operazione che può essere eseguita facendo clic con il pulsante destro del mouse sull'intestazione di una colonna e selezionando **Nascondi piè di pagina**.  Da notare che il posizionamento dell'azione **Mostra piè di pagina/Nascondi piè di pagina** dovrebbe essere modificato in un aggiornamento futuro. 

### <a name="specifying-columns-with-totals"></a>Specificare colonne con totali
Attualmente, nessuna colonna verrà configurata per mostrare i totali per impostazione predefinita. Questa è considerata come un'attività di impostazione unica, simile alla regolazione della larghezza delle colonne nelle griglie. Dopo aver specificato che si desidera visualizzare i totali per una colonna, tale impostazione verrà ricordata alla successiva visita della pagina.  

Esistono due modi per configurare una colonna per mostrare un totale: 

- Fare clic con il pulsante destro del mouse sulla colonna per la quale si desidera visualizzare un totale e selezionare **Totale di questa colonna**. Questa azione provoca tre eventi:

    1. Il piè di pagina diventa visibile. 
    2. La preferenza per la visualizzazione di un totale in questa colonna viene salvata. 
    3. Un calcolo dei totali viene avviato per questa colonna e per le altre colonne per le quali è stata impostata la visualizzazione dei totali. Il tempo necessario per mostrare un totale dipende dalla dimensione del set di dati di cui si stanno genrando i totali.

- Dopo che il piè di pagina è visibile, selezionare **Mostra totale** nell'area per i piè di pagina nella parte inferiore della colonna per cui si desidera visualizzare un totale. Se non vi sono colonne configurate, il pulsante **Mostra totale** sarà disponibile per tutte le colonne numeriche. 

    Una volta configurata almeno una colonna per i totali, il pulsante **Mostra totale** sarà disponibile solo al passaggio del mouse o quando è l'elemento attivo. L'azione di selezione **Mostra totale** salva solo la preferenza per la visualizzazione di un totale in questa colonna, in modo che la preferenza venga applicata durante le future visite alla pagina. Nel piè di pagina, questo stato è indicato da un trattino che appare nella colonna. (In alternativa, se il set di dati è abbastanza piccolo, viene immediatamente mostrato un totale.)

Se si commette un errore e non si desidera più vedere un totale in una determinata colonna, fare clic con il pulsante destro sulla colonna e scegliere **Nascondi totale** oppure selezionare il pulsante **Nascondi totale** nel piè di pagina in quella colonna. Questa preferenza verrà salvata anche per visite future alla pagina. 

### <a name="calculating-totals"></a>Calcolo totali in corso
Quando si arriva a una pagina con il piè di pagina visibile e le colonne sono già configurate per i totali, questi possono o meno essere visualizzati nel piè di pagina. Il comportamento dipende dalla dimensione del set di dati nella pagina. Se il set di dati è sufficientemente piccolo, i totali verranno visualizzati automaticamente, insieme al numero di righe nel set di dati. Se sono presenti trattini nel piè di pagina sotto le colonne configurate per i totali, il set di dati è troppo grande per consentire al sistema di mostrare immediatamente i totali e per calcolare i totali è necessaria un'azione esplicita. A questo proposito, fare clic sul pulsante **Calcola** nel piè di pagina o fare clic con il pulsante destro del mouse su una colonna per la quale si desidera un totale e selezionare **Totale in questa colonna**.  

Se il calcolo richiede troppo tempo, è possibile annullare l'operazione selezionando il pulsante **Annulla**. A volte, tuttavia, il set di dati sarà troppo grande per calcolare i totali (un limite imposto dalla propria organizzazione) e verrà invece richiesto di filtrare ulteriormente i dati.

I totali verranno aggiornati automaticamente a mano a mano che si aggiornano, eliminano o si creano righe nel set di dati.  

## <a name="grouping-data"></a>Raggruppare i dati
Gli utenti aziendali devono spesso eseguire analisi ad hoc dei dati. Sebbene questa operazione possa essere eseguita esportando dati in Microsoft Excel e usando tabelle pivot, la funzionalità **Raggruppamento** nelle griglie tabulari consente agli utenti di organizzare i dati in modi interessanti nelle app Finance and Operations. Poiché questa funzionalità estende la funzionalità **Totali**, **Raggruppamento** consente inoltre di ottenere informazioni dettagliate significative sui dati fornendo subtotali a livello di gruppo.

Per utilizzare questa funzionalità, fare clic con il pulsante destro del mouse sulla colonna in base alla quale eseguire il raggruppamento e selezionare **Raggruppa in base a questa colonna**. Questa azione ordina i dati in base alla colonna selezionata, aggiunge un nuovo gruppo all'inizio della griglia e inserisce "righe di intestazione" all'inizio di ciascun gruppo. Queste righe di intestazione forniscono le seguenti informazioni su ciascun gruppo: 
-  Valore dei dati per il gruppo 
-  Etichetta della colonna (Queste informazioni saranno particolarmente utili dopo il supporto di più livelli di raggruppamento).
-  Numero di righe di dati in questo gruppo
-  Subtotali per qualsiasi colonna configurata per mostrare i totali

Con la funzionalità [Visualizzazioni salvate](saved-views.md) abilitata, questo raggruppamento può essere salvato mediante personalizzazione come parte di una visualizzazione per un accesso rapido alla successiva visita della pagina.  

Se si seleziona **Raggruppa in base a questa colonna** per una colonna diversa, il raggruppamento originale viene sostituito, poiché un solo livello di raggruppamento è supportato nella versione 10.0.9 con l'update 33 della piattaforma.

Per annullare il raggruppamento in una griglia, fare clic con il pulsante destro del mouse sulla colonna di raggruppamento e selezionare **Separa**.  


## <a name="evaluating-math-expressions"></a>Valutare espressioni matematiche
Come booster di produttività, gli utenti possono inserire formule matematiche nelle celle numeriche di una griglia. Non devono eseguire il calcolo in un'app esterna al sistema. Ad esempio, se si immette **=15\*4** e quindi si preme il tasto **TAB** per uscire dal campo, il sistema valuterà l'espressione e salverà un valore di **60** per il campo.

Per fare in modo che il sistema riconosca un valore come espressione, iniziare il valore con un segno uguale (**=**). Per maggiori dettagli sugli operatori supportati e sulla sintassi, vedere [Simboli matematici supportati](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).  
