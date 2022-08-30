---
title: Configurare le detrazioni
description: L'utilizzo delle detrazioni in Microsoft Dynamics 365 Human Resources consente di determinare quanto eventualmente detrarre dalla busta paga di un dipendente per ogni benefit.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 46a37aebf99751d16952d3d7c07c538713377a67
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324875"
---
# <a name="configure-deductions"></a>Configurare le detrazioni


L'utilizzo delle detrazioni in Microsoft Dynamics 365 Human Resources consente di determinare quanto eventualmente detrarre dalla busta paga di un dipendente per ogni benefit. Le detrazioni hanno una data di validità, pertanto è possibile tenere un record cronologico delle informazioni sulla detrazione. 

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Detrazioni**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Detrazione** | Un ID univoco utilizzato per identificare la detrazione per benefit. |
   | **Descrizione** | Una descrizione della detrazione. |
   | **Valido** | La data di inizio. Il valore predefinito è la data di sistema corrente. |
   | **Scadenza** | La data di fine. 31/12/2154 (che significa mai) è il valore predefinito. |
   | **Intestazione** | Il codice di intestazione del sistema di gestione delle retribuzioni che la detrazione utilizzerà per la parte della detrazione del dipendente durante l'elaborazione dei benefit per la retribuzione. Questo codice viene utilizzato quando si utilizza un fornitore di retribuzioni di terze parti. |
   | **Riferimento detrazioni sulle retribuzioni del dipendente** | Codice di detrazione del sistema di gestione delle retribuzioni utilizzato dalla detrazione per la parte relativa al dipendente della detrazione durante l'elaborazione dei benefit per le retribuzioni. |
   | **Intestazione importo** | Il codice di intestazione del sistema di gestione delle retribuzioni che questo importo di detrazioni utilizzerà per la parte della detrazione del dipendente durante l'elaborazione dei benefit per la retribuzione. Questo codice viene normalmente utilizzato quando si utilizza un fornitore di retribuzioni di terze parti. |
   | **Eliminazione possibile** | Specifica se un valore esportato da Dynamics 365 Finance può causare l'eliminazione del valore nel sistema di gestione delle retribuzioni. |
   | **Colonne associate** | Specifica se esportare l'intestazione e l'importo delle detrazioni in colonne adiacenti accoppiate nel sistema di gestione delle retribuzioni. |
   | **Data di validità modifica** | La data in cui la modifica alle detrazioni per benefit diventa effettiva. In questa data, le modifiche alla deduzione dei benefici e tutti i piani di benefici associati a questa deduzione sono aggiornati, a condizione che si esegua l'elaborazione dell' **aggiornamento della modifica della deduzione** . |
   | **Modifica detrazione completata** | La casella di controllo **Modifica detrazione completata** verrà selezionata automaticamente una volta completate le modifiche alla detrazioni per benefit mediante l'elaborazione dell'aggiornamento delle modifiche alle detrazioni. |
   
4. Per tenere traccia e gestire le modifiche all'impostazione del tasso di benefit, selezionare **Azioni**, quindi selezionare **Gestisci versioni**.

5. Selezionare **Salva**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]

