---
title: Utilizzare la data e l'ora in Microsoft Dynamics 365 for Talent
description: Comprendere cosa aspettarsi quando si utilizzano i campi di data e ora in Microsoft Dynamics 365 for Talent. Chiarire cosa aspettarsi quando si interagisce con i dati di data e ora in un modulo in Dynamics 365 for Talent, un'origine esterna o in Common Data Service.
author: Darinkramer
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-06-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b4c652992272ed1a5aecbb4c78f0d11f077149d1
ms.sourcegitcommit: 46bded82aa072adfedcf443629c2adc69f512c09
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "1791216"
---
# <a name="date-and-time-fields-in-talent"></a>Campi di data e ora in Talent

[!include [banner](includes/banner.md)]

I campi **Data e ora** sono un concetto fondamentale in Dynamics 365 for Talent. È importante capire come utilizzare i dati di **Data e ora** in un modulo di Dynamics 365, Common Data Service e di origini esterne.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>Differenza tra i tipi di dati dei campi Data e Data e ora

I campi**Data e ora** contengono informazioni sul fuso orario, mentre i campi **Data** no. I campi **Data** visualizzano le stesse informazioni in tutte le posizioni. Quando si immette una data nel campo **Data**, Talent scrive la stessa data nel database.

Quando si visualizzano i dati in un campo **Data e ora**, Talent regola la data e l'ora in base al fuso orario dell'utente impostato nel modulo **Opzioni utente** (**Common > Impostazioni > Opzioni utente**). Le informazioni di data e ora immesse nel campo possono non essere le stesse informazioni scritte nel database.

[![Modulo Opzioni utente](./media/useroptionsform.png)](./media/useroptionsform.png)

## <a name="understanding-date-and-time-fields-in-forms"></a>Campi Data e ora nei moduli 

Quando si inseriscono dati in un campo **Data e ora**, i dati visualizzati non sono gli stessi dati memorizzati nel database se il fuso orario dell'utente non è impostato su Coordinated Universal Time (UTC). I dati nei campi **Data e ora** vengono sempre memorizzati come UTC.

[![Modulo Lavoratore](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>Campi Data e ora nel database 

Quando Talent scrive un valore di **Data e ora** nel database, memorizza i dati in UTC. Ciò consente agli utenti di visualizzare tutti i dati di **Data e ora** relativi al fuso orario definito nelle opzioni utente.
 
Nell'esempio precedente, l'ora di inizio è un punto nel tempo, non una data specifica. Se si modifica il fuso orario dell'utente connesso da GMT +12:00 a GMT UTC, lo stesso record appena creato mostra 04/30/2019 12:00:00 invece di 05/01/2019 12:00:00.
  
Nell'esempio seguente, l'impiego di un dipendente 000724 diventa attivo alla stessa ora indipendentemente dal fuso orario. Il dipendente sarà attivo il 04/30/2019 nel fuso orario GMT, che è lo stesso di 05/01/2019 nel fuso orario GMT+12:00. Entrambi fanno riferimento allo stesso punto nel tempo e non a una data specifica. 

[![Modulo Lavoratore](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a>Dati di Data e ora in Data Management Framework, Excel, Common Data Service e Power BI 

La creazione di report in Data Management Framework, componente aggiuntivo di Excel, Common Data Service e Power BI è progettata per interagire con i dati direttamente a livello di database. Poiché non c'è un client che regola i dati di **Data e ora** sul fuso orario dell'utente, tutti i valori di **Data e ora** sono in UTC. Per questo motivo si può essere indotti in alcuni errori quando si inseriscono o si visualizzano i dati.  
 
I database presuppone che i dati di **Data e ora** che vengono inviati tramite DMF, Excel o Common Data Service siano in UTC. Questa impostazione può causare una certa confusione quando il valore inviato di **Data e ora** non viene visualizzato come previsto perché il fuso orario dell'utente che visualizza i dati non è impostato su UTC. 
 
La stessa cosa può verificarsi al contrario quando i dati vengono esportati. I dati di **Data e ora** nell'entità DMF esportata possono essere differenti da quelli visualizzati nel client Dynamics. 
 
Quando si utilizzano origini esterne come DMF per visualizzare o creare dati, è importante da tenere presente che i valori di **Data e ora** vengono considerati per impostazione predefinita in UTC, indipendentemente dal fuso orario del computer dell'utente o dalle impostazioni correnti del fuso orario dell'utente. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Esempi dello stesso record che viene visualizzato nelle diverse aree del prodotto 

**Talent con fuso orario impostato su UTC**

[![Modulo Lavoratore](./media/worker-form3.png)](./media/worker-form3.png)

**Talent con fuso orario impostato su GMT +12:00** 

[![Modulo Lavoratore](./media/worker-form4.png)](./media/worker-form4.png)

**Excel tramite OData**

[![Excel tramite OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**Gestione temporanea DMF**

[![Gestione temporanea DMF](./media/DMFStaging.png)](./media/DMFStaging.png)

**Esportazione DMF**

[![Gestione temporanea DMF](./media/DMFexport.png)](./media/DMFexport.png)

**Excel tramite Common Data Service**

[![Excel tramite Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)

### <a name="see-also"></a>Vedere anche

[Dai di Data e ora](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[Fusi orari preferiti dall'utente](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
