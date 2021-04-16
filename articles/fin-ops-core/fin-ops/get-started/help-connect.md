---
title: Configurare l'esperienza della Guida per le app Finance and Operations
description: Questo argomento fornisce informazioni sui componenti del sistema della Guida per alcune app Microsoft Dynamics 365.
author: margoc
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 82bb9a09e6d302b0d453ceb5131da039769b58fb
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745691"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a>Configurare l'esperienza della Guida per le app Finance and Operations

[!include [banner](../includes/banner.md)]

In questo argomento, troverai una panoramica dei componenti del sistema della Guida per le app Finance and Operations, come Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce e Dynamics 365 Human Resources. L'argomento spiega inoltre come collegare tali componenti e fornisce un riepilogo del processo per la creazione di una Guida personalizzata.

## <a name="help-architecture"></a>Architettura della Guida

Le app Finance and Operations includono panoramiche concettuali e altri argomenti pubblicati sul sito [https://docs.microsoft.com/dynamics365](/dynamics365/). È possibile accedere a questo contenuto dal riquadro della **Guida** interno al prodotto. La figura seguente mostra le parti della Guida.

[![Architettura della Guida](./media/help-architecture.png)](./media/help-architecture.png)

Il sistema della Guida interno al prodotto estrae articoli da docs.microsoft.com e altri siti Web collegati. Inserisce anche le guide attività archiviate in Business process modeler (BPM) in Microsoft Dynamics Lifecycle Services (LCS).

## <a name="adding-task-guides"></a>Aggiunta di guide per le attività

> [!NOTE]
> La scheda **Guide attività** non è attualmente disponibile in Human Resources o Commerce. <!--We are currently working to enable this functionality in a future release.--> Tuttavia, le guide attività nell'esperienza Attività iniziali in Human Resources rimangono disponibili per coprire le funzionalità di base. La Guida sulle procedure è disponibile nel sito [https://docs.microsoft.com/dynamics365](/dynamics365/) per Human Resources e Commerce.

Nella pagina **Parametri di sistema**, gli amministratori di sistema possono configurare l'accesso alle librerie della guida attività pertinenti per un'implementazione.

> [!NOTE]
> - Per configurare la Guida, devi eseguire l'accesso utilizzando con un account nello stesso tenant di distribuzione dell'app.
> - Non è possibile connettere una libreria LCS da un'istanza dell'app in esecuzione su un'unità disco rigido virtuale (VHD) locale.

[![Modulo Parametri di sistema con impostazioni per la Guida](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

Per configurare le guide attività per una soluzione, attieniti alla seguente procedura nella pagina **Parametri di sistema**.

> [!IMPORTANT]
> La prima volta che si apre la scheda della **Guida**, è necessario connettersi a Lifecycle Services. Assicurati di selezionare il collegamento al centro del modulo, attendi la connessione, chiudi la finestra di dialogo quindi seleziona **OK** per accedere alla pagina **Parametri di sistema**.
>
> [![Connetti a LCS](./media/connect-to-lcs-crop-1024x365.png "Connetti a LCS")](./media/connect-to-lcs-crop.png)

1. Selezionare il progetto Lifecycle Services a cui connettersi.
2. Selezionare le librerie BPM (nel progetto selezionato) da cui recuperare le registrazioni attività.
3. Impostare l'ordine di visualizzazione delle librerie BPM. L'ordine di visualizzazione definisce l'ordine in cui le registrazioni attività delle librerie verranno visualizzate nel riquadro **Guida**.

Dopo aver completato questi passaggi, puoi aprire il riquadro **Guida** e selezionare la scheda **Guide attività**. Vengono visualizzate le guide attività applicabili alla pagina attualmente aperta nelle app Finance and Operations. Se non viene trovata alcuna guida attività, è possibile immettere le parole chiave per ridefinire la ricerca.

### <a name="showing-translated-task-guides"></a>Visualizzazione delle guide attività tradotte

Le guide attività tradotte sono state rilasciate per la prima volta nella libreria unificata APQC di maggio 2016 e nella libreria di introduzione. Per visualizzare la Guida della guida attività localizzata, assicurati che la tua soluzione Dynamics 365 sia connessa alla libreria di maggio 2016. Gli utenti possono modificare la lingua in cui viene visualizzata una guida attività modificando le impostazioni relative alla lingua in **Opzioni** &gt; **Preferenze**.

> [!NOTE]
> Sebbene molte guide attività sono state tradotte, al momento il client non visualizza i nomi delle guide attività tradotte. Inoltre, solo le guide di attività che sono state rilasciate nel mese di febbraio 2016 sono disponibili in versione tradotta nella libreria di maggio 2016. Microsoft rilascerà una libreria aggiornata con traduzioni aggiuntive.
>
> - Se è stata tradotta una Guida attività, quando si apre la Guida attività tutto il testo apparirà nella lingua selezionata.
> - Se una Guida attività non è stata ancora tradotta, quando si apre solo parte del testo (quello dei controlli) apparirà nella lingua selezionata.

## <a name="adding-custom-help"></a>Aggiunta della Guida personalizzata

Puoi utilizzare guide attività per creare una Guida personalizzata oppure puoi collegare un sito Web della Guida personalizzata al riquadro **Guida**.

### <a name="create-custom-help-by-using-task-guides"></a>Creare una Guida personalizzata con guide attività

Puoi creare la Guida personalizzata per le app supportate creando registrazioni attività che riflettono l'implementazione e salvarle in una libreria di processi aziendali in LCS successivamente. Non è possibile creare guide attività personalizzate per Human Resources.

Per i partner, se promuovi una libreria a libreria aziendale e la includi in una soluzione, sarà disponibile per i clienti. Puoi inoltre effettuare una copia della libreria globale unificata APQC e quindi aprire i file di Registrazione attività nella copia, modificarli e salvare le modifiche. Per ulteriori informazioni, vedere [Risorse registrazione attività](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-help-site"></a>Collega un sito della Guida personalizzato

Le app Finance and Operations vengono utilizzate raramente nella loro forma predefinita. Invece, la soluzione è personalizzata ed estesa per soddisfare le esigenze dell'organizzazione. È inoltre possibile personalizzare ed estendere l'esperienza della Guida. Ad esempio, puoi aggiungere una Guida personalizzata al riquadro interno **Guida** del prodotto.

Microsoft ha fornito un toolkit per aiutarti a distribuire e connettere la Guida personalizzata al riquadro **Guida**. Per informazioni su come impostare una soluzione della Guida personalizzata connessa al riquadro **Guida**, vedi [Panoramica della Guida personalizzata](../../dev-itpro/help/custom-help-overview.md).

Se desideri collaborare con Microsoft su strumenti e processi per la personalizzazione della Guida, compila il modulo all'indirizzo [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).

## <a name="see-also"></a>Vedere anche

[Guida](help-overview.md)  
[Panoramica della Guida personalizzata](../../dev-itpro/help/custom-help-overview.md)  
[Risorse registrazione attività](../../dev-itpro/user-interface/task-recorder.md)  
[Creare la documentazione o la formazione con Registrazione attività](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[Archivio GitHub per una Guida personalizzata](https://github.com/microsoft/dynamics356f-o-custom-help)  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]