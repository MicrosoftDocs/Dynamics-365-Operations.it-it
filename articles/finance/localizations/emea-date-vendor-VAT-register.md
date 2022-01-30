---
title: Data del registro IVA fornitore
description: In questo argomento vengono fornite informazioni su una funzionalità per l'abilitazione della data di registrazione IVA fornitore
author: anasyash
ms.date: 01/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: global
ms.author: anasyash
ms.search.validFrom: 2022-01-15
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 882d5a8718d819cff80bfa5b86e054a39e9db159
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7992063"
---
# <a name="date-of-vendor-vat-register"></a>Data del registro IVA fornitore

In Microsoft Dynamics 365 Finance versione 10.0.24, un nuovo campo **Data di registrazione IVA fornitore** è disponibile per le fatture fornitore. Questo campo specifica la data dell'offerta tassabile per un acquisto.

Per abilitare il nuovo campo, vai nell'area di lavoro **Gestione funzionalità** trova e seleziona la funzionalità **Abilita data di registrazione IVA fornitore in fatture fornitore** quindi seleziona **Abilita ora**.

Le fatture in entrata dai tuoi fornitori possono avere due date: la data in cui il fornitore ha emesso la fattura e la data dell'offerta tassabile (vale a dire, la data in cui il fornitore ha addebitato l'IVA dovuta). In alcuni scenari, queste due date potrebbero differire.

Puoi detrarre l'importo IVA in entrata per una fattura di acquisto e includere tale fattura nei report IVA in un secondo momento, in una data diversa da entrambe le date menzionate in precedenza. Questa data è controllata dalle norme della legislazione locale sulla detrazione dell'IVA in entrata posticipata per alcuni scenari. Varia per paese o area geografica.

Alcuni report IVA, come il [Report dichiarazione di controllo IVA](emea-cze-vat-declaration-tax-declaration-model.md#vat-control-statement) nella Repubblica Ceca, richiedono che la data dell'offerta tassabile sia indicata per un documento di acquisto. Tale data deve essere indicata in modo che le autorità fiscali possano riconciliare la dichiarazione IVA tra le controparti.

In Finance, puoi definire le date nei seguenti campi:

- **Data fattura** – La data in cui la fattura è stata emessa dal fornitore.
- **Data di registrazione IVA** – La data di detrazione dell'importo IVA per la fattura di acquisto.
- **Data di registrazione IVA fornitore** – La data dell'offerta tassabile del fornitore.
- **Data documento di ricezione** – La data in cui hai ricevuto la fattura.

Questi campi sono inclusi nelle seguenti pagine:

- Fattura fornitore
- Registro fatture fornitori
- Approvazione fattura fornitore
- Giornale di registrazione fatture fornitore

Dopo la registrazione della fattura fornitore puoi esaminare le date nelle pagine **Giornale di registrazione fatture** e **Transazioni fornitore**.
