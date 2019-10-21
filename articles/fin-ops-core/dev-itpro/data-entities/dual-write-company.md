---
title: Concetto di società in Common Data Service
description: In questo argomento viene descritta l'integrazione dei dati della società tra Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: aa4d54fd7b3ab407751ad6ca1032d742c23eed41
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184533"
---
## <a name="company-concept-in-common-data-service"></a>Concetto di società in Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

In Finance and Operations, il concetto di *società* è un costrutto sia legale che commerciale. È inoltre un limite di visibilità e di sicurezza per i dati. Gli utenti lavorano sempre nel contesto di una singola società e la maggior parte dei dati è oggetto dello striping della società.

Common Data Service non dispone di un concetto equivalente. Il concetto più vicino è *Business Unit*, ovvero principalmente un limite di visibilità e sicurezza per i dati utente. Questo concetto non ha le stesse implicazioni legali o commerciali del concetto di società.

Poiché Business Unit e società non sono equivalenti concetti, non è possibile applicare un mapping di uno-a-uno (1:1) tra loro a scopo dell'integrazione con Common Data Service. Tuttavia, poiché gli utenti devono, per impostazione predefinita, poter visualizzare gli stessi record nell'applicazione e in Common Data Service, Microsoft ha introdotto una nuova entità in Common Data Service denominata cdm\_Company. Questa entità equivale all'entità Società nell'applicazione. Per contribuire a garantire che la visibilità dei record è equivalente tra l'applicazione e Common Data Service in modo predefinito, è consigliabile la seguente impostazione per i dati in Common Data Service:

+ Per ogni record di Finance and Operations abilitato per la doppia scrittura, un record cdm\_Company associato viene creato.
+ Quando un record cdm\_Company viene creato e abilitato per la doppia scrittura, una Business Unit predefinito viene creata con lo stesso nome. Sebbene un team predefinito venga creato automaticamente per tale Business Unit, la Business Unit non viene utilizzata.
+ Un team proprietario distinto viene creato con lo stesso nome. Sarà inoltre associato al Business Unit.
+ Per impostazione predefinita, il proprietario di un record creato e oggetto di doppia scrittura in Common Data Service è impostato sul team "DW Owner" collegato alla Business Unit associata.

Di seguito viene illustrato un esempio di questa impostazione dei dati in Common Data Service.

![Impostazione dei dati in Common Data Service](media/dual-write-company-1.png)

Grazie a questa configurazione, qualsiasi record correlato alla società USMF sarà di proprietà di un team collegato alla Business Unit USMF in Common Data Service. Pertanto, qualsiasi utente con diritti di accesso a tale Business Unit tramite un ruolo di sicurezza impostato su visibilità a livello Business Unit potrà visualizzare i record. Nel seguente esempio viene illustrato come i team possono essere utilizzati per fornire l'accesso corretto a tali record.

+ Il ruolo "Sales Manager" viene assegnato ai membri del team "USMF Sales".
+ Gli utenti con il ruolo "Sales Manager" possono accedere a tutti record relativi ai conti appartenenti alla stessa Business Unit di cui sono membri.
+ Il team "USMF Sales" è collegato alla Business Unit USMF menzionata in precedenza.
+ Di conseguenza, i membri del team "USMF Sales" possono visualizzare qualsiasi conto che appartiene all'utente "USMF DW", proveniente dall'entità Società USMF in Finance and Operations.

![Come utilizzare i team](media/dual-write-company-2.png)

Come mostra la figura precedente, questo mapping 1:1 tra Business Unit, società e team è solo un punto di partenza. In questo esempio, il nuovo Business Unit "Europe" è stata creata manualmente in Common Data Service come padre sia per DEMF che ESMF. La nuova Business Unit principale non è correlata alla doppia scrittura. Tuttavia, è possibile utilizzarla per dare ai membri del team "EUR Sales" accesso ai dati dei conti sia in DEMF che in ESMF impostando la visibilità dei dati su **BU padre/figlio** nel ruolo di sicurezza associato.

Argomento finale da discutere è come la doppia scrittura determina a quale team proprietario assegnare i record. Questo funzionamento dipende dal campo **Team proprietario predefinito** nel record cdm\_Company. Quando un record cdm\_Company è abilitato per la doppia scrittura, un plugin crea automaticamente la Business Unit e il team proprietario (se non esiste già) associati e imposta il campo **Team proprietario predefinito**. Il amministratore può modificare questo campo su un valore diverso. Tuttavia, l'amministratore non può cancellare il campo finché l'entità è abilitata per la doppia scrittura.

![Campo Team proprietario predefinito](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Striping e bootstrap della società

L'integrazione con Common Data Service porta la parità della società utilizzando un identificatore della società per lo striping dei dati. Come nella seguente figura viene illustrato, tutte le entità specifiche della società vengono estese in modo che abbiano una relazione molti-a-uno (N:1) con l'entità cdm'\_Company.

![La relazione N:1 tra un'entità specifica della società e l'entità cdm_Company](media/dual-write-bootstrapping.png)

+ Per i record, dopo che una società viene aggiunta e salvata, il valore diventa di sola lettura. Di conseguenza, gli utenti devono assicurarsi di scegliere la società corretta.
+ Solo i record con dati della società sono idonei alla doppia scrittura tra l'applicazione e Common Data Service.
+ Per i dati di Common Data Service esistenti, sarà presto disponibile un'esperienza di bootstrap gestita da amministratore.
