---
title: Formati di file per i metodi di pagamento
description: In questo articolo vengono descritti i due metodi per ottenere i formati di file che è possibile utilizzare per i metodi di pagamento.
author: AdamTrukawka
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 262514
ms.search.form: CustPaymMode, VendPaymMode
ms.openlocfilehash: eae21fba2499d819a146953e56f48a8f9d748582
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292218"
---
# <a name="file-formats-for-methods-of-payment"></a>Formati di file per i metodi di pagamento

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritti i due metodi per ottenere i formati di file che è possibile utilizzare per i metodi di pagamento.

Sono disponibili due metodi che consentono di ottenere i formati di file da utilizzare con i metodi di pagamento, i formati di file di report elettronici (ER) o i formati di file X++. Quando si imposta un metodo di pagamento per un cliente o un fornitore, specificare i formati di file e gli standard da utilizzare per i pagamenti e la modalità con cui i pagamenti verranno elaborati. È possibile selezionare uno dei seguenti tipi di formati:

-   Esportazione
-   Importazione
-   Restituita
-   Rimessa

### <a name="method-1-electronic-reporting-file-formats"></a>Metodo 1: formati di file di report elettronici

Per i formati di file che si basano sulle configurazioni di report elettronici, è necessario importare le configurazioni da Lifecycle Services (LCS). Per ulteriori informazioni, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md). Dopo che le configurazioni di report per i formati di file sono state importate, i formati importati saranno disponibili per la selezione nella pagina **Metodi di pagamento**. Il processo per importare e selezionare i formati di file per l'Europa è simile alla procedura per il Giappone. Per ulteriori informazioni, vedere [Abilitare il formato del file di pagamento JBA](tasks/jba-payment-file-format.md)

### <a name="method-2-x-file-formats"></a>Metodo 2: formati di file X++

Per selezionare i formati di file basati sul codice X++, effettuare le operazioni seguenti.

1.  Passare alla pagina **Metodi di pagamento**.
2.  Nella Scheda dettaglio **Formati file** fare clic su **Impostazione**.
3.  Selezionare la scheda corrispondente al tipo di formato di file.
4.  Selezionare un formato di file dall'elenco **Disponibile** e spostarlo nell'elenco **Selezionati** utilizzando la freccia.
5.  Chiudere la pagina **Formati di file per i metodi di pagamento**.
6.  Nella Scheda dettaglio **Formati file** selezionare il formato di file per il metodo di pagamento per il campo di formato di file appropriato. Le opzioni di report elettronico generali devono essere impostate su **No** per i formati di file X++.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
