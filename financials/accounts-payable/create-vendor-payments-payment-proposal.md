---
title: Creare pagamenti fornitore utilizzando una proposta di pagamento
description: "Questo argomento fornisce una panoramica delle opzioni di proposta di pagamento e include alcuni esempi che illustrano come funzionano le proposte di pagamento. Le proposte di pagamento sono spesso utilizzate per creare pagamenti fornitore, poiché la query può essere utilizzata per selezionare rapidamente le fatture fornitore per il pagamento, in base a criteri quali la data di scadenza e lo sconto di cassa."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14312
ms.assetid: 585d5b0b-1b79-4a03-ab18-528918070377
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b351ea58a25c763dcf90ff1c61e0e3b3cba6c34a
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="create-vendor-payments-by-using-a-payment-proposal"></a>Creare pagamenti fornitore utilizzando una proposta di pagamento

[!include[banner](../includes/banner.md)]


Questo argomento fornisce una panoramica delle opzioni di proposta di pagamento e include alcuni esempi che illustrano come funzionano le proposte di pagamento. Le proposte di pagamento sono spesso utilizzate per creare pagamenti fornitore, poiché la query può essere utilizzata per selezionare rapidamente le fatture fornitore per il pagamento, in base a criteri quali la data di scadenza e lo sconto di cassa. 

Le organizzazioni spesso utilizzano proposte di pagamento per creare pagamenti fornitore, poiché la query della proposta di pagamento può essere utilizzata per selezionare rapidamente le fatture fornitore per il pagamento, in base alla data di scadenza, allo sconto di cassa e ad altri criteri. 

La query della proposta di pagamento contiene le varie schede, ciascuna delle quali ha opzioni diverse per selezionare le fatture da pagare. La scheda **Parametro** la scheda contiene opzioni che la maggioranza delle organizzazioni utilizza con maggiore frequenza. Nella scheda dettaglio **Record da includere**, è possibile specificare le fatture o i fornitori da includere per il pagamento definendo intervalli per diverse caratteristiche. Ad esempio, se si desidera pagare solo un determinato intervallo di fornitori, è possibile definire un filtro per l'intervallo di fornitori. Questa funzionalità viene spesso utilizzata per selezionare le fatture per uno specifico metodo di pagamento. Ad esempio, se si definisce un filtro in cui **Metodo di pagamento** = **Assegno**, solo le fatture con quel metodo di pagamento sono selezionate per il pagamento, purché soddisfino anche gli altri criteri specificati nella query. Nella scheda **Parametri avanzati** scheda sono contenute opzioni aggiuntive, alcune delle quali non sono rilevanti per l'organizzazione. Ad esempio, questa scheda contiene le opzioni per il pagamento di fatture per pagamenti centralizzati.

## <a name="parameters"></a>Parametri
-   **Selezionare le fatture in base a**: le fatture incluse nell'intervallo di date specificato dai campi **Dal** e **Al** possono essere selezionate in base alla data di scadenza, alla data dello sconto di cassa o entrambe. Se si utilizza la data dello sconto di cassa, il sistema cercherà innanzitutto fatture con data dello sconto di cassa inclusa nell'intervallo di date specificato dai Campi Dal e Al. Il sistema quindi determina se la fattura è ammissibile per lo sconto di cassa utilizzando la data della sessione per assicurarsi che la data dello sconto di cassa non sia già trascorsa.
-   **Dal** e**Al**: le fatture con data dello sconto di cassa o di scadenza comprese in questo intervallo sono selezionate per il pagamento.
-   **Data di pagamento**: se una data viene definita, tutti i pagamenti vengono creati in questa data. Il campo **Data di pagamento minima** viene ignorato.
-   **Data di pagamento minima**: consente di immettere la data di pagamento minima. Ad esempio, i campi **Dal** e **Al** specificano un intervallo dal 1° settembre al 10 settembre e la data di pagamento minima corrisponde al 5 settembre. In questo caso, tutte le fatture con data di scadenza dal 1° settembre al 5 settembre hanno una data di pagamento del 5 settembre. Tuttavia, tutte le fatture con data di scadenza dal 5 settembre al 10 settembre hanno una data di pagamento che corrisponde alla data di scadenza di ciascuna fattura.
-   **Limite importo**: consente di immettere l'importo totale massimo per tutti i pagamenti.
-   **Crea pagamenti senza anteprima fattura**: se questa opzione è impostata su **Sì**, i pagamenti verranno creati immediatamente nella pagina **Pagamenti fornitore**. La pagina **Proposta di pagamento** verrà ignorata. Di conseguenza, i pagamenti verranno creati più rapidamente. I pagamenti possono comunque essere modificati nella pagina. **Pagamenti fornitore**. In alternativa, è possibile tornare alla pagina **Proposta di pagamento** utilizzando il pulsante **Modifica fatture per il pagamento selezionato**.

## <a name="advanced-options"></a>Opzioni avanzate
-   **Verifica saldo fornitori**: se questa opzione è impostata su **Sì**, il sistema verifica che per il fornitore non sia presente un saldo in Dare prima del pagamento di qualsiasi fattura. Se un fornitore ha un saldo in Dare, non viene creato alcun pagamento. Ad esempio, il fornitore potrebbe avere note di credito o pagamenti registrati ma non ancora liquidati. In questi casi, il fornitore non deve essere pagato, ma le note di credito o i pagamenti devono essere liquidati a fronte delle fatture in sospeso.
-   **Elimina pagamenti negativi**: questa opzione funziona in modo diverso, a seconda che i pagamenti vengano eseguiti per le singole fatture o per la somma delle fatture che soddisfano i criteri di pagamento. Questo comportamento è definito nel metodo di pagamento.
-   **Pagamento per ciascuna fattura**: se l'opzione **Elimina pagamenti negativi** è impostata su **Sì** e per un fornitore sono presenti una fattura e un pagamento non liquidati, solo la fattura viene selezionata per il pagamento. Il pagamento esistente non viene liquidato rispetto alla fattura. Se l'opzione **Elimina pagamenti negativi** è impostata su **No** e una fattura e un pagamento non vengono liquidati, sia la fattura che il pagamento vengono selezionati per il pagamento. Viene creato un pagamento e un rimborso (pagamento negativo) viene creato per il pagamento.
-   **Pagamento per la somma delle fatture**: se l'opzione **Elimina pagamenti negativi** è impostata su **Sì** e per un fornitore esistono una fattura e un pagamento non liquidati, sia la fattura che il pagamento non liquidati vengono selezionati per il pagamento e gli importi vengono sommati per produrre l'importo del pagamento totale. La sola eccezione si verifica se la somma determina un rimborso. In questo caso, non vengono selezionati né la fattura né il pagamento. Se l'opzione **Elimina pagamenti negativi** è impostata su **No** e né la fattura né il pagamento sono liquidati, per il pagamento vengono selezionati entrambi e gli importi vengono sommati per produrre l'importo del pagamento totale.
-   **Esegui solo stampa report**: impostare questa opzione su **Sì** per visualizzare i risultati della proposta di pagamento in un report, ma senza creare alcun pagamento.
-   **Includi fatture fornitore da altre persone giuridiche**: se l'organizzazione dispone di un processo centralizzato per il pagamento e la proposta di pagamento deve includere le fatture di altre persone giuridiche presenti nei criteri di ricerca, impostare questa opzione su **Sì**.
-   **Proponi pagamenti fornitore separati per persona giuridica**: se questa opzione è impostata su **Sì**, un pagamento separato viene creato per ogni persona giuridica per fornitore. Il fornitore nel pagamento corrisponde a quello della fattura per ogni persona giuridica. Se questa opzione è impostata su **No** e per lo stesso fornitore sono presenti fatture in più persone giuridiche, un pagamento viene creato per l'importo totale delle fatture selezionate. Il fornitore utilizzato per il pagamento corrisponde al fornitore presente nella persona giuridica corrente. Se tale account non esiste nella persona giuridica corrente, verrà utilizzato l'account fornitore della prima fattura da pagare.
-   **Valuta pagamento**: questo campo specifica la valuta in cui vengono creati tutti i pagamenti. Se una valuta non è definita, ogni fattura viene pagata nella valuta della fattura.
-   **Giorno feriale di pagamento**: immettere il giorno feriale in cui il pagamento deve essere eseguito. Questo campo viene utilizzato solo se il metodo di pagamento viene impostato sul totale delle fatture per un determinato giorno della settimana.
-   **Tipo di conto di contropartita** e **Conto di contropartita**: impostare questi campi per definire un tipo di conto specifico (ad esempio **Contabilità generale** o **Banca**) e il conto di contropartita (ad esempio un determinato conto bancario). Il metodo di pagamento della fattura definisce il tipo di conto di contropartita e il conto di contropartita predefiniti, ma è possibile utilizzare questi campi per sostituire i valori predefiniti.
-   **Filtri aggiuntivi**: nella scheda dettaglio **Record da includere** è possibile definire ulteriori intervalli di criteri. Ad esempio, se si desidera pagare solo un intervallo di fornitori, è possibile definire un filtro per l'intervallo di fornitori. Questa funzionalità viene spesso utilizzata per selezionare le fatture per uno specifico metodo di pagamento. Ad esempio, se si definisce un filtro in cui **Metodo di pagamento** = **Assegno**, solo le fatture con quel metodo di pagamento sono selezionate per il pagamento, purché soddisfino anche gli altri criteri specificati nella query.

## <a name="scenarios"></a>Scenari
| Fornitore | Fattura | Data fattura | Importo fattura | Data di scadenza | Data sconto di cassa | Importo sconto di cassa |
|--------|---------|--------------|----------------|----------|--------------------|----------------------|
| 3050   | 1001    | 15 giugno      | 500,00         | 15 luglio  | 29 giugno            | 10,00                |
| 3050   | 1002    | 20 giugno      | 600,00         | 20 luglio  | 4 luglio             | 12,00                |
| 3075   | 1003    | 15 giugno      | 250,00         | 29 giugno  |                    | 0,00                 |
| 3100   | 1004    | 17 giugno      | 100,00         | 17 luglio  | 1 luglio             | 1,00                 |

Il 1° luglio April paga i fornitori. Utilizza una proposta di pagamento per consentire il completamento dell'attività in modo più efficiente.

### <a name="option-1-by-cash-discount"></a>Opzione 1: per sconto di cassa

April seleziona **Sconto di cassa** come tipo di proposta. Inserisce un intervallo di date dal 26 giugno al 10 luglio. Le seguenti fatture sono incluse nella proposta:

-   1002, poiché la data dello sconto del 4 luglio rientra nell'intervallo delle date di pagamento.
-   1004, poiché la data dello sconto del 1 luglio rientra nell'intervallo delle date di pagamento.

Le seguenti fatture non sono incluse nella proposta:

-   1001, poiché la data dello sconto del 29 giugno è scaduta, pertanto questa fattura non è più idonea per lo sconto di cassa.
-   1003, poiché la fattura non ha una data dello sconto.

### <a name="option-2-by-due-date"></a>Opzione 2: per data di scadenza

April seleziona **Per data di scadenza** come tipo di proposta. Inserisce un intervallo di date dal 26 giugno al 10 luglio. Le seguenti fatture sono incluse nella proposta:

-   1003, poiché la data di scadenza del 29 giugno rientra nell'intervallo delle date di pagamento.

Le seguenti fatture non sono incluse nella proposta:

-   1001, poiché la data di scadenza del 15 luglio non rientra nell'intervallo delle date di pagamento.
-   1002, poiché la data di scadenza del 20 luglio non rientra nell'intervallo delle date di pagamento.
-   1004, poiché la data di scadenza del 17 luglio non rientra nell'intervallo delle date di pagamento.

### <a name="option-3-by-due-date-and-cash-discount"></a>Opzione 3: per data di scadenza e sconto di cassa

April seleziona **Data di scadenza e sconto di cassa** come tipo di proposta. Inserisce un intervallo di date dal 26 giugno al 10 luglio. Le seguenti fatture sono incluse nella proposta:

-   1003, poiché la data di scadenza del 29 giugno rientra nell'intervallo delle date di pagamento.
-   1002, poiché la data dello sconto del 4 luglio rientra nell'intervallo delle date di pagamento.
-   1004, poiché la data dello sconto del 1 luglio rientra nell'intervallo delle date di pagamento.

Le seguenti fatture non sono incluse nella proposta:

-   1001, poiché la data dello sconto del 29 giugno è scaduta, pertanto tale fattura non è più idonea per lo sconto di cassa e la data di scadenza del 15 luglio non è compresa nell'intervallo.

## <a name="country-specific-considerations"></a>Considerazioni specifiche di paese
### <a name="norway"></a>Norvegia

#### <a name="dimension-control"></a>Controllo dimensioni

Il controllo delle dimensioni consente di determinare il raggruppamento delle righe generate per proposta di pagamento e impostare dimensioni predefinite in base alle dimensioni finanziarie utilizzate per le fatture applicate. Nel contesto norvegese per ogni metodo di pagamento esiste una scheda Dimensione finanziaria in cui è possibile attivare il controllo delle dimensioni nonché attivare il raggruppamento per ciascuna dimensione. Sono possibili le seguenti opzioni:

-   Il campo **Controllo dimensioni** è disabilitato. La proposta di pagamento funzionerà come per qualsiasi altro paese.
-   Il campo **Controllo dimensioni** è attivato senza definire ulteriormente le dimensioni. La proposta di pagamento verrà creata senza prendere le dimensioni in considerazione. La transazione creata non eredita dimensioni della voce applicata.
-   Il campo **Controllo dimensioni** è attivato e sono abilitate le ulteriori dimensioni. Ora si definisce come le dimensioni verranno copiate nel giornale di registrazione. Ad esempio: • Selezionare la casella di controllo **BusinessUnit** per creare una proposta di pagamento per Business Unit per il metodo di pagamento. • Selezionare la casella di controllo **CostCenter** per creare una proposta di pagamento per centro di costo per il metodo di pagamento.

**Nota:** Se si selezionano più dimension nella terza opzionei, verrà creata una proposta di pagamento per la combinazione di dimensioni.

#### <a name="bank-account-selection"></a>Selezione del conto bancario

È possibile definire un conto di addebito di pagamento standard per il metodo di pagamento indipendentemente dal contesto del paese. Questo verrà impostato nelle righe di pagamento generate da una proposta. Con la funzionalità di conto bancario è possibile definire più conti bancari di addebito gestiti per dimensione e valuta o una combinazione di questi per utilizzare diversi conti bancari di addebito, in base a ciascuna combinazione. È possibile impostare queste combinazioni nella pagina **Metodi di pagamento** utilizzando il pulsante **Conti bancari** disponibile per ogni metodo di pagamento con **Tipo di conto di registrazione** = **Banca**.




