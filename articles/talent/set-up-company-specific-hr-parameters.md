---
title: Impostare i parametri di Risorse umane specifici della società
description: Le impostazioni di alcuni parametri delle Risorse umane sono condivise tra società, mentre le impostazioni di altri parametri sono specifiche. In questo articolo viene illustrato come impostare parametri risorse umane specifici della società.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HRMParameters
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 00facce5913fb82f67c5844d74d29032735db707
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1506105"
---
# <a name="set-up-company-specific-human-resources-hr-parameters"></a>Impostare i parametri di Risorse umane specifici della società

[!include [banner](includes/banner.md)]

Le impostazioni di alcuni parametri delle Risorse umane sono condivise tra società, mentre le impostazioni di altri parametri sono specifiche. In questo articolo viene illustrato come impostare parametri risorse umane specifici della società.

Per l'impostazione dei parametri HR vengono utilizzate due pagine. Per i parametri che vengono condivisi tra le società, si utilizza la pagina **Parametri condivisi Risorse umane**. Per i parametri che sono specifici della società (vale a dire le impostazioni che si applicano a una singola società), si utilizza la pagina **Parametri Risorse umane**. Nella pagina **Parametri Risorse umane** le impostazioni sono suddivise in sei schede:

-   Generali
-   Selezione del personale - Questa funzionalità non è inclusa in Dynamics 365 for Talent
-   Retribuzione
-   Sequenze numeriche
-   Normativa per il congedo per motivi medici e familiari (FMLA)
-   Dipendente self-service

Ogni scheda contiene informazioni che si riferiscono a una singola società. Le impostazioni nella scheda **Generale** definiscono l'aspetto delle informazioni sull'assenza, gli infortuni, la malattia e le nuove assunzioni. Le impostazioni di questa scheda definiscono inoltre alcuni valori predefiniti che vengono visualizzati quando si lavora. Nello specifico, questa scheda consente di selezionare un colore da applicare alle transazioni assenze aperte, specificare il foglio di stile da utilizzare per i report, indicare se attivare l'integrazione tra corsi di formazione e registrazione delle assenze e selezionare il codice assenza utilizzato per controllare questa integrazione. È inoltre possibile indicare per quanto tempo mantenere i casi su eventi di infortunio e malattia e specificare il numero di identificazione predefinito che viene visualizzato quando viene assunto un nuovo lavoratore. 

Le impostazioni nella scheda **Selezione del personale** definiscono i tipi di documenti che vengono utilizzati per la corrispondenza che viene automaticamente inviata ai candidati e il progetto di selezione del personale che viene utilizzato per le domande di lavoro non sollecitate (le domande che non appartengono a un progetto specifico di selezione del personale). Il periodo che viene definito per l'aging del progetto di selezione determina i progetti di selezione che sono inclusi nel riquadro **Progetti di aging** nell'area di lavoro **Gestione della selezione del personale**. Il periodo che viene definito per l'avviso di scadenza della domanda di lavoro viene utilizzato per visualizzare i progetti di selezione che si avvicinano alla scadenza della domanda nel riquadro **Scadenza domanda di lavoro imminente** nell'area di lavoro **Selezione del personale**. 

Le impostazioni della scheda **Retribuzione** definiscono se gli utenti devono confermare che desiderano salvare le informazioni relative a un piano di retribuzione fissa o variabile. Se si seleziona la casella di controllo **Attivare la convalida del salvataggio**, qualsiasi momento che gli utenti chiudono una pagina correlata alla retribuzione, ricevono un messaggio in cui viene chiesto se si desidera salvare il record. Alcune pagine della gestione delle retribuzioni non permettono agli utenti di eliminare le informazioni. Di conseguenza, la richiesta agli utenti per verificare se desiderano salvare le informazioni può limitare la quantità di informazioni che vengono salvate, ma che non possono essere successivamente eliminate. Se la casella di controllo **Attivare la convalida del salvataggio** è deselezionata, i record vengono sempre salvati immediatamente, possibilmente prima che l'utente sia pronto. Se si utilizza la gestione delle prestazioni, nella scheda **Retribuzione** è possibile selezionare un modello di valutazione da utilizzare al posto di quello assegnato ai piani di retribuzione durante la valutazione delle prestazioni. 

### <a name="previously-released-functionality"></a>Funzionalità già rilasciata
Le impostazioni nella scheda **Sequenza numerica** determinano le sequenze che vengono utilizzate per assegnare automaticamente gli ID agli elementi in Risorse umane, ad esempio le domande di lavoro, le registrazioni delle assenze, i risultati del processo retributivo, i numeri dei casi, i corsi e le agende dei corsi. Per gestire i codici e riferimenti delle sequenze numeriche, utilizzare la pagina elenco **Sequenze numerich** e (fare clic su **Amministrazione organizzazione** &gt; **Sequenze numeriche** &gt; **Sequenze numeriche**).

### <a name="if-youre-using-dynamics-365-for-talent"></a>Se si utilizza Dynamics 365 for Talent
Le impostazioni nella scheda **Sequenza numerica** determinano le sequenze che vengono utilizzate per assegnare automaticamente gli ID agli elementi in Risorse umane, ad esempio le domande di lavoro, le registrazioni delle assenze, i risultati del processo retributivo, i numeri dei casi, i corsi e le agende dei corsi. Per gestire i codici e riferimenti delle sequenze numeriche, utilizzare la pagina elenco **Sequenze numeriche** (fare clic su **Amministrazione sistema** &gt; **scheda Collegamenti** &gt; **Sequenze numeriche** &gt; **Sequenze numeriche**). 

Le impostazioni nella scheda **FMLA** definiscono la quantità di ore che un dipendente deve svolgere per ottenere l'idoneità ai vantaggi FMLA, la durata dell'impiego che è richiesta per l'idoneità e la data di inizio dell'impiego che viene utilizzata per determinare la durata dell'impiego. Le impostazioni definiscono inoltre il numero di ore FMLA a cui i dipendenti sono autorizzati e il calendario di congedo FMLA che viene utilizzato per calcolare il numero di ore FMLA utilizzato dai dipendenti. La scheda **FMLA** è disponibile solo per le società negli Stati Uniti. 

**Nota:** il numero di ore lavorate non può superare le 1.250 ore e la durata dell'impiego non può superare i 12 mesi. Questi valori massimi sono definiti in osservanza delle normative federali negli Stati Uniti. Infine, le impostazioni nella scheda **Dipendente self-service** determinano le informazioni che un responsabile può immettere per conto dei propri dipendenti.

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Impostare i parametri di Risorse umane per le persone giuridiche](set-up-hr-parameters-across-legal-entities.md)



