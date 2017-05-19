---
title: Inizializzare i dati iniziali in un nuovo ambiente di vendita al dettaglio
description: In questo articolo viene descritto i dati creati durante il processo di inizializzazione di Microsoft Dynamics 365 for Operations - Retail.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: b5290bb62ab8ad71b06b0478ccaf6dbb61454170
ms.contentlocale: it-it
ms.lasthandoff: 04/26/2017


---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a>Inizializzare i dati iniziali in un nuovo ambiente di vendita al dettaglio

[!include[banner](includes/banner.md)]


In questo articolo viene descritto i dati creati durante il processo di inizializzazione di Microsoft Dynamics 365 for Operations - Retail.

Dopo la distribuzione della soluzione di vendita al dettaglio tramite Microsoft Dynamics Lifecycle Services (LCS), è necessario inizializzare la configurazione della soluzione per creare i dati di configurazione di base. **Importante:** prima di inizializzare la configurazione di vendita al dettaglio, assicurarsi che sia specificata una lingua e un indirizzo postale per ogni persona giuridica per cui si desidera impostare i punti vendita al dettaglio. Questo passaggio deve essere completato per ogni persona giuridica che utilizza la funzionalità di vendita al dettaglio. Per inizializzare la configurazione della funzionalità di vendita al dettaglio, effettuare le operazioni indicate di seguito.

1.  Avviare il client Microsoft Dynamics 365 for Operations.
2.  Fare clic su **Vendita al dettaglio e commercio** &gt; **Impostazione sedi centrali** &gt; **Parametri** &gt; **Parametri di vendita al dettaglio**.
3.  Fare clic su **Inizializza**.

L'inizializzazione crea i seguenti dati di configurazione predefiniti:

-   Processi e processi secondari di Retail Scheduler
-   Schema del canale di vendita al dettaglio
-   Programmazioni della distribuzione di vendita al dettaglio
-   Layout della schermata predefiniti, che includono griglie dei pulsanti, immagini e temi
-   Informazioni fuso orario
-   Operazioni POS
-   Autorizzazioni POS
-   Report canale
-   Metadati di attributi
-   Modelli di convalida entità
-   Processo batch per l'eliminazione dello storico della sessione di scambio dei dati commerciali

Inoltre, la registrazione correlata a PCI (Payment Cad Industry) è abilitata per il database di Dynamics 365 for Operations. **Nota:** è disponibile un'opzione per configurare separatamente Retail scheduler. Questa opzione consente di reimpostare la configurazione il dettaglio dell'utilità di pianificazione con le relative impostazioni predefinite. Dopo il completamento dell'inizializzazione, è necessario configurare i dati aggiuntivi per la dati vendita al dettaglio. Di seguito sono riportati alcuni esempi.

-   Parametri di vendita al dettaglio
-   Parametri Retail Scheduler
-   Canali di vendita al dettaglio
-   Registri e dispositivi
-   Assortimenti





