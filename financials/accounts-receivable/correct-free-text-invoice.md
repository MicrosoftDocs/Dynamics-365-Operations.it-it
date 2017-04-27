---
title: Correzione di una fattura a testo libero
description: In questo articolo viene illustrato come correggere una fattura a testo libero registrata e come riemetterla in modo corretto.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: ab16c517abfd3fa2b59625fff04b7427ee3471bb
ms.lasthandoff: 03/31/2017


---

# <a name="correct-a-free-text-invoice"></a>Correzione di una fattura a testo libero

[!include[banner](../includes/banner.md)]


In questo articolo viene illustrato come correggere una fattura a testo libero registrata e come riemetterla in modo corretto.

Per correggere una fattura a testo libero già registrata, aprire la fattura a testo libero registrata. Nella pagina **Fattura** selezionare **Annulla** e quindi selezionare **Fattura corretta**. Selezionare un codice motivo, aggiungere commenti e selezionare la data della nuova fattura corretta. È possibile modificare la fattura corretta e registrarla. 

Quando si registra la fattura corretta, una fattura di annullamento viene creata per un importo in Avere equivalente all'importo della fattura originale. Quindi, il saldo combinato della fattura originale e della fattura di annullamento sarà 0 (zero). La fattura di annullamento viene liquidata a fronte della fattura originale. 

Dopo la registrazione della fattura corretta, si avranno tre fatture:

-   **Fattura originale**: fattura che include le informazioni da correggere.
-   **Fattura di annullamento**: fattura nota di accredito generata dal sistema e creata per annullare l'ultima fattura corretta.
-   **Fattura corretta**: fattura che contiene le informazioni della fattura corrette.

È possibile identificare la fattura di annullamento e di correzione in due modi:

-   La pagina **Tutte le fatture a testo libero** include una colonna **Correzione**, in cui è possibile visualizzare quali fatture sono di annullamento e quali fatture corrette.
-   Nell'intestazione della fattura a testo libero viene visualizzato uno stato **Fattura di annullamento '\[numero fattura\]'** o **Fattura corretta '\[numero fattura\]'**.

> [!NOTE]
> Questa funzionalità è disponibile solo se è selezionata la chiave di configurazione **Correzione fattura a testo libero.**




