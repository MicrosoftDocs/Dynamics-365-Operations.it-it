---
title: Margini di sicurezza
description: In questo argomento viene descritto come utilizzare i margini di sicurezza con il componente aggiuntivo Planning Optimization per Microsoft Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 09/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-9-14
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 7eb5128f3a337bd728cfe8e6d8d3deb0b6b5ef88
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8074969"
---
# <a name="safety-margins"></a>Margini di sicurezza

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come utilizzare i margini di sicurezza con il componente aggiuntivo Planning Optimization per Microsoft Dynamics 365 Supply Chain Management.

## <a name="safety-margins-overview"></a>Panoramica dei margini di sicurezza

Lo scopo dei margini di sicurezza è consentire una configurazione che fornisca un tempo di buffer oltre il normale lead time. Ad esempio, quando il materiale deve essere disimballato o ispezionato dopo che è arrivato dal fornitore, non è possibile semplicemente aggiungere il tempo extra al lead time di acquisto, perché questo approccio darà il tempo di buffer aggiuntivo al fornitore. In questo esempio, il margine di ricevimento può essere utilizzato per garantire che il fornitore consegni prima. Questo approccio fornisce un tempo di buffer in modo che le merci possano essere gestite internamente.

Sono disponibili tre tipi di margini di sicurezza:

- **Margine di riordino** - Il tempo di buffer per l'immissione dell'ordine di fornitura
- **Margine su entrata** - Il tempo di buffer per la gestione della fornitura in entrata
- **Margine su uscita** - Il tempo di buffer per la gestione delle spedizioni

L'illustrazione seguente mostra come questi margini di sicurezza si applicano nel tempo.

![Margini di sicurezza.](media/safety-margins-1.png)

Tutti i margini sono definiti in giorni. Un valore predefinito di *0* (zero) indica che non viene utilizzato il margine. Se si impostano più margini, si aggiungono tutti al tempo totale dalla *data dell'ordine* di offerta alla *data di richiesta* della domanda. Ad esempio, una configurazione non ha tempi di consegna e tutti e tre i tipi di margine sono impostati su un giorno. In questo caso, ci saranno tre giorni tra la data dell'ordine di fornitura e la data del fabbisogno della domanda, quindi se la data dell'ordine è il 1° luglio, la data del fabbisogno sarà il 4 luglio.

### <a name="receipt-margin"></a>Margine su entrata

Il margine su entrata è probabilmente il più utilizzato dei tre margini di sicurezza. Viene applicato alla *data della consegna* e a ritroso dalla *data del fabbisogno*. In altre parole, i prodotti devono ricevere il numero specificato di giorni di margine su entrata prima che siano richiesti.

La figura seguente evidenzia il margine su entrata.

![Margine su entrata.](media/safety-margins-2.png)

Il margine su entrata viene generalmente utilizzato come buffer per garantire il tempo per la registrazione del magazzino o altri processi dispendiosi in termini di tempo che non vengono acquisiti come parte del lead time generale nel sistema. Per gli acquisti, un vantaggio è che la *data di consegna* dell'ordine fornitore viene spostata in avanti di conseguenza. Se si aumenta il lead time invece di utilizzare un margine di sicurezza, al venditore verrà comunque chiesto di consegnare all'ultimo minuto.

Si noti che il margine su entrata non cambia la *data del fabbisogno* dell'offerta. Pertanto, il margine su entrata non è direttamente visibile quando vengono confrontate le date del fabbisogno per domanda e offerta (ad esempio, nella pagina **Fabbisogno netto**). Se ad esempio il margine su entrata in magazzino è impostato su 4 giorni e una riga dell'ordine fornitore è pianificata per l'entrata il giorno 15 del mese, nella pianificazione generale la data di entrata rettificata verrà calcolata come il giorno 19 del mese.

Tenere presente che un margine su entrata non viene applicato quando le scorte disponibili vengono utilizzate come fornitura. Si presume che tutto l'inventario disponibile sia immediatamente disponibile, indipendentemente da quando è stato effettivamente ricevuto.

### <a name="reorder-margin"></a>Margine di riordino

La figura seguente evidenzia il margine di riordino.

![Margine di riordino.](media/safety-margins-3.png)

Il margine di riordino viene aggiunto prima del lead time dell'articolo per tutti gli ordini pianificati durante la pianificazione generale. Pertanto, garantisce tempo aggiuntivo per l'invio di un ordine di fornitura. Questo margine viene generalmente utilizzato come buffer per garantire il tempo ai processi di approvazione o altri processi interni richiesti durante la creazione degli ordini di fornitura. Il margine di riordino viene inserito tra la *data dell'ordine* di fornitura e la *data di inizio*.

### <a name="issue-margin"></a>Margine su uscita

La figura seguente evidenzia il margine su uscita.

![Margine su uscita.](media/safety-margins-4.png)

Il margine di emissione viene detratto dalla data del fabbisogno della domanda durante la pianificazione generale. Aiuta a garantire il tempo per reagire e spedire gli ordini di domanda in arrivo. Questo margine viene generalmente utilizzato come buffer per garantire il tempo per la spedizione e i relativi processi di magazzino in uscita.

Si noti che quando viene applicato un margine su uscita, le date relative al fabbisogno di domanda e offerta non corrispondono. Differiscono per il margine su uscita perché il margine su uscita viene aggiunto tra la *data del fabbisogno* dell'offerta e la *data del fabbisogno* della domanda.

## <a name="set-up-safety-margins"></a>Impostare i margini di sicurezza

### <a name="turn-on-safety-margins-in-feature-management"></a>Attivare i margini di sicurezza in Gestione funzionalità

Prima di poter utilizzare questa funzione con Planning Optimization, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** _Pianificazione generale_
- **Nome funzionalità:** _Margini per Planning Optimization_

### <a name="define-safety-margins"></a>Definire i margini di sicurezza

I margini di sicurezza hanno una configurazione flessibile. Possono essere impostati su *gruppo di copertura* e *piano generale*. È importante capire che i margini vengono aggiunti uno sull'altro. Ad esempio, un margine su entrata di due giorni sul gruppo di copertura e tre giorni sul piano generale produrrà un margine su entrata effettivo di cinque giorni.

La possibilità di impostare il margine sul piano generale può essere utile quando si desidera simulare tempi di consegna più lunghi o non c'è certezza per un piano specifico, ma senza influire sulla pianificazione quotidiana.

#### <a name="coverage-group-safety-margins"></a>Margini di sicurezza del gruppo di copertura

Per applicare un margine di sicurezza a un gruppo di copertura, attenersi alla seguente procedura.

1. Andare a **Pianificazione generale \> Impostazioni \> Gruppi di copertura**.
1. Nel riquadro dell'elenco selezionare il gruppo di copertura desiderato.
1. Nella scheda dettaglio **Altro** nella sezione **Margini di sicurezza in giorni**, utilizzare i seguenti campi per impostare i margini di sicurezza richiesti (in giorni):

    - Margine su entrata in magazzino aggiunto dalla data del fabbisogno
    - Margine su uscita da magazzino detratto dalla data del fabbisogno
    - Margine di riordino aggiunto al lead time dell'articolo

#### <a name="master-plan-safety-margins"></a>Margini di sicurezza del piano generale

Per applicare un margine di sicurezza a un piano generale, attenersi alla seguente procedura.

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Nel riquadro dell'elenco selezionare il piano generale desiderato.
1. Nella scheda dettaglio **Margini di sicurezza in giorni** utilizzare i seguenti campi per impostare i margini di sicurezza richiesti (in giorni):

    - Margine su entrata in magazzino aggiunto dalla data del fabbisogno
    - Margine su uscita da magazzino detratto dalla data del fabbisogno
    - Margine di riordino aggiunto al lead time dell'articolo

### <a name="define-whether-calculations-are-based-on-calendar-days-or-work-days"></a>Definire se i calcoli si basano su giorni di calendario o giorni lavorativi

È possibile impostare tutti i margini di sicurezza in modo che vengano calcolati in base ai giorni di calendario o ai giorni lavorativi.

1. Andare a **Pianificazione generale \> Impostazioni \>Parametri di pianificazione generale**.
1. Nella scheda **Generale** nella sezione **Margini di sicurezza in giorni** impostare l'opzione **Giorni lavorativi** su *Sì* per calcolare i margini in base ai giorni lavorativi. Impostare l'opzione su *No* per calcolare i margini in base ai giorni di calendario.

Ad esempio, un calendario è aperto dal lunedì al venerdì e chiuso dal sabato alla domenica. Se c'è un margine su entrata di un giorno, una data di fabbisogno di lunedì produce una data di consegna il venerdì precedente, perché sabato e domenica non sono giorni lavorativi.

Il calendario utilizzato per determinare i giorni lavorativi dipende dalla configurazione e dal tipo di fornitura. Può essere controllato dai calendari del gruppo di copertura, del magazzino e del fornitore.

> [!NOTE]
> Se *magazzino* non fa parte della dimensione di copertura (in altre parole, la pianificazione si basa solo su *sito*), il calendario del magazzino non viene utilizzato.

Il sistema può gestire una configurazione in cui sono definiti uno o più calendari. Le seguenti sottosezioni descrivono le possibili combinazioni che possono essere utilizzate per controllare il risultato.

#### <a name="calendar-that-is-used-for-the-duration"></a>Calendario utilizzato per la durata

I calendari definiti controllano il lead time totale effettivo in giorni di calendario, dalla data dell'ordine di fornitura alla data del fabbisogno della domanda. Viene utilizzata la seguente priorità di calendario:

- **Lead time acquisto** - Viene considerato solo il calendario del gruppo di copertura.
- **Margine su entrata** - Viene utilizzato il calendario del gruppo di copertura, se definito. In caso contrario, viene utilizzato il calendario del magazzino.
- **Margine su uscita** - Viene utilizzato il calendario del gruppo di copertura, se definito. In caso contrario, viene utilizzato il calendario del magazzino.
- **Margine di origine** - Viene considerato solo il calendario del gruppo di copertura.

#### <a name="calendar-that-is-used-for-the-final-date"></a>Calendario utilizzato per la data finale

Le seguenti regole vengono applicate per determinare se il motore di pianificazione può utilizzare una determinata data per un determinato tipo di data:

- **Data di ricevimento acquisto** - Viene utilizzato il calendario del fornitore, se definito. In caso contrario, viene utilizzato il calendario del gruppo di copertura, se definito. Se nessuno di questi calendari è definito, viene utilizzato il calendario del magazzino.
- **Data di ricevimento trasferimento** - Viene utilizzato il calendario del gruppo di copertura, se definito. In caso contrario, viene utilizzato il calendario del magazzino.
- **Data di ricevimento produzione** - Viene utilizzato il calendario del gruppo di copertura, se definito. In caso contrario, viene utilizzato il calendario del magazzino.
- **Giorno lavorativo uscita domanda** - Viene utilizzato il calendario del magazzino, se definito. In caso contrario, viene utilizzato il calendario del gruppo di copertura.
- **Giorno lavorativo ordine** - Viene utilizzata una combinazione (intersezione) del calendario del gruppo di copertura e del calendario del fornitore. Entrambi i calendari devono essere aperti per utilizzare la data. Se è definito solo uno di questi calendari, viene utilizzato solo quel calendario.

#### <a name="calendar-setup-overview-matrix"></a>Matrice della panoramica dell'impostazione del calendario

La figura seguente presenta una matrice che riepiloga i calendari applicabili quando vengono calcolati i margini di sicurezza. (Seleziona l'immagine per aprirne una versione ad alta risoluzione.) Le seguenti abbreviazioni e colori vengono utilizzati per indicare dove è specificato ogni tipo di calendario:

- **Gruppo di copertura (CG):** verde
- **Magazzino (WH):** giallo
- **Fornitore (V):** blu

[![Matrice della panoramica dell'impostazione del calendario.](media/safety-margins-calendar-matrix.png)](media/safety-margins-calendar-matrix-high.png)

## <a name="calculating-delays"></a>Calcolo dei ritardi

Tutti e tre i tipi di margini di sicurezza sono inclusi quando il sistema determina se un ordine è in ritardo.

Ad esempio, un articolo ha un lead time di un giorno e un margine su entrata di tre giorni. Un ordine cliente per questo articolo è impostato come richiesto oggi. In questo caso, il ritardo viene calcolato come *lead time* + *margine su entrata* = quattro giorni. Pertanto, se oggi è il 14 agosto, i quattro giorni di ritardo producono una consegna il 18 agosto. Nella figura seguente viene illustrato questo esempio.

![Esempio di calcolo dei ritardi.](media/safety-margins-delays.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Introduzione all'ottimizzazione della pianificazione](get-started.md)

[Analisi corrispondenza Ottimizzazione pianificazione](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]