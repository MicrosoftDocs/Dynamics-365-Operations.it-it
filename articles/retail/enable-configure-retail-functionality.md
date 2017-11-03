---
title: Inizializzare i dati iniziali in un nuovo ambiente di vendita al dettaglio
description: In questo articolo viene descritto i dati creati durante il processo di inizializzazione di Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ac4f651cd7e5df912ea2535eafd5e54c11377253
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a>Inizializzare i dati iniziali in un nuovo ambiente di vendita al dettaglio

[!include[banner](includes/banner.md)]


In questo articolo viene descritto i dati creati durante il processo di inizializzazione di Microsoft Dynamics 365 for Retail.

Dopo la distribuzione della soluzione di vendita al dettaglio tramite Microsoft Dynamics Lifecycle Services (LCS), è necessario inizializzare la configurazione della soluzione per creare i dati di configurazione di base. **Importante:** prima di inizializzare la configurazione di vendita al dettaglio, assicurarsi che sia specificata una lingua e un indirizzo postale per ogni persona giuridica per cui si desidera impostare i punti vendita al dettaglio. Questo passaggio deve essere completato per ogni persona giuridica che utilizza la funzionalità di vendita al dettaglio. Per inizializzare la configurazione della funzionalità di vendita al dettaglio, effettuare le operazioni indicate di seguito.

1.  Avviare il client Microsoft Dynamics 365 for Retail.
2.  Fare clic su **Vendita al dettaglio** &gt; **Impostazione sedi centrali** &gt; **Parametri** &gt; **Parametri di vendita al dettaglio**.
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

Inoltre, la registrazione correlata a PCI (Payment Card Industry) è abilitata per il database di Dynamics 365 for Retail. **Nota:** è disponibile un'opzione per configurare separatamente Retail scheduler. Questa opzione consente di reimpostare la configurazione il dettaglio dell'utilità di pianificazione con le relative impostazioni predefinite. Dopo il completamento dell'inizializzazione, è necessario configurare i dati aggiuntivi per la dati vendita al dettaglio. Di seguito sono riportati alcuni esempi.

-   Parametri di vendita al dettaglio
-   Parametri Retail Scheduler
-   Canali di vendita al dettaglio
-   Registri e dispositivi
-   Assortimenti





