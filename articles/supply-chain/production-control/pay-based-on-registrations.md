---
title: Retribuzione basata sulle registrazioni
description: In questo argomento viene descritto come la retribuzione viene calcolata in base alle registrazioni lavoratore.
author: johanhoffmann
manager: tfehr
ms.date: 03/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgCalcApproveWeekView, JmgProdStatusListPagePayrollCostDetails, JmgPayCountTable, JmgPayStatConfig, JmgOvertimeSlize, JmgPayAgreementOverride, JmgPayCountSum, JmgPayAdjustSetup, JmgPayAdjustCostType, JmgPayEmployee, JmgMESBreak, JmgPayAddTable, JmgPayAddTransSelectTransId, JmgPayrollCostDetailsPart, jmgProdStatusListPagePayrollCosts, JmgPayrollCostPart, JmgPayEvents, JmgTermRegPayStatSetup, JmgPayStatGroup, JmgPayAddTrans, JmgPayStatTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-03-20
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 98ca6f7713b2f605a49a97d391fb8485bea78c4b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966382"
---
# <a name="pay-based-on-registrations"></a>Retribuzione basata sulle registrazioni

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto in dettaglio come la retribuzione viene calcolata in base alle registrazioni lavoratore. Include gli esempi che mostrano come le diverse combinazioni di opzioni di impostazione disponibili per il calcolo influenzano il risultato. Di seguito vengono riportate alcune delle aree coperte:

- Orario flessibile
- Straordinario
- Pause
- Codici Switch
- Elementi retributivi
- Accordi salariali
- Parametri di calcolo di Orario e presenze
- Assenza

## <a name="the-use-of-flex-time"></a>Utilizzo dell'orario flessibile

I periodi di orario flessibile vengono impostati nei profili tempo utilizzati in Orario e presenze. Sono disponibili due tipi di profilo flessibile: **Flessibilità in eccesso** e **Flessibilità in difetto**. Quando un lavoratore registra il tempo in un periodo di flessibilità in eccesso, il relativo saldo flessibilità viene aumentato del numero di ore lavorate. Il lavoratore non riceve alcuna compensazione per le ore di lavoro svolte durante il periodo di flessibilità in eccesso. Il lavoratore può tuttavia richiedere un permesso durante i periodi di flessibilità in difetto e compensare con le ore del proprio saldo flessibilità. Di conseguenza, un permesso durante i periodi di flessibilità è considerato come assenza dal sistema.

## <a name="scenarios-based-on-flex-periods"></a>Scenari basati su periodi di flessibilità

I due scenari che seguono sono basati su un profilo flessibile che rappresenta un giorno lavorativo. Per entrambi gli scenari, la retribuzione viene calcolata in base al periodo di flessibilità in cui il lavoratore registra l'entrata e l'uscita.

### <a name="flex-profile-for-one-workday"></a>Profilo flessibile per un giorno lavorativo

| Tipo profilo  | Avvio    | Fine periodo      | Giorno     |
|---------------|----------|----------|---------|
| Straordinario     | 00:00 | 06:00 | Lunedì  |
| Flessibilità in eccesso         | 06:00 | 07:00 | Lunedì  |
| Entrata      | 07:00 | 07:00 | Lunedì  |
| Orario standard | 07:00 | 14:30 | Lunedì  |
| Flessibilità in difetto-         | 14:30 | 15:30 | Lunedì  |
| Uscita     | 15:30 | 15:30 | Lunedì  |
| Straordinario     | 15:30 | 06:00 | Martedì |

### <a name="scenario-1-a-worker-registers-clock-in-during-a-flex-period-and-clock-out-during-a-flex--period"></a>Scenario 1: un lavoratore registra l'ora di entrata durante un periodo di flessibilità in eccesso e l'ora di uscita durante un periodo di flessibilità in difetto

Le registrazioni del lavoratore per il giorno sono riportate di seguito.

| Tipo di registrazione giornale | Avvio    | Fine periodo      |
|---------------------------|----------|----------|
| Entrata                  | 06:30 | 06:30 |
| Processo di produzione            | 06:30 | 14:45 |
| Uscita                 | 14:45 | 14:45 |

Le registrazioni del lavoratori per il giorno vengono calcolate e trasferite al sistema di retribuzione nella pagina **Approva** (**Orario e presenze** &gt; **Rivedi e approva** &gt; **Approva**). Dopo che le registrazioni sono state calcolate, il risultato del calcolo può essere visualizzato nella scheda **Periodi**. 

Per comprendere questo scenario, vedere i campi seguenti.

| Flessibilità in eccesso | Flessibilità in difetto | Tempo | Tempo retribuito |
|--------|--------|------|----------|
| 0,50   | 0.75   | 8.25 | 8.50     |

#### <a name="calculation-of-flex"></a>Calcolo della flessibilità in eccesso

A seconda del profilo flessibile, il periodo compreso tra le 06:00 e le 07:00 è un periodo di flessibilità in eccesso. Pertanto, se il lavoratore entra alle 06:30, guadagna 0,5 ore. Questo periodo di tempo viene aggiunto al conto di flessibilità del lavoratore.

#### <a name="calculation-of-flex-"></a>Calcolo della flessibilità in difetto

A seconda del profilo flessibile, il periodo di flessibilità in difetto inizia alle 14:30 e termina alle 15:30. Pertanto, se il lavoratore esce alle 14:45, i 45 minuti (0,75 ore) che rimarranno nel periodo di flessibilità in difetto vengono registrati come tempo retribuito e lo stesso periodo di tempo viene dedotto dal conto flessibilità del lavoratore. I 45 minuti sono inclusi nel tempo retribuito poiché il lavoratore viene retribuito per i 45 minuti rimanenti nel periodo di flessibilità in difetto. Se il lavoratore è assente durante il periodo di flessibilità in difetto, i 45 minuti verranno sottratti dal conto flessibilità.

#### <a name="calculation-of-time"></a>Calcolo del tempo

L'orario corrisponde al periodo tra l'ora di entrata e quella di uscita, dalle 06:30 alle 14:45, ovvero 8,25 ore.

#### <a name="calculation-of-pay-time"></a>Calcolo del tempo retribuito

Il tempo retribuito è il tempo durante il quale un lavoratore viene retribuito. In questo esempio, il lavoratore è al lavoro per 8,25 ore (**Ora**). Tuttavia, il **Tempo retribuito** viene calcolato come 8,50 ore perché il lavoratore ha diritto a essere retribuito durante il periodo di flessibilità in difetto dopo l'uscita. Il tempo retribuito equivale alle ore lavorative previste perché il tempo di flessibilità in eccesso viene aggiunto al conto della flessibilità del lavoratore, non al tempo retribuito. Il tempo di assenza durante il periodo di flessibilità in difetto viene compensato dal tempo retribuito e dedotto dal conto flessibilità del lavoratore.

| Tempo              | Tipo di registrazione | Tempo retribuito (ore)      |
|-------------------|-------------------|-----------------------|
| 6:30 - 7:00 | Flessibilità in eccesso             | 0                     |
| 7:00 - 14:45 | Orario standard     | 7.75                  |
| 14:45 - 15:30 | Flessibilità in difetto-             | 0,75 (periodo di assenza) |
|                   | Totale             | 8.50                  |

### <a name="scenario-2-a-worker-works-during-the-whole-flex--period-and-also-works-overtime"></a>Scenario 2: un dipendente lavora durante l'intero periodo di flessibilità in difetto e lavora anche ore di straordinario

Le registrazioni del lavoratore per il giorno sono riportate di seguito.

| Tipo di registrazione giornale | Avvio    | Fine periodo      |
|---------------------------|----------|----------|
| Entrata                  | 06:30 | 06:30 |
| Processo di produzione            | 06:30 | 17:00 |
| Uscita                 | 17:00 | 17:00 |

Dopo avere calcolato le registrazioni di giornale nella pagina **Approva**, è possibile visualizzare il risultato del calcolo nella scheda **Periodi**. Per comprendere questo scenario, vedere i campi seguenti.

| Flessibilità in eccesso | Flessibilità in difetto | Tempo  | Tempo retribuito | Straordinario retribuito |
|--------|--------|-------|----------|--------------|
| 0,50   | 0,00   | 10,50 | 10.00    | 1.50         |

#### <a name="calculation-of-flex"></a>Calcolo della flessibilità in eccesso

A seconda del profilo flessibile, il periodo compreso tra le 06:00 e le 07:00 è un periodo di flessibilità in eccesso. Pertanto, se il lavoratore entra alle 06:30, guadagna 0,5 ore di orario flessibile in eccesso sul suo saldo flessibilità.

#### <a name="calculation-of-flex-"></a>Calcolo della flessibilità in difetto

Poiché il lavoratore lavora nel periodo di flessibilità in difetto, la flessibilità in difetto non viene calcolata. La flessibilità in difetto viene calcolata solo se il lavoratore è assente nel periodo di flessibilità in difetto. In una prospettiva di pagamento, se il lavoratore lavora durante il periodo di flessibilità in difetto, ha diritto alla tariffa retributiva definita per l'orario standard. Se il lavoratore è assente durante il periodo di flessibilità in difetto, i 45 minuti vengono sottratti dal conto di flessibilità.

#### <a name="calculation-of-time"></a>Calcolo del tempo

L'orario corrisponde al periodo tra l'ora di entrata alle 06:30 e quella di uscita alle 17:00, ovvero 10,50 ore.

#### <a name="calculation-of-pay-time"></a>Calcolo del tempo retribuito

In questo esempio, il lavoratore lavora per 10,50 ore (**Ora**). Tuttavia, il **Tempo retribuito** viene calcolato come 10,00 ore perché il lavoratore non ha diritto a essere retribuito durante il periodo di flessibilità in eccesso.

#### <a name="calculation-of-pay-overtime"></a>Calcolo dello straordinario retribuito

| Tempo               | Tipo di registrazione | Tempo retribuito (ore) |
|--------------------|-------------------|------------------|
| 6:30 - 7:00  | Flessibilità in eccesso             | 0                |
| 7:00 - 14:30  | Orario standard     | 7.50             |
| 14:30 - 15:30  | Flessibilità in difetto-             | 1,00             |
| 15:30 - 17:00 | Straordinario          | 1.50             |
|                    | Totale             | 10.00            |

### <a name="generation-of-pay-items"></a>Generazione di elementi retributivi

Le registrazioni dei lavoratori per il giorno corrente possono essere trasferite dalla pagina **Approva**. Durante il processo di trasferimento vengono generati elementi retributivi e registrazioni trasferite. Gli elementi retributivi rappresentano una scomposizione del tempo retribuito in orario standard, straordinario, tempo di pausa retribuito e così via.

Per aprire l'elenco di elementi retributivi, selezionare **Orario e presenze** &gt; **Rivedi e approva** &gt; **Approva**. Quindi selezionare **Richiesta info** &gt; **Registrazioni trasferite**.

Gli elementi retributivi sono la base della retribuzione di un lavoratore. È possibile generare un file contenente informazioni da elementi retributivi e trasferire quel file in un sistema di gestione delle retribuzioni.

Durante il processo di trasferimento, il tempo e i costi delle attività di progetto e di produzione vengono trasferiti in giornali di progetto e di produzione per rappresentare le spese di costi e di tempo. Le registrazioni trasferite costituiscono la base dell'orario e del prezzo di costo orario per ordini di produzione e progetti. È possibile aprire le registrazioni trasferite utilizzando il menu **Richiesta info** della pagina **Approva**.

Ad esempio, per lo scenario 2, vengono generati gli articoli di retribuzione seguenti.

| Tipo di retribuzione     | Tipo di retribuzione | Unità retributive | Tasso  | Costo totale |
|---------------|----------|-----------|-------|------------|
| Orario standard | 1201     | 10.0      | 10    | 100        |
| Straordinario      | 1301     | 1.50      | 5     | 7.50       |
|               |          |           | Totale | 107.50     |

L'elemento retributivo per l'orario standard ha un'unità retributiva di 10 ore che copre l'orario standard, l'orario flessibile in difetto e lo straordinario. Orario standard, orario flessibile in difetto e straordinario vengono consolidati in un elemento retributivo in quanto tutti i tipi vengono calcolati come orario standard, in base all'impostazione predefinita di un parametro nella pagina **Parametri di calcolo** (**Orario e presenze** &gt; **Impostazione** &gt; **Parametri di calcolo**). Lo straordinario viene calcolato in aggiunta all'orario standard utilizzando una tariffa aggiuntiva pari a 5.

Se si desidera distinguere chiaramente tra orario standard e straordinario, in modo che le unità retributive per i tipi di retribuzione coprano solo la spesa di tempo effettiva nell'orario standard o nello straordinario, le unità retributive per l'orario standard devono essere calcolate come 8,50 e le unità retributive per lo straordinario devono essere calcolate come 1,50.

Per configurare il sistema in modo da distinguere chiaramente l'orario standard e lo straordinario, è necessario escludere lo straordinario dell'orario standard. È inoltre necessario modificare l'impostazione del tipo di retribuzione per il lavoro straordinario in modo che la relativa retribuzione copra tutti i pagamenti per le ore di lavoro straordinario.

### <a name="exclude-overtime-from-the-standard-time"></a>Escludere lo straordinario dall'orario standard

Nella pagina **Parametri di calcolo**, selezionare **Straordinario** come tipo di specifica profilo e impostare l'opzione **Tempo retribuito** su **No**, come illustrato qui.

| Specifica reg. | Tipo di specifica profilo | Calcolo   |     | Pagato         |     |
|--------------------|----------------------------|---------------|-----|--------------|-----|
| Orario di lavoro       | Straordinario                   | Orario standard | Sì | Tempo retribuito     | No  |
|                    |                            | Tempo retribuito      | Sì | Straordinario retribuito | Sì |

Dopo la rettifica dei parametri di calcolo, vengono generati gli elementi di retribuzione seguenti.

| Tipo di retribuzione     | Tipo di retribuzione | Unità retributive | Tasso  | Costo totale |
|---------------|----------|-----------|-------|------------|
| Orario standard | 1201     | 8.50      | 10    | 85.0       |
| Straordinario      | 1301     | 1.50      | 15    | 22.50      |
|               |          |           | Totale | 107.50     |

> [!NOTE]
> I parametri di calcolo hanno un'impostazione standard consigliata. In genere è necessario prestare attenzione quando si modificano questi parametri. Per ripristinare le impostazioni standard consigliate, nella pagina **Parametri di calcolo**, selezionare **Ripristina valori**.

### <a name="allow-a-deviation-from-the-standard-pay-profiles"></a>Consentire una deviazione dai profili di retribuzione standard

Nella pagina **Profili** (**Orario e presenze** &gt; **Impostazione** &gt; **Profili tempo** &gt; **Profili**), è possibile impostare i tipi di profilo che includono codici Switch e pause.

### <a name="switch-codes"></a>Codici Switch

È possibile utilizzare codici Switch per consentire ai lavoratori di discostarsi dal relativo tipo di profilo modificando un differente tipo di profilo. Ad esempio, è possibile consentire a un lavoratore di modificare il periodo di flessibilità in eccesso in straordinario. Un lavoratore può aggiungere un codice Switch durante la registrazione oppure è possibile assegnare l'attività di aggiunta di un codice Switch all'approvatore delle registrazioni.

Prima di poter utilizzare un codice Switch, è necessario definirlo come tipo di attività indiretta. È quindi necessario aggiungere il codice Switch al profilo orario per il periodo in cui si desidera consentire una modifica del tipo di profilo. Ad esempio, attenersi alla procedura seguente per creare un codice Switch che consenta di modificare il periodo di flessibilità in eccesso dalle 06:00 alle 07:00 in straordinario.

1. Creare un codice Switch denominato **OTBCI (Converti orario flessibile in straordinario prima dell'ora di entrata)**. Selezionare **Orario e presenze** &gt; **Gestisci attività indirette** &gt; **Attività indirette**.
2. Nella colonna **Codice Switch**, aggiungere OTBCI alla riga Flessibilità in eccesso nel profilo orario.
3. Nella colonna **Secondario**, aggiungere il tipo di profilo **Straordinario**.

Considerare il seguente profilo flessibile che rappresenta un giorno lavorativo.

| Tipo profilo  | Avvio    | Fine periodo      | Giorno     |
|---------------|----------|----------|---------|
| Straordinario     | 00:00 | 06:00 | Lunedì  |
| Flessibilità in eccesso         | 06:00 | 07:00 | Lunedì  |
| Entrata      | 07:00 | 07:00 | Lunedì  |
| Orario standard | 07:00 | 14:30 | Lunedì  |
| Flessibilità in difetto-         | 14:30 | 15:30 | Lunedì  |
| Uscita     | 15:30 | 15:30 | Lunedì  |
| Straordinario     | 15:30 | 06:00 | Martedì |

Queste sono le registrazioni del lavoratore per il giorno.

| Tipo di registrazione giornale | Avvio    | Fine periodo      |
|---------------------------|----------|----------|
| Entrata                  | 06:30 | 06:30 |
| Processo di produzione            | 06:30 | 14:45 |
| Uscita                 | 17:00 | 17:00 |

I seguenti elementi retributivi vengono generati dopo il trasferimento.

| Tipo di retribuzione     | Tipo di retribuzione | Unità retributive | Tasso  | Costo totale |
|---------------|----------|-----------|-------|------------|
| Orario standard | 1201     | 8.50      | 10    | 85.0       |
| Straordinario      | 1305     | 1.50      | 15    | 22.50      |
|               |          |           | Totale | 107.50     |

Nella pagina **Approva**, annullare il trasferimento, quindi utilizzare il menu **Codice Switch** per applicare il codice Switch **OTBCI**. Quando si trasferiscono le registrazioni una seconda volta, vengono generati i seguenti elementi retributivi.

| Tipo di retribuzione     | Tipo di retribuzione | Unità retributive | Tasso  | Costo totale |
|---------------|----------|-----------|-------|------------|
| Orario standard | 1201     | 8.50      | 10    | 80.0       |
| Straordinario      | 1305     | 2.00      | 15    | 30.0       |
|               |          |           | Totale | 107.50     |

> [!NOTE]
> Quando si applica il codice Switch, lo straordinario viene aumentato di 0,5 ore, da 1,50 a 2,00. Le 0,5 ore costituiscono la conversione in straordinario dell'orario flessibile in eccesso registrato, ovvero dalle 6:30 alle 07:00.

### <a name="breaks"></a>Pause

Le pause dal lavoro influiscono sul calcolo della retribuzione del lavoratore. Le pause vengono definite come tipo di attività indiretta. Possono essere definite come **Pagata**, per consentire l'aggiunta della pausa alla retribuzione del lavoratore, o come **Non pagata**, per impedire l'aggiunta della pausa alla retribuzione del lavoratore. Una pausa può essere definita anche come **Pianificata** o **Registrata**.

#### <a name="planned-breaks"></a>Pause pianificate

Se una società ha un tempo di pausa fisso, ad esempio una pausa fissa per il pranzo, la pausa può essere predefinita nel profilo orario. In questo caso, il lavoratore non deve registrare la pausa nelle pagina Scheda processo. La pausa viene invece conteggiata automaticamente quando le registrazioni del lavoratore sono calcolate nella pagina **Approva**.

#### <a name="registered-breaks"></a>Pause registrate

Se una società non utilizza pause previste, i lavoratori possono registrare le pause durante la giornata lavorativa. Le pause registrate possono essere utilizzate, ad esempio, se un lavoratore lavora in base a un profilo di orario flessibile che non ha ore di entrata e di uscita definite. Le pause registrate sono un tipo di attività indiretta. Il lavoratore registra la pausa nella pagina **Terminale scheda processi** o **Dispositivo schede processo**. In entrambe queste pagine, l'utente può selezionare il tipo di pausa in un elenco di attività di pausa predefinite.

#### <a name="paid-and-unpaid-breaks"></a>Pause retribuite e non retribuite

Le attività di pausa possono essere impostate come **Pagata** o **Non pagata**. Una pausa retribuita viene inclusa nel calcolo del tempo di retribuzione e il sistema utilizza il tipo di pagamento che è definito nell'accordo salariale per il tipo di registrazione **Pausa**.

### <a name="example-of-a-planned-break"></a>Esempio di una pausa pianificata

Considerare il seguente profilo orario che include una pausa pranzo non retribuita.

| Tipo profilo  | Avvio    | Fine periodo      | Giorno     |
|---------------|----------|----------|---------|
| Straordinario     | 00:00 | 06:00 | Lunedì  |
| Flessibilità in eccesso         | 06:00 | 07:00 | Lunedì  |
| Entrata      | 07:00 | 07:00 | Lunedì  |
| Orario standard | 07:00 | 12:00 | Lunedì  |
| Interruzione         | 12:00 | 12:30 | Lunedì  |
| Orario standard | 12:30 | 14:30 | Lunedì  |
| Flessibilità in difetto-         | 14:30 | 15:30 | Lunedì  |
| Uscita     | 15:30 | 15:30 | Lunedì  |
| Straordinario     | 15:30 | 06:00 | Martedì |

Queste sono le registrazioni del lavoratore per il giorno.

| Tipo di registrazione giornale | Avvio    | Fine periodo      |
|---------------------------|----------|----------|
| Entrata                  | 06:30 | 06:30 |
| Processo di produzione            | 06:30 | 14:45 |
| Uscita                 | 17:00 | 17:00 |

Dopo avere calcolato le registrazioni di giornale nella pagina **Approva**, è possibile visualizzare il risultato del calcolo nella scheda **Periodi**. Per comprendere questo scenario, vedere i campi seguenti.

| Flessibilità in eccesso | Flessibilità in difetto | Tempo  | Tempo retribuito | Tempo pause non retribuite | Straordinario retribuito |
|--------|--------|-------|----------|---------------------|--------------|
| 0,50   | 0,00   | 10,50 | 9.50     | 0.5                 | 1.50         |

> [!NOTE] 
> Il sistema ha calcolato 0,5 ore di tempo di pausa non retribuito e quel tempo non fa parte del tempo retribuito.

### <a name="example-of-a-registered-break"></a>Esempio di una pausa registrata

Considerare il seguente profilo orario che non include pause pianificate.

| Tipo profilo  | Avvio    | Fine periodo      | Giorno     |
|---------------|----------|----------|---------|
| Straordinario     | 00:00 | 06:00 | Lunedì  |
| Flessibilità in eccesso         | 06:00 | 07:00 | Lunedì  |
| Entrata      | 07:00 | 07:00 | Lunedì  |
| Orario standard | 07:00 | 14:30 | Lunedì  |
| Flessibilità in difetto-         | 14:30 | 15:30 | Lunedì  |
| Uscita     | 15:30 | 15:30 | Lunedì  |
| Straordinario     | 15:30 | 06:00 | Martedì |

Queste sono le registrazioni del lavoratore per il giorno.

| Tipo di registrazione giornale | Avvio    | Fine periodo      |
|---------------------------|----------|----------|
| Entrata                  | 06:30 | 06:30 |
| Processo di produzione            | 06:30 | 17:00 |
| Interruzione                     | 12:03 | 12:32 |
| Uscita                 | 17:00 | 17:00 |

Quando le registrazioni vengono calcolate, viene calcolata la durata delle attività.

| Tipo di registrazione giornale | Avvio    | Fine periodo      | Tempo  |
|---------------------------|----------|----------|-------|
| Entrata                  | 06:30 | 06:30 |       |
| Processo di produzione            | 06:30 | 17:00 | 10.00 |
| Interruzione                     | 12:03 | 12:32 | 0,50  |
| Uscita                 | 17:00 | 17:00 |       |

> [!NOTE]
> Il tempo della pausa viene eseguito in parallelo con il tempo dell'attività (un processo di produzione, in questo esempio). Questo comportamento è sempre utilizzato per le attività di pausa. Quando le registrazioni vengono calcolate, il tempo di pausa viene sottratto dall'orario attività. In questo caso, il processo di produzione ha una durata di 10,50 ore, ma l'orario viene calcolato come 10 in quanto 0,5 ore di pausa vengono sottratte dall'orario attività.

Dopo avere calcolato le registrazioni di giornale nella pagina **Approva**, è possibile visualizzare il risultato del calcolo nella scheda **Periodi**. Per comprendere questo scenario, vedere i campi seguenti.

| Flessibilità in eccesso | Flessibilità in difetto | Tempo  | Tempo retribuito | Tempo pause non retribuite | Straordinario retribuito |
|--------|--------|-------|----------|---------------------|--------------|
| 0,50   | 0,00   | 10,50 | 9.50     | 0.5                 | 1.50         |

Se la pausa pianificata è stata pagata, il risultato del calcolo sarà simile al seguente.

| Flessibilità in eccesso | Flessibilità in difetto | Tempo  | Tempo retribuito | Tempo pause retribuite | Straordinario retribuito |
|--------|--------|-------|----------|-----------------|--------------|
| 0,50   | 0,00   | 10,50 | 10.00    | 0.5             | 1.50         |

### <a name="pay-items-and-paid-breaks"></a>Elementi retributivi e pause retribuite

Quando si trasferiscono registrazioni nella pagina **Approva**, vengono generati gli elementi retributivi. Viene generato un elemento retributivo per le pause retribuite.

La retribuzione per una pausa retribuita dipende dal tipo di retribuzione impostato negli accordi salariali per la pausa. Anziché utilizzare un tipo di retribuzione, è possibile impostare il prezzo di costo orario della pausa per un intervallo di date definito.

Considerare il seguente profilo orario.

| Tipo profilo  | Avvio    | Fine periodo      | Giorno     |
|---------------|----------|----------|---------|
| Straordinario     | 00:00 | 06:00 | Lunedì  |
| Flessibilità in eccesso         | 06:00 | 07:00 | Lunedì  |
| Entrata      | 07:00 | 07:00 | Lunedì  |
| Orario standard | 07:00 | 14:30 | Lunedì  |
| Flessibilità in difetto-         | 14:30 | 15:30 | Lunedì  |
| Uscita     | 15:30 | 15:30 | Lunedì  |
| Straordinario     | 15:30 | 06:00 | Martedì |

Queste sono le registrazioni del lavoratore per il giorno.

| Tipo di registrazione giornale | Avvio    | Fine periodo      | Tempo |
|---------------------------|----------|----------|------|
| Entrata                  | 07:00 | 07:00 |      |
| Processo di produzione            | 07:00 | 15:00 | 7.5  |
| Pausa (retribuita)              | 12:00 | 12:30 | 0.5  |
| Uscita                 | 15:00 | 15:00 |      |

Per questo esempio, il tipo di retribuzione per l'orario standard è impostato su **1201** e nell'accordo salariale è impostata una tariffa retributiva pari a **10**. Il tipo di retribuzione della pausa retribuita è **1301** e la retribuzione è **8**. Quando le registrazioni vengono trasferite, i seguenti elementi retributivi vengono generati.

| Tipo di retribuzione     | Tipo di retribuzione | Unità retributive | Tasso |
|---------------|----------|-----------|------|
| Orario standard | 1201     | 7.50      | 10   |
| Flessibilità in difetto-         | 1201     | 0,50      | 10   |
| Pausa (retribuita)  | 1301     | 0,50      | 8    |

## <a name="how-the-cost-of-paid-breaks-is-allocated-to-projects-and-production-orders"></a>Modalità di allocazione del costo delle pause retribuite ai progetti e agli ordini di produzione

Il costo orario delle attività di progetto e dei processi di produzione può essere impostato in modo che venga determinato dalle retribuzioni calcolate in Orario e presenze o dalle categorie di costi definite per le attività.

Per impostare la categoria di costi, selezionare **Controllo produzione** &gt; **Impostazione** &gt; **Esecuzione produzione** &gt; **Impostazioni predefinite ordini di produzione** e impostare il campo **Categoria costi** su **Sì** o **No**.

- **No** - Il costo viene calcolato in base a tariffe retributive che sono definite per i tipi di registrazione Ore e presenze.
- **Sì** - Il costo viene calcolato in base alle categorie di costi per le attività di progetto e di produzione.

### <a name="cost-calculation-based-on-pay-rates-that-are-calculated-in-time-and-attendance"></a>Calcolo dei costi basato su tariffe retributive che vengono calcolate in Orario e presenze

Nel seguente esempio viene illustrato come il costo orario viene calcolato quando il costo è impostato in modo che venga calcolato in base alle retribuzioni.

Il tasso di costo orario utilizzato per gli ordini di produzione e i progetti viene calcolato durante il processo di trasferimento. Per visualizzare la tariffa oraria per attività, aprire la pagina **Approva** in Orario e presenze, quindi selezionare **Richiesta info** &gt; **Registrazioni trasferite**. È possibile trovare il tasso di costo orario per registrazione nella scheda **Prezzi di costo**.

Considerare le seguenti registrazioni che utilizzano lo stesso profilo orario dell'esempio precedente.

| Tipo di registrazione giornale | Avvio    | Fine periodo      | Tempo |
|---------------------------|----------|----------|------|
| Entrata                  | 07:00 | 07:00 |      |
| Elaborazione (Ordine: 4711)     | 07:00 | 11:00 | 4    |
| Elaborazione (Ordine: 4712)     | 11:00 | 15:00 | 3.50 |
| Pausa (retribuita)              | 12:00 | 12:30 | 0,50 |
| Uscita                 | 15:00 | 15:00 |      |

Dopo che le registrazioni sono state trasferite, vengono generate le registrazioni trasferite seguenti.

| Tipo di registrazione     | Tempo | Prezzo di costo orario |
|-----------------------|------|---------------------|
| Entrata              | 0,00 | 0,00                |
| Elaborazione (Ordine: 4711) | 4,00 | 10.00               |
| Elaborazione (Ordine: 4712) | 3.50 | 11.14               |
| Pausa (retribuita)          | 0,50 | 0,00                |
| Uscita             | 0,00 | 0,00                |

Il calcolo del prezzo di costo orario per la pausa retribuita dipende dall'impostazione dei costi diretti delle retribuzioni. Selezionare **Orario e presenze** &gt; **Impostazione** &gt; **Parametri Orario e presenze**. Nella scheda **Prezzo di costo**, sotto **Costi diretti delle retribuzioni**, nel campo **Orario standard**, è possibile selezionare **Sì**, **No** o **Allocazione**.

- **Sì** - Questo valore viene utilizzato per l'esempio precedente. Il costo viene allocato all'attività di progetto o di produzione eseguita in parallelo con l'attività di pausa retribuita. In questo esempio, questa compito è il processo di produzione per l'ordine 4712. Come si può vedere, il prezzo di costo orario per la pausa retribuita è 0 (zero) ed è assegnato alla posizione lavorativa eseguita in parallelo con la pausa.

    La pausa retribuita ha una durata di 0,5 ore e la retribuzione è 8. Pertanto, il costo totale per la pausa retribuita è 4. Il costo totale viene quindi allocato al processo di lavorazione di 3,5 ore. Di conseguenza, la pausa retribuita contribuisce con 1,14 per ora al costo (4 ÷ 3,5 = 1,14).

- **Allocazione** - La pausa retribuita viene distribuita equamente alle posizioni lavorative registrate per il giorno. Se questo valore viene utilizzato per l'esempio precedente, vengono generate le registrazioni trasferite seguenti.

    | Tipo di registrazione     | Tempo | Prezzo di costo orario |
    |-----------------------|------|---------------------|
    | Entrata              | 0,00 | 0,00                |
    | Elaborazione (Ordine: 4711) | 4,00 | 10.53               |
    | Elaborazione (Ordine: 4712) | 3.50 | 10.53               |
    | Pausa (retribuita)          | 0,50 | 0,00                |
    | Uscita             | 0,00 | 0,00                |

    Il tempo di lavorazione totale per i due processi di produzione è di 7,5 ore e il costo totale di una pausa retribuita è 4. Pertanto, il costo della pausa viene calcolato come 0,53 (= 4 ÷ 7,5).

- **No** - Il costo di una pausa retribuita non aumenta il costo orario delle attività di processo.

    | Tipo di registrazione     | Tempo | Prezzo di costo orario |
    |-----------------------|------|---------------------|
    | Entrata              | 0,00 | 0,00                |
    | Elaborazione (Ordine: 4711) | 4,00 | 10.00               |
    | Elaborazione (Ordine: 4712) | 3.50 | 10.00               |
    | Pausa (retribuita)          | 0,50 | 0,00                |
    | Uscita             | 0,00 | 0,00                |

## <a name="absence"></a>Assenza

Un codice assenza viene utilizzato per registrare il periodo di assenza di un lavoratore. Come pause e codici Switch, un codice assenza è un tipo di attività indiretta. Il tempo di assenza può essere pianificato e registrato e l'assenza può essere legale o illegale. Gli esempi di assenza legale includono l'appuntamento con un medico, un seminario o l'espletamento di una funzione pubblica. L'assenza illegale è un'assenza senza valido motivo, ad esempio quando un lavoratore arriva al lavoro in ritardo. In genere, l'assenza legale, a differenza di quella illegale, non comporta una detrazione nella retribuzione di un lavoratore.

### <a name="planned-absence"></a>Assenza pianificata

È possibile creare un'assenza pianificata per i lavoratori nella pagina **Crea assenza pianificata** (**Orario e presenze** &gt; **Crea assenza pianificata**). In tale pagina, l'assenza pianificata viene registrata come processo di assenza per una data e un intervallo di tempo specificati.

Il processo è basato su una query. Di conseguenza, è possibile creare un'assenza pianificata per più lavoratori, ad esempio lavoratori appartenenti allo stesso gruppo di calcolo. Se l'assenza pianificata riguarda un singolo lavoratore, la registrazione può essere immessa dalla pagina **Presenze** o dalla pagina **Lavoratori per registrazione ore**.

- Per immettere una registrazione assenze dalla pagina **Presenze**, selezionare &gt; **Orario e presenze** **Richieste di informazioni e report** &gt; **Presenze** &gt; **Presenze** quindi **Registrazione assenze**.
- Per immettere una registrazione assenze dalla pagina *<strong><em>Lavoratori per registrazione ore</em></strong>*, selezionare <strong>Orario e presenze</strong> &gt; <strong>Impostazioni</strong> &gt; <strong>Lavoratori per registrazione ore</strong>, quindi nella scheda <strong>Ora</strong>, in <strong>Assegnazione ora</strong>, selezionare <strong>Registrazioni assenze</strong>.

È possibile utilizzare il report **Assenze pianificate** per visualizzare una panoramica delle assenze pianificate per i lavoratori. Per aprire questo report, selezionare **Orario e presenze** &gt; **Richieste di informazioni e report** &gt; **Report assenze** &gt; **Assenze pianificate**.

### <a name="registered-absence"></a>Assenza registrata

In genere, i lavoratori vengono considerati assenti se non si trovano al lavoro per qualsiasi periodo compreso tra le ore di entrata e di uscita pianificate. Se i lavoratori entrano al lavoro in ritardo rispetto all'orario pianificato o se escono prima dell'orario pianificato, viene chiesto loro di selezionare un codice assenza per indicare il motivo dell'assenza. È possibile impostare un codice assenza che sia applicabile alla registrazione. Solo i codici applicabili saranno disponibili per la selezione nell'elenco.

## <a name="scenarios-based-on-various-combinations-of-work-hour-registrations"></a>Scenari basati su varie combinazioni di registrazioni di ore di lavoro

I seguenti scenari mostrano gli elementi retributivi e le immissioni per l'approvazione generati per i lavoratori in base alle relative registrazioni. Tutti gli scenari si basano sul seguente profilo orario.

| Tipo profilo  | Avvio    | Fine periodo      | Giorno     |
|---------------|----------|----------|---------|
| Straordinario     | 00:00 | 06:00 | Lunedì  |
| Flessibilità in eccesso         | 06:00 | 07:00 | Lunedì  |
| Entrata      | 07:00 | 07:00 | Lunedì  |
| Orario standard | 07:00 | 14:30 | Lunedì  |
| Flessibilità in difetto-         | 14:30 | 15:30 | Lunedì  |
| Uscita     | 15:30 | 15:30 | Lunedì  |
| Straordinario     | 15:30 | 06:00 | Martedì |

### <a name="scenario-1-the-worker-clocks-in-later-than-planned"></a>Scenario 1: il lavoratore entra a un'ora successiva a quella pianificata

Il lavoratore entra alle 8:30. Poiché l'ora di entrata pianificata è 07:00, il lavoratore è di 1,50 ore in ritardo sul lavoro. Poiché 1,50 ore vengono considerate tempo di assenza, al lavoratore viene chiesto di selezionare un codice assenza. Il lavoratore parte alle 15:30, ovvero all'ora di uscita pianificata. Quando le registrazioni del lavoratore vengono calcolate e approvate, la registrazione assenze, insieme al codice assenza che il lavoratore ha selezionato all'entrata, viene visualizzata per il periodo tra le 07:00 e le 08:30.

Nel profilo orario, è possibile configurare il tipo di registrazione **Entrata** in modo che esista una tolleranza quando i lavoratori arrivano in ritardo al lavoro. Ad esempio, se si imposta una tolleranza di 5, il lavoratore deve immettere un codice assenza solo se entra al lavoro dopo le 07:05.

In questo caso, poiché il lavoratore non ha un buon motivo per arrivare in ritardo al lavoro, seleziona un codice assenza definito per assenza illegale. Un codice assenza viene considerato applicabile alle assenze illegali se l'impostazione per la detrazione dello straordinario è abilitata per il gruppo assenze a cui appartiene il codice assenza. Per definire l'impostazione, selezionare **Orario e presenze** &gt; **Impostazione** &gt; **Gruppi** &gt; **Gruppi assenze** e quindi selezionare la casella di controllo **Detrai straordinario**.

Ecco come vengono visualizzate le registrazioni del lavoratore per il giorno nella pagina **Approva** dopo il calcolo.

| Tipo di registrazione giornale         | Avvio    | Fine periodo      | Tempo |
|-----------------------------------|----------|----------|------|
| Assenza (illegale - in ritardo) | 07:00 | 08:30 | 1.5  |
| Entrata                          | 08:30 | 08:30 |      |
| Processo di produzione                    | 07:30 | 15:30 | 7.0  |
| Uscita                         | 15:30 | 15:30 |      |

Ecco l'elemento retributivo risultante dopo il trasferimento delle registrazioni.

| Tipo di retribuzione     | Tipo di retribuzione | Unità retributive | Tasso |
|---------------|----------|-----------|------|
| Orario standard | 1201     | 7.00      | 10   |

### <a name="scenario-2-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-standard-time-period"></a>Scenario 2: il lavoratore esce prima dell'ora di uscita pianificata durante un periodo di tempo standard

Il lavoratore entra alle 7:00 ed esce in anticipo alle 13:00. Poiché l'orario delle 13:00 è precedente all'uscita pianificata delle 15:30 e la 01:00 è compresa in un periodo di tempo standard, al lavoratore viene chiesto di selezionare un codice assenza. Il lavoratore seleziona un codice assenza per un appuntamento dal dottore, che è definito come assenza legale. La retribuzione per l'assenza legale è definita negli accordi salariali per il tipo di registrazione **Assenza** (**Orario e presenze** &gt; **Impostazione** &gt; **Retribuzioni** &gt; **Accordi salariali**).

Ecco come vengono visualizzate le registrazioni del lavoratore per il giorno nella pagina **Approva** dopo il calcolo.

| Tipo di registrazione giornale              | Avvio    | Fine periodo      | Tempo |
|----------------------------------------|----------|----------|------|
| Entrata                               | 07:00 | 07:00 |      |
| Processo di produzione                         | 07:00 | 13:00 | 4.0  |
| Uscita                              | 13:00 | 13:00 |      |
| Assenza (legale - visita medica) | 13:00 | 15:30 | 3.5  |

Ecco l'elemento retributivo risultante dopo il trasferimento delle registrazioni.

| Tipo di retribuzione     | Tipo di retribuzione | Unità retributive | Tasso |
|---------------|----------|-----------|------|
| Orario standard | 1201     | 7.50      | 10   |

### <a name="scenario-3-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-flex--period"></a>Scenario 3: il lavoratore esce prima dell'ora di uscita pianificata durante un periodo di flessibilità in difetto

Il lavoratore entra alle 7:00 ed esce alle 14:15, ovvero il periodo di flessibilità in difetto pianificato. Il tempo tra l'orario di uscita effettiva e l'orario di uscita pianificato non viene considerato come assenza e al lavoratore non viene richiesto di selezionare un codice assenza. L'importo viene sottratto dal conto flessibilità del lavoratore e il lavoratore viene retribuito durante la parte rimanente del periodo di flessibilità in difetto, ovvero dalle 14:15 alle 15:30.

Ecco come vengono visualizzate le registrazioni del lavoratore per il giorno nella pagina **Approva** dopo il calcolo.

| Tipo di registrazione giornale | Avvio    | Fine periodo      | Tempo |
|---------------------------|----------|----------|------|
| Entrata                  | 07:00 | 07:00 |      |
| Processo di produzione            | 07:00 | 14:15 | 7.25 |
| Uscita                 | 14:15 | 14:15 |      |

Ecco l'elemento retributivo risultante dopo il trasferimento delle registrazioni.

| Tipo di retribuzione     | Tipo di retribuzione | Unità retributive | Tasso |
|---------------|----------|-----------|------|
| Orario standard | 1201     | 8.50      | 10   |

### <a name="scenario-4-the-worker-clocks-in-late-and-clocks-out-after-the-planned-clock-out-time-during-an-overtime-period"></a>Scenario 4: il lavoratore entra in ritardo ed esce dopo l'ora di uscita pianificata durante un periodo di straordinario

Il lavoratore entra in ritardo alle 09:30 e quindi, per compensare il tempo perso, svolge del lavoro straordinario ed esce alle 17:00. Poiché il lavoratore è entrato in ritardo ma ha compensato le ore lavorando più a lungo, la società non vuole concedere al lavoratore lo straordinario per le ore che ha lavorato tra l'uscita pianificata alle 15:30 e l'uscita effettiva avvenuta alle 17:00, anche se questo periodo nel profilo orario è definito come straordinario.

Per gestire questo scenario, il codice assenza può essere impostato per ridurre le ore di lavoro straordinario delle eventuali ore di assenza illegale dal lavoratore nel giorno stesso. Selezionare **Orario e presenze** &gt; **Impostazione** &gt; **Gruppi** &gt; **Gruppi assenze** e selezionare la casella di controllo **Detrai straordinario** per detrarre lo straordinario delle ore di assenza illegale.

Ecco come vengono visualizzate le registrazioni del lavoratore per il giorno nella pagina **Approva** dopo il calcolo.

| Tipo di registrazione giornale         | Avvio    | Fine periodo      | Tempo |
|-----------------------------------|----------|----------|------|
| Assenza (illegale - in ritardo) | 07:00 | 09:30 | 1.5  |
| Entrata                          | 09:30 | 09:30 |      |
| Processo di produzione                    | 09:30 | 17:00 | 7.5  |
| Uscita                         | 17:30 | 17:30 |      |

Se la casella di controllo **Detrai straordinario** è selezionata per il codice assenza selezionato, dalla retribuzione dello straordinario vengono detratte le ore in cui il lavoratore è stato assente illegalmente. In questo caso, i seguenti elementi retributivi vengono generati dopo il trasferimento delle registrazioni.

| Tipo di retribuzione     | Tipo di retribuzione | Unità retributive | Tasso |
|---------------|----------|-----------|------|
| Orario standard | 1201     | 9.00      | 10   |
| Straordinario      | 1301     | 0.5       | 15   |

In questo caso, le 1,5 ore di assenza illegale, dalle 07:00 alle 09:30, vengono dedotte dalle 2,0 ore di straordinario, dalle 15:30 alle 17:30. Il risultato della registrazione è 1,5 ore di orario standard e 0,5 ore di lavoro straordinario.

Per contro, se la casella di controllo **Detrai straordinario** è deselezionata per il codice assenza selezionato, il pagamento dello straordinario viene concesso al lavoratore, anche se è entrato al lavoro in ritardo e l'assenza era illegale. In questo caso, i seguenti elementi retributivi vengono generati dopo il trasferimento delle registrazioni.

| Tipo di retribuzione     | Tipo di retribuzione | Unità retributive | Tasso |
|---------------|----------|-----------|------|
| Orario standard | 1201     | 7.50      | 10   |
| Straordinario      | 1301     | 2.0       | 15   |

### <a name="scenario-5-the-worker-clocks-out-before-the-planned-clock-out-time-and-can-convert-the-absence-period-to-a-flex--period"></a>Scenario 5: il lavoratore esce prima dell'ora di uscita pianificata e può convertire il periodo di assenza in un periodo di flessibilità in difetto

Nel seguente esempio viene illustrato come il conto flessibilità di un lavoratore può essere ridotto convertendo il periodo di assenza in un periodo di flessibilità in difetto.

Il lavoratore entra alle 7:00 ed esce alle 13:00. Ha raggiunto un accordo con il supervisore secondo il quale può stare a casa durante il fine settimana se deduce queste ore dal suo conto flessibilità. Quando il lavoratore esce alle 13:00, gli viene richiesto di selezionare un codice assenza, in quanto il periodo di assenza per la parte rimanente della giornata lavorativa interessata non è compresa in un periodo di flessibilità in difetto pianificato. Per convertire la parte rimanente della giornata lavorativa in periodo di flessibilità in difetto, il lavoratore può selezionare un codice assenza impostato per ridurre il proprio conto di flessibilità.

Per ridurre il saldo delle ore flessibili per i lavoratori che registrano un'assenza in un giorno lavorativo, selezionare **Orario e presenze** &gt; **Impostazione** &gt; **Gruppi** &gt; **Gruppi assenze** e selezionare la casella di controllo **Riduci flessibilità**.

Ecco come vengono visualizzate le registrazioni del lavoratore per il giorno nella pagina **Approva** prima del calcolo.

| Tipo di registrazione giornale | Avvio    | Fine periodo      | Tempo |
|---------------------------|----------|----------|------|
| Entrata                  | 07:00 | 07:00 |      |
| Processo di produzione            | 07:00 | 13:00 | 6.0  |
| Uscita                 | 13:00 | 13:00 |      |

Se il lavoratore seleziona un codice assenza per un'assenza illegale, ecco come apparirà l'elemento retributivo risultante dopo il trasferimento della registrazione.

| Tipo di retribuzione     | Tipo di retribuzione | Unità retributive | Tasso |
|---------------|----------|-----------|------|
| Orario standard | 1201     | 6,00      | 10   |

Se il lavoratore seleziona un codice assenza per un'assenza legale e il codice assenza è impostato in modo che venga ridotto il conto flessibilità del lavoratore, ecco come appariranno gli elementi retributivi risultanti dopo il trasferimento delle registrazioni.

| Tipo di retribuzione     | Tipo di retribuzione | Unità retributive | Tasso |
|---------------|----------|-----------|------|
| Orario standard | 1201     | 8.50      | 10   |

In questo caso, il saldo flessibilità del lavoratore viene ridotto delle ore comprese tra l'ora di uscita effettiva e l'ora di uscita pianificata (ovvero, 2,5 ore tra le 13:00 e le 15:30).

> [!NOTE]
> Non è consigliabile selezionare entrambe le caselle di controllo **Deduct flex** e **Detrai straordinario** per il codice assenza, poiché questa impostazione dedurrà le ore non valide dalle ore di lavoro straordinario del lavoratore e contemporaneamente ridurrà il conto di flessibilità del lavoratore.

### <a name="scenario-6-there-is-no-planned-absence-for-the-day-and-no-worker-attendance-for-the-day"></a>Scenario 6: non esiste alcuna assenza pianificata e nessuna presenza del lavoratore per il giorno corrente

Se il lavoratore non risulta al lavoro un giorno e non sono presenti assenze pianificate per il lavoratore in quel giorno, viene utilizzato un codice assenza predefinito per il calcolo delle registrazioni del lavoratore. Per definire i codici assenze predefiniti, selezionare **Orario e presenze** &gt; **Parametri Orario e presenze**. È possibile quindi selezionare un codice assenza nei seguenti campi:

- Inserimento automatico della flessibilità in difetto
- Inserimento automatico dell'assenza

Quando le registrazioni giornaliere vengono calcolate per un lavoratore che ha diritto a ore flessibili, il codice assenza specificato nel campo **Inserimento automatico della flessibilità in difetto-** viene utilizzato come codice assenza predefinito. Se il lavoratore non ha diritto all'orario flessibile, viene utilizzato il codice assenza specificato nel campo **Inserimento automatico dell'assenza**. Se una società ha una combinazione di lavoratori che sono abilitati a usufruire degli orari flessibili e lavoratori che non lo sono, è necessario impostare entrambi i parametri.
