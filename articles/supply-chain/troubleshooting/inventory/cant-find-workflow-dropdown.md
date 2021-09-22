---
title: Impossibile trovare la finestra di dialogo a discesa "Flusso di lavoro" per i giornali di registrazione magazzino
description: Non è possibile trovare la finestra di dialogo a discesa "Flusso di lavoro" nella pagina del giornale di registrazione o le operazioni del flusso di lavoro correlate non sono disponibili
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8b2772a75c2388f4d78a459f9dfb72ad7c1be4ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476750"
---
# <a name="you-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>Impossibile trovare la finestra di dialogo a discesa "Flusso di lavoro" per i giornali di registrazione magazzino

## <a name="symptoms"></a>Sintomi

Non riesci a trovare la finestra di dialogo a discesa **Flusso di lavoro** nella pagina del giornale di registrazione o le operazioni del flusso di lavoro correlate non sono disponibili.

Questo problema può verificarsi per tre motivi, come descritto nelle sezioni seguenti.

## <a name="resolution-1"></a>Risoluzione 1

Se il problema si applica a tutti gli utenti, potrebbe verificarsi perché il flusso di lavoro di approvazione non è stato assegnato al nome del giornale di registrazione. Per risolvere il problema, procedere come segue.

1. Andare a **Gestione inventario &gt; Imposta &gt; Nomi giornale di registrazione &gt; Inventario**.
1. Nel riquadro dell'elenco, selezionare il nome di un giornale di registrazione per aprirne le impostazioni.
1. Nella Scheda dettaglio **Generale**, impostare l'opzione **Flusso di lavoro di approvazione** su *Sì*. Se viene richiesto di confermare la modifica, fare clic su **Sì**.
1. Nel campo **Flusso di lavoro** selezionare il flusso di lavoro che si desidera utilizzare per il nome del giornale di registrazione selezionato.

## <a name="resolution-2"></a>Risoluzione 2

Se il flusso di lavoro utilizza codice personalizzato, potrebbero verificarsi problemi dopo l'aggiornamento del sistema. Ad esempio, nel flusso di lavoro del giornale di registrazione, il pulsante **Invia** potrebbe essere disattivato, quindi non puoi selezionarlo per approvare un invio.

Se il pulsante **Invia** è disattivato, il flusso di lavoro potrebbe essere stato personalizzato, il che significa che il metodo del flusso di lavoro, `canSubmitToWorkflow()` in `FormDataUtil`, è stato esteso. Per risolvere questo problema, modifica il modo in cui estendi il metodo `canSubmitToWorkflow()` per utilizzare la struttura nel seguente esempio.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

## <a name="resolution-3"></a>Risoluzione 3

Se il problema si applica solo a pochi utenti specifici, tali utenti potrebbero non disporre dei privilegi di sicurezza obbligatori per eseguire le operazioni del flusso di lavoro sui giornali di registrazione magazzino. Verifica che ogni utente interessato disponga del privilegio di sicurezza *Mantieni il flusso di lavoro del giornale di registrazione magazzino*. Per impostazione predefinita, questo privilegio viene assegnato a un compito con lo stesso nome e tale compito viene applicato ai ruoli *Addetto magazzino* e *Responsabile magazzino*.
