---
title: Risoluzione dei problemi relativi alla consapevolezza della soluzione
description: Questo articolo fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla consapevolezza della soluzione.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6866956efcc76a7da6c3aa5fb36058de78d5472e
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111300"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Risoluzione dei problemi relativi alla consapevolezza della soluzione

[!include [banner](../../includes/banner.md)]





In questo articolo vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app per la finanza e le operazioni e Dataverse. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla consapevolezza della soluzione.

> [!IMPORTANT]
> Alcuni problemi che questo articolo tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="error-on-the-dual-write-page"></a>Errore nella pagina di doppia scrittura

Nella pagina **Doppia scrittura** è possibile che venga visualizzato un messaggio di errore simile al seguente esempio:

*L'entità con nome "msdyn\_dualwriteentitymap" con namemapping = "Logico" non è stata trovata in MetadataCache.*

Per risolvere il problema, assicurarsi che sia installata la soluzione core doppia scrittura in Dataverse. La soluzione core doppia scrittura è un prerequisito per la consapevolezza della soluzione.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
