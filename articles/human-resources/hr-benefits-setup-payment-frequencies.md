---
title: Impostare le frequenze pagamenti
description: Microsoft Dynamics 365 Human Resources utilizza frequenze di pagamento per calcolare la retribuzione benefit annuale, determinare l'importo del premio di benefit che un dipendente paga ogni periodo retributivo e definire la frequenza del pagamento per i fornitori.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1a11023f6b80b74ff4e4e5523550288f7c15cdb9
ms.sourcegitcommit: 8592c661b41f9cef8b7ef2863a3b97bf49a4e6f9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "7423392"
---
# <a name="set-up-payment-frequencies"></a>Impostare le frequenze pagamenti

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources utilizza frequenze di pagamento per calcolare la retribuzione benefit annuale, determinare l'importo del premio di benefit che un dipendente paga ogni periodo retributivo e definire la frequenza del pagamento per i fornitori.

Le frequenze di pagamento di benefit utilizzano fattori di conversione per convertire periodi di pagamento di benefit tra frequenze di pagamento mensili, semestrali, quindicinali, settimanali e giornaliere. Ciò consente alle società di definire l'interdipendenza tra le frequenze di pagamento in un piano di benefit.

I campi dei fattori di conversione identificano il fattore di conversione dalla frequenza di pagamento ai periodi di pagamento standard e consentono al sistema di eseguire calcoli tra le frequenze di pagamento. L'importo del fattore di conversione determina anche l'importo del premio di benefit che un dipendente deve pagare a ogni frequenza di retribuzione.

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Frequenze pagamenti**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Frequenza pagamenti** | Un nome di frequenza di pagamento univoco. |
   | **Descrizione** | Una descrizione della frequenza di pagamento. |
   | **Periodo** | Il periodo appropriato che corrisponde meglio alla frequenza di pagamento del dipendente e del prestatore di benefit. L'elenco Periodo è composto da periodi di pagamento standard. |
   | **Numero di periodi retributivi** | Il numero di periodi retributivi che rappresenta la frequenza alla quale il prestatore di benefit o i dipendenti sono pagati. Questo importo verrà utilizzato per calcolare l'importo della retribuzione benefit annuale del dipendente. |
   | **Fattore di conversione annuale** | Il fattore di conversione annuale per la frequenza di pagamento. Ad esempio, il fattore di conversione annuale per la frequenza di retribuzione mensile è: </br></br>(12 pagamenti mensili/1 anno) = 12 |
   | **Fattore di conversione semestrale** | Il fattore di conversione semestrale per la frequenza di pagamento. Ad esempio, il fattore di conversione semestrale per la frequenza di retribuzione mensile è: </br></br>(12 pagamenti mensili/2 volte all'anno) = 6 |
   | **Fattore di conversione trimestrale** | Il fattore di conversione trimestrale per la frequenza di pagamento. Ad esempio, il fattore di conversione trimestrale per la frequenza di retribuzione mensile è: </br></br>(12 pagamenti mensili/4 trimestri) = 3 |
   | **Fattore di conversione mensile** | Il fattore di conversione mensile per la frequenza di pagamento. Ad esempio, il fattore di conversione mensile per la frequenza di retribuzione mensile è: </br></br>(12 pagamenti mensili/12 mesi) = 1 |
   | **Fattore di conversione quindicinale** | Il fattore di conversione quindicinale per la frequenza di pagamento. Ad esempio, il fattore di conversione quindicinale per la frequenza di retribuzione mensile è: </br></br>(12 pagamenti mensili/24 (2x al mese)) = 0,5 | 
   | **Fattore di conversione bisettimanale** | Il fattore di conversione annuale per la frequenza di pagamento. Ad esempio, il fattore di conversione annuale per la frequenza di retribuzione mensile è: </br></br>(12 pagamenti mensili/26 settimane) = 0,461538 |
   | **Fattore di conversione settimanale** | Il fattore di conversione annuale per la frequenza di pagamento. Ad esempio, il fattore di conversione annuale per la frequenza di retribuzione mensile è: </br></br>(12 pagamenti mensili/52 settimane) = 0,230769 |
   | **Fattore di conversione giornaliero** | Il fattore di conversione annuale per la frequenza di pagamento. Ad esempio, il fattore di conversione annuale per la frequenza di retribuzione mensile è: </br></br>(12 pagamenti mensili/365 giorni) = 0,032877 |
   | **Fattore di conversione oraria** | Il fattore di conversione annuale per la frequenza di pagamento. Ad esempio, il fattore di conversione annuale per la frequenza di retribuzione mensile è: </br></br>(12 pagamenti mensili/2080 ore) = 0,005769

4. Selezionare **Salva**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
