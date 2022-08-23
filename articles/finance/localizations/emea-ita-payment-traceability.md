---
title: Localizzazione italiana - Tracciabilità dei pagamenti
description: Questo articolo spiega come controllare l'identificazione della procedura di gara e i codici CIPE durante l'elaborazione end-to-end dalla fattura originale al pagamento.
author: AdamTrukawka
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: atrukawk
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.17
ms.search.form: ''
ms.openlocfilehash: 446a8fc944cc4def701d1553d3bd32954fe52801
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274593"
---
# <a name="italian-localization---payment-traceability"></a>Localizzazione italiana - Tracciabilità dei pagamenti

[!include [banner](../includes/banner.md)]


Per le aziende italiane che lavorano con aziende del settore pubblico, potrebbero essere presenti dei requisiti per controllare l'identificazione della procedura di gara e i codici CIPE durante l'elaborazione end-to-end dalla fattura originale al pagamento. Questo controllo richiesto può essere nei moduli Contabilità clienti e Contabilità fornitori.

## <a name="prerequisites"></a>Prerequisiti

Per poter utilizzare la funzionalità di tracciabilità dei pagamenti, è necessario soddisfare i seguenti prerequisiti:

- L'indirizzo principale della persona giuridica deve essere in Italia.
- La funzione **(Italia) Miglioramenti al tracciamento del documento di base** deve essere attivata nell'area di lavoro **Gestione funzionalità**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="feature-details"></a>Dettagli delle funzionalità

Con la funzionalità attivata, i codici CIG (Tender Procedure Identification) e CIPE (CUP) vengono ereditati in relazione alla particolare transazione del cliente o del fornitore. Questa eredità consente una maggiore tracciabilità in tutto il sistema e può essere rivista utilizzando il meccanismo di personalizzazione standard. Per ereditare i valori dalla transazione fattura originale durante la proposta di pagamento, nella pagina **Metodi di pagamento** attiva l'attributo **Pagamento documento di base**. Per garantire che i campi obbligatori corrispondano ai codici CIG e CUP siano popolati nella transazione, contrassegna il conto cliente, il conto fornitore o il gruppo come con il parametro del settore pubblico.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
