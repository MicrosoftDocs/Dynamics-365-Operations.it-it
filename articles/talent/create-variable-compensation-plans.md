---
title: Creare piani di retribuzione variabile
description: La retribuzione variabile rappresenta una retribuzione non regolare del dipendente, ad esempio premio o premi in azioni. Questo argomento descrive i componenti che devono essere impostati per utilizzare una retribuzione variabile e per iscrivere un dipendente in un piano di retribuzione variabile.
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HCMCompEligibility, HcmJobFunction, HcmWorker, HRMCompPerfPlan
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 16011
ms.assetid: fc3a394e-9ac6-4f8c-9162-dc16ec22720f
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4ced76315bb4667f84be532a703e7e9b134b829b
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="create-variable-compensation-plans"></a>Creare piani di retribuzione variabile

[!include[banner](includes/banner.md)]


La retribuzione variabile rappresenta una retribuzione non regolare del dipendente, ad esempio premio o premi in azioni. Questo articolo descrive i componenti che devono essere impostati per utilizzare una retribuzione variabile e per iscrivere un dipendente in un piano di compensazione variabile.

Il calcolo degli importi di retribuzione variabile per i dipendenti può basarsi su diversi fattori, ad esempio le prestazioni del dipendente, il livello retributivo del dipendente e le prestazioni del reparto.

## <a name="variable-compensation-components"></a>Componenti della retribuzione variabile
### <a name="create-compensation-types"></a>Creare tipi di retribuzione

I **tipi di retribuzione variabile**costituiscono una componente necessaria. I tipi di retribuzione variabile consentono di descrivere i tipi di retribuzione assegnati dall'organizzazione. Consentono inoltre di specificare se la retribuzione avverrà in contanti o mediante un modulo non monetario, ad esempio come scorte.

### <a name="describe-vesting-rules"></a>Descrivere regole di distribuzione incentivi

Facoltativamente, le società possono impostare **regole di distribuzione incentivi**. Le regole di distribuzione incentivi descrivono come il premio variabile deve essere allocato nel tempo. Ad esempio, una regola di distribuzione degli incentivi potrebbe indicare che il dipendente riceverà il 25% del proprio premio totale ogni anno per i quattro anni successivi. Le regole di distribuzione incentivi sono solo informative.

## <a name="variable-compensation-plans"></a>Piani di retribuzione variabile
Il **piano di retribuzione variabile** contiene le regole, i metodi di calcolo e i valori predefiniti per il calcolo di retribuzione variabile per dipendenti iscritti al piano. Quando si crea un piano di retribuzione variabile, è necessario impostare il tipo di retribuzione variabile. Il tipo di retribuzione variabile determina se il sistema calcolerà un importo in valuta o un numero di unità come premio. È inoltre necessario impostare il metodo di calcolo:

-   **Temporizzato** - Il calcolo del premio variabile è basato sulla retribuzione fissa che il dipendente ha avuto in una data specifica. Tale data viene specificata all'evento processo quando i nuovi importi di retribuzione vengono elaborati.
-   **Composito**: un importo del premio viene calcolato per ogni tariffa retributiva univoca della retribuzione fissa che il dipendente ha percepito tra la data di inizio e la data di fine del ciclo nell'evento di processo. I tassi vengono quindi sommati per determinare il premio finale. Ad esempio, durante il ciclo, un dipendente trasferito in una posizione diversa che aveva una retribuzione diversa. In questo caso, il premio variabile viene rettificato in base alla durata di ogni tariffa retributiva del dipendente.

L'importo del premio variabile può basarsi su una percentuale del reddito di base regolare del dipendente o su un numero stabilito di unità.

-   Selezionare l'opzione **Percentuale della base** per immettere una percentuale predefinita e specificare se la base deve essere la tariffa di retribuzione fissa del dipendente o il punto di controllo per il livello retributivo del dipendente. Il livello retributivo viene impostato sulla mansione del dipendente. Uno dei punti di riferimento dalla struttura retributiva può essere impostato come punto di controllo nel piano di retribuzione fissa. Il sistema utilizzerà il livello retributivo della mansione del dipendente e lo incrocerà con il punto di controllo elencato nel piano di retribuzione fissa del dipendente per trovare l'importo del punto di controllo per il livello retributivo del dipendente. L'importo del punto di controllo verrà quindi utilizzato in sostituzione della retribuzione fissa del dipendente come base per il premio.
-   Selezionare l'opzione**Numero di unità** per immettere un numero di unità predefinito, il valore di ciascuna unità e la valuta del valore unitario se il piano di retribuzione è relativo a un premio non in contanti (ad esempio, 200 unità di scorte che vengono valutate a 40 EUR) o solo il numero di unità se il piano di retribuzione è relativo a un premio in contanti. Per un premio in contanti, il dipendente riceverà il numero di unità specificate della valuta utilizzata per il proprio piano di retribuzione fissa, ad esempio 500 unità di 1 EUR. Il controllo della relazione uno-a-uno può essere utilizzato per indicare se esiste un mapping uno-a-uno diretto tra il numero di unità e il valore unitario. Quando si crea un piano di retribuzione variabile per un piano basato su contanti usando il numero di unità, questa viene automaticamente bloccata su **Sì** e il valore unitario è **1,0000**.

L'impostazione **Regola di assunzione** consente di specificare se tutti i dipendenti devono ricevere lo stesso aumento, indipendentemente dalla data in cui sono stati assunti (**Regola di assunzione** = **Nessuno**) o se i dipendenti devono ottenere una percentuale del premio in base alla durata dell'impiego durante il ciclo (**Regola di assunzione** = **Percentuale**). 

**Fattore**  consente di rettificare il premio di un dipendente, a seconda delle prestazioni del reparto del dipendente. Metriche delle prestazioni possono essere impostate per ciascun reparto nella pagina **Reparti**, in **Moduli correlati** &gt; **Retribuzione** &gt; **Prestazioni**. Il premio che i dipendenti del reparto ricevono dipende dal valore del campo **Percentuale dell'obiettivo raggiunta**, che indica le prestazioni del reparto:

-   Se le prestazioni del reparto sono 100 percento, il premio per i dipendenti in tale reparto viene moltiplicato per la percentuale impostata nel campo**Pagamento al 100%**.
-   Se le prestazioni del reparto sono superiori al 100 percento, il sistema aggiunge la percentuale impostata nel campo **Ogni 1% al di sopra dell'obiettivo** alla percentuale impostata nel campo **Pagamento al 100%** finché non viene raggiunto il valore impostato nel campo **Pagamento massimo consentito**.
-   Se le prestazioni del reparto sono inferiori al 100 percento, il sistema sottrae la percentuale impostata nel campo **Ogni 1% al di sotto dell'obiettivo** dalla percentuale impostata nel campo **Pagamento al 100%** finché non viene raggiunto il valore impostato nel campo **Pagamento minimo consentito**.

È possibile impostare**livelli di tolleranza** sulle percentuali di soglia in modo da visualizzare un messaggio di avviso se il fattore causa il superamento della percentuale di soglia. 

Per impostazione predefinita, il sistema cerca il reparto impostato sulla posizione del dipendente. Tuttavia, il premio per alcuni dipendenti potrebbe dipendere dalle prestazioni di più reparti. In questo caso, i diversi reparti e la percentuale del premio allocato alle prestazioni di ciascun reparto possono essere impostati all'iscrizione del dipendente al piano di retribuzione variabile. Per ulteriori informazioni, vedere la sezione "Iscrizione retribuzione variabile" che segue. 

Il fattore viene utilizzato solo se l'impostazione **Retribuzione basata sulla produttività** è selezionata quando viene eseguito il processo retributivo. 

La scheda **Sostituzioni livelli** consente di sostituire la percentuale predefinita o il numero di unità del premio, in base al livello retributivo del dipendente. Se **Abilita sostituzioni per livelli** è impostato su **Sì** per i dipendenti che sono iscritti al piano di retribuzione variabile, il sistema prende il livello dalla mansione di un dipendente e quindi lo cerca nella tabella delle sostituzioni livelli per determinare la percentuale o il numero di unità per tale livello. Se il livello non viene trovato nella tabella delle sostituzioni livelli, la percentuale o il numero di unità predefinito dalla scheda **Generale** viene utilizzato. La percentuale e il numero di unità possono inoltre essere sostituiti nell'iscrizione del dipendente nel piano di retribuzione variabile.

## <a name="variable-compensation-enrollment"></a>Iscrizione retribuzione variabile
### <a name="determine-who-is-eligible-for-the-plan"></a>Stabilire chi è idoneo per il piano

Se si desidera iscrivere i dipendenti a un piano di retribuzione variabile, il primo passaggio consiste nello stabilire chi è idoneo per la retribuzione specificata nel piano. Non è possibile assegnare il piano ai dipendenti se non si stabilisce l'idoneità. Per impostare l'idoneità, aprire la pagina **Regole di idoneità** per creare una nuova regola di idoneità per il piano, quindi definire i criteri che un dipendente deve soddisfare per essere idoneo per il piano di retribuzione. È possibile limitare l'idoneità in base al reparto, al sindacato, al paese di retribuzione (località), alla mansione, alla funzione lavorativa, al tipo di mansione e/o al livello retributivo. I dipendenti possono essere iscritti a un piano di retribuzione solo se soddisfano **tutti** i criteri impostati nella regola di idoneità. 

**Nota:** le regole di idoneità determinano l'idoneità per i piani di retribuzione fissa e variabile. Le regole di idoneità utilizzano i seguenti campi nei record relativi a mansione, posizione e dipendente per stabilire se un dipendente è idoneo per un piano di retribuzione:

-   Nella pagina **Mansione**:
    -   Il campo **Mansione**
    -   I campi **Funzione** e **Tipo di mansione** sulla scheda **Classificazione mansione**
    -   Il campo **Livello** sulla scheda **Retribuzione**
-   Nella pagina **Posizioni**: i campi **Reparto** e **Paese di retribuzione**
-   Nella pagina **Dipendenti**: le informazioni sui sindacati associati al dipendente in **Informazioni personali** &gt; **Sindacati** sulla scheda ****Lavoratore****

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a>Abilitare l'iscrizione al piano di retribuzione variabile

Nella pagina **Piani di retribuzione variabile**, impostare l'opzione **Abilita iscrizione** su **Sì** per consentire l'iscrizione dei dipendenti idonei al piano.

### <a name="enroll-the-employee"></a>Iscrivere il dipendente al piano

È ora possibile iscrivere i dipendenti al piano di retribuzione variabile. Per iscrivere un dipendente, passare alla pagina **Dipendenti** e selezionare il dipendente. Quindi, nel riquadro azioni, fare clic su **Retribuzione** &gt; **Iscrizione al piano di retribuzione variabile**. 

**Nota:** l'opzione **Iscrizione** deve essere impostata su **Sì** nel piano di retribuzione variabile. Il campo **Piano** indica solo i piani per i quali un dipendente è idoneo in base alle regole di idoneità impostate per tali piani. Se non si specifica alcuna regola di idoneità per un piano, nessun dipendente sarà idoneo per tale piano. 

Assicurarsi che il campo **Data di validità** sia impostato correttamente. Se il piano di retribuzione variabile utilizza il metodo di calcolo **Composito**, la data di validità dell'iscrizione può essere considerata durante il calcolo del premio del dipendente. 

È possibile utilizzare la scheda **Sostituzioni** per sostituire i valori specifici per il dipendente. Ad esempio, se **Regola di assunzione**  è impostato su **Percentuale** nel piano e una data di assunzione diversa deve essere utilizzata durante il calcolo della percentuale dell'assunzione del dipendente, è possibile impostare la data di assunzione nel campo **Data regola di assunzione**. È inoltre possibile sostituire il valore **Percentuale premio** o il valore **Numero di unità** per un dipendente specifico, a seconda delle impostazioni del piano. Questi valori verranno comunque moltiplicati per la regola di assunzione, i fattori di prestazioni e altri impostazioni nel piano. 

**Sostituzioni organizzative** vengono utilizzate per basare il premio del dipendente sulle prestazioni di uno o più reparti. La percentuale allocata tra reparti deve essere pari al 100%. La singola prestazioni di un dipendente viene anche considerata. Queste impostazioni vengono utilizzate solo se **Retribuzione basata sulla produttività** è selezionata quando viene eseguito il processo retributivo.

<a name="see-also"></a>Vedere anche
--------

[Piani di retribuzione](compensation-plans.md)




