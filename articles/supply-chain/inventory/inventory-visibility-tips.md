---
title: Suggerimenti per Visibilità inventario
description: Questo articolo fornisce alcuni suggerimenti da tenere in considerazione quando si configura e si utilizza il componente aggiuntivo Visibilità inventario.
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
ms.openlocfilehash: 3bdd161815a15d5c39b3c0afc176a288c8d9055a
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306087"
---
# <a name="inventory-visibility-tips"></a>Suggerimenti per Visibilità inventario

[!include [banner](../includes/banner.md)]

Questo argomento illustra alcuni suggerimenti da tenere in considerazione quando si configura e si utilizza il componente aggiuntivo Visibilità inventario.

- Attualmente, il componente aggiuntivo Visibilità inventario supporta solo ambienti Microsoft Dataverse che sono stati creati utilizzando Microsoft Dynamics Lifecycle Services (LCS). Se il tuo ambiente Dataverse è stato creato in qualche altro modo (per esempio, usando l'interfaccia di amministrazione di Power Apps), e se è collegato al tuo ambiente Dynamics 365 Supply Chain Management, devi prima contattare il team del prodotto Visibilità inventario per risolvere il problema di mapping. Puoi contattare il team all'indirizzo [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com). Il team ti farà sapere quando il tuo ambiente è pronto per l'installazione di Visibilità inventario.
- Se è disponibile più di un ambiente LCS, creare un'applicazione Azure Active Directory (Azure AD) diversa per ogni ambiente. Se si utilizza lo stesso ID applicazione e ID tenant per installare il componente aggiuntivo Visibilità inventario per ambienti diversi, si verificherà un problema relativo al token per gli ambienti meno recenti. Sarà valida solo l'ultima istanza del componente aggiuntivo Visibilità inventario installato.
- Visibilità inventario non è attualmente supportata per gli ambienti ospitati nel cloud. È supportato solo per ambienti Tier-2+.
- L'API attualmente supporta le query fino a 100 singoli elementi con il valore `ProductID`. Più valori `SiteID` e `LocationID` possono anche essere specificati in ogni query. Il limite massimo è definito come `NumOf(SiteID) * NumOf(LocationID) <= 100`.
- L'API in blocco può restituire un massimo di 512 record per ogni richiesta.
- L'origine dati `fno` è riservata a Supply Chain Management. Se il tuo componente aggiuntivo Visibilità inventario è integrato con un ambiente Supply Chain Management, ti consigliamo di non eliminare le configurazioni relative a `fno` nell'[origine dati](inventory-visibility-configuration.md#data-source-configuration).
- Visibilità inventario non può modificare alcun dato per l'origine dati `fno`. Il flusso di dati è unidirezionale, il che significa che tutte le quantità cambiano per l'origine dati `fno` deve provenire dall'ambiente di Supply Chain Management. Pertanto, non è possibile utilizzare l'API per inviare richieste di modifica o prenotazione disponibili per l'origine dati `fno`.
- Se aggiungi una o più nuove misure al tuo ambiente di Supply Chain Management, dovresti aggiungerle anche in Visibilità inventario. Tuttavia, tutte le modifiche alla quantità per le nuove misure devono provenire dal tuo ambiente di Supply Chain Management.
- La [configurazione della partizione](inventory-visibility-configuration.md#partition-configuration) attualmente si compone di due dimensioni di base (`SiteId` e `LocationId`) che indicano come sono distribuiti i dati. Le operazioni nella stessa partizione possono fornire prestazioni più elevate a costi inferiori. La soluzione include questa configurazione della partizione per impostazione predefinita. Di conseguenza, *non è necessario ridefinirla*. Non personalizzare la configurazione della partizione predefinita. Se la elimini o la modifichi, è probabile che si verifichi un errore imprevisto.
- Le dimensioni di base che sono definite nella configurazione della partizione non devono essere definite nella [configurazione della gerarchia dell'indice del prodotto](inventory-visibility-configuration.md#index-configuration).
- La [configurazione della gerarchia dell'indice di prodotto](inventory-visibility-configuration.md#index-configuration) deve includere almeno una gerarchia di indici (ad esempio, contenente la dimensione di base `Empty`), altrimenti le query non riusciranno con l'errore "Nessuna gerarchia di indici è stata impostata".
- L'origine dati `@iv` è un'origine dati predefinita e le misure fisiche definite in `@iv` con prefisso `@` sono misure predefinite. Queste misure sono una configurazione predefinita per la funzionalità di allocazione, quindi non modificarle o eliminarle altrimenti è probabile che si verifichino errori imprevisti durante l'utilizzo della funzionalità di allocazione.
- Puoi aggiungere nuove misure fisiche alla misura calcolata predefinita `@iv.@available_to_allocate`, ma non devi cambiarne il nome.
- Se ripristini un database di Supply Chain Management, il database ripristinato potrebbe contenere dati che non sono più coerenti con i dati precedentemente sincronizzati da Visibilità inventario con Dataverse. Questa incoerenza dei dati può causare errori di sistema e altri problemi. Pertanto, è importante pulire sempre tutti i dati di Visibilità inventario correlati da Dataverse prima di ripristinare un database di Supply Chain Management. Per dettagli, vedi [Pulire i dati di Visibilità inventario da Dataverse prima di ripristinare il database di Supply Chain Management](inventory-visibility-setup.md#restore-environment-database).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
