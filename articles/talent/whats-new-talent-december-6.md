---
title: Novità o modifiche in Dynamics 365 for Talent Core HR (6 dicembre 2018)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 80d62492d58a436c15fac82df0d000ab9efa6ea5
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518414"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-6-2018"></a>Novità o modifiche in Dynamics 365 for Talent Core HR (6 dicembre 2018)

[!include [banner](includes/banner.md)]

**Build 8.1.2071**

Questo argomento descrive le funzionalità nuove o modificate di Core HR.


## <a name="platform-update-22"></a>Update 22 della piattaforma

### <a name="export-up-to-1-million-rows-to-excel"></a>Esportazione fino a 1 milione di righe in Excel

La funzionalità Esporta in Excel può ora essere configurata per consentire agli utenti di esportare fino a 1 milione di righe da una griglia in Talent; un aumento sostanziale rispetto al limite precedente di 10.000 righe. 

### <a name="restyled-personalization-toolbar"></a>Barra degli strumenti di personalizzazione modificata

La barra degli strumenti di personalizzazione è stata modificata nell'aggiornamento 22 della piattaforma per consentire agli utenti di adattare più facilmente le proprie esperienze in Talent. Sono state apportate le seguenti modifiche: 

-  Il nome di ogni strumento di personalizzazione è ora visualizzato con un'icona e ciò consente agli utenti di riconoscere rapidamente lo strumento che intendono utilizzare.
-  Ora è visualizzata anche la descrizione su come utilizzare lo strumento corrente e ciò consente agli utenti di comprendere come eseguire le personalizzazioni necessarie.  
-  L'intera barra degli strumenti di personalizzazione può essere spostata sullo schermo trascinando una specifica area nella parte sinistra della barra degli strumenti. Ciò consente agli utenti di personalizzare gli elementi in precedenza nascosti dalla barra degli strumenti.   

### <a name="optimized-is-one-of-filtering-experience"></a>Esperienza di filtro "è uno di" ottimizzata

L'operatore di filtro "è uno di" è disponibile per la maggior parte dei campi quando si utilizza il riquadro filtri e gli elenchi a discesa dell'intestazione della griglia. Questo operatore consente a un utente di filtrare un campo in base a molteplici valori. Una nuova e migliorata esperienza per l'operatore "è uno di" è disponibile nell'aggiornamento della piattaforma 22. Per ulteriori informazioni, vedere [Esperienza del filtro "è uno di" ottimizzata](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering).

### <a name="paste-lists-from-excel-into-filter-fields-with-the-is-one-of-operator"></a>Incollare elenchi da Excel nei campi filtro con l'operatore "è uno di"

Per alcune attività, è possibile che gli utenti dispongano di un elenco di valori in Excel che desiderano utilizzare per filtrare i dati in Talent. Ad esempio, un utente Risorse umane può aver identificato un gruppo di dipendenti in un report per i quali è necessaria un'ulteriore ricerca nel sistema e per questo utente sarebbe ideale poter copiare l'elenco direttamente da Excel in un campo filtro in Talent.

A partire dall'aggiornamento 22 della piattaforma, l'operatore "è uno di" nel riquadro filtri e nel filtro delle colonne della griglia riconosce gli elenchi copiati da Excel in modo da poter essere incollati direttamente in un campo filtro. Ciò include una raccolta di valori copiati da varie righe e colonne in Excel. Per ulteriori informazioni su questa funzionalità, vedere [Incollare elenchi da Excel nei campi filtro con l'operatore "è uno di"](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/paste-filter-lists-from-excel).

## <a name="in-preview"></a>In anteprima

### <a name="configure-uk-payroll-integration-between-talent-and-dayforce"></a>Configurare l'integrazione retribuzioni per il Regno Unito tra Talent e Dayforce

L'integrazione tra Microsoft Dynamics 365 for Talent e Ceridian Dayforce è disponibile in anteprima per il Regno Unito. Per ulteriori informazioni, fare riferimento all'argomento [Configurare l'integrazione retribuzioni tra Talent e Dayforce](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/configure-payroll-integration).

## <a name="coming-soon"></a>Presto disponibili

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Congedo e assenza: saldi congedo futuri e previsione di saldi congedo

A seguito delle modifiche apportate per consentire ai dipendenti di prevedere i permessi e richiedere richieste di permessi futuri senza alterare i relativi saldi permesso correnti, anche la modalità di visualizzazione dei saldi permesso risulterà modificata. 

Il saldo disponibile attualmente visualizzato è la quantità di permessi disponibile per le richieste inclusi gli accumuli fino alla data odierna e tutte le richieste di congedo approvate. 

Al rilascio della funzionalità di previsione, il saldo visualizzato sarà il saldo permessi corrente inclusi gli accumuli e le richieste fino alla data odierna. Dipendenti e responsabili vedranno questi saldi aggiornati in responsabile e dipendente self service nella scheda **Tempo libero** e nella finestra **Saldi permessi**. I responsabili risorse umane vedranno questi saldi aggiornati nell'area di lavoro **Persone** e nella finestra **Piani di congedo assegnati del dipendente**.

## <a name="other-changes"></a>Altre modifiche 

### <a name="termination-code-is-not-populated-to-the-worker-position-assignment-record"></a>Il codice di fine rapporto non viene popolato in base al record dell'assegnazione posizione lavoratore

È stata apportata una modifica che popola il codice motivo in base al record dell'assegnazione posizione durante il processo di fine rapporto.

### <a name="validation-for-personnel-number-being-in-use-needs-additional-details"></a>La convalida del numero personale utilizzato necessita ulteriori dettagli

Ulteriori informazioni sono visualizzate quando si utilizzano sequenze numeriche, per comprendere meglio i motivi per cui un nuovo numero non può essere generato.
 
### <a name="attachments-buttons-not-available-for-workers"></a>Pulsante Allegati non disponibile per i lavoratori

Sono stata apportate delle modifiche per correggere gli allegati. Ora quando si aggiunge un nuovo allegato a un lavoratore, i pulsanti **Nuovo** e **Modifica** sono disponibili all'apertura dei riquadri Dettaglio informazioni nella finestra del lavoratore. 

## <a name="known-issues"></a>Problemi noti

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a>Errori di mapping nell'integrazione con Finance and Operations

I seguenti problemi sono stati identificati nel modello corrente per l'integrazione di Talent con Finance and Operations. Un nuovo modello verrà pubblicato a breve e applicato a tutti i nuovi progetti di integrazione creati. Per i progetti di integrazione esistenti, i mapping di attività possono essere aggiornati. Consultare la tabella seguente per i mapping aggiornati. 

>[!NOTE]
> L'attività di assegnazione del processo padre Posizioni lavorative a Posizioni non integra dati. Questo problema è attualmente in fase di risoluzione. Non esiste alcuna soluzione alternativa nel mapping corrente. 

L'attività Reparti a Unità operativa necessita l'aggiornamento dei mapping seguenti.

| Campo origine esistente          | Campo nuova origine |
| -------------------------------|------------------|
| cdm_description (Descrizione)  | cdm_name (Nome)  |

È necessario aggiungere anche un ulteriore mapping. Selezionare l'ultimo campo **Nessuno** per aggiungere il mapping successivo.

| Campo di origine                   | Campo di destinazione    |
| -------------------------------|----------------------|
| cdm_description (Descrizione)  | NAMEALIAS (NAMEALIAS)|

I mapping aggiornati devono risultare simili a quanto segue.

![Attività Reparti a Unità operative](./media/DepartmentMapping.png)


L'attività Mansioni a Dettagli mansione necessita l'aggiornamento dei mapping seguenti.

| Campo origine esistente          | Campo nuova origine                   |
| -------------------------------|------------------------------------|
| cdm_name (Nome)                | cdm_description (Descrizione)      |
| cdm_name (Descrizione)         | cdm_jobdescription(Descrizione mansione)|


I mapping aggiornati devono risultare simili a quanto segue.

![Attività Mansioni a Dettagli mansione](./media/JobMapping.png)

L'attività Lavoratori a Lavoro necessita l'aggiornamento dei mapping seguenti.

| Campo origine esistente                 | Campo nuova origine                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (Indirizzo di posta elettronica 1)   | cdm_primaryemailaddress (Indirizzo di posta elettronica principale) |
| cdm_telephone1 (Telefono 1)          | cdm_primarytelephone (Telefono principale)       |

Anche la trasformazione del campo Sesso deve essere aggiornata. Selezionare il tipo di mappa **fn** (funzione) per Sesso e aggiornare i mapping dei valori seguenti.

| Common Data Service Value   | Finance and Operations value | | ------------|------------------ -----------| | 75440000    | Male                         | | 75440001    | Female                       | | 75440002    | None                         | | 75440003    | NonSpecific                  |

I mapping aggiornati devono risultare simili a quanto segue.

![Attività Lavoratori a Lavoratore.](./media/WorkerMapping.png)

![Trasformazione del campo Sesso](./media/WorkerTransform.png)

