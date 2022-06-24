---
title: Miglioramento dell'usabilità dei dati bancari
description: Questo articolo spiega come risparmiare tempo e semplificare la registrazione dei dati bancari per clienti e fornitori.
author: ilkond
ms.date: 11/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 6fb9ba103e40ebf9bc8071527169144ea9ac02c5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902350"
---
# <a name="bank-data-usability-enhancement"></a>Miglioramento dell'usabilità dei dati bancari

[!include [banner](../includes/banner.md)]

Le aziende spesso devono inserire e conservare una grande quantità di informazioni bancarie. Il costo dell'inserimento di informazioni bancarie errate può essere molto elevato. Per risparmiare tempo e semplificare la registrazione dei dati bancari, è possibile importare informazioni bancarie italiane da fonti affidabili. In questo modo, contribuisci a ridurre il rischio di errori quando vengono utilizzati i dati bancari per clienti e fornitori.

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, è necessario soddisfare i seguenti prerequisiti:

- L'indirizzo principale della persona giuridica deve essere in Italia.
- La funzionalità **Miglioramento della configurazione del conto bancario** deve essere attivata nell'area di lavoro **Gestione delle funzionalità**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="import-bank-groups"></a>Importare gruppi bancari

È possibile importare l'elenco delle banche utilizzando l'entità **Gruppi bancari** e il framework Gestione dati. Per ulteriori informazioni, vedere [Panoramica dei processi di importazione ed esportazione dei dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

I dati di origine utilizzati per importare i gruppi bancari possono essere presentati come un file di Microsoft Excel con i seguenti nomi di colonna:

- BANKGROUPID
- ADDRESSCITY
- ADDRESSCOUNTRY
- ADDRESSCOUNTY
- ADDRESSDESCRIPTION
- ADDRESSDISTRICTNAME
- ADDRESSLATITUDE
- ADDRESSLOCATIONID
- ADDRESSLONGITUDE
- ADDRESSSTATE
- ADDRESSSTREET
- ADDRESSTIMEZONE
- ADDRESSVALIDFROM
- ADDRESSVALIDTO
- ADDRESSZIPCODE
- NOME
- ROUTINGNUMBER
- ROUTINGNUMBERTYPE
- STATEMENTFORMATID
- SUFFIX
- BRANCHNAME\_IT

> [!NOTE]
> Il valore **BANKGROUPID** deve corrispondere al valore **ROUTINGNUMBER**.

## <a name="use-the-enhanced-list-of-bank-groups"></a>Utilizzare l'elenco avanzato dei gruppi bancari

Quando la funzione di miglioramento della configurazione del conto bancario è attivata, due campi descrittivi aggiuntivi, **Nome filiale** e **Città**, diventano disponibili per gruppi bancari.

![Campi Nome filiale e Città.](media/emea-ita-exil-bank-pic.jpg)

Durante la configurazione di un conto bancario, sono disponibili campi descrittivi aggiuntivi per i gruppi bancari che consentono una selezione più precisa di una banca.

![Campi descrittivi aggiuntivi in una configurazione del conto bancario.](media/emea-ita-exil-bank-pic2.jpg)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]