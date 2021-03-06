---
title: Localizzazione italiana - Tracciabilità dei pagamenti
description: Questo argomento spiega come controllare l'identificazione della procedura di gara e i codici CIPE durante l'elaborazione end-to-end dalla fattura originale al pagamento.
author: neserovleo
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: v-lenest
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 820753a7b1c6896d77729f31a443dbdc660a7115
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894726"
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