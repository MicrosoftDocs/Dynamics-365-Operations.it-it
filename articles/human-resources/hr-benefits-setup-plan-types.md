---
title: Panoramica del tipo di piano
description: Un tipo di piano in Microsoft Dynamics 365 Human Resources è un raggruppamento di alto livello di specifici tipi di benefit.
author: twheeloc
ms.date: 08/24/2021
ms.topic: overview
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
ms.openlocfilehash: 87be947c829641ba809e6850ccf41ea6d142161d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228962"
---
# <a name="plan-type-overview"></a>Panoramica del tipo di piano


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [banner](../includes/preview-banner.md)]

Un tipo di piano è un raggruppamento di alto livello di specifici tipi di benefit. Ogni tipo di piano ha un codice di tipo di piano che determina le regole per il tipo di piano. Ad esempio, il tipo di piano **Vita base** avrebbe il codice di tipo di piano **Vita** perché è un tipo di piano di assicurazione sulla vita e deve essere conforme alle regole stabilite per il codice **Vita**. Un altro tipo di piano potrebbe essere **Vita supplementare**. Anche questo tipo di piano avrà il codice tipo piano **Vita**.

Ogni tipo di piano indica se un dipendente può iscriversi a uno o più piani di quel tipo. Ad esempio, un dipendente sarebbe probabilmente in grado di iscriversi a entrambe le polizze **Vita base** e **Vita supplementare** del tipo di piano Vita. Un dipendente sarebbe probabilmente autorizzato a iscriversi a una sola polizza di tipo Medico.

Se un tipo di piano implica dei contatti, il tipo di piano indica se i contatti sono beneficiari o persone a carico. Ad esempio, un tipo di piano **Vita base** avrebbe beneficiari, mentre un tipo di piano Medico base avrebbe persone a carico. In alcuni casi, un piano potrebbe non avere contatti personali. Ad esempio, un conto spesa flessibile o un'indennità di parcheggio.


Un tipo di piano può definire opzioni di copertura. Le opzioni di copertura sono definite nella pagina **Opzioni di copertura**. Un'opzione di copertura può specificare l'importo del benefit o i contatti che sono idonei per il tipo di piano. Ad esempio, se il tipo di contatto è **Beneficiario**, l'opzione di copertura dovrebbe definire i termini di ciò che il beneficiario ha diritto di ricevere quando il benefit viene utilizzato. Se il tipo di contatto è **Persona a carico**, l'opzione di copertura deve definire la relazione tra la persona a carico e il dipendente. 

> [!IMPORTANT]
> La pagina **Tipi di piano** include dati chiave che influenzano le opzioni disponibili quando viene creato un nuovo piano di benefici:
>
> - **Codice tipo di piano** – Questo campo influisce su ciò che viene mostrato nella scheda **Configurazione** quando viene impostato il benefit effettivo.  
> - **Iscrizione simultanea** – Questo campo determina se sono consentite più iscrizioni. (Per un piano medico, questo campo è generalmente impostato su **Una iscrizione**.)
> - **Tipo di contatto** – Questo campo consente di aggiungere dipendenti o beneficiari a un piano. Se è impostato su **Nessuno**, i dipendenti che si iscrivono ai benefit non avranno la possibilità di selezionare un beneficiario o un dipendente.
> - **Opzioni di copertura** – Utilizza questo campo per collegare le opzioni di copertura ai tipi di piano. Definisce le persone che saranno coperte da questo tipo di piano o gli importi di copertura disponibili per questo tipo di piano. Ad esempio, è possibile specificare che la copertura per un tipo di piano medico sarà disponibile solo per il dipendente, per il dipendente e un'altra persona o per il dipendente e la sua famiglia.

## <a name="create-plan-types"></a>Creare i tipi di piano

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

4. Per configurare opzioni di eventi di vita, selezionare **Azioni**, quindi selezionare **Opzioni di eventi di vita**. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Tipo di piano** | Il tipo di piano per il quale configurare le opzioni di eventi di vita. |
   | **ID tipo di evento di vita** | L'ID del tipo di evento di vita. |
   | **Modifica opzione di copertura** | Specifica se un dipendente può modificare le opzioni di copertura durante l'evento di vita. |
   | **Modifica in un nuovo piano** | Specifica se un dipendente può modificare i piani durante l'evento di vita. |
   | **Riapri automaticamente il controllo di idoneità** | Specifica se riaprire automaticamente il controllo di idoneità di iscrizione di benefit durante l'evento di vita. |
   | **Periodo di iscrizione a evento di vita** | Specifica il periodo di reporting dell'evento di vita, in giorni. **Nota**: se non si immette un importo, il sistema presuppone che la finestra di reporting sia zero e non elaborerà l'evento di vita. |
   | **Modificabile solo dagli amministratori** | Specifica se gli amministratori possono annullare o modificare un piano durante un evento di vita. Nessuna modifica può essere apportata dal dipendente nell'area di lavoro **Dipendente self-service**. |
   | **Annulla piano automaticamente** | Specifica se un piano deve essere annullato automaticamente durante un evento di vita. Dopo l'elaborazione delle modifiche all'evento di vita, l'opzione **Annulla piano automaticamente** manterrà la selezione del piano. Solo lo stato **Confermato** o **Verificato** verrà rimosso. Il piano rimane selezionato. Pertanto, i dipendenti che non eseguono selezioni del piano durante il periodo di iscrizione all'evento di vita non perderanno la selezione del piano. 

5. Seleziona **Salva**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
