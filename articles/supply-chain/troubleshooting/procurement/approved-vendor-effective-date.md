---
title: Impossibile modificare la data di validità per un fornitore approvato
description: L'elenco dei fornitori approvati per entità prodotto non consente la modifica della data di validità
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: cb6dbd134d63daa163261cabdbd7eceb978877ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476724"
---
# <a name="cant-change-the-effective-date-for-an-approved-vendor"></a>Impossibile modificare la data di validità per un fornitore approvato


## <a name="symptoms"></a>Sintomi

Un prodotto ha un fornitore approvato che ha, ad esempio, una data di validità dell'11 gennaio 2018 (*11/01/2018*) e una data di scadenza di *Mai*. Se provi a modificare la data di validità al 10 gennaio 2018 (*10/01/2018*) o il 12 gennaio 2018 (*12/01/2018*), viene visualizzato il seguente errore:

> Impossibile creare un record nell'elenco dei fornitori approvati (PdsApproveVendorList). Il valore "Scadenza" deve essere maggiore o uguale al valore "Validità".

## <a name="resolution"></a>Risoluzione

È possibile estendere solo il periodo per il quale il fornitore è approvato. Vengono applicate le seguenti regole:

- Per modificare la data di validità in modo che sia precedente a qualsiasi record (periodo) esistente per il fornitore dell'articolo, la data di scadenza del nuovo periodo deve essere precedente a tutte le date di scadenza nei record esistenti.
- Per modificare la data di scadenza in modo che sia successiva a uno qualsiasi dei periodi esistenti, la data di validità deve essere successiva all'ultima data di scadenza in qualsiasi record esistente.
- Per ridurre il periodo complessivo per il quale il fornitore è approvato, è necessario eliminare o modificare i record esistenti. In alternativa, puoi utilizzare l'interruttore **Tronca** durante l'importazione. Questa opzione elimina tutti i record esistenti nella tabella per i fornitori approvati per articolo.

Per lo scenario di esempio descritto nella descrizione del problema, in cui un record ha una data di validità di *11/01/2018* e una data di scadenza di *Mai*, puoi importare un nuovo record con data di validità *10/01/2018* e una data di scadenza di *Mai*. Tuttavia, non è possibile ridurre il periodo in modo che la data di validità venga aggiornata a *12/01/2018* tramite la gestione dei dati. È necessario apportare questa modifica tramite l'interfaccia utente.
