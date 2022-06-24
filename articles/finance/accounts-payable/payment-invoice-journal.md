---
title: Applicare uno scadenziario pagamenti al giornale di registrazione fatture
description: Questo articolo descrive come aggiungere un pagamento al giornale di registrazione fatture fornitore.
author: sunfzam
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f3ae08ea46be66dd8bf26f7f91bd73f6c5b9192f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863132"
---
# <a name="apply-a-payment-schedule-to-the-invoice-journal"></a>Applicare uno scadenziario pagamenti al giornale di registrazione fatture

[!include [banner](../includes/preview-banner.md)]

In Microsoft Dynamics 365 Finance versione 10.0.25, ora è supportato uno scadenzario pagamenti nel **giornale di registrazione fatture fornitore**.

Per utilizzare questa funzionalità, è necessario abilitare la funzionalità **Applica scadenzario pagamenti a giornale di registrazione fatture** in Gestione funzionalità.

Dopo che la funzionalità è stata abilitata, un nuovo campo **Scadenzario pagamenti** viene aggiunto alla pagina **Giornale di registrazione fatture**. Quando si crea una riga del giornale di registrazione fatture, se i termini di pagamento sono mantenuti nel fornitore e i termini di pagamento sono selezionati nello scadenzario pagamenti, il campo **Scadenzario pagamenti** viene aggiornato sulla pagina **Giornale di registrazione fatture**.

È possibile modificare lo scadenziario dei pagamenti utilizzato, in base alle proprie esigenze aziendali. Durante la registrazione del giornale di registrazione fatture fornitore, le transazioni aperte fornitore verranno create in base allo scadenzario pagamenti.

 - Per esaminare più transazioni aperte fornitore generate dallo scadenzario pagamenti, vai a **Contabilità fornitori \> Fatture \> Fatture fornitore aperte** e inserire il numero di fattura o il conto fornitore.
 - Per rivedere o configurare lo scadenziario dei pagamenti, vai a **Contabilità fornitori \> Impostazione pagamenti \> Scadenzario pagamenti**.
 - Per configurare i termini di pagamento e assegnare uno scadenzario pagamenti, vai a **Contabilità fornitori \> Impostazione pagamenti \> Termini di pagamento**.
 - Per mantenere i termini di pagamento su un fornitore, vai a **Contabilità fornitori \> Tutti i fornitori**, selezionare il conto fornitore, quindi nella scheda **Pagamento**, impostare il campo **Termini di pagamento**.

La funzione di scadenziario dei pagamenti è disponibile anche nel processo **Registro fatture fornitori**. Se nel giornale di registrazione fatture viene selezionato uno scadenzario pagamenti, più righe di pagamento fornitore **non** verranno generate al momento della registrazione nel registro fatture. Le righe di pagamento fornitore verranno generate al momento dell'approvazione della fattura.

## <a name="limitation"></a>Limite

Per una fattura fornitore in sospeso, se lo scadenzario pagamenti è nell'intestazione della fattura, è disponibile una pagina avanzata che consente agli utenti di modificare le righe di pagamento. (Ad esempio, gli utenti possono modificare la data di scadenza e il valore per ciascuna riga di pagamento.) Le righe di pagamento generate dal giornale di registrazione fatture avranno il valore dallo scadenzario pagamenti.

Questa funzionalità sarà disponibile per il **giornale di registrazione fatture fornitore** e le **fatture in sospeso** in una versione futura.
