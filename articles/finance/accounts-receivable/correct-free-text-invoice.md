---
title: Correzione di una fattura a testo libero
description: In questo articolo viene illustrato come correggere una fattura a testo libero registrata e come riemetterla in modo corretto.
author: abruer
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b3cc07a1f0ba444250eddcf892681e2ca63e9c1a
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780519"
---
# <a name="correct-a-free-text-invoice"></a>Correzione di una fattura a testo libero

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato come correggere una fattura a testo libero registrata e come riemetterla in modo corretto.

Per correggere una fattura a testo libero già registrata: 
1. Apri la fattura a testo libero registrata. 
2. Nella pagina **Fattura** selezionare **Annulla** e quindi selezionare **Fattura corretta**. 
3. Selezionare un codice motivo, aggiungere commenti e selezionare la data della nuova fattura corretta.
4. È possibile modificare la fattura corretta e registrarla. 

Quando si registra la fattura corretta, una fattura di annullamento viene creata per un importo in Avere equivalente all'importo della fattura originale. Quindi, il saldo combinato della fattura originale e della fattura di annullamento sarà 0 (zero). La fattura di annullamento viene liquidata a fronte della fattura originale. 

Dopo la registrazione della fattura corretta, si avranno tre fatture:

-   **Fattura originale**: fattura che include le informazioni da correggere.
-   **Fattura di annullamento**: fattura nota di accredito generata dal sistema e creata per annullare l'ultima fattura corretta.
-   **Fattura corretta**: fattura che contiene le informazioni della fattura corrette.

È possibile identificare la fattura di annullamento e di correzione in due modi:

-   La pagina **Tutte le fatture a testo libero** include una colonna **Correzione**, in cui è possibile visualizzare quali fatture sono di annullamento e quali fatture corrette.
-   Nell'intestazione della fattura a testo libero viene visualizzato uno stato **Fattura di annullamento '\[numero fattura\]'** o **Fattura corretta '\[numero fattura\]'**.

> [!NOTE]
> Questa funzionalità è disponibile solo se è selezionata la chiave di configurazione **Correzione fattura a testo libero.** Per ulteriori informazioni su come abilitare le chiavi di configurazione, vedi la sezione relativa all'abilitazione (o disabilitazione) delle chiavi di configurazione nell'articolo [Modalità manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md). 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
