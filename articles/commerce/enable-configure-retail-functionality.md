---
title: Inizializzare i dati iniziali nei nuovi ambienti Commerce
description: In questo articolo viene descritto i dati creati durante il processo di inizializzazione di Dynamics 365 Commerce.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9f534410b21fd97554f4e038bb14eebd5f887130
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792585"
---
# <a name="initialize-seed-data-in-new-commerce-environments"></a>Inizializzare i dati iniziali nei nuovi ambienti Commerce

[!include [banner](includes/banner.md)]

In questo articolo viene descritto i dati creati durante il processo di inizializzazione di Dynamics 365 Commerce.

Dopo la distribuzione della soluzione Commerce tramite Microsoft Dynamics Lifecycle Services (LCS), è necessario inizializzare la configurazione della soluzione per creare i dati di configurazione di base.

> [!IMPORTANT]
> Prima di inizializzare la configurazione di Commerce, assicurarsi che sia specificata una lingua e un indirizzo postale per ogni persona giuridica per cui si desidera impostare i punti vendita al dettaglio. Questo passaggio deve essere completato per ogni persona giuridica utilizzata per Commerce.

Per inizializzare la configurazione procedere come segue.

1. Avviare il client Commerce.
2. Fare clic su **Retail e Commerce** &gt; **Impostazione sedi centrali** &gt; **Parametri** &gt; **Parametri di commercio**.
3. Fare clic su **Inizializza**.

L'inizializzazione crea i seguenti dati di configurazione predefiniti:

- Processi e processi secondari dell'utilità di pianificazione di commercio
- Schema del canale di commercio
- Programmazioni di distribuzione di commercio
- Layout della schermata predefiniti, che includono griglie dei pulsanti, immagini e temi
- Informazioni fuso orario
- Operazioni POS
- Autorizzazioni POS
- Report canale
- Metadati di attributi
- Modelli di convalida entità
- Processo batch per l'eliminazione dello storico della sessione di Commerce Data Exchange

Inoltre, la registrazione correlata a PCI (Payment Cad Industry) è abilitata per il database di Commerce.

> [!NOTE]
> È disponibile un'opzione per configurare separatamente l'utilità di pianificazione di commercio. Questa opzione consente di reimpostare la configurazione dell'utilità di pianificazione di commercio con le relative impostazioni predefinite.

Dopo il completamento dell'inizializzazione, è necessario configurare i dati di commercio aggiuntivi. Di seguito sono riportati alcuni esempi.

- Parametri di commercio
- Parametri utilità di pianificazione commercio
- Canali di commercio
- Registri e dispositivi
- Assortimenti


[!INCLUDE[footer-include](../includes/footer-banner.md)]