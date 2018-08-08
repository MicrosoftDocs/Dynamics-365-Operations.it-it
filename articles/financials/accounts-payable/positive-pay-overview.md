---
title: Informazioni generali sui pagamenti sicuri
description: Questo articolo fornisce informazioni sui pagamenti sicuri, che vengono utilizzati per generare un elenco elettronico di assegni da presentare a una banca.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 13a7a842e7b4522b508a34fdf86bb3bf58a0845f
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="positive-pay-overview"></a>Informazioni generali sui pagamenti sicuri

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sui pagamenti sicuri, che vengono utilizzati per generare un elenco elettronico di assegni da presentare a una banca. 

I pagamenti sicuri vengono utilizzati per generare un elenco elettronico di assegni da presentare a una banca. I file pagamenti sicuri possono agevolare le banche a impedire le frodi di assegni. È possibile impostare un pagamento sicuro per generare un elenco elettronico di assegni ogni volta che vengono stampati. Quando un assegno viene presentato alla banca, la banca lo confronta con l'elenco degli assegni inviati in precedenza. Se l'assegno corrisponde a uno presente nell'elenco, la banca lo liquida. Se l'assegno non corrisponde a un assegno nell'elenco, la banca lo trattiene per esaminarlo.

La retribuzione positiva anche è conosciuta come SafePay. 

I file pagamenti sicuri possono contenere dati riservati sui beneficiari e sugli importi dell'assegno. Di conseguenza, assicurarsi di utilizzare le misure di sicurezza appropriate dalla generazione dei file fino alla loro ricezione da parte della banca. I file pagamenti sicuri vengono scaricati in base alle istruzioni di download per il Web browser. 

Questi file vengono creati tramite entità di dati. Prima di generare un file pagamenti sicuri, è necessario impostare i formati di trasformazione per l'XML che converte i dati in un formato interpretabile dalla banca. 

Per ogni conto bancario per il quale generare informazioni pagamenti sicuri, è necessario assegnare il formato pagamenti sicuri. Dopo aver generato pagamenti, è possibile generare un file pagamenti sicuri per una singola persona giuridica e un singolo conto bancario. In alternativa, è possibile generare file pagamenti sicuri per più persone giuridiche e più conti bancari contemporaneamente. 

Dopo aver pagato gli assegni elencati in un file pagamenti sicuri, viene visualizzato un numero di conferma dalla banca. Sarà quindi possibile confermare il file pagamenti sicuri in Microsoft Dynamics 365 for Finance and Operations. 

Per modificare un file pagamenti sicuri, è possibile richiamarlo. Per ogni assegno nel file pagamenti sicuri, viene reimpostato il campo che indica se l'assegno è stato incluso in un file pagamenti sicuri.

Per ulteriori informazioni, vedere [Impostare e generare file di pagamenti sicuri](set-up-generate-positive-pay-files.md).




