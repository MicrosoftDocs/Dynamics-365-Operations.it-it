---
title: Formati di file per i metodi di pagamento
description: "In questo argomento vengono descritti i due metodi per ottenere i formati di file che è possibile utilizzare per i metodi di pagamento."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPaymMode, VendPaymMode
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 262514
ms.assetid: 72ea2018-5a49-419c-93d0-755e5ff2722f
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9b3cf1d469998389895c137fa842b73adb0eeddc
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="file-formats-for-methods-of-payment"></a>Formati di file per i metodi di pagamento

[!include[banner](../includes/banner.md)]


In questo argomento vengono descritti i due metodi per ottenere i formati di file che è possibile utilizzare per i metodi di pagamento.

Sono disponibili due metodi che consentono di ottenere i formati di file da utilizzare con i metodi di pagamento, i formati di file di report elettronici (ER) o i formati di file X++. Quando si imposta un metodo di pagamento per un cliente o un fornitore, specificare i formati di file e gli standard da utilizzare per i pagamenti e la modalità con cui i pagamenti verranno elaborati. È possibile selezionare uno dei seguenti tipi di formati:

-   Esportazione
-   Importazione
-   Restituita
-   Rimessa

### <a name="method-1-electronic-reporting-file-formats"></a>Metodo 1: formati di file di report elettronici

Per i formati di file che si basano sulle configurazioni di report elettronici, è necessario importare le configurazioni da Lifecycle Services (LCS). Per ulteriori informazioni, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs). Dopo che le configurazioni di report per i formati di file sono state importate, i formati importati saranno disponibili per la selezione nella pagina **Metodi di pagamento**. Il processo per importare e selezionare i formati di file per l'Europa è simile alla procedura per il Giappone. <!---For more details, see [Enable the JBA payment file format](https://ax.help.dynamics.com/en/wiki/enable-the-jba-payment-file-format/).-->

### <a name="method-2-x-file-formats"></a>Metodo 2: formati di file X++

Per selezionare i formati di file basati sul codice X++, effettuare le operazioni seguenti.

1.  Passare alla pagina **Metodi di pagamento**.
2.  Nella Scheda dettaglio **Formati file** fare clic su **Impostazione**.
3.  Selezionare la scheda corrispondente al tipo di formato di file.
4.  Selezionare un formato di file dall'elenco **Disponibile** e spostarlo nell'elenco **Selezionati** utilizzando la freccia.
5.  Chiudere la pagina **Formati di file per i metodi di pagamento**.
6.  Nella Scheda dettaglio **Formati file** selezionare il formato di file per il metodo di pagamento per il campo di formato di file appropriato. Le opzioni di report elettronico generali devono essere impostate su **No** per i formati di file X++.





