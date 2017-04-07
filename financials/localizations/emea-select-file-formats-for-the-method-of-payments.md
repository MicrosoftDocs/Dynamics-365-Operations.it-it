---
title: Formati di file per i metodi di pagamento
description: "In questo argomento vengono descritti i due metodi per ottenere i formati di file che è possibile utilizzare per i metodi di pagamento."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 54af22f1f2ec779bf947ae584a3ae09c20e6a364
ms.lasthandoff: 03/31/2017


---

# <a name="file-formats-for-methods-of-payment"></a>Formati di file per i metodi di pagamento

In questo argomento vengono descritti i due metodi per ottenere i formati di file che è possibile utilizzare per i metodi di pagamento.

Sono disponibili due metodi che consentono di ottenere i formati di file da utilizzare con i metodi di pagamento, i formati di file di report elettronici (ER) o dei formati di file X++. Quando si imposta un metodo di pagamento per un cliente o un fornitore, specificare i formati di file e standard deve essere utilizzato per i pagamenti e il modo in cui i pagamenti verranno elaborati. È possibile selezionare uno dei seguenti tipi di formati:

-   Esportazione
-   Importazione
-   Restituita
-   Rimessa

### <a name="method-1-electronic-reporting-file-formats"></a>Metodo 1: Formati di file elettronici di report

Per i formati di file che si basano sulle configurazioni di ER, è necessario importare le configurazioni da Servizi (LCS) del ciclo di vita. Per ulteriori informazioni, vedere [configurazioni elettroniche di download da Servizi] del ciclo di vita (/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs). Una volta importate le configurazioni di reporting per i formati di file, inclusi i formati saranno disponibili per la selezione ** modalità di pagamento ** nella pagina. Il processo per importare e selezionare i formati di file per Europa è simile alla procedura per il Giappone. <!---For more details, see [Enable the JBA payment file format](https://ax.help.dynamics.com/en/wiki/enable-the-jba-payment-file-format/).-->

### <a name="method-2-x-file-formats"></a>Metodo 2: Formati di file X++

Per selezionare i formati di file basati sul codice X++, effettuare le operazioni seguenti.

1.  Passare ** modalità di pagamento ** nella pagina.
2.  ** Formati di file ** clic su, ** impostazione **.
3.  Selezionare la scheda corrispondente al tipo di formato di file.
4.  Selezionare un formato di file dall'** disponibile ** lo elencate e lo spostamento ** selezionato ** elenco con il controllo della freccia.
5.  Chiudere ** formati di file per i metodi di pagamento ** la pagina.
6.  ** Formati di file ** sulla scheda dettaglio, selezionare il formato di file da utilizzare per il metodo di pagamento nel campo formato di file appropriato. Le opzioni generali elettroniche di report deve essere impostato alcun ** ** per i formati di file X++.



