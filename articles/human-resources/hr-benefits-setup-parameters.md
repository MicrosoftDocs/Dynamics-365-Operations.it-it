---
title: Impostare i parametri di gestione dei benefit e self-service dei dipendenti per tutte le aziende
description: Configurare i parametri di gestione dei benefit e self-service dei dipendenti in Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b50c4f71789c34f08ce810312f3c3198303b031e
ms.sourcegitcommit: d02fae79d5c02a4bc4f4b16a410c2f5ce026c204
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "4962442"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a>Impostare i parametri di gestione dei benefit e self-service dei dipendenti per tutte le aziende

Prima di poter impostare piani di benefit in Microsoft Dynamics 365 Human Resources, è necessario configurare i parametri di Gestione benefit. Questi parametri impostano valori predefiniti, codici motivo e altre opzioni. 

## <a name="configure-general-parameters"></a>Configurare i parametri generali

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri condividi Risorse umane**.

2. Nella scheda **Gestione benefit** specificare i valori per i seguenti campi:

   | Campo | descrizione |
   | --- | --- |
   | **Paese** | Il campo **Paese** determina l'ordine di visualizzazione di paesi/CAP. Il paese selezionato viene visualizzato per primo nell'elenco a discesa. |
   | **Codice motivo iscrizione** | Selezionare un codice motivo predefinito da utilizzare quando vengono creati piani per i dipendenti durante l'elaborazione dell'iscrizione aperta. |
   | **Codice motivo annullamento** | Il codice motivo da utilizzare quando un piano benefit per i dipendenti viene annullato. Viene visualizzato in una finestra di dialogo durante il processo di annullamento. Gli utenti possono modificarlo in **Codice motivo annullamento** se necessario. |
   | **Codice motivo riapertura** | Il codice motivo da utilizzare quando un piano benefit per i dipendenti viene riaperto. Viene visualizzato in una finestra di dialogo durante il processo di annullamento. Gli utenti possono modificare il **Codice motivo riapertura** se necessario. | 
   | **Codice motivo evento reale** | Il codice motivo da utilizzare quando si verifica un evento reale. |
   | **Codice motivo modifica tassi** | Il codice motivo da utilizzare si annulla e si riapre un piano di benefit per i dipendenti durante il processo di aggiornamento delle modifiche ai tassi. Indica quali record sono stati modificati dal processo di aggiornamento delle modifiche ai tassi. |
   | **Retribuzione annuale benefit** | Consente di impostare un importo **Retribuzione annuale benefit** per un dipendente. Le risorse umane useranno l'importo **Retribuzione annuale benefit** nel determinare gli importi di copertura, anziché l'importo annuale di retribuzione fissa. |
   | **Nuova assunzione idonea** | Specifica se le nuove assunzioni sono idonee. |
   | **Periodo di iscrizione nuova assunzione** | Il periodo di tempo in cui è consentita l'iscrizione di un nuova assunzione.</br></br>**Nota**: questa impostazione sostituisce qualsiasi periodo di iscrizione di nuove assunzioni impostato nella regola di idoneità del piano. |
   | **Frequenza pagamenti predefinita** | La frequenza di retribuzione predefinita da utilizzare quando vengono aggiunti nuovi lavoratori. |
   | **Eventi reali abilitati** | Abilita gli eventi reali. |
   | **Nascondi moduli di benefit legacy** | Consente di nascondere i moduli di benefit legacy. |
   | **Verifica benefit** | Il testo di verifica da utilizzare durante il checkout dei benefit self-service. |
   | **Seleziona automaticamente i beneficiari designati** | Specifica se selezionare automaticamente le persone a carico e i beneficiari in base alla loro idoneità per le opzioni del piano. |

3. Selezionare **Salva**.

## <a name="configure-employee-self-service-parameters"></a>Configurare i parametri di self-service dipendenti

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri Risorse umane**.

2. Nella scheda **Gestione benefit** specificare i valori per i seguenti campi:

   | Campo | descrizione |
   | --- | --- |
   | **Verifica benefit** | Il testo di verifica da utilizzare durante il checkout dei benefit self-service. |
   | **Seleziona automaticamente i beneficiari designati** | Specifica se selezionare automaticamente le persone a carico e i beneficiari in base alla loro idoneità per le opzioni del piano. |

3. Selezionare **Salva**.


