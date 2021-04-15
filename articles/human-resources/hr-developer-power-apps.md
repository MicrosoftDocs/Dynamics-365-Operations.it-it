---
title: Estendere Talent con Power Apps e Power Automate
description: In questo articolo vengono descritti alcuni esempi di scenari di estendibilità per Microsoft Dynamics 365 Human Resources che utilizzano Microsoft Power Apps e Microsoft Power Automate.
author: negudava
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ad55de4b660de89d323f32a1ce2911d880c24ec5
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793563"
---
# <a name="extend-with-power-apps-and-power-automate"></a>Estendere con Power Apps e Power Automate

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

In questo articolo vengono descritti alcuni esempi di scenari di estendibilità per Microsoft Dynamics 365 Human Resources che utilizzano Microsoft Power Apps e Microsoft Power Automate. È possibile importare il pacchetto di soluzioni associato a ogni esempio nell'ambiente di Power Apps. È quindi possibile utilizzare i pacchetti come riferimento o punto di partenza per implementare scenari applicabili all'organizzazione.

> [!IMPORTANT]
> Se si desidera utilizzare i modelli e le app descritti in questo argomento "così come sono", testarli per assicurarsi che coprano tutti gli scenari specifici dell'implementazione.

## <a name="prerequisites"></a>Prerequisiti

- Per importare pacchetti, gli utenti devono disporre dell'autorizzazione **Creazione ambiente**.
- Per esportare o importare app, gli utenti devono disporre di una licenza di Power Apps Piano 2 o una licenza di valutazione di Power Apps Piano 2.

## <a name="integration-with-microsoft-365-power-automate"></a>Integrazione con Microsoft 365, Power Automate

L'app **Integrazione con Microsoft 365** può essere utilizzata per estrarre informazioni sui team per gli utenti registrati da Microsoft 365. Fa riferimento ai lavoratori in Human Resources per estrarre i tipi di identificazione dei dipendenti. I manager possono controllare le date di scadenza dei tipi di ID dipendente. Possono anche inviare un promemoria via e-mail se il tipo di ID dipendente è in scadenza. Power Automate si integra con Power Apps per inviare questo promemoria. La conferma verrà rispedita a Power Apps da Power Automate quando viene inviato il promemoria. I tipi di identificazione includono la patente di guida, il passaporto e altre forme di identità accettabili.

È possibile estendere questa app per altri scenari. Ad esempio, è possibile utilizzarla per visualizzare informazioni sulle ferie del team, eventi di calendario e qualsiasi evento specifico del team.

Per scaricare l'app **Integrazione con Microsoft 365, Power Automate**, passa a [Integrazione con Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) nell'Area download Microsoft.

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate – Connessione a SQL ed esecuzione

Il modello **Power Automate – Connessione a SQL ed esecuzione** esegue la connessione a Microsoft SQL Server e consente l'esecuzione delle query SQL.

Sebbene questo modello legga e aggiorni le tabelle SQL, è possibile estenderlo e utilizzarlo per altri scenari. Ad esempio, per compilare una tabella di gestione temporanea in Dataverse con record di SQL Server e per sincronizzarla periodicamente utilizzando un push incrementale di SQL Server.

Query avanzata è integrata con Flow per abilitare la trasformazione dei dati e il push incrementale.

Per scaricare il modello **Power Automate – Connessione a SQL ed esecuzione**, andare a [Power Automate – Connessione a SQL ed esecuzione](https://go.microsoft.com/fwlink/?linkid=2081789) nell'Area download Microsoft.

## <a name="additional-resources"></a>Risorse aggiuntive

[Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]