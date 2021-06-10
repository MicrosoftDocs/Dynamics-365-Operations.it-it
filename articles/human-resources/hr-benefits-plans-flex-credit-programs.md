---
title: Impostare programmi di crediti flessibili
description: È possibile utilizzare programmi di crediti flessibili in Microsoft Dynamics 365 Human Resources per iscrivere i dipendenti ai benefit secondo un numero prestabilito di crediti flessibili.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitCreditPrograms, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1dba179e47f586d7fe689b4a021eb9003eb0d9fc
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051859"
---
# <a name="set-up-flex-credit-programs"></a>Impostare programmi di crediti flessibili

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

È possibile utilizzare programmi di crediti flessibili in Microsoft Dynamics 365 Human Resources per iscrivere i dipendenti ai benefit secondo un numero prestabilito di crediti flessibili. I dipendenti possono scegliere il modo in cui allocare i propri crediti flessibili. Ad esempio, se un dipendente è coperto dal piano di assicurazione sanitaria del coniuge, potrebbe voler utilizzare i crediti che avrebbe altrimenti utilizzato per la copertura sanitaria per altri benefit. 

1. Nell'area di lavoro **Gestione benefit**, sotto **Piani**, selezionare **Programmi di crediti flessibili**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **ID credito benefit** | L'identificatore univoco del programma di crediti flessibili. |
   | **Descrizione** | Una descrizione del programma di crediti flessibili. | 
   | **Dal** | La data in cui il programma di crediti flessibili diventa attivo. |
   | **Al** | La data di fine del programma di crediti flessibili. È possibile mantenere il valore predefinito (31/12/2154) per indicare che il programma di crediti flessibili non ha una scadenza programmata. |
   | **Valore di credito totale** | Il numero di crediti che ciascun dipendente dovrà utilizzare per i propri benefit. |
   | **Regola di ripartizione** | La regola da utilizzare per ripartire i crediti flessibili quando un dipendente viene assunto durante il periodo di credito flessibile. </br></br><ul><li>**Nessuna** - Il dipendente non riceve crediti flessibili se viene assunto dopo l'inizio del periodo del programma di crediti flessibili.</li><li>**Credito totale** - Il dipendente riceve l'intero importo di crediti flessibili, indipendentemente da quando è stato assunto.</li><li>**Ripartizione** - Il dipendente riceve una quantità di crediti flessibili ripartita proporzionalmente in base alla data di inizio.</li></ul> |
   | **Formula di ripartizione del credito flessibile** | La regola da utilizzare per ripartire i crediti flessibili per i dipendenti che vengono assunti durante un periodo di benefit per il programma di crediti flessibili. La ripartizione si basa sulla data di inizio dell'impiego. Questo campo è utilizzato solo se si seleziona **Ripartizione** nel campo **Regola di ripartizione**. </br></br><ul><li>**Giornaliero** - Ripartisce il numero di crediti flessibili che un dipendente riceve a livello giornaliero. Il numero totale di crediti flessibili è diviso per il numero di giorni nel periodo. Ad esempio, se il periodo di benefit è 400 giorni, il sistema dividerà il numero totale di crediti flessibili per 400 per calcolare il numero di crediti flessibili che i dipendenti ricevono giornalmente.</li><li>**Mese corrente** - Ripartisce il numero di crediti flessibili che un dipendente riceve a livello mensile, arrotondato al mese corrente. Il numero totale di crediti flessibili è diviso per il numero di mesi nel periodo. Ad esempio, se il periodo di benefit è 15 mesi, il sistema dividerà il numero totale di crediti flessibili per 15 per calcolare il numero di crediti flessibili che i dipendenti ricevono al mese.</li><li>**Mese successivo** - Ripartisce il numero di crediti flessibili che un dipendente riceve a livello mensile, arrotondato al mese successivo. Il numero totale di crediti flessibili è diviso per il numero di mesi nel periodo. Ad esempio, se il periodo di benefit è 15 mesi, il sistema divide il numero totale di crediti flessibili per 15 per calcolare il numero di crediti flessibili che i dipendenti ricevono al mese.</li></ul> |
   


[!INCLUDE[footer-include](../includes/footer-banner.md)]