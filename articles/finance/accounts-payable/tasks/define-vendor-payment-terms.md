---
title: Definire termini di pagamento fornitore
description: In questo argomento viene spiegato come impostare le condizioni di pagamento per le fatture fornitore.
author: abruer
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1b69b505996b5536088578885c11a7e8c27f4975
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971855"
---
# <a name="define-vendor-payment-terms"></a>Definire termini di pagamento fornitore

[!include [banner](../../includes/banner.md)]

In questo argomento viene spiegato come impostare le condizioni di pagamento per le fatture fornitore. In questa attività viene utilizzata la società dimostrativa USMF.

1. Andare a **Pannello di navigazione > Moduli > Contabilità fornitori > Impostazione pagamenti > Termini di pagamento**.
2. Selezionare **Nuovo**. La pagina Termini di pagamento viene utilizzata per definire la modalità di calcolo della data di scadenza. Tale pagina viene utilizzata per definire come la data dello sconto di cassa verrà calcolata.  
3. Digitare un valore nel campo **Termini di pagamento**.
4. Digitare un valore nel campo **Descrizione**
5. Nel campo **Giorni** immettere un numero. Il numero immesso in questo campo verrà utilizzato per essere aggiunto alla data di scadenza o alla fine del periodo identificato nel Metodo di pagamento. Ad esempio, se si seleziona **Netto**, il numero verrà aggiunto alla data di scadenza. Se si seleziona **Mese corrente**, verrà aggiunto il numero all'ultimo giorno del mese corrente per calcolare la data di scadenza.  
6. Selezionare **Salva**.
7. Chiudere la pagina.
8. Andare a **Contabilità fornitori > Impostazione pagamenti > Sconti di cassa**.
9. Selezionare **Nuovo**.
10. Nel campo **Sconto di cassa** immettere un ID.
11. Digitare un valore nel campo **Descrizione**
12. Se il fornitore offre più livelli di sconto, selezionare lo sconto di cassa successivo dopo che quello corrente è scaduto.
13. Chiudere la pagina.
14. Nel campo **Giorni** immettere un numero. La quantità immessa nel campo **Giorni** verrà utilizzata per calcolare la data dello sconto di cassa in base all'opzione selezionata nel campo **Netto/Corrente**. Se è stato selezionato **Netto**, la quantità verrà aggiunta alla data della fattura per determinare la data dello sconto di cassa. Se è stato selezionato **Mese corrente**, la quantità verrà aggiunta alla fine del mese della valuta per determinare la data dello sconto di cassa.  
15. Immettere la percentuale dello sconto di cassa nel campo **Sconto**. 
16. Immettere il conto principale in cui lo sconto di cassa verrà registrato per le fatture cliente, quindi immettere il conto principale in cui lo sconto di cassa verrà registrato per le fatture fornitore. Se **Conti di contropartita sconti** viene impostato su **Utilizza conto principale per sconti fornitore**, verrà utilizzato il conto principale. Se l'opzione è impostata su **Conti nelle righe fattura**, lo sconto di cassa verrà registrato nei conti spese/cespite nelle righe della fattura.  
17. Selezionare **Salva**.

