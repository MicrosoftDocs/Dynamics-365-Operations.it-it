---
title: Creare opzioni di copertura
description: Le opzioni di copertura in Microsoft Dynamics 365 Human Resources sono i livelli di copertura per l'idoneità di un partecipante in un piano o programma di benefit.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
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
ms.openlocfilehash: 8690dbe00c2316ccf745f5222c3cbaa9c3379f85
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430741"
---
# <a name="create-coverage-options"></a>Creare opzioni di copertura

Le opzioni di copertura in Microsoft Dynamics 365 Human Resources sono i livelli di copertura per l'idoneità di un partecipante in un piano o programma di benefit. Ad esempio, le opzioni di copertura possono includere **Solo dipendente** per un piano sanitario o **2x stipendio** per un piano di assicurazione sulla vita. Una volta definite, è possibile riutilizzare le opzioni di copertura dei benefit. È possibile associare un'opzione a uno o più piani.

Dopo aver definito le opzioni di copertura, associarle a un tipo di piano di benefit. Il tipo di piano viene quindi associato a un piano o programma di benefit. Le opzioni di copertura associate a un tipo di piano sono disponibili per tutti i piani creati con quel tipo di piano. 

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni di copertura**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Opzione di copertura** | Un nome di opzione di copertura univoco. |
   | **Descrizione** | Una descrizione dell'opzione di copertura. |
   | **Codice copertura** | I codici di copertura assegnano importi minimi e massimi per ogni tipo di persona coperta idonea. Un codice di copertura indica chi è coperto o l'importo di copertura consentito per un tipo di piano. È possibile esprimere l'importo di copertura in dollari o come percentuale. Ad esempio:</br></br>- **Dip+1** - Per essere idoneo, il dipendente deve avere una persona a carico selezionata (se sono selezionate più persone a carico, non è più idoneo).</br></br>- **Dip+ famiglia** - Per essere idoneo, il dipendente deve aver selezionato almeno due persone a carico. |
   | **Numero massimo** | Il numero massimo di persone a carico. |
   | **Stato** | Lo stato dell'opzione di copertura. Se lo stato dell'opzione di copertura è impostato su Non attivo, l'opzione di copertura non può essere selezionata nei tipi di piano. |
   | **Percentuale** | L'importo in percentuale. Questo campo è attivo solo se % x stipendio è stato selezionato nel campo Codice copertura. |
   | **Divisore** | Il divisore da utilizzare nel calcolo quando si seleziona il codice di copertura % x stipendio. |
   | **Percentuale minima** | La percentuale minima quando si seleziona il codice di copertura Percentuale. |
   | **Percentuale massima** | La percentuale massima quando si seleziona il codice di copertura Percentuale. |

4. Sotto **Opzioni di idoneità per contatti personali**, associare l'opzione di idoneità dei contatti personali appropriata a ciascuna opzione di copertura.

5. Sotto **Self service**, specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Consenti importo di contribuzione dipendente** | Specifica se consentire ai dipendenti di modificare l'importo di contribuzione nel self-service dei benefit quando selezionano i benefit. Se si seleziona questa casella di controllo, il sistema calcolerà i parametri del piano di benefit in base all'importo di contribuzione immesso dal dipendente nel self-service dei benefit. |
   | **Consenti importo di copertura dipendente** | Specifica se consentire ai dipendenti di modificare l'importo di copertura nel self-service dei benefit quando selezionano i benefit. Se si seleziona questa casella di controllo, il sistema calcolerà i parametri del piano di benefit in base all'importo di copertura immesso in Dipendente self-service. |

6. Selezionare **Salva**. 
