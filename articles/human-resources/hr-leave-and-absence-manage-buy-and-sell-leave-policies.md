---
title: Gestire criteri di acquisto e vendita di congedi
description: È possibile consentire ai dipendenti di acquistare e vendere congedi in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1fe7ce7eafdec175e3395a6ac37b33cb2bb8dbda
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066677"
---
# <a name="manage-buy-and-sell-leave-policies"></a>Gestire i criteri di acquisto e vendita congedo


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

È possibile consentire ai dipendenti di acquistare e vendere congedi creando un criterio di acquisto e vendita di congedi. È possibile configurare questi criteri per utilizzare il flusso di lavoro per le approvazioni, impostare importi e tariffe massime e impostare tariffe per l'acquisto e la vendita. 

## <a name="enable-employees-to-buy-and-sell-leave"></a>Consentire ai dipendenti di acquistare e vendere congedi

1. Nella pagina **Parametri di congedi e assenze**, selezionare **Sì** per **Consenti a dipendenti di acquistare congedi** e **Consenti a dipendenti di vendere congedi**.

## <a name="create-a-buy-and-sell-leave-policy"></a>Creare criteri per l'acquisto e la vendita di congedi

1. Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**. 

2. Selezionare **Criterio di acquisto e vendita di congedi**.

3. Selezionare **Nuovo**.

4. Immettere un **Nome** e una **Descrizione** per il criterio sotto **Criterio di acquisto e vendita di congedi**. 

5. Selezionare un **Tipo di criterio**. 

   I tipi di criteri disponibili sono **Quantità** e **Ore per settimana**. Selezionare **Quantità** per immettere un **Quantità fissa** per le quantità massime che i dipendenti possono acquistare e vendere. Se si seleziona **Ore per settimana**, l'orario di lavoro definito nel calendario dell'orario di lavoro assegnato del dipendente viene utilizzato per determinare la quantità massima del criterio. 

6. Selezionare una **Data di inizio** e una **Data di fine** per il criterio. Le richieste di acquisto o vendita di congedi possono essere inviate solo durante questo periodo di tempo. 

7. Selezionare un **ID flusso di lavoro** per i criteri. Qualsiasi richiesta di acquisto e vendita utilizzerà questo flusso di lavoro per la revisione e l'approvazione. 

8. Sotto **Criterio di acquisto**, selezionare **Equivalenza a tempo pieno** per ripartire la quantità massima in base all'equivalenza a tempo pieno definita nella posizione del dipendente. Se il tipo di criterio è **Quantità**, immettere una **Quantità fissa massima**. 

9. Selezionare **Aggiungi** per aggiungere i tipi di congedo che i dipendenti possono acquistare. È possibile aggiungere più tipi di congedo al criterio. 

10. Immettere i **Mesi di servizio** per il tipo di congedo allo scopo di consentire diversi mesi di servizio e determinare la quantità massima che un dipendente può acquistare. 

11. Immettere la **Quantità massima** per il tipo di congedo. 

12. Immettere il **Tasso** al quale il dipendente acquisterà il congedo. 

13. Eventualmente, immettere il **Codice di reddito** da utilizzare per l'acquisto dei congedi. 

14. Se necessario, impostare se utilizzare l'equivalenza a tempo pieno per determinare la quantità massima per il tipo di congedo. 

15. Per creare i criteri di vendita, seguire i passaggi da 8 a 14 in **Criteri di vendita**. 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a>Aggiungere il criterio di acquisto e vendita di congedi a un piano di congedo e assenza

1. Nella pagina **Congedo e assenza**, selezionare un piano di congedo e assenza.

2. Sotto **Regole**, selezionare **Criterio di acquisto e vendita di congedi**.

## <a name="see-also"></a>Vedere anche

[Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)</br>
[Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md)</br>
[Accumulare piani di congedo e assenza](hr-leave-and-absence-accrue.md)</br>
[Acquista e vendi congedo](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
