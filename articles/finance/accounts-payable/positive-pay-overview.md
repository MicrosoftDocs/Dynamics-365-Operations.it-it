---
title: Informazioni generali sui pagamenti sicuri
description: Questo articolo fornisce informazioni sui pagamenti sicuri, che vengono utilizzati per generare un elenco elettronico di assegni da presentare a una banca.
author: angelad116
ms.date: 10/24/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: thweeloc
ms.custom:
- "88463"
- intro-internal
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: f25dfaaa2e52b58c7b6971b4d277ef315de431a0
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715768"
---
# <a name="positive-pay-overview"></a>Informazioni generali sui pagamenti sicuri

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sui pagamenti sicuri, che vengono utilizzati per generare un elenco elettronico di assegni da presentare a una banca. 

I pagamenti sicuri vengono utilizzati per generare un elenco elettronico di assegni da presentare a una banca. I file pagamenti sicuri possono agevolare le banche a impedire le frodi di assegni. È possibile impostare un pagamento sicuro per generare un elenco elettronico di assegni ogni volta che vengono stampati. Quando un assegno viene presentato alla banca, la banca lo confronta con l'elenco degli assegni inviati in precedenza. Se l'assegno corrisponde a uno presente nell'elenco, la banca lo liquida. Se l'assegno non corrisponde a un assegno nell'elenco, la banca lo trattiene per esaminarlo.

La retribuzione positiva anche è conosciuta come SafePay. 

I file pagamenti sicuri possono contenere dati riservati sui beneficiari e sugli importi dell'assegno. Di conseguenza, assicurarsi di utilizzare le misure di sicurezza appropriate dalla generazione dei file fino alla loro ricezione da parte della banca. I file pagamenti sicuri vengono scaricati in base alle istruzioni di download per il Web browser. 

Questi file vengono creati tramite entità di dati. Prima di generare un file pagamenti sicuri, è necessario impostare i formati di trasformazione per l'XML che converte i dati in un formato interpretabile dalla banca. 

Per ogni conto bancario per il quale generare informazioni pagamenti sicuri, è necessario assegnare il formato pagamenti sicuri. Dopo aver generato pagamenti, è possibile generare un file pagamenti sicuri per una singola persona giuridica e un singolo conto bancario. In alternativa, è possibile generare file pagamenti sicuri per più persone giuridiche e più conti bancari contemporaneamente. 

Dopo aver pagato gli assegni elencati in un file pagamenti sicuri, viene visualizzato un numero di conferma dalla banca. Sarà quindi possibile confermare il file pagamenti sicuri nel sistema. 

Per modificare un file pagamenti sicuri, è possibile richiamarlo. Per ogni assegno nel file pagamenti sicuri, viene reimpostato il campo che indica se l'assegno è stato incluso in un file pagamenti sicuri.

Per ulteriori informazioni, vedere [Impostare e generare file di pagamenti sicuri](set-up-generate-positive-pay-files.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
