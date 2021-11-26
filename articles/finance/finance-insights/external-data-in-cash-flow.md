---
title: Utilizzare dati esterni nelle previsioni di cassa
description: In questo argomento vengono descritti i passaggi di configurazione che è necessario completare in modo che i dati esterni possano essere immessi o importati nelle previsioni di cassa.
author: rcarlson
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: dbfa04228cf63c0874a7d69af4e2b932544c0d7f
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753004"
---
# <a name="use-external-data-in-cash-flow-forecasts"></a>Utilizzare dati esterni nelle previsioni di cassa

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I dati esterni possono essere inseriti o importati nelle previsioni di cassa. In questo argomento vengono descritti i passaggi di configurazione specifici per l'utilizzo di dati esterni e che consentono di includere i dati esterni in una previsione di cassa.

## <a name="external-data-setup"></a>Configurazione dei dati esterni

Utilizza la scheda **Origine esterna** nella pagina **Configurazione della previsione di cassa** (**Cassa e gestione bancaria \> Previsione di cassa \> Impostazione di previsione di cassa**) per inserire impostazioni che supportano l'uso di dati esterni nelle previsioni di cassa.

I dati esterni possono essere inseriti o importati nelle previsioni di cassa. Prima di immettere o importare dati esterni, è necessario configurare le origini esterne. Nella scheda **Origine esterna**, confgura le categorie di flussi di cassa esterne. Una categoria può essere **In uscita** o **In entrata**. **Liquidità** deve essere selezionato come tipo di registrazione. Nella griglia **Impostazioni persona giuridica**, seleziona le persone giuridiche e i corrispondenti conti principali a cui si applicano le categorie di flussi di cassa esterni.

Per ulteriori informazioni su come impostare Previsione di cassa, vedere [Previsione di cassa](../cash-bank-management/cash-flow-forecasting.md).

## <a name="enter-external-data"></a>Immettere dati esterni

Per immettere e modificare dati esterni per le previsioni di cassa, puoi utilizzare l'esperienza **Apri in Excel**. Seleziona il pulsante **Dati esterni** nella pagina **Impostazione di previsione di cassa** e quindi seleziona **Aggiungi dati esterni** o **Modifica dati esterni esistenti**. Quando il file Microsoft Excel viene aperto, puoi inserire le informazioni nei seguenti campi:

- **ID immissione** (univoco)
- **Descrizione** (facoltativa)
- **Nome origine esterna**: seleziona uno dei valori nell'elenco che hai definito durante la configurazione di Finance Insights.
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

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
