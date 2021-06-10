---
title: Creare i tipi di piano
description: Un tipo di piano in Microsoft Dynamics 365 Human Resources è un raggruppamento di alto livello di specifici tipi di benefit. Ogni tipo di piano ha un codice di tipo di piano che determina le regole per il tipo di piano.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eb4746425c2faa3c0b1bd3940bf2e03cf7f9595c
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057864"
---
# <a name="create-plan-types"></a>Creare i tipi di piano

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Un tipo di piano in Microsoft Dynamics 365 Human Resources è un raggruppamento di alto livello di specifici tipi di benefit. Ogni tipo di piano ha un codice di tipo di piano che determina le regole per il tipo di piano. Ad esempio, il tipo di piano Vita base avrebbe il codice di tipo di piano Vita perché è un tipo di piano di assicurazione sulla vita e deve essere conforme alle regole stabilite per il codice Vita. Un altro tipo di piano potrebbe essere Vita supplementare, anch'esso con il codice di tipo di piano Vita.

Ogni tipo di piano indica se un dipendente può iscriversi a uno o più piani di quel tipo. Ad esempio, un dipendente sarebbe probabilmente in grado di iscriversi a entrambe le polizze Vita base e Vita supplementare del tipo di piano Vita. Un dipendente sarebbe probabilmente autorizzato a iscriversi a una sola polizza di tipo Medico.

Se un tipo di piano implica dei contatti, il tipo di piano indica se i contatti sono beneficiari o persone a carico. Ad esempio, un tipo di piano Vita base avrebbe beneficiari, mentre un tipo di piano Medico base avrebbe persone a carico. In alcuni casi, un piano potrebbe non avere contatti personali. Ad esempio, un conto spesa flessibile o un'indennità di parcheggio.

Un tipo di piano può definire opzioni di copertura. Le opzioni di copertura sono definite nel modulo Opzione di copertura. Un'opzione di copertura può specificare l'importo del benefit o i contatti che sono idonei per il tipo di piano. Ad esempio, se il tipo di contatto è Beneficiario, l'opzione di copertura dovrebbe definire i termini di ciò che il beneficiario ha diritto di ricevere quando il benefit viene utilizzato. Se il tipo di contatto è Persona a carico, l'opzione di copertura deve definire la relazione tra la persona a carico e il dipendente. 

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Tipi di piano**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Tipo di piano** | Nome univoco che identifica il tipo di piano. |
   | **Descrizione** | Descrizione del tipo di piano. |
   | **Codice tipo di piano** | Selezionare un codice di tipo di piano dall'elenco a discesa di valori. L'elenco di codici di tipo di piano contiene tutti i tipi di piano supportati nella versione corrente. |
   | **Iscrizione simultanea** | Specifica se un dipendente può iscriversi a più piani di benefit dello stesso tipo di piano o a un solo piano di benefit per tipo di piano. |
   | **Tipo di contatto** | Specifica il ruolo del contatto personale. I valori sono vuoto, Persona a carico e Beneficiario. È possibile lasciare vuoto il campo **Tipo di contatto** se il tipo di piano non richiede una persona a carico o un beneficiario in funzione dell'opzione di copertura. |

4. Per configurare opzioni di eventi reali, selezionare **Azioni**, quindi selezionare **Opzioni di eventi reali**. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Tipo di piano** | Il tipo di piano per il quale configurare le opzioni di eventi reali. |
   | **ID tipo di evento reale** | L'ID del tipo di evento reale. |
   | **Consenti annullamento** | Specifica se un dipendente può annullare un piano di benefit durante l'evento reale. |
   | **Modifica opzione di copertura** | Specifica se un dipendente può modificare le opzioni di copertura durante l'evento reale. |
   | **Modifica in un nuovo piano** | Specifica se un dipendente può modificare i piani durante l'evento reale. |
   | **Annulla piano automaticamente** | Specifica se annullare automaticamente un piano durante l'evento reale. |
   | **Riapri automaticamente il controllo di idoneità** | Specifica se riaprire automaticamente il controllo di idoneità di iscrizione di benefit durante l'evento reale. |
   | **Periodo di reporting** | Specifica il periodo di reporting dell'evento reale, in giorni. **Nota**: se non si immette un importo, il sistema presuppone che la finestra di reporting sia zero e non elaborerà l'evento reale. |

5. Selezionare **Salva**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]