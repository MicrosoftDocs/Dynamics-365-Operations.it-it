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
ms.openlocfilehash: c280eef995664c640e382817dda9d6e1cde154c6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871497"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Risoluzione dei problemi relativi alla consapevolezza della soluzione

[!include [banner](../../includes/banner.md)]





In questo articolo vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra Finanza e operazioni e Dataverse. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla consapevolezza della soluzione.

> [!IMPORTANT]
> Alcuni problemi che questo articolo tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="error-on-the-dual-write-page"></a>Errore nella pagina di doppia scrittura

Nella pagina **Doppia scrittura** è possibile che venga visualizzato un messaggio di errore simile al seguente esempio:

*L'entità con nome "msdyn\_dualwriteentitymap" con namemapping = "Logico" non è stata trovata in MetadataCache.*

Per risolvere il problema, assicurarsi che sia installata la soluzione core doppia scrittura in Dataverse. La soluzione core doppia scrittura è un prerequisito per la consapevolezza della soluzione.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]