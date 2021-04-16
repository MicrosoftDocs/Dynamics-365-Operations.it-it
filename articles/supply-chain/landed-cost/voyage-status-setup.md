---
title: Impostazione dello stato dei viaggi
description: In questo argomento viene descritto come stabilire i valori di stato che gli utenti possono assegnare ai viaggi.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 80433c17ed9d790d88b20ecc253c8e4459ffea10
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829790"
---
# <a name="voyage-status-setup"></a>Impostazione dello stato dei viaggi

[!include [banner](../../includes/banner.md)]

La pagina **Stati viaggio** consente di stabilire una serie di valori di stato che gli utenti possono assegnare ai viaggi. Gli utenti possono assegnare valori di stato di viaggio a tutti i livelli di un viaggio: viaggio, contenitore di spedizione, registrazione, ordine fornitore e articolo (righe di acquisto e righe di ordine di trasferimento). Sono utilizzati per due scopi:

- Informare l'utente sullo stato di viaggio, contenitore di spedizione, registrazione, ordine fornitore o articolo (righe di acquisto e righe di ordine di trasferimento).
- Limitare l'uso dell'area di costo prevenendone la modifica o l'eliminazione.

Selezionare **Costo sbarcato \> Impostazioni \> Stati viaggio** per aggiungere, rimuovere e modificare stati utilizzando i pulsanti nel riquadro Azioni.

Ogni area di costo comporta un insieme e una gerarchia di stati di viaggio. Pertanto, nella pagina **Stati viaggio**, nel campo **Area di costo**, è necessario dapprima selezionare l'area di costo per la quale si desidera visualizzare o creare stati di viaggio. Quindi, per ogni stato di viaggio, impostare i campi descritti nella tabella seguente, come necessario. Da notare che lo stato di un viaggio può anche essere modificato automaticamente dagli eventi di sistema, come le regole stabilite utilizzando il centro di controllo tracciabilità.

| Campo | Descrizione |
|---|---|
| Stato viaggio | Immettere il nome dello stato di viaggio. |
| Descrizione | Immettere una descrizione dello stato di viaggio. |
| Modifica | Selezionare questa casella di controllo se gli utenti possono modificare i viaggi con questo stato. |
| Elimina | Selezionare questa casella di controllo se gli utenti possono eliminare i viaggi con questo stato. |
| Obbligatorio | Selezionare questa casella di controllo per rendere obbligatorio lo stato del viaggio, in modo che non possa essere ignorato. |
| Padre | Utilizzare questo campo per stabilire una gerarchia tra i valori di stato. Gli stati di viaggio possono essere modificati (manualmente o automaticamente) solo verso il basso nella gerarchia, da uno stato padre a uno dei relativi stati figlio.

> [!NOTE]
> È necessario impostare solo gli stati di viaggio specifici utilizzati dall'organizzazione. Gli stati di viaggio tipici includono *Confermato*, *Merci in transito*, *Ricevuto*, *Pronto per determinazione costi* e *Preventivato*. Tuttavia, potrebbero essere presenti altri stati.
