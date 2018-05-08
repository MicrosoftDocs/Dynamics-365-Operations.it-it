---
title: "Estendere la funzionalità di Microsoft Dynamics 365 for Talent"
description: "Se sono state create Microsoft PowerApps, è possibile avviare tali applicazioni dai collegamenti in Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 03/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 51eb4288f5b6c732755007c1dcd8c4db090ccc0a
ms.contentlocale: it-it
ms.lasthandoff: 03/08/2018

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a>Estendere la funzionalità di Microsoft Dynamics 365 for Talent

[!include [banner](includes/banner.md)]

Se sono state create Microsoft PowerApps, è possibile avviare tali applicazioni dai collegamenti in Microsoft Dynamics 365 for Talent. Per impostare l'accesso alle applicazioni, sarà necessario impostare alcune informazioni in Talent in una pagina di configurazione che è possibile aprire dall'area di lavoro **Amministrazione sistema**.

## <a name="configuring-embedded-powerapps-within-talent"></a>Configurazione di PowerApps incorporate in Talent
Utilizzare la pagina **Imposta Microsoft PowerApps incorporate** per configurare le pagine di Talent per l'avvio delle applicazioni PowerApps. Per aprire la pagina **Imposta Microsoft PowerApps incorporate**, aprire l'area di lavoro **Amministrazione sistema** e quindi aprire la scheda **Collegamenti**. Selezionare **Microsoft PowerApps** dal gruppo **Impostazioni**. 

In questa pagina vengono inserite o impostate le informazioni seguenti: 

 -  Un nome descrittivo o un identificatore per ciascuna applicazione PowerApps.
 -  Un identificatore univoco (GUID) per ciascuna applicazione che si aggiunge a una pagina di Talent. L'ID app è disponibile nel sito di PowerApps, [powerapps.com](http://powerapps.com/). 
 -  La pagina da cui gli utenti possono aprire un'applicazione o un report. Non tutte le pagine di Talent supportano PowerApps e i report Power BI. 

 > [!NOTE]
 >  Immettere il nome interno della pagina, anziché il nome visualizzato che appare in cima alla pagina. Per trovare il nome interno, aprire la pagina di cui si necessita il nome interno e fare clic con il pulsante destro del mouse in un punto qualsiasi della pagina. Quando si apre il menu, posizionare il puntatore del mouse sulla voce **Informazioni modulo**. Il nome interno del modulo viene visualizzato accanto alla voce **Modulo informazioni** nel menu.
 
-   Specificare il controllo del modulo da cui l'applicazione può recuperare i dati del contesto. Ad esempio, un'applicazione potrebbe utilizzare i dati di un lavoratore. Se si accede alla pagina **Lavoratore** nel campo **Contesto**, la pagina **Lavoratore** si aprirà quando si avvia l'applicazione. Qualsiasi immissione nel campo **Contesto** è facoltativa. 
-   Impostare le dimensioni della finestra di dialogo in cui sarà eseguita l'applicazione PowerApps. Le finestre di dialogo sono indicate come "piccole" o "grandi" al fine di ottimizzare l'interfaccia utente quando l'applicazione viene eseguita rispettivamente su un telefono o un dispositivo più grande. 


È anche possibile specificare le persone giuridiche per le quali un'applicazione sarà disponibile oppure renderla disponibile per tutte le persone giuridiche. Per impostazione predefinita, le applicazioni PowerApps sono disponibili per tutte le persone giuridiche.

## <a name="opening-an-application"></a>Apertura di un'applicazione
Dopo avere configurato le applicazioni PowerApps incorporate, verranno aggiunti collegamenti alle applicazioni specificate nelle pagine all'interno di Talent. Fare clic sul collegamento per aprire un'applicazione. 



