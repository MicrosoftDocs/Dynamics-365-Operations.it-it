---
title: Configurare le regole e le opzioni di idoneità
description: Impostare le regole e le opzioni di idoneità in Gestione vantaggi in Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 07dd8a6ca7edb460769f761950dc0c143112f708
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229903"
---
# <a name="configure-eligibility-rules-and-options"></a>Configurare le regole e le opzioni di idoneità

Dopo aver configurato i parametri necessari per Gestione benefit in Microsoft Dynamics 365 Human Resources, è possibile creare regole di idoneità, pacchetti, periodi e programmi da associare ai piani di benefit.

## <a name="create-an-eligibility-rule"></a>Creare una regola di idoneità

Le regole di idoneità definiscono quali dipendenti possono iscriversi a ciascun piano di benefit. Dopo aver definito le regole di idoneità, le si assegnano a piani di benefit. Successivamente è possibile elaborare l'idoneità di iscrizione per determinare quali dipendenti sono idonei per ciascun piano. 

Durante l'iscrizione aperta, i dipendenti possono selezionare piani di benefit. Se non sono più idonei per un piano di benefit in base alle regole di idoneità dopo essersi iscritti, la loro iscrizione non viene annullata automaticamente. In genere, quando si verifica un evento reale che influisce sull'idoneità al piano, viene avviato un periodo di iscrizione affinché il dipendente selezioni i piani per i quali è idoneo. 

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni e regole di idoneità**.

2. Nella scheda **Regole di idoneità**, selezionare **Nuovo** per creare una regola di idoneità. Per visualizzare i piani associati a una regola di idoneità, selezionare **Piani associati**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
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

4. Sotto **Criteri aggiuntivi**, selezionare le seguenti opzioni e aggiungere informazioni come necessario:

   | Opzione | Descrizione |
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
   | **Sindacato idoneo** | Specifica le adesioni a un sindacato che soddisfano la regola di idoneità. Ad esempio, Forklift Drivers of America. </br></br>Quando si utilizza una regola di idoneità basata sul sindacato, il record sindacale del lavoratore deve contenere una data di fine. Non è possibile non specificare tale valore. |
   | **Codice postale/CAP idoneo** | Specifica i codici postali/CAP che soddisfano la regola di idoneità. Ad esempio, 58104. |

5. Sotto **Dettagli aggiuntivi**, è possibile visualizzare i seguenti dettagli aggiuntivi:

   | Campo | Descrizione |
   | --- | --- |
   | **Campo utente idoneo** | Specifica ulteriori regole di idoneità basate sui campi definiti dal cliente. |
   | **Tipo di idoneità** | Specifica la categoria di criteri selezionata sotto **Criteri aggiuntivi**. |
   | **Riferimento di idoneità** | Specifica i valori selezionati sotto **Criteri aggiuntivi**. |
   | **Descrizione** | La descrizione selezionata sotto **Criteri aggiuntivi**. |

6. Selezionare **Salva**.

## <a name="configure-bundles"></a>Configurare i pacchetti

I pacchetti sono un set di piani di benefit correlati. È possibile utilizzare pacchetti di benefit per raggruppare i piani di benefit che un dipendente deve scegliere per iscriversi a determinati piani di benefit che potrebbero dipendere da altre iscrizioni a piani di benefit. Esempi di quando si potrebbe voler utilizzare un pacchetto includono:

- Un pacchetto di piani sanitari che include un'assicurazione sanitaria altamente deducibile con un conto di risparmio sanitario associato (HSA).

- Un piano di assicurazione sulla vita con un piano di assicurazione sulla vita obbligatorio per i dipendenti abbinato a un piano di assicurazione sulla vita per persone a carico. Ciò garantirebbe l'impossibilità per un dipendente di selezionare un'assicurazione sulla vita per persone a carico senza iscriversi alla copertura dei dipendenti.

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni e regole di idoneità**.

2. Nella scheda **Pacchetti**, selezionare **Nuovo** per creare un pacchetto. Per visualizzare i piani associati a un pacchetto, selezionare **Piani associati**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Pacchetto** | Identificatore univoco per il pacchetto. |
   | **Descrizione** | Descrizione del pacchetto. |
   | **Generale** | Indica se uno dei piani del pacchetto deve essere contrassegnato come piano generale. Il piano generale deve essere selezionato durante l'iscrizione aperta come parte del pacchetto prima che l'amministratore dei benefit possa confermare le selezioni dei benefit del dipendente. |
   | **Ora e data di inizio validità** | Data e ora in cui il pacchetto diventa attivo. |
   | **Data di fine validità** | Data di scadenza del pacchetto. La data predefinita è 31/12/2154 (che rappresenta mai). |

4. Selezionare **Salva**.

## <a name="configure-periods"></a>Configurare i periodi

I periodi definiscono quando i benefit sono in vigore e quando i dipendenti possono iscriversi. È possibile creare un numero illimitato di periodi per mantenere aperte le iscrizioni ai benefit e i periodi di copertura dei benefit. Gli anni del piano di benefit possono o meno seguire un anno solare. 

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni e regole di idoneità**.

2. Nella scheda **Periodi**, selezionare **Nuovo** per creare un periodo. Per eseguire un processo che allega tutti i piani di benefit attivi validi al periodo di benefit, selezionare **Associa piani**. Per visualizzare i piani associati a un pacchetto, selezionare **Piani associati**. 

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
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

3. Selezionare un programma di crediti flessibili da applicare. I campi contengono le seguenti informazioni:

   | Campo | Descrizione |
   | --- | --- |
   | ID credito benefit | L'identificatore univoco del programma di crediti flessibili. |
   | Descrizione | Una descrizione del programma di crediti flessibili. | 
   | Dal | La data in cui il programma di crediti flessibili diventa attivo. |
   | Al | La data di fine del programma di crediti flessibili. È possibile mantenere il valore predefinito (31/12/2154) per indicare che il programma di crediti flessibili non ha una scadenza programmata. |
   | Valore di credito totale | Il numero di crediti che ciascun dipendente dovrà utilizzare per i propri benefit. |
   | Regola di ripartizione | La regola da utilizzare per ripartire i crediti flessibili quando un dipendente viene assunto durante il periodo di credito flessibile. </br></br><ul><li>**Nessuna** - Il dipendente non riceve crediti flessibili se viene assunto dopo l'inizio del periodo del programma di crediti flessibili.</li><li>**Credito totale** - Il dipendente riceve l'intero importo di crediti flessibili, indipendentemente da quando è stato assunto.</li><li>**Ripartizione** - Il dipendente riceve una quantità di crediti flessibili ripartita proporzionalmente in base alla data di inizio.</li></ul> |
   | Formula di ripartizione del credito flessibile | La regola da utilizzare per ripartire i crediti flessibili per i dipendenti che vengono assunti durante un periodo di benefit per il programma di crediti flessibili. La ripartizione si basa sulla data di inizio dell'impiego. Questo campo è utilizzato solo se si seleziona **Ripartizione** nel campo **Regola di ripartizione**. </br></br><ul><li>**Giornaliero** - Ripartisce il numero di crediti flessibili che un dipendente riceve a livello giornaliero. Il numero totale di crediti flessibili è diviso per il numero di giorni nel periodo. Ad esempio, se il periodo di benefit è 400 giorni, il sistema dividerà il numero totale di crediti flessibili per 400 per calcolare il numero di crediti flessibili che i dipendenti ricevono giornalmente.</li><li>**Mese corrente** - Ripartisce il numero di crediti flessibili che un dipendente riceve a livello mensile, arrotondato al mese corrente. Il numero totale di crediti flessibili è diviso per il numero di mesi nel periodo. Ad esempio, se il periodo di benefit è 15 mesi, il sistema dividerà il numero totale di crediti flessibili per 15 per calcolare il numero di crediti flessibili che i dipendenti ricevono al mese.</li><li>**Mese successivo** - Ripartisce il numero di crediti flessibili che un dipendente riceve a livello mensile, arrotondato al mese successivo. Il numero totale di crediti flessibili è diviso per il numero di mesi nel periodo. Ad esempio, se il periodo di benefit è 15 mesi, il sistema divide il numero totale di crediti flessibili per 15 per calcolare il numero di crediti flessibili che i dipendenti ricevono al mese.</li></ul> |
   
   Assicurarsi che ciascun piano di benefit sia iscritto a un solo programma di crediti flessibili per periodo di benefit. In caso contrario, il sistema non saprà quale programma di crediti flessibili utilizzare per concedere crediti flessibili e si verificheranno dei problemi. 

## <a name="configure-programs"></a>Configurare i programmi

I programmi sono una serie di piani di benefit che condividono un set comune di regole di idoneità. È possibile definire regole di idoneità per l'intero programma anziché per ogni singolo piano. Ad esempio, un programma FTE di Contoso Canada o un programma di livello esecutivo di Contoso Europa. 

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni e regole di idoneità**.

2. Nella scheda **Programmi**, selezionare **Nuovo** per creare un programma. Per creare eccezioni per i dipendenti che non soddisfano i requisiti della regola di idoneità, selezionare **Sostituzione regole di idoneità**. Per visualizzare i piani associati a un programma, selezionare **Piani associati**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Programma** | Identificatore univoco per un il programma. |
   | **Descrizione** | Descrizione del programma. | 
   | **Ora e data di inizio validità** | Data e ora in cui il programma diventa attivo. |
   | **Ora e data di fine validità** | Data e ora in cui il programma scade. La data predefinita è 31/12/2154 (che rappresenta mai). |
   | **Periodo di attesa copertura** | Il periodo che un dipendente deve attendere prima dell'inizio della copertura per il programma di benefit. |
   | **Periodo di attesa detrazione** | Il periodo che un dipendente attende prima dell'inizio delle detrazioni per il programma di benefit. |
   | **Regole di idoneità** | Selezionare le regole di idoneità da applicare al programma di benefit. Le regole di ammissibilità vengono definite nella scheda **Regole di idoneità** in questa pagina. |
   
4. Selezionare **Salva**.
