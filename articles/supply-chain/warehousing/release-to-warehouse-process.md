---
title: Rilascia in magazzino
description: Questo argomento fornisce dettagli sul processo di rilascio in magazzino. Descrive le entità che vengono create quando si rilascia un ordine in magazzino e le opzioni che è possibile utilizzare per avviare il processo.
author: Mirzaab
ms.date: 8/13/2021
ms.topic: article
ms.search.form: WHSReleaseToWarehouse, WHSReleaseToWarehouseSalesOrder, WHSReleaseToWarehouseTransferOrder, WHSLoadPlanningWorkbench, WHSWaveTemplateTable, WHSWorkTemplateTable, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8624db42e9d0f3d08ed3b582224ed7937d52f85d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678353"
---
# <a name="release-to-warehouse"></a>Rilascia in magazzino

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce dettagli sul processo di rilascio in magazzino. Descrive le entità che vengono create quando si rilascia un ordine in magazzino e le opzioni che è possibile utilizzare per avviare il processo.

## <a name="release-to-warehouse-overview"></a>Panoramica del rilascio in magazzino

Il rilascio in magazzino è il processo di preparazione dell'inventario per l'elaborazione della spedizione. Quando si rilascia un ordine in magazzino, il sistema crea righe di carico e spedizioni. Se è impostata l'elaborazione automatica dei cicli, vengono creati anche i carichi e il lavoro richiesto. La configurazione delle entità coinvolte dipende dalle impostazioni di sistema. Questa sezione dell'argomento esamina le entità create durante il processo di rilascio in magazzino e le impostazioni di sistema che le definiscono.

Una *spedizione* è un gruppo di righe di ordini cliente o di ordini di trasferimento per lo stesso cliente o lo stesso indirizzo di consegna.

Un *carico* è un gruppo di righe di ordini cliente o di ordini di trasferimento raggruppate insieme per prodotti che in genere escono su un singolo camion, vagone ferroviario o altro mezzo di trasporto. Per un carico può essere presente una o più spedizioni. È possibile creare manualmente un carico aggiungendo righe di ordine a un nuovo carico. In questo caso, le righe di ordine vengono assegnate al carico prima che venga avviato il processo di rilascio in magazzino e possono essere rilasciate solo nella pagina **Workbench pianificazione carico**.

Per *lavoro* di magazzino si intende qualsiasi operazione di magazzino eseguita da un addetto al magazzino stesso. In genere, le operazioni di magazzino sono costituite almeno da due azioni consecutive: un addetto preleva le scorte disponibili da un'ubicazione e le colloca in un'altra ubicazione.

Quando gli ordini vengono rilasciati in magazzino, il sistema crea *righe di carico* e le raggruppa in spedizioni. Il processo di consolidamento della spedizione viene eseguito in automatico durante il processo di rilascio in magazzino. Per ulteriori informazioni, vedere [Criteri di consolidamento della spedizione](about-shipment-consolidation-policies.md).

Il sistema utilizza *cicli* per creare lavori di prelievo e carichi per la spedizione. Un *modello di ciclo* deve essere disponibile per il tipo di ciclo che si desidera creare e per il magazzino della riga ordine. I modelli di ciclo di tipo *Spedizione* vengono utilizzati per spedire articoli relativi a ordini cliente e ordini di trasferimento.

Ogni modello di ciclo contiene *metodi di ciclo*. I metodi di ciclo eseguono azioni come la creazione di lavoro per il ciclo o la creazione di carichi. Ad esempio, un modello di ciclo per i cicli di spedizione può contenere metodi per la creazione di carichi, l'allocazione di righe a cicli, il rifornimento e la creazione del lavoro di prelievo per il ciclo. Il modello di ciclo stabilisce alcune impostazioni che definiscono il modo in cui il ciclo verrà generato ed elaborato, inclusi i passaggi da eseguire manualmente e automaticamente. Per ulteriori informazioni, vedi [Modelli di ciclo](wave-templates.md). Pertanto, a seconda della configurazione del modello, un ciclo viene creato, elaborato e rilasciato automaticamente quando si rilascia un ordine in magazzino oppure alcune o tutte queste azioni vengono eseguite manualmente dopo il rilascio in magazzino.

Quando un ciclo viene elaborato, il sistema crea un lavoro di prelievo, basato su un adeguato *modello di ciclo* e su una *direttiva di ubicazione* e lo rende disponibile sui dispositivi mobili. Il modello di lavoro determina come viene eseguito il lavoro per ogni processo di magazzino, mentre la direttiva di ubicazione specifica le ubicazioni di prelievo e stoccaggio per il movimento delle scorte. Per ulteriori informazioni, vedere [Rifornimento e Controllare il lavoro di magazzino utilizzando i modelli di lavoro e le direttive ubicazione](control-warehouse-location-directives.md).

> [!NOTE]
> Per impostazione predefinita, i cicli vengono elaborati in modalità batch.

Durante l'elaborazione delle ondate, il sistema di solito crea un nuovo carico per ogni spedizione a cui non è assegnato alcun carico. Se si desidera invece che il sistema assegni le spedizioni non assegnate ai carichi esistenti, è possibile utilizzare la funzionalità avanzata di allestimento del carico durante un ciclo. Per ulteriori informazioni, vedere [Allestimento avanzato del carico durante un ciclo](advanced-load-building-during-wave.md).

Nelle pagine **Ordini cliente** e **Ordini di trasferimento** è possibile rivedere le entità create per le righe di ordine durante il processo di rilascio in magazzino.

- Pagina **Ordini cliente**:

    - Nella Scheda dettaglio **Righe ordine cliente** selezionare **Magazzino** e quindi, nel menu, selezionare **Dettagli spedizione**, **Dettagli carico** o **dettagli lavoro** per aprire le spedizioni, i carichi o il lavoro correlato rispettivamente.
    - Nella scheda dettaglio **Dettagli riga** selezionare la scheda **Carico** per esaminare i carichi correlati.

- Pagina **Ordini di trasferimento**:

    - Nel riquadro Azioni, nella scheda **Spedizione** selezionare **Dettagli spedizione** o **Dettagli carico** per aprire le spedizioni o i carichi correlati.
    - Nella Scheda dettaglio **Righe ordine di trasferimento** selezionare **Dettagli lavoro** per aprire i dettagli del lavoro correlato.

In conclusione, quando un ordine viene rilasciato al magazzino, il flusso più automatizzato funziona nel seguente modo:

1. Il sistema crea una spedizione per l'ordine e un ciclo.
1. Il ciclo viene elaborato.
1. Il sistema crea un carico e un ID lavoro.

A seconda dei modelli di ciclo, dei modelli di lavoro e delle impostazioni delle direttive di ubicazione, alcuni passaggi in questo flusso potrebbero diventare manuali. Tuttavia, il flusso complessivo rimane lo stesso.

Sono disponibili diverse opzioni per il rilascio di un ordine in magazzino. È possibile eseguire l'operazione manualmente oppure configurare un lavoro batch. Le restanti sezioni di questo argomento esaminano in dettaglio i vari modi in cui è possibile eseguire un'operazione di rilascio in magazzino.

## <a name="manual-release-to-the-warehouse-from-the-sales-orders-and-transfer-orders-pages"></a>Rilascio manuale in magazzino dalle pagine Ordini cliente e Ordini di trasferimento

È possibile rilasciare un ordine in magazzino direttamente dalla pagina **Ordini cliente** o **Ordini di trasferimento** selezionando **Rilascia in magazzino**.

- Nella pagina **Ordini cliente** il pulsante è sulla scheda **Magazzino** del riquadro Azioni.
- Nella pagina **Ordini di trasferimento** il pulsante è sulla scheda **Spedizione** del riquadro Azioni.

Nella pagina **Ordini cliente** è possibile rilasciare più ordini cliente contemporaneamente.

## <a name="manual-release-to-the-warehouse-from-the-release-to-warehouse-pages"></a>Rilascio manuale in magazzino dalle pagine Rilascia in magazzino

Il sistema attualmente fornisce tre pagine in cui è possibile rivedere le righe per più ordini e rilasciarle in magazzino:

- **Rilascia in magazzino** (**Gestione magazzino \> Rilascio in magazzino \> Rilascia in magazzino**): consente di usare sia ordini cliente sia ordini di trasferimento. Tuttavia, fornisce prestazioni più lente rispetto alle altre due pagine. Questa pagina sarà presto deprecata.
- **Rilascia ordini cliente in magazzino** (**Gestione magazzino \> Rilascio in magazzino \> Rilascia ordini cliente in magazzino**): consente di usare solo gli ordini cliente. Fornisce prestazioni migliori rispetto alla pagina **Rilascia in magazzino**.
- **Rilascia ordini di trasferimento in magazzino** (**Gestione magazzino \> Rilascio in magazzino \> Rilascia ordini di trasferimento in magazzino**): consente di usare solo gli ordini di trasferimento. Fornisce prestazioni migliori rispetto alla pagina **Rilascia in magazzino**.

Tutte le tre pagine forniscono funzionalità simili, come descritto nella parte rimanente di questa sezione. Tutte le pagine consentono di selezionare righe di ordine o interi ordini e quindi di rilasciarli in magazzino.

Ciascuna delle pagine è costituita da una sezione superiore, in cui è possibile selezionare le righe dell'ordine, e da una sezione inferiore, in cui è possibile avviare il processo di rilascio in magazzino. È possibile utilizzare i filtri nella sezione superiore per cercare le righe dell'ordine cliente che si desidera rilasciare. Nella pagina **Rilascia in magazzino** è presente una scheda separata per gli ordini cliente e gli ordini di trasferimento nella sezione superiore, mentre in ciascuna delle altre due pagine è presente un solo tipo di ordine.

La barra degli strumenti nella sezione superiore include i seguenti pulsanti che è possibile utilizzare per selezionare le righe di ordine da rilasciare in magazzino:

- **Aggiungi**: selezionare una o più righe di ordine nella sezione superiore e quindi selezionare questo pulsante per tali righe nella sezione inferiore.
- **Aggiungi tutto**: consente di aggiungere tutte le righe dalla sezione superiore alla sezione inferiore.
- **Aggiungi ordine**: selezionare un ordine, quindi selezionare questo pulsante per aggiungere tutte le righe di tale ordine alla sezione inferiore.

Dopo aver finito di aggiungere righe alla sezione inferiore, contrassegnare ogni riga da rilasciare. Selezionare **Rilascia in magazzino** sulla barra degli strumenti per rilasciare tali righe in magazzino.

## <a name="manual-release-to-the-warehouse-from-the-load-planning-workbench-page"></a>Rilascio manuale in magazzino nella pagina Workbench pianificazione del carico

È anche possibile rilasciare manualmente gli ordini in magazzino utilizzando la pagina **Workbench pianificazione del carico**. Questa pagina consente di organizzare le righe di ordine in carichi e quindi di rilasciare tali carichi in magazzino.

Per aprire la pagina **Workbench pianificazione del carico** andare a **Gestione magazzino \> Carichi**. È anche possibile aprirla nelle pagine **Ordini cliente** e **Ordini di trasferimento**. Nella sezione superiore della pagina, è possibile selezionare le righe dell'ordine cliente nella scheda **Righe vendita** e le righe dell'ordine di trasferimento nella scheda **Righe trasferimento**, quindi aggiungere tali righe a un carico nuovo o esistente.

Nella scheda **Domanda e offerta** nel riquadro Azioni include i pulsanti seguenti che è possibile usare per aggiungere a un carico righe di ordine nella sezione superiore:

- **Al nuovo carico**: selezionare una o più righe di ordine nella sezione superiore e quindi selezionare questo pulsante per creare un nuovo carico e aggiungere tali righe.
- **Al carico esistente**: selezionare una o più righe di ordine nella sezione superiore e quindi selezionare questo pulsante per aggiungere tali righe a un carico esistente.
- **Ordine intero in un nuovo carico**: selezionare gli ordini e quindi selezionare questo pulsante per creare un nuovo carico e aggiungervi tutte le righe di tali ordini.
- **Ordine intero in un carico esistente**: selezionare un ordine e quindi selezionare questo pulsante per aggiungere tutte le righe di tale ordine a un carico esistente.

Nella sezione inferiore è possibile esaminare i carichi creati. Per rilasciare carichi in magazzino, selezionarli e quindi selezionare **Rilascia \> Rilascia in magazzino** sulla barra degli strumenti. Se si utilizza l'elaborazione automatica dei cicli, poiché i carichi sono già assegnati alle righe di ordine, il sistema crea le spedizioni e gli ID lavoro quando viene eseguita l'operazione di rilascio in magazzino.

## <a name="automatic-release-to-the-warehouse"></a>Rilascio automatico in magazzino

Per rilasciare automaticamente gli ordini in magazzino, utilizzare i processi **Rilascio automatico degli ordini cliente** e **Rilascio automatico degli ordini di trasferimento**.

Per configurare il processo batch che rilascia gli ordini di cliente, seguire questi passaggi.

1. Vai a **Gestione del magazzino \> Rilascio in magazzino \> Rilascio automatico degli ordini cliente**.
1. Nella finestra di dialogo **Rilascio automatico degli ordini cliente**, nella Scheda dettaglio **Parametri**, impostare i campi seguenti:

    - **Quantità da rilasciare**: specifica se l'intera quantità o solo la quantità prenotata fisicamente deve essere rilasciata nel magazzino.
    - **Consenti rilascio degli ordini parzialmente rilasciati**: specificare se le quantità rimanenti per gli ordini parzialmente rilasciati devono essere rilasciate in magazzino.
    - **Mantieni le prenotazioni in caso di mancato rilascio**: specificare se le quantità che sono state prenotate automaticamente per un ordine cliente devono rimanere prenotate se il processo di rilascio in magazzino non riesce.
    - **Raggruppa rilasci per cliente** – Specifica se il sistema deve elaborare il rilascio alle operazioni di magazzino separatamente per ciascun cliente o se deve rilasciare tutti gli ordini di vendita contemporaneamente. Quando questa opzione è impostata su *Sì*, il sistema raccoglie tutte le righe dell'ordine cliente per un cliente selezionato, rilascia tali ordini al magazzino e quindi elabora il cliente successivo. Quando questa opzione è impostata su *No*, il sistema rilascia tutte le righe di ordine di vendita disponibili in un unico rilascio all'operazione di magazzino. L'abilitazione di questa opzione consente di migliorare le prestazioni e la resilienza del processo di rilascio in magazzino. Tuttavia, è necessario prestare attenzione quando si utilizza questa opzione insieme ai modelli di ciclo configurati per "Elabora ciclo al rilascio in magazzino" perché questa combinazione può generare molti cicli di un singolo cliente, ciascuno con il lavoro generato solo per quel cliente. Per generare un lavoro che combini spedizioni per più clienti, è necessario disattivare l'opzione *Raggruppa rilasci per cliente* o configurare i modelli di ciclo per utilizzare l'elaborazione posticipata.
    - **Gestione ordini bloccati**: selezionare il modo in cui il sistema deve gestire gli ordini cliente attualmente bloccati perché modificati da altri utenti o processi:

        - *Attendi lo sblocco degli ordini*: il sistema deve attendere lo sblocco degli ordini prima di rilasciarli in magazzino. In questo caso, il processo di rilascio in magazzino potrebbe richiedere più tempo.
        - *Ignora ordini bloccati*: il sistema deve ignorare gli ordini bloccati.

    - **Tipi di ordine validi**: selezionare i tipi di ordini cliente da includere nel batch.
    - **Tipo di limite di credito**: specificare se i controlli dei limiti di credito devono essere eseguiti durante il processo di rilascio in magazzino e, in caso affermativo, indicare le informazioni sulla transazione da includere.

1. Per controllare quali ordini devono essere elaborati, nella Scheda dettaglio **Record da includere** selezionare **Filtro**. Viene visualizzata una finestra di dialogo di query standard, in cui è possibile definire criteri di selezione, criteri di ordinamento e join. I campi funzionano esattamente come per altri tipi di query in Microsoft Dynamics 365 Supply Chain Management.
1. Nella scheda dettaglio **Esegui in background** scegliere se il lavoro deve essere eseguito in modalità batch e/o impostare una programmazione ricorrente. I campi funzionano esattamente come funzionano per altri tipi di [processi in background](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Supply Chain Management.
1. Selezionare **OK** per applicare le impostazioni e avviare il processo di rilascio in magazzino.

Per configurare il processo batch che rilascia gli ordini di trasferimento, seguire questi passaggi.

1. Vai a **Gestione magazzino \> Rilascio in magazzino \> Rilascio automatico degli ordini di trasferimento**.
1. Nella finestra di dialogo **Rilascio automatico degli ordini di trasferimento**, nella Scheda dettaglio **Parametri**, impostare i campi seguenti:

    - **Quantità da rilasciare**: specifica se l'intera quantità o solo la quantità prenotata fisicamente deve essere rilasciata nel magazzino.
    - **Consenti rilascio degli ordini parzialmente rilasciati**: specificare se le quantità rimanenti per gli ordini parzialmente rilasciati devono essere rilasciate in magazzino.
    - **Raggruppa rilasci per magazzino di destinazione**: specificare se il sistema deve rilasciare tutti gli ordini di trasferimento contemporaneamente o se deve raggruppare le righe dell'ordine di trasferimento per magazzino di destinazione e quindi rilasciare ciascun gruppo in magazzino separatamente.

1. Per controllare quali ordini devono essere elaborati, nella Scheda dettaglio **Record da includere** selezionare **Filtro**. Viene visualizzata una finestra di dialogo di query standard, in cui è possibile definire criteri di selezione, criteri di ordinamento e join. I campi funzionano esattamente come per altri tipi di query in Supply Chain Management.
1. Nella scheda dettaglio **Esegui in background** scegliere se il lavoro deve essere eseguito in modalità batch e/o impostare una programmazione per la ricorrenza. I campi funzionano esattamente come funzionano per altri tipi di [processi in background](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Supply Chain Management.
1. Selezionare **OK** per applicare le impostazioni e avviare il processo di rilascio in magazzino.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
