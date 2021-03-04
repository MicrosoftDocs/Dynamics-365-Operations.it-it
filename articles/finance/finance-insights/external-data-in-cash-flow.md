---
title: Utilizzare dati esterni nelle previsioni di cassa (anteprima)
description: In questo argomento vengono descritti i passaggi di configurazione che è necessario completare in modo che i dati esterni possano essere immessi o importati nelle previsioni di cassa.
author: rcarlson
manager: AnnBe
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 801327dc54f6d4cfef7a9f062395e29846783e8f
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644947"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a>Utilizzare dati esterni nelle previsioni di cassa (anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I dati esterni possono essere inseriti o importati nelle previsioni di cassa. In questo argomento vengono descritti i passaggi di configurazione specifici per l'utilizzo di dati esterni e che consentono di includere i dati esterni in una previsione di cassa.

## <a name="external-data-setup"></a>Configurazione dei dati esterni

Utilizza la scheda **Origine esterna** nella pagina **Configurazione della previsione di cassa** (**Cassa e gestione bancaria \> Previsione di cassa**) per inserire impostazioni che supportano l'uso di dati esterni nelle previsioni di cassa.

Per ulteriori informazioni sulla configurazione, vedi [Previsione di cassa](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).

Per immettere dati esterni per le previsioni di cassa, puoi utilizzare l'esperienza Apri in Excel per immettere e modificare dati esterni. Seleziona il pulsante **Dati esterni** e quindi seleziona **Aggiungi dati esterni** o **Modifica dati esterni esistenti**. Quando il file Microsoft Excel viene aperto, puoi inserire le informazioni nei seguenti campi:

- **ID immissione**
- **Descrizione** (facoltativa)
- **Nome origine esterna**: seleziona uno dei valori nell'elenco che hai definito durante la configurazione di Informazioni finanziarie dettagliate.
- **Persona giuridica**
- **Data**
- **Importo nella valuta della transazione**
- **Codice valuta**
- **Dimensione predefinita** (facoltativa)
- **Numero documento** (facoltativa)
- **Numero conto** (facoltativa)
- **Nome conto** (facoltativa)

## <a name="importing-external-data-by-using-the-data-management-framework"></a>Importazione di dati esterni utilizzando il framework Gestione dati

Puoi importare dati esterni per previsioni di cassa utilizzando l'area di lavoro **Gestione dati** e l'entità denominata **Inserimento origine esterna previsione di cassa**.

Inoltre, se è necessario spostare i dati di configurazione da un ambiente a un altro, la seguente area delle entità è disponibile per le tabelle di configurazione richieste:

- Impostazione origine esterna per previsione di cassa
- Impostazione persona giuridica origine esterna per previsione di cassa

#### <a name="privacy-notice"></a>Informativa sulla privacy
Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]