---
title: Configurare le regole e le opzioni di idoneità
description: Questo articolo descrive come impostare le regole e le opzioni di ammissibilità nella gestione dei benefici in Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b4c8cd4e32880df771a4a72237d212e061f849ce
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848254"
---
# <a name="configure-eligibility-rules-and-options"></a>Configurare le regole e le opzioni di idoneità 


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dopo aver configurato i parametri necessari per Gestione benefit è possibile creare regole di idoneità, pacchetti, periodi e programmi da associare ai piani di benefit.

Le regole di idoneità vengono utilizzate per determinare se i dipendenti sono idonei per un piano. I dipendenti devono soddisfare la condizione di almeno una regola per essere considerati idonei al benefit. Ad esempio, hai due regole su un piano. La prima regola (riga 1) afferma che il tipo di dipendente deve essere **Dipendente**. La seconda regola (riga 2) afferma che il tipo di dipendente deve essere impegato a tempo pieno. Pertanto, i dipendenti che soddisfano la regola 1 sono idonei anche se sono assunti solo a tempo parziale.

Tuttavia, puoi impostare una singola regola con più condizioni. In questo caso, i dipendenti devono soddisfare tutte le condizioni della regola per essere considerati idonei al benefit. Ad esempio, hai una regola denominata **Dipendente a tempo pieno**. Questa regola stabilisce che il tipo di dipendente deve essere **Dipendente** *e* il lavoratore deve essere assunto a tempo pieno. Pertanto, i dipendenti devono soddisfare entrambe le condizioni della regola per essere idonei.

> [!IMPORTANT]
> Ad ogni piano di benefit deve essere associata almeno una regola di idoneità. Puoi associare più regole a un benefit.

## <a name="create-an-eligibility-rule"></a>Creare una regola di idoneità

Le regole di idoneità definiscono quali dipendenti possono iscriversi a ciascun piano di benefit. Dopo aver definito le regole di idoneità, le si assegnano a piani di benefit. Successivamente è possibile elaborare l'idoneità di iscrizione per determinare quali dipendenti sono idonei per ciascun piano. 

Durante l'iscrizione aperta, i dipendenti possono selezionare piani di benefit. Se non sono più idonei per un piano di benefit in base alle regole di idoneità dopo essersi iscritti, la loro iscrizione non viene annullata automaticamente. In genere, quando si verifica un evento reale che influisce sull'idoneità al piano, viene avviato un periodo di iscrizione affinché il dipendente selezioni i piani per i quali è idoneo. 

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni e regole di idoneità**.

2. Nella scheda **Regole di idoneità**, selezionare **Nuovo** per creare una regola di idoneità. Per visualizzare i piani associati a una regola di idoneità, selezionare **Piani associati**.

3. Specifica i valori per i seguenti campi.

   | Campo | descrizione |
   | --- | --- |
   | **Regola di idoneità** | Identificatore univoco per la regola di idoneità. |
   | **Descrizione** | Descrizione della regola di idoneità. |
   | **Ora e data di inizio validità** | Data di inizio della regola di idoneità. | 
   | **Ora e data di fine validità** | Data di fine della regola di idoneità. |
   | **Tipo di dipendente utente** | Specifica se utilizzare il tipo di dipendente del dipendente nella regola di idoneità ai benefit. |
   | **Tipo di lavoratore** | Il tipo di lavoratore, se **Usa tipo di dipendente** è impostato su **Sì**. |
   | **Usa stato dipendenti** | Specifica se utilizzare lo stato del dipendente nella regola di idoneità ai benefit. |
   | **Stato** | Lo stato del dipendente, se **Usa stato dipendenti** è impostato su **Sì**. Se **Usa stato dipendenti** è impostato su **No**, il campo non viene utilizzato. |
   | **Usa categoria impiego** | Specifica se utilizzare il valore **Categoria di impiego** del dipendente come parte della regola di idoneità ai benefit. | 
   | **Categoria impiego** | La categoria di impiego del dipendente se **Usa categoria di impiego** è impostato su **Sì**. |
   | **Usa regola nuova assunzione** | Specifica se utilizzare il valore del periodo di nuova assunzione come parte della regola di idoneità ai benefit. |
   | **Periodo di iscrizione** | Il periodo di tempo in cui è consentita l'iscrizione di un nuovo assunto. Se si imposta anche questa opzione in Parametri, l'impostazione in Parametri è prioritaria. |
   | **Usa lo stato di impiego precedente** | Specifica se utilizzare lo stato di impiego precedente del dipendente come parte della regola di idoneità ai benefit. Ad esempio, è possibile specificare una regola di idoneità che revoca un periodo di attesa di copertura per tutti i dipendenti che sono passati dallo stato **Licenziato** a **Occupato** entro 90 giorni dalla loro precedente occupazione. |

4. Sotto **Criteri aggiuntivi**, selezionare le seguenti opzioni e aggiungere informazioni come necessario.

   | Opzione | descrizione |
   | --- | --- |
   | **Età idonea** | Specifica la fascia o le fasce di età richieste per soddisfare la regola di idoneità. |
   | **Reparto idoneo** | Specifica il reparto o i reparti a cui deve appartenere un dipendente per soddisfare la regola di idoneità. |
   | **Tipo di impiego idoneo** | Specifica il tipo o i tipi di impiego in cui un dipendente deve essere categorizzato per soddisfare la regola di idoneità. Ad esempio, a tempo pieno o part-time. |
   | **Processo idoneo** | Specifica il lavoro o i lavori che soddisfano la regola di idoneità. I lavori sono associati alle posizioni e le posizioni sono occupate dai dipendenti. |
   | **Funzione lavorativa idonea** | Specifica la funzione o le funzioni lavorative che soddisfano la regola di idoneità. Ad esempio, addetti alle vendite o tecnici. |
   | **Tipo di processo idoneo** | Specifica il tipo o i tipi di lavoro che soddisfano la regola di idoneità. Ad esempio, impiegato o dirigente. |
   | **Persona giuridica idonea** | Specifica la persona giuridica o le persone giuridiche valide per la regola di idoneità. Ad esempio, Contoso Entertainment System USA. |
   | **Area di retribuzione idonea** | Specifica l'ubicazione del dipendente che soddisfa la regola di idoneità. Ad esempio, Stati Uniti centrali. |
   | **Posizione idonea** | Specifica la posizione o le posizioni che soddisfano la regola di idoneità. Ad esempio, Assistente risorse umane o Responsabile risorse umane. |
   | **Tipo di posizione idoneo** | Specifica il tipo o i tipi di posizione che soddisfano la regola di idoneità. Ad esempio, a tempo pieno. |
   | **Stato idoneo** | Specifica gli stati o le province che soddisfano la regola di idoneità. Ad esempio, North Dakota USA o Columbia Britannica, Canada. |
   | **Condizioni di impiego idonee** | Specifica le condizioni di impiego che soddisfano la regola di idoneità. Ad esempio, a volontà o contratto di gruppo. |
   | **Sindacato idoneo** | Specifica le adesioni a un sindacato che soddisfano la regola di idoneità. Ad esempio, Forklift Drivers of America.</br></br>Quando si utilizza una regola di idoneità basata sul sindacato, il record sindacale del lavoratore deve contenere una data di fine. Non è possibile lasciare il campo vuoto. |
   | **Codice postale/CAP idoneo** | Specifica i codici postali/CAP che soddisfano la regola di idoneità. Ad esempio, 58104. |

5. Sotto **Dettagli aggiuntivi**, è possibile visualizzare i seguenti dettagli aggiuntivi.

   | Campo | descrizione |
   | --- | --- |
   | **Campo utente idoneo** | Specifica ulteriori regole di idoneità basate sui campi definiti dal cliente. |
   | **Tipo di idoneità** | Specifica la categoria di criteri selezionata sotto **Criteri aggiuntivi**. |
   | **Riferimento di idoneità** | Specifica i valori selezionati sotto **Criteri aggiuntivi**. |
   | **Descrizione** | La descrizione selezionata sotto **Criteri aggiuntivi**. |

6. Selezionare **Salva**.

## <a name="using-custom-fields-in-eligibility-rules"></a>Utilizzo di campi personalizzati nelle regole di idoneità

[Campi personalizzati](hr-developer-custom-fields.md) possono essere creati all'interno di Human Resources per tenere traccia di informazioni aggiuntive. Questi campi possono essere aggiunti direttamente all'interfaccia utente e una colonna viene aggiunta dinamicamente alla tabella sottostante.  

I campi personalizzati possono essere utilizzati nel processo di idoneità. Le regole di idoneità possono utilizzare uno o più valori di campi personalizzati per determinare l'idoneità di un dipendente.  Per aggiungere un campo personalizzato a una regola esistente o per creare una nuova regola, vai a **Gestione benefit > Collegamenti> Configurazione > Regole di idoneità> Idoneità del campo personalizzato**. All'interno di questa pagina, puoi creare una regola che utilizza uno o più campi personalizzati e puoi definire più valori per ogni campo personalizzato per determinare l'idoneità.

Le tabelle seguenti supportano i campi personalizzati che possono essere utilizzati nell'elaborazione dell'idoneità:

- Lavoratore (HcmWorker)  
- Lavoro (HcmJob)  
- Posizione (HcmPosition)  
- Dettaglio posizione (HcmPositionDetail)  
- Assegnazione lavoratore posizione  
- Impiego (HcmEmployment)  
- EmploymentDetails (HcmEmploymentDetails)  
- Dettagli processo (HcmJobDetails)  

I tipi di campi personalizzati seguenti sono supportati nell'elaborazione dell'idoneità:

- Testo  
- Elenco a discesa  
- Numero  
- Decimali  
- Casella di controllo  

La tabella seguente mostra le informazioni sui campi del modulo di idoneità del campo personalizzato.

| Campo  | descrizione |
|--------|-------------|
| Nome | Nome dei criteri che si sta creando. |
| Nome tabella | Il nome della tabella che contiene il campo personalizzato utilizzato per la regola di idoneità. |
| Nome campo | Il campo che verrà utilizzato per la regola di idoneità. |
| Tipo di operatore | Visualizza l'operatore utilizzato nella configurazione dell'idoneità del campo personalizzato. |
| Valore | Visualizza il valore utilizzato nella configurazione dell'idoneità del campo personalizzato. |

## <a name="eligibility-logic"></a>Logica di idoneità

Le sezioni seguenti descrivono come viene elaborata l'idoneità ai benefit.

### <a name="rules-assigned-to-a-plan"></a>Regole assegnate a un piano 
Quando più regole di idoneità vengono assegnate a un piano di benefit, un dipendente deve soddisfare almeno una regola per essere idoneo a iscriversi al piano di benefit.  Nell'esempio seguente, il dipendente deve soddisfare i requisiti della regola **Tipo di lavoro** o la regola **Dipendenti attivi**.

![Il dipendente deve soddisfare i requisiti della regola Tipo di lavoro o la regola Dipendenti attivi.](media/RulesAssignedToAPlan.png)
 
### <a name="criteria-within-an-eligibility-rule"></a>Criteri all'interno di una regola di idoneità 
All'interno di una regola si definiscono i criteri che compongono la regola. Nell'esempio sopra, i criteri per la regola **Tipo di lavoro** è dove Tipo di lavoro = Direttori. Pertanto, il dipendente deve essere un dirigente per essere idoneo. Questa è una regola in cui esiste un solo criterio all'interno della regola.

È possibile definire regole che hanno più criteri. Quando si definiscono più criteri all'interno di una regola di idoneità, un dipendente deve soddisfare tutti i criteri all'interno della regola per essere idoneo per il piano di benefit. 

Ad esempio, la regola **Dipendenti attivi** di cui sopra si compone dei seguenti criteri. Affinché il dipendente possa essere idoneo in base alla regola **Dipendenti attivi**, il dipendente deve essere impiegato nella persona giuridica USMF *e* avere un tipo di posizione a tempo pieno.  

![Criteri all'interno di una regola di idoneità.](media/CriteriaWithinAnEligibilityRule.png) 
 
### <a name="multiple-conditions-within-criteria"></a>Molteplici condizioni all'interno dei criteri

Le regole possono essere ulteriormente ampliate per utilizzare più condizioni all'interno di un singolo criterio. Il dipendente deve soddisfare almeno una condizione per essere idoneo. Per costruire sull'esempio sopra, la regola **Dipendenti attivi** può essere ulteriormente ampliata per includere i dipendenti che sono anche dipendenti part-time. Di conseguenza, ora il dipendente deve essere un dipendente in USMF *e* un dipendente a tempo pieno o part-time.  

![Molteplici condizioni all'interno dei criteri.](media/MultipleConditionsWithinCriteria.png) 
 
### <a name="eligibility-conditions-within-a-custom-field-criterion"></a>Condizioni di idoneità all'interno di un criterio di campo personalizzato 
Analogamente a quanto sopra, i campi personalizzati possono essere utilizzati durante la creazione di regole di idoneità e funzionano allo stesso modo. Ad esempio, potresti voler offrire un rimborso Internet ai dipendenti di Fargo e Copenhagen che lavorano da casa, poiché i costi di Internet sono più alti in quelle località. Per fare ciò, crea due campi personalizzati: **Posizione dell'ufficio** (elenco di selezione) e **Lavoro da casa** (casella di controllo). Quindi crea una regola chiamata **Dipendenti WFH**. Il criterio per la regola è dove **Sede dell'ufficio = Fargo** o **Copenaghen** *e* dove **Lavoro da casa = Sì**.

Le regole di ammissibilità personalizzate dovrebbero essere impostate come indicato nell'immagine seguente. 

![Condizioni di idoneità all'interno di un criterio di campo personalizzato.](media/EligibilityConditionsWithinACustomFieldCriterion.png) 
 
## <a name="configure-bundles"></a>Configurare i pacchetti

I pacchetti sono un set di piani di benefit correlati. È possibile utilizzare pacchetti di benefit per raggruppare i piani di benefit che un dipendente deve scegliere per iscriversi a determinati piani di benefit che potrebbero dipendere da altre iscrizioni a piani di benefit. Esempi di quando si potrebbe voler utilizzare un pacchetto includono:

- Un pacchetto di piani sanitari che include un'assicurazione sanitaria altamente deducibile con un conto di risparmio sanitario associato (HSA).

- Un piano di assicurazione sulla vita con un piano di assicurazione sulla vita obbligatorio per i dipendenti abbinato a un piano di assicurazione sulla vita per persone a carico. Ciò garantirebbe l'impossibilità per un dipendente di selezionare un'assicurazione sulla vita per persone a carico senza iscriversi alla copertura dei dipendenti.

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni e regole di idoneità**.

2. Nella scheda **Pacchetti**, selezionare **Nuovo** per creare un pacchetto. Per visualizzare i piani associati a un pacchetto, selezionare **Piani associati**.

3. Specifica i valori per i seguenti campi.

   | Campo | descrizione |
   | --- | --- |
   | **Aggregazione** | Identificatore univoco per il pacchetto. |
   | **Descrizione** | Descrizione del pacchetto. |
   | **Generale** | Indica se uno dei piani del pacchetto deve essere contrassegnato come piano generale. Il piano generale deve essere selezionato durante l'iscrizione aperta come parte del pacchetto prima che l'amministratore dei benefit possa confermare le selezioni dei benefit del dipendente. |
   | **Ora e data di inizio validità** | Data e ora in cui il pacchetto diventa attivo. |
   | **Data di fine validità** | Data di scadenza del pacchetto. La data predefinita è 31/12/2154 (che rappresenta mai). |

4. Selezionare **Salva**.

## <a name="configure-periods"></a>Configurare i periodi

I periodi definiscono quando i benefit sono in vigore e quando i dipendenti possono iscriversi. È possibile creare un numero illimitato di periodi per mantenere aperte le iscrizioni ai benefit e i periodi di copertura dei benefit. Gli anni del piano di benefit possono o meno seguire un anno solare. 

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni e regole di idoneità**.

2. Nella scheda **Periodi**, selezionare **Nuovo** per creare un periodo. Per eseguire un processo che allega tutti i piani di benefit attivi validi al periodo di benefit, selezionare **Associa piani**. Per visualizzare i piani associati a un pacchetto, selezionare **Piani associati**. 

3. Specifica i valori per i seguenti campi.

   | Campo | descrizione |
   | --- | --- |
   | **Periodo** | Identificatore univoco per il periodo. |
   | **Ora e data di inizio validità** | Data e ora di inizio della validità del periodo di benefit. |
   | **Ora e data di fine validità** | Data e ora in cui il periodo di benefit diventa inattivo. |
   | **Inizio iscrizione** | Data di inizio dell'iscrizione aperta. L'iscrizione aperta è quando un dipendente può scegliere i benefit. |
   | **Fine iscrizione** | Data di fine dell'iscrizione aperta. |
   | **Scadenze aperte** | Indica se il periodo è aperto in base alla data di sistema e alle date e ore di inizio e fine validità. | 
   | **Periodo precedente** | Specifica il periodo di benefit che precede il periodo di benefit selezionato. Queste informazioni vengono utilizzate durante l'iscrizione all'idoneità ai benefit per assegnare piani, opzioni di copertura e beneficiari di un anno precedente. |
 
4. Selezionare **Salva**.

## <a name="use-a-flex-credit-program"></a>Utilizzare un programma di crediti flessibili

È possibile utilizzare programmi di crediti flessibili per iscrivere i dipendenti ai benefit secondo un numero prestabilito di crediti flessibili. I dipendenti possono scegliere il modo in cui allocare i propri crediti flessibili. Ad esempio, se un dipendente è coperto dal piano di assicurazione sanitaria del coniuge, potrebbe voler utilizzare i crediti che avrebbe altrimenti utilizzato per la copertura sanitaria per altri benefit.

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni e regole di idoneità**.

2. Nella scheda **Periodi**, selezionare **Programmi di crediti flessibili**.

3. Selezionare un programma di crediti flessibili da applicare. I campi contengono le seguenti informazioni.

   | Campo | descrizione |
   | --- | --- |
   | **ID credito benefit** | L'identificatore univoco del programma di crediti flessibili. |
   | **Descrizione** | Una descrizione del programma di crediti flessibili. | 
   | **Dal** | La data in cui il programma di crediti flessibili diventa attivo. |
   | **Al** | La data di fine del programma di crediti flessibili. È possibile mantenere il valore predefinito (31/12/2154) per indicare che il programma di crediti flessibili non ha una scadenza programmata. |
   | **Valore di credito totale** | Il numero di crediti che ciascun dipendente dovrà utilizzare per i propri benefit. |
   | **Regola di ripartizione** | La regola da utilizzare per ripartire i crediti flessibili quando un dipendente viene assunto durante il periodo di credito flessibile. </br></br><ul><li>**Nessuna** - Il dipendente non riceve crediti flessibili se viene assunto dopo l'inizio del periodo del programma di crediti flessibili.</li><li>**Credito totale** - Il dipendente riceve l'intero importo di crediti flessibili, indipendentemente da quando è stato assunto.</li><li>**Ripartizione** - Il dipendente riceve una quantità di crediti flessibili ripartita proporzionalmente in base alla data di inizio.</li></ul> |
   | **Formula di ripartizione del credito flessibile** | La regola da utilizzare per ripartire i crediti flessibili per i dipendenti che vengono assunti durante un periodo di benefit per il programma di crediti flessibili. La ripartizione si basa sulla data di inizio dell'impiego. Questo campo è utilizzato solo se si seleziona **Ripartizione** nel campo **Regola di ripartizione**. </br></br><ul><li>**Giornaliero** - Ripartisce il numero di crediti flessibili che un dipendente riceve a livello giornaliero. Il numero totale di crediti flessibili è diviso per il numero di giorni nel periodo. Ad esempio, se il periodo di benefit è 400 giorni, il sistema dividerà il numero totale di crediti flessibili per 400 per calcolare il numero di crediti flessibili che i dipendenti ricevono giornalmente.</li><li>**Mese corrente** - Ripartisce il numero di crediti flessibili che un dipendente riceve a livello mensile, arrotondato al mese corrente. Il numero totale di crediti flessibili è diviso per il numero di mesi nel periodo. Ad esempio, se il periodo di benefit è 15 mesi, il sistema dividerà il numero totale di crediti flessibili per 15 per calcolare il numero di crediti flessibili che i dipendenti ricevono al mese.</li><li>**Mese successivo** - Ripartisce il numero di crediti flessibili che un dipendente riceve a livello mensile, arrotondato al mese successivo. Il numero totale di crediti flessibili è diviso per il numero di mesi nel periodo. Ad esempio, se il periodo di benefit è 15 mesi, il sistema divide il numero totale di crediti flessibili per 15 per calcolare il numero di crediti flessibili che i dipendenti ricevono al mese.</li></ul> |
   
   Assicurarsi che ciascun piano di benefit sia iscritto a un solo programma di crediti flessibili per periodo di benefit. In caso contrario, il sistema non saprà quale programma di crediti flessibili utilizzare per concedere crediti flessibili e si verificheranno dei problemi. 

## <a name="configure-programs"></a>Configurare i programmi

I programmi sono una serie di piani di benefit che condividono un set comune di regole di idoneità. È possibile definire regole di idoneità per l'intero programma anziché per ogni singolo piano. Ad esempio, un programma FTE di Contoso Canada o un programma di livello esecutivo di Contoso Europa. 

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni e regole di idoneità**.

2. Nella scheda **Programmi**, selezionare **Nuovo** per creare un programma. Per creare eccezioni per i dipendenti che non soddisfano i requisiti della regola di idoneità, selezionare **Sostituzione regole di idoneità**. Per visualizzare i piani associati a un programma, selezionare **Piani associati**.

3. Specifica i valori per i seguenti campi.

   | Campo | descrizione |
   | --- | --- |
   | **Programma** | Identificatore univoco per un il programma. |
   | **Descrizione** | Descrizione del programma. | 
   | **Ora e data di inizio validità** | Data e ora in cui il programma diventa attivo. |
   | **Ora e data di fine validità** | Data e ora in cui il programma scade. La data predefinita è 31/12/2154 (che rappresenta mai). |
   | **Periodo di attesa copertura** | Il periodo che un dipendente deve attendere prima dell'inizio della copertura per il programma di benefit. |
   | **Periodo di attesa detrazione** | Il periodo che un dipendente attende prima dell'inizio delle detrazioni per il programma di benefit. |
   | **Regole di idoneità** | Selezionare le regole di idoneità da applicare al programma di benefit. Le regole di ammissibilità vengono definite nella scheda **Regole di idoneità** in questa pagina. |
   
4. Selezionare **Salva**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
