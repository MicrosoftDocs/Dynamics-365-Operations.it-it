---
title: Suggerimenti per Visibilità inventario
description: Questo argomento fornisce alcuni suggerimenti da tenere in considerazione quando si configura e si utilizza il componente aggiuntivo Visibilità inventario.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: f5fb4c7cb941b352bbc6e2fcf5347244e1c8a40c
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920806"
---
# <a name="inventory-visibility-tips"></a>Suggerimenti per Visibilità inventario

[!include [banner](../includes/banner.md)]

Questo argomento illustra alcuni suggerimenti da tenere in considerazione quando si configura e si utilizza il componente aggiuntivo Visibilità inventario.

- Attualmente, il componente aggiuntivo Visibilità inventario supporta solo ambienti Microsoft Dataverse che sono stati creati utilizzando Microsoft Dynamics Lifecycle Services (LCS). Se il tuo ambiente Dataverse è stato creato in qualche altro modo (per esempio, usando l'interfaccia di amministrazione di Power Apps), e se è collegato al tuo ambiente Dynamics 365 Supply Chain Management, devi prima contattare il team del prodotto Visibilità inventario per risolvere il problema di mapping. Puoi contattare il team all'indirizzo [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com). Il team ti farà sapere quando il tuo ambiente è pronto per l'installazione di Visibilità inventario.
- Se è disponibile più di un ambiente LCS, creare un'applicazione Azure Active Directory (Azure AD) diversa per ogni ambiente. Se si utilizza lo stesso ID applicazione e ID tenant per installare il componente aggiuntivo Visibilità inventario per ambienti diversi, si verificherà un problema relativo al token per gli ambienti meno recenti. Sarà valida solo l'ultima istanza del componente aggiuntivo Visibilità inventario installato.
- Visibilità inventario non è attualmente supportata per gli ambienti ospitati nel cloud. È supportato solo per ambienti Tier-2+.
- L'API attualmente supporta le query fino a 100 singoli elementi con il valore `ProductID`. Più valori `SiteID` e `LocationID` possono anche essere specificati in ogni query. Il limite massimo è definito come `NumOf(SiteID) * NumOf(LocationID) <= 100`.
- L'origine dati `fno` è riservata a Supply Chain Management. Se il tuo componente aggiuntivo Visibilità inventario è integrato con un ambiente Supply Chain Management, ti consigliamo di non eliminare le configurazioni relative a `fno` nell'[origine dati](inventory-visibility-configuration.md#data-source-configuration).
- La [configurazione della partizione](inventory-visibility-configuration.md#partition-configuration) attualmente si compone di due dimensioni di base (`SiteId` e `LocationId`) che indicano come sono distribuiti i dati. Le operazioni nella stessa partizione possono fornire prestazioni più elevate a costi inferiori. La soluzione include questa configurazione della partizione per impostazione predefinita. Di conseguenza, *non è necessario ridefinirla*. Non personalizzare la configurazione della partizione predefinita. Se la elimini o la modifichi, è probabile che si verifichi un errore imprevisto.
- Le dimensioni di base che sono definite nella configurazione della partizione non devono essere definite nella [configurazione della gerarchia dell'indice del prodotto](inventory-visibility-configuration.md#index-configuration).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
