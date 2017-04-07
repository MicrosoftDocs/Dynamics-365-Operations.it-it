---
title: Creare piani di retribuzione variabile
description: La retribuzione variabile rappresenta una retribuzione non regolare del dipendente, ad esempio premio o premi in azioni. In questo argomento vengono descritti i componenti che devono essere impostate per poter utilizzare la retribuzione variabile e registrare un dipendente a un piano di retribuzione variabile.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HCMCompEligibility, HcmJobFunction, HcmWorker, HRMCompPerfPlan
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16011
ms.assetid: fc3a394e-9ac6-4f8c-9162-dc16ec22720f
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9397e84f03ee5b340fa2aa0a64e582fc0078526e
ms.openlocfilehash: be156afa73de731e54985485b617bcbae883db3a
ms.lasthandoff: 03/31/2017


---

# <a name="create-variable-compensation-plans"></a>Creare piani di retribuzione variabile

La retribuzione variabile rappresenta una retribuzione non regolare del dipendente, ad esempio premio o premi in azioni. Questo articolo descrive i componenti che devono essere impostati per utilizzare una retribuzione variabile e per iscrivere un dipendente in un piano di compensazione variabile.

Il calcolo degli importi di retribuzione variabile per i dipendenti può basarsi su diversi fattori, ad esempio le prestazioni del dipendente, il livello retributivo del dipendente e le prestazioni del reparto.

## <a name="variable-compensation-components"></a>Componenti della retribuzione variabile
### <a name="create-compensation-types"></a>Creare tipi di retribuzione

I **tipi di retribuzione variabile **costituiscono una componente necessaria. I tipi di retribuzione variabile consentono di descrivere i tipi di retribuzione assegnati dall'organizzazione. Consentono inoltre di specificare se la retribuzione avverrà in contanti o mediante un modulo non monetario, ad esempio come scorte.

### <a name="describe-vesting-rules"></a>Descrivere regole di distribuzione incentivi

Facoltativamente, le società possono impostare **regole di distribuzione incentivi**. Conferendo le regole viene descritto come premio variabile deve disporre nel tempo. Ad esempio, una regola di distribuzione degli incentivi è possibile che il dipendente riceverà il 25 del premio totale per ciascun anno i quattro anni successivi. Conferendo le regole sono solo informative.

## <a name="variable-compensation-plans"></a>Piani di retribuzione variabile
Il **piano di retribuzione variabile** contiene le regole, i metodi di calcolo e i valori predefiniti per il calcolo di retribuzione variabile per dipendenti iscritti al piano. Quando si crea un piano di retribuzione variabile, è necessario impostare il tipo di retribuzione variabile. Tipo di retribuzione variabile determinano se il sistema calcolerà un importo in valuta o un numero di unità come premio. È inoltre necessario impostare il metodo di calcolo:

-   ** Il momento ** il calcolo del premio variabile è basato sulla retribuzione fissa che il dipendente ha avuto in una data specifica. Tale data viene specificata sull'evento processo quando nuovi importi di incremento retributivo verranno elaborati.
-   **Composito**: un importo del premio viene calcolato per ogni tariffa retributiva univoca della retribuzione fissa che il dipendente ha percepito tra la data di inizio e la data di fine del ciclo nell'evento di processo. I tassi vengono combinati per determinare il premio finale. Ad esempio, durante il ciclo, un dipendente trasferito in un percorso diverso che ha un tasso retributivo diverso. In questo caso, il premio variabile viene rettificato in base alla durata di ogni tariffa retributiva del dipendente.

L'importo del premio variabile può basarsi su una percentuale del reddito di base regolare del dipendente o su un numero stabilito di unità.

-   Selezionare l'opzione **Percentuale della base** per immettere una percentuale predefinita e specificare se la base deve essere la tariffa di retribuzione fissa del dipendente o il punto di controllo per il livello retributivo del dipendente. Livello retributivo viene impostato sulla mansione dei dipendenti. Uno dei punti di riferimento dalla struttura retributiva può essere impostato come punto di controllo nel piano di retribuzione fissa. Nel sistema verrà utilizzato il livello retributivo dal processo del dipendente e lo riferirà al punto di controllo elencato nel piano di retribuzione fissa del dipendente e l'importo di controllo per il livello retributivo del dipendente. Importo del punto di controllo quindi utilizzare in sostituzione della retribuzione fissa del dipendente come base per il premio.
-   Selezionare l'opzione** Numero di unità** per immettere un numero di unità predefinito, il valore di ciascuna unità e la valuta del valore unitario se il piano di retribuzione è relativo a un premio non in contanti (ad esempio, 200 unità di scorte che vengono valutate a 40 EUR) o solo il numero di unità se il piano di retribuzione è relativo a un premio in contanti. Per un premio in contanti, il dipendente riceverà il numero di unità specificate della valuta utilizzata per il proprio piano di retribuzione fissa, ad esempio 500 unità di 1 EUR). Il controllo uno-a-uno di relazione può essere utilizzato per indicare se esiste un mapping uno-a-uno diretto tra il numero di unità e il valore unitario. Quando si crea un piano di retribuzione variabile per un piano base alla cassa con il numero di unità, questa verrà chiusa automaticamente su Sì ** ** e il valore unitario è 1.0000 ** **.

** Regola di assunzione ** l'impostazione consente di specificare se tutti i dipendenti devono ricevere lo stesso aumento, indipendentemente dalla data che sono stati Dipendente (** regola di assunzione ** = ** ** nessuno), ovvero se i dipendenti devono ricevere una percentuale del premio basato sulla durata del lavoro durante il ciclo (** regola di assunzione ** = ** la percentuale **). 

** Influenza ** consente di rettificare il premio dipendente, a seconda delle prestazioni del reparto del dipendente. La stato delle prestazioni può essere impostata per ciascun reparto ** reparti ** nella pagina, in ** moduli correlati ** &gt; ** retribuzione ** &gt; ** ** prestazioni. Il premio che i dipendenti del reparto ricevono dipende dal valore di ** la percentuale di obiettivo raggiunta ** sistema, che indica le prestazioni del reparto:

-   Se le prestazioni del reparto sono 100 percento, il premio per i dipendenti in tale reparto viene moltiplicato per la percentuale impostata nel campo** Pagamento al 100%**.
-   Se le prestazioni del reparto sono superiori al 100 percento, il sistema aggiunge la percentuale impostata nel campo **Ogni 1% al di sopra dell'obiettivo** alla percentuale impostata nel campo **Pagamento al 100%** finché non viene raggiunto il valore impostato nel campo **Pagamento massimo consentito**.
-   Se le prestazioni del reparto sono inferiori al 100 percento, il sistema sottrae la percentuale impostata nel campo **Ogni 1% al di sotto dell'obiettivo** dalla percentuale impostata nel campo **Pagamento al 100%** finché non viene raggiunto il valore impostato nel campo **Pagamento minimo consentito**.

È possibile impostare** livelli di tolleranza** sulle percentuali di soglia in modo da visualizzare un messaggio di avviso se il fattore causa il superamento della percentuale di soglia. 

Per impostazione predefinita, il sistema cerca il reparto impostato in base alla posizione. Tuttavia, il premio per alcuni dipendenti potrebbe dipendere dalle prestazioni di più reparti. In questo caso, i diversi reparti e la percentuale del premio assegnato alla prestazione di ciascun reparto possono essere impostate sull'iscrizione della retribuzione variabile dipendente. Per ulteriori informazioni, vedere la sezione di registrazione di retribuzione variabile" che segue. 

Il fattore viene utilizzato solo se l'impostazione **Retribuzione basata sulla produttività** è selezionata quando viene eseguito il processo retributivo. 

** I livelli sovrascrive ** la scheda consente di sostituire la percentuale predefinita o il numero di unità del premio, in base al livello retributivo del dipendente. ** Se abilitare sovrascrive per i livelli ** è impostato su Sì ** ** per i dipendenti che sono iscritti al piano di retribuzione variabile, vengono presi il livello retributivo o dipendenti e quindi liquidarla la ricerca nei livelli sostituisce la tabella per determinare la percentuale o il numero di unità per tale livello. Se il livello non viene ricavato dal livello sostituisce la tabella, la percentuale predefinita o il numero di unità ** ** dettagli relativi all'identificazione della scheda utilizzata. Percentuale e il numero di unità possono inoltre essere sostituiti nell'iscrizione del dipendente nel piano di retribuzione variabile.

## <a name="variable-compensation-enrollment"></a>Iscrizione retribuzione variabile
### <a name="determine-who-is-eligible-for-the-plan"></a>Stabilire chi è idoneo per il piano

Se si desidera iscrivere i dipendenti a un piano di retribuzione variabile, il primo passaggio consiste nello stabilire chi è idoneo per la retribuzione specificata nel piano. Non è possibile assegnare il piano ai dipendenti se non si stabilisce l'idoneità. Per impostare l'idoneità, aprire la pagina **Regole di idoneità** per creare una nuova regola di idoneità per il piano, quindi definire i criteri che un dipendente deve soddisfare per essere idoneo per il piano di retribuzione. È possibile limitare l'idoneità in base al reparto, al sindacato, al paese di retribuzione (località), alla mansione, alla funzione lavorativa, al tipo di mansione e/o al livello retributivo. I dipendenti possono essere iscritti a un piano di retribuzione solo se soddisfano **tutti** i criteri impostati nella regola di idoneità. 

**Nota:** le regole di idoneità determinano l'idoneità per i piani di retribuzione fissa e variabile. Le regole di idoneità utilizzano i seguenti campi nei record relativi a mansione, posizione e dipendente per stabilire se un dipendente è idoneo per un piano di retribuzione:

-   Nella pagina **Mansione**:
    -   Il campo **Mansione**
    -   I campi **Funzione** e **Tipo di mansione** sulla scheda **Classificazione mansione**
    -   Il campo **Livello** sulla scheda **Retribuzione**
-   Nella pagina **Posizioni**: i campi **Reparto** e **Paese di retribuzione**
-   ** Dipendenti ** nella pagina: Le informazioni sui sindacati associate ai sindacati dipendente in ** &gt; informazioni personali ** ** ** nella scheda del **** del lavoratore di ****

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a>Abilitare l'iscrizione al piano di retribuzione variabile

Nella pagina **Piani di retribuzione variabile**, impostare l'opzione **Abilita iscrizione** su **Sì** per consentire l'iscrizione dei dipendenti idonei al piano.

### <a name="enroll-the-employee"></a>Iscrivere il dipendente al piano

È ora possibile iscrivere i dipendenti al piano di retribuzione variabile. Per iscrivere un dipendente, passare alla pagina **Dipendenti** e selezionare il dipendente. Quindi, nel riquadro azioni, fare clic su retribuzione ** ** &gt; ** registrazione variabile di piano **. 

**Nota:** l'opzione **Iscrizione** deve essere impostata su **Sì** nel piano di retribuzione variabile. ** Piano ** il campo viene visualizzato solo i piani in cui il dipendente ha diritto a, in base alle regole di idoneità impostate per i piani. Se una regola di idoneità non viene definita per un piano, non verrà apportata alcuna dipendenti idonee per il piano. 

Assicurarsi che ** data di validità ** il campo sia impostato correttamente. Se il piano di retribuzione variabile utilizza ** composizione ** il metodo di calcolo, la data di validità di registrazione può essere considerata durante il calcolo del premio dipendente. 

È possibile utilizzare ** sovrascrive ** la scheda per sostituire i valori specifici per il dipendente. Ad esempio, se ** regola di assunzione ** è impostato su ** le percentuali ** sul piano e una data diversa di assunzione deve essere utilizzato durante il calcolo della percentuale dell'assunzione del dipendente, è possibile impostare la data di assunzione ** assumere la data della regola ** nel campo. È inoltre possibile sostituire uno o ** la percentuale del premio ** il valore o ** numero di unità ** il valore per un dipendente specifico, a seconda delle impostazioni del piano. Questi valori che verranno scomposti dalla regola di assunzione, dai fattori di performance e ad altre impostazioni per il piano. 

** Organizzativo sovrascrive ** vengono utilizzati per basare il premio dipendente sulle prestazioni di uno o più reparti. Percentuale assegnata tra reparti deve essere pari al 100. La singola prestazioni di un dipendente verrà considerata. Queste impostazioni vengono utilizzate solo se ** retribuzione basata sulla produttività ** viene prelevato quando il processo retributivo viene eseguito.

<a name="see-also"></a>Vedere anche
--------

[Piani di retribuzione](compensation-plans.md)


