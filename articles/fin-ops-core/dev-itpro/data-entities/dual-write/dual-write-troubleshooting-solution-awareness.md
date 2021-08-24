---
title: Risoluzione dei problemi relativi alla consapevolezza della soluzione
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla consapevolezza della soluzione.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: aa5ba0cfb127f20012237774fe948c23731eb56f8680d9fa23309e189683dbf3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736352"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Risoluzione dei problemi relativi alla consapevolezza della soluzione

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla consapevolezza della soluzione.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="error-on-the-dual-write-page"></a>Errore nella pagina di doppia scrittura

Nella pagina **Doppia scrittura** è possibile che venga visualizzato un messaggio di errore simile al seguente esempio:

*L'entità con nome "msdyn\_dualwriteentitymap" con namemapping = "Logico" non è stata trovata in MetadataCache.*

Per risolvere il problema, assicurarsi che sia installata la soluzione core doppia scrittura in Dataverse. La soluzione core doppia scrittura è un prerequisito per la consapevolezza della soluzione.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]