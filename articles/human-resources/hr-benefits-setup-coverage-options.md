---
title: Creare opzioni di copertura
description: Questo argomento descrive le opzioni di copertura in Microsoft Dynamics 365 Human Resources per l'elezione di un partecipante in un piano o programma di benefici.
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
ms.openlocfilehash: 01eb0c56578cf6f6b070c4a05768ec5361993555
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065870"
---
# <a name="create-coverage-options"></a>Creare opzioni di copertura


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Le opzioni di copertura determinano chi deve essere coperto o quanta copertura è disponibile in un piano assicurativo. Per esempio, per un piano medico, si potrebbe avere un'opzione **solo per il dipendente** , un'opzione **per il dipendente + 1** e un'opzione per la **famiglia** . Per l'assicurazione sulla vita, potresti offrire una copertura per **1 x stipendio** o **2 x stipendio**.

Una volta definite le opzioni di copertura dei benefit, è possibile riutilizzarle. È possibile associare un'opzione a uno o più piani.

> [!IMPORTANT]
> Dopo aver definito le opzioni di copertura, associarle a un tipo di piano di benefit. Il tipo di piano viene quindi associato a un piano o programma di benefit. Le opzioni di copertura associate a un tipo di piano sono disponibili per tutti i piani creati con quel tipo di piano.

## <a name="create-coverage-options"></a>Creare opzioni di copertura
1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni di copertura**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Opzione di copertura** | Un nome di opzione di copertura univoco. |
   | **Descrizione** | Una descrizione dell'opzione di copertura. |
   | **Codice copertura** | I codici di copertura assegnano importi minimi e massimi per ogni tipo di persona coperta idonea. Un codice di copertura indica chi è coperto o l'importo di copertura consentito per un tipo di piano. È possibile esprimere l'importo di copertura in dollari o come percentuale. Ad esempio:<ul><li>**Dip +1**- Per essere idoneo, il dipendente deve avere una persona a carico selezionata (se sono selezionate più persone a carico, non è più idoneo).</li><li>**Dip+ famiglia** - Per essere idoneo, il dipendente deve aver selezionato almeno due persone a carico.</li></ul> |
   | **Numero massimo** | Il numero massimo di persone a carico. |
   | **Stato** | Lo stato dell'opzione di copertura. Se lo stato dell'opzione Copertura è impostato su **Non attivo**, l'opzione Copertura non può essere selezionata sui tipi di piano. |
   | **Percentuale** | L'importo in percentuale. Questo campo è attivo solo se % x stipendio è stato selezionato nel campo Codice copertura. |
   | **Divisore** | Il divisore da utilizzare nel calcolo quando si seleziona il codice di copertura % x stipendio. |
   | **Percentuale minima** | La percentuale minima quando si seleziona il codice di copertura Percentuale. |
   | **Percentuale massima** | La percentuale massima quando si seleziona il codice di copertura Percentuale. |

4. Sotto **Opzioni di idoneità per contatti personali**, associare l'opzione di idoneità dei contatti personali appropriata a ciascuna opzione di copertura.

5. Sotto **Self service**, specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Consenti importo di contribuzione dipendente** | Specifica se permettere ai dipendenti di modificare l'importo del contributo in Benefits self service quando selezionano i benefici. Se si seleziona questa casella di controllo, il sistema calcolerà i parametri del piano dei benefici in base all'importo del contributo che il dipendente inserisce in Benefits self service. |
   | **Consenti importo di copertura dipendente** | Specifica se permettere ai dipendenti di modificare l'importo della copertura in Benefits self service quando selezionano i benefici. Se si seleziona questa casella di controllo, il sistema calcolerà i parametri del piano di benefit in base all'importo di copertura immesso in Dipendente self-service. |

6. Selezionare **Salva**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
