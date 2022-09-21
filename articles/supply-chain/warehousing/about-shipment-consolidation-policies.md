---
title: Panoramica dei criteri di consolidamento delle spedizioni
description: Questo articolo offre una panoramica delle funzionalità che forniscono una configurazione flessibile delle politiche di consolidamento delle spedizioni.
author: Mirzaab
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSShipConsolidationError, WHSShipConsolidationSetShipment, WHSShipConsolidationPolicySelect, WHSShipPlanningListPage, TMSCarrierGroup, WHSShipConsolidationTemplate, WHSShipConsolidationTemplateApply, WHSShipConsolidationTemplateCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 7113fc635a7c01e4b9cc44898daa3d2617058b6b
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2022
ms.locfileid: "9427930"
---
# <a name="shipment-consolidation-policies-overview"></a>Panoramica dei criteri di consolidamento delle spedizioni

[!include [banner](../includes/banner.md)]

Il processo di consolidamento delle spedizioni che utilizza criteri di consolidamento delle spedizioni consente il consolidamento automatico delle spedizioni durante il rilascio automatico e manuale al magazzino. Il consolidamento automatizzato disponibile prima dell'introduzione di questa funzionalità aveva campi codificati e si basava sul campo **Consolida spedizione al rilascio al magazzino** impostato per un magazzino.

Le politiche di consolidamento della spedizione vengono utilizzate per le seguenti funzionalità:

- Il processo batch automatizzato di rilascio in magazzino
- Il comando **Rilascia in magazzino** in un ordine cliente o in un ordine di trasferimento
- La pagina **Rilascia in magazzino** dedicata
- Il comando **Rilascia in magazzino** nella pagina **Workbench pianificazione del carico**
- Il consolidamento manuale delle spedizioni nelle pagine **Consolidamento delle spedizioni** e **Workbanch consolidamento spedizione**

Prima dell'introduzione delle politiche di consolidamento delle spedizioni, la funzione di consolidamento esisteva come impostazione a livello di magazzino. Tutti gli ordini per tutti i clienti da un unico magazzino sono stati trattati come se avessero gli stessi requisiti di consolidamento. Le politiche di consolidamento della spedizione aggiungono supporto per scenari in cui diverse organizzazioni hanno requisiti diversi per il consolidamento della spedizione.

Le query vengono utilizzate per identificare i criteri di consolidamento della spedizione applicabile, quindi un insieme modificabile di campi determina il modo in cui le linee di carico sono raggruppate a livello di spedizione. Questo modulo ricorda il modulo seguito dai modelli wave. Inoltre, un'opzione **Consolida con spedizioni esistenti** è stata aggiunta a ciascun criterio. Quando questa opzione è attivata, la procedura *Rilascia in magazzino* trova le spedizioni per il consolidamento cercando tra le spedizioni esistenti create in base allo stesso criterio di consolidamento. In questo caso, il sistema selezionerà una spedizione o un carico esistente invece di crearne uno nuovo. Tuttavia, il sistema si consoliderà solo con spedizioni esistenti con uno stato *Aperto*; spedizioni che appartengono a un rilascio ondata con uno stato *Rilasciato* o superiore non saranno considerate obiettivi per il consolidamento.

Quando la funzionalità *Criteri consolidamento spedizione* è attivata nel sistema, l'impostazione **Consolida spedizione al rilascio al magazzino** precedentemente disponibile nella pagina di configurazione **Magazzini** è nascosta. Per aiutarti a passare alla nuova funzionalità di consolidamento della spedizione, una funzione nella pagina **Criteri di consolidamento della spedizione** ti consente di creare un criterio predefinito che include automaticamente la vecchia impostazione per i magazzini esistenti. Dopo aver creato i criteri predefiniti, l'impostazione **Consolida spedizione al rilascio al magazzino** nella pagina di configurazione **Magazzini** non verrà più considerata. Per ulteriori informazioni, vedi [Configurazione dei criteri di consolidamento delle spedizioni](configure-shipment-consolidation-policies.md).

Puoi usare la pagina **Rilascia in magazzino** per sovrascrivere manualmente i criteri di consolidamento applicabili nello stesso modo in cui è possibile ignorare i criteri di adempimento.

Puoi usare il comando **Rilascia \> Rilascia in magazzino** nella pagina **Workbench pianificazione del carico** per creare carichi in uscita basati sugli ordini clienti e trasferire le righe dell'ordine prima di effettuare il rilascio al magazzino. Questi carichi utilizzano la stessa logica di consolidamento introdotta insieme al consolidamento dei criteri di spedizione.

Puoi usare la pagina **Workbanch consolidamento spedizione** per consolidare le spedizioni esistenti che non sono state ancora confermate ma che sono già state rilasciate al magazzino. Questa funzionalità supporta scenari in cui il processo di rilascio automatizzato, che ha il proprio consolidamento delle spedizioni, viene eseguito più volte al giorno, ma i potenziali consolidamenti aggiuntivi vengono identificati manualmente prima che la spedizione ai corrieri venga completata durante il processo di conferma. Questa funzionalità consente di consolidare le spedizioni in uscita create dall'ordine cliente o dalle righe dell'ordine di trasferimento in qualsiasi momento dopo il rilascio delle spedizioni nel magazzino ma prima che vengano confermate.

La pagina **Workbanch consolidamento spedizione** funziona come il workbench di costruzione del carico in cui è possibile valutare più spedizioni contemporaneamente e assegnare un ordine non consolidato a una spedizione specifica. Puoi applicare i modelli di consolidamento spedizione per valutare più volte i consolidamenti proposti e confermarli. Alcune regole sono implementate per prevenire il consolidamento non autorizzato e per avvisarti di possibili errori.

## <a name="overview-of-new-functionality"></a>Panoramica di nuove funzionalità

Questa sezione descrive le pagine, i comandi e le funzionalità che vengono modificati o aggiunti quando si abilita e si utilizza la funzionalità *Criteri di consolidamento della spedizione*.

### <a name="shipment-consolidation-policies-page"></a>Pagina Criteri di consolidamento della spedizione

I criteri sono differenziati per tipo di ordine di lavoro. Il tipo **Ordini cliente** rappresenta le spedizioni _Ordini cliente_ e il tipo **Ordini di trasferimento** rappresenta le spedizioni _Uscita di trasferimento_.

Ciascun criterio di consolidamento della spedizione ha una query che definisce quando viene applicato e un numero progressivo che determina l'ordine di esecuzione. Il consolidamento viene applicato per ciascuna combinazione unica dei campi selezionati. Un parametro aggiuntivo fornito viene utilizzato per il consolidamento con spedizioni (aperte) esistenti. I criteri vengono valutati e applicati ogni volta che viene creata una nuova spedizione (prima dell'elaborazione delle ondate).

Se in un criterio mancano dei campi obbligatori o se include campi proibiti, il criterio viene contrassegnato come non valido nella sezione **Selezionato**. Gli elenchi di campi obbligatori e vietati sono codificati e possono essere estesi.

Il seguente elenco mostra i campi obbligatori. Poiché le spedizioni sono sempre suddivise in base a questi campi, non puoi raggruppare più spedizioni con valori diversi per questi campi.

- Per gli ordini cliente:

    - **Numero di conto:** _WHSShipmentTable.AccountNum_
    - **Destinatario consegna:** _WHSShipmentTable.DeliveryName_
    - **Indirizzo postale (RecId):** _WHSShipmentTable.DeliveryPostalAddress_
    - **Magazzino:** _WHSShipmentTable.InventLocationId_

- Per ordini di trasferimento:

    - **Dal magazzino:** _InventTransferTable.InventLocationIdFrom_
    - **Al magazzino:** _InventTransferTable.InventLocationIdTo_

I seguenti campi non sono disponibili per tutti i tipi di documento. Questi campi non sono visibili nell'interfaccia utente e non possono essere utilizzati per il consolidamento.

- **ID spedizione:** _WHSShipmentTable.ShipmentId_
- **Stato:** _WHSShipmentTable.ShipmentStatus_
- **Criteri di consolidamento spedizioni:** _WHSShipmentTable.ShipConsolidationPolicyName_
- **Tipo di transazione di lavoro:** _WHSShipmentTable.WorkTransType_
- **ID ondata:** _WHSShipmentTable.WaveId_
- **ID caricamento:** _WHSShipmentTable.LoadId_
- **ID spedizione:** _WHSLoadLine.ShipmentId_
- **ID caricamento:** _WHSLoadLine.LoadId_

Per impostazione predefinita, quando si crea un criterio, l'insieme di campi obbligatori viene utilizzato come campi di consolidamento. Tuttavia, puoi modificare l'elenco utilizzando i pulsanti freccia sinistra e freccia destra. Il processo è simile al processo di selezione dei metodi nei modelli ondata.

I valori selezionati dagli utenti per questi campi verranno utilizzati per tutte le spedizioni di nuova creazione o verranno aggiunti alle spedizioni esistenti durante il consolidamento con tali spedizioni. Quando le due spedizioni hanno lo stesso valore per un campo selezionato per il consolidamento di tali spedizioni, le spedizioni vengono consolidate. Lo stesso principio si applica a tutti i campi di consolidamento successivi selezionati. Se i valori differiscono, la seconda spedizione viene scartata e verrà selezionata per una nuova spedizione. Il processo di consolidamento automatizzato consiste nel creare tutte le combinazioni univoche di valori per i campi di consolidamento della spedizione e quindi nell'assegnare una spedizione alla combinazione pertinente.

I campi non selezionati vengono ignorati durante il processo di consolidamento. Se due spedizioni hanno valori diversi per un campo non selezionato, il campo viene cancellato (ovvero è impostato su vuoto). Se entrambe le spedizioni hanno lo stesso valore per un campo non selezionato, il campo viene compilato.

L'elenco dei campi di consolidamento (ovvero i campi che verranno cancellati se hanno valori diversi) è codificato. L'elenco contiene tutti i campi inizializzati da un ordine cliente o da una riga ordine di trasferimento quando viene creata una nuova spedizione. In altre parole, se un campo non è inizializzato da un ordine cliente o da una riga ordine di trasferimento, viene ignorato quando vengono aggiunti nuovi dati a una spedizione esistente.

### <a name="release-to-warehouse-page"></a>Pagina Rilascia in magazzino

- Un nuovo campo nella griglia inferiore mostra i criteri di consolidamento che sono stati applicati.
- Un nuovo pulsante consente di selezionare e/o sovrascrivere manualmente i criteri di consolidamento.

### <a name="release-to-warehouse-command-on-the-load-planning-workbench-page"></a>Comando Rilascia in magazzino nella pagina Workbench pianificazione del carico

- La logica è stata modificata in modo da utilizzare i criteri di consolidamento applicati.
- Le spedizioni sono ora consolidate solo all'interno di un singolo carico.

### <a name="consolidate-shipments-page"></a>Pagina Consolida spedizioni

- La ricerca di spedizioni simili (ovvero candidati al consolidamento) è stata modificata in modo da utilizzare i campi selezionati nei criteri di consolidamento delle spedizioni.
- I campi con valori diversi in spedizioni diverse sono ora impostati su vuoti. In precedenza, venivano utilizzati i valori della spedizione "base" selezionata.

### <a name="shipment-consolidation-workbench-page"></a>Pagina Workbanch consolidamento spedizione

- La nuova funzionalità replica il processo di consolidamento manuale su una scala più ampia.
- Ora puoi aprire questa pagina dal menu **Rilascia in magazzino** nel modulo **Gestione magazzino**.
- L'algoritmo analizza le spedizioni esistenti che non sono ancora state spedite. Propone quindi il consolidamento, in base ai campi selezionati nei criteri di consolidamento.

## <a name="comparison-of-functionality"></a>Confronto di funzionalità

La tabella seguente riepiloga il funzionamento del consolidamento delle spedizioni quando non si utilizzano i criteri di consolidamento delle spedizioni e quando vengono utilizzati.

| Senza criteri di consolidamento delle spedizioni | Con criteri di consolidamento delle spedizioni |
|---|----|
| Non applicabile | Le spedizioni di vendita o di trasferimento selezionate per il consolidamento devono avere lo stesso criterio di consolidamento della spedizione che viene creata o devono essere assegnate a una spedizione aperta (quando l'opzione **Consolida con spedizioni esistenti** è attivata). |
| La procedura *Rilascia in magazzino* non cerca tra le spedizioni esistenti per trovare una spedizione per il consolidamento. Solo le spedizioni create da un'istanza corrente della procedura *Rilascia in magazzino* viene utilizzata per trovare una spedizione per il consolidamento. | Se l'opzione **Consolida con spedizioni esistenti** è attivata per un criterio di consolidamento attualmente in uso, la procedura *Rilascia in magazzino* cerca tra le spedizioni esistenti che sono state create sulla base dello stesso criterio di consolidamento per trovare una spedizione per il consolidamento. Pertanto, se si dispone di due criteri, una spedizione creata in base al criterio 2 non verrà mai consolidata con una spedizione creata in base al criterio 1. |
| Non applicabile | Se un elenco di campi dei criteri di consolidamento è vuoto o se non è possibile trovare un criterio, viene creata una nuova spedizione per ciascun ordine cliente o riga di ordine di trasferimento. |
| Il seguente campo di consolidamento definisce la combinazione univoca di valori utilizzata per consolidare le spedizioni per una *riga di trasferimento*. Tutti gli altri campi vengono ignorati.<ul><li>Numero ordine (OrderNum)</li></ul> | I seguenti campi di consolidamento definiscono la combinazione univoca di valori utilizzata per consolidare le spedizioni per una *riga di trasferimento*. Tutti gli altri campi vengono ignorati.<ul><li>Numero ordine (OrderNum)</li><li>Destinatario consegna (DeliveryName)</li><li>Indirizzo postale (DeliveryPostalAddress)</li><li>Codice paese ISO (CountryRegionISOCode)</li><li>Indirizzo (Address)</li><li>Sito (InventSiteId)</li><li>Magazzino (InventLocationId)</li><li>Vettore spedizione (CarrierCode)</li><li>Servizio trasporto (CarrierServiceCode)</li><li>Modalità di consegna (ModeCode) \*</li><li>Gruppo vettore (CarrierGroupCode)</li><li>Termini di consegna (DlvTermId)</li></ul><p>Questi campi sono gli unici campi disponibili e inizializzati quando viene creata una nuova spedizione.</p><p>\* Nota: *ModeCode* è la **Modalità** assegnata al **Vettore spedizione** selezionato per una riga di trasferimento (non la **Modalità di consegna** selezionata per una riga di trasferimento). Se scegli di includere *Modalità di consegna (ModeCode)* tra i criteri di consolidamento, il sistema consoliderà solo le righe di trasferimento con lo stesso valore **Modalità** a condizione che **Vettore spedizione**, **Servizio di trasporto** e **Modalità di consegna** siano tutti definiti per la riga (indipendentemente dai loro valori). Inoltre, il sistema consoliderà anche tutte le righe di trasferimento in cui **Modalità** è vuoto.</p> |
| I seguenti campi di consolidamento definiscono la combinazione univoca di valori utilizzata per consolidare le spedizioni per una *riga di vendita*. Tutti gli altri campi vengono ignorati.<ul><li>Numero ordine (OrderNum)</li><li>Riferimento cliente (CustomerRef)</li><li>Richiesta di approvvigionamento cliente (CustomerReq)</li><li>Termini di consegna (DlvTermId)</li></ul> | I seguenti campi di consolidamento definiscono la combinazione univoca di valori utilizzata per consolidare le spedizioni per una *riga di vendita*. Tutti gli altri campi vengono ignorati.<ul><li>Numero ordine (OrderNum)</li><li>Numero account (AccountNum)</li><li>Destinatario consegna (DeliveryName)</li><li>Indirizzo postale (DeliveryPostalAddress)</li><li>Codice paese ISO (CountryRegionISOCode)</li><li>Indirizzo (Address)</li><li>Sito (InventSiteId)</li><li>Magazzino (InventLocationId)</li><li>Vettore spedizione (CarrierCode)</li><li>Servizio trasporto (CarrierServiceCode)</li><li>Modalità di consegna (ModeCode) \*</li><li>Gruppo vettore (CarrierGroupCode)</li><li>ID gestore (BrokerCode)</li><li>Direzione (LoadDirection)</li><li>Termini di consegna (DlvTermId)</li><li>Riferimento cliente (CustomerRef)</li><li>Richiesta di approvvigionamento cliente (CustomerReq)</li></ul><p>Questi campi sono gli unici campi disponibili e inizializzati quando viene creata una nuova spedizione.</p><p>\* Nota: *ModeCode* è la **Modalità** assegnata al **Vettore spedizione** selezionato per una riga di vendita (non la **Modalità di consegna** selezionata per una riga di vendita). Se scegli di includere *Modalità di consegna (ModeCode)* tra i criteri di consolidamento, il sistema consoliderà solo le righe di vendita con lo stesso valore **Modalità** a condizione che **Vettore spedizione**, **Servizio di trasporto** e **Modalità di consegna** siano tutti definiti per la riga (indipendentemente dai loro valori). Inoltre, il sistema consoliderà anche tutte le righe di vendita in cui **Modalità** è vuoto.</p> |
| Non applicabile | I seguenti campi di consolidamento sono obbligatori per una *riga vendita* e non possono essere rimossi:<ul><li>Numero account (AccountNum)</li><li>Destinatario consegna (DeliveryName)</li><li>Indirizzo postale (DeliveryPostalAddress)</li><li>Magazzino (InventLocationId)</li></ul>Per impostazione predefinita, questi campi verranno assegnati quando viene creato un nuovo criterio. Non possono essere rimossi. |
| La procedura *Rilascio carichi in magazzino* nella pagina **Workbench pianificazione carico** usa un proprio codice separato per creare spedizioni e ondate. | I criteri di consolidamento della spedizione vengono applicati per determinare quali campi devono essere valutati per il consolidamento. Le spedizioni sono consolidate solo all'interno di un singolo carico. |
| Seleziona manualmente **Consolida spedizioni** nella pagina **Tutte le spedizioni** e quindi seleziona una spedizione "base" di destinazione. Il filtro suggerirà eventuali spedizioni esistenti con valori corrispondenti per diversi campi chiave. | Seleziona manualmente **Consolida spedizioni** nella pagina **Tutte le spedizioni** e quindi seleziona una spedizione "base" di destinazione. Il sistema suggerirà altre spedizioni esistenti abbinando i valori di diversi campi chiave configurati per i relativi criteri di consolidamento delle spedizioni. |
| Puoi usare il comando **Consolida spedizioni** nella pagina **Tutte le spedizioni** per una sola spedizione. | La pagina **Workbanch consolidamento spedizione** ti aiuta a trovare una serie di spedizioni che non sono ancora in uno stato spedito. Queste spedizioni vengono analizzate in base a diversi campi chiave configurati nei criteri di consolidamento della spedizione. Tutte le spedizioni in cui i valori di questi campi corrispondono sono consigliate per il consolidamento.<p>Puoi mantenere manualmente il consolidamento rimuovendo le spedizioni dai consolidamenti suggeriti e/o aggiungendo spedizioni ad essi. Possono verificarsi diversi tipi di errori, ma è possibile sovrascriverne alcuni.</p> |
| **Nota di progettazione:** la procedura *Rilascio automatico degli ordini cliente a magazzino* suddivide le righe di vendita in gruppi. Ciascun gruppo ha il suo valore **ReleaseToWarehouseId** univoco e viene elaborato separatamente dalla procedura *Rilascia in magazzino*. Questa procedura crea nuovo lavoro indipendentemente dall'impostazione dell'interruzione di lavoro. | **Nota di progettazione:** la procedura *Rilascio automatico degli ordini cliente a magazzino* assegna lo stesso valore **ReleaseToWarehouseId** per tutte le righe di vendita che vengono elaborate. Tutte le righe di vendita vengono elaborate dalla procedura *Rilascia in magazzino* allo stesso tempo. Per garantire il comportamento precedente, devi configurare l'interruzione di lavoro per l'ID della spedizione. |

## <a name="additional-resources"></a>Risorse aggiuntive

- [Configurazione dei criteri di consolidamento delle spedizioni](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]