---
title: Utilizzare dati esterni nelle previsioni di cassa
description: In questo argomento vengono descritti i passaggi di configurazione che è necessario completare in modo che i dati esterni possano essere immessi o importati nelle previsioni di cassa.
author: rcarlson
ms.date: 07/16/2021
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
ms.openlocfilehash: 855f428ae8ce79f2b7ce9a6f3347cd454bad9566
ms.sourcegitcommit: 822aea26c5da259efe11ff3b3dc4cf1598425689
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2021
ms.locfileid: "7386464"
---
# <a name="use-external-data-in-cash-flow-forecasts"></a>Utilizzare dati esterni nelle previsioni di cassa

[!include [banner](../includes/banner.md)]

I dati esterni possono essere inseriti o importati nelle previsioni di cassa. In questo argomento vengono descritti i passaggi di configurazione specifici per l'utilizzo di dati esterni e che consentono di includere i dati esterni in una previsione di cassa.

## <a name="external-data-setup"></a>Configurazione dei dati esterni

Utilizza la scheda **Origine esterna** nella pagina **Configurazione della previsione di cassa** (**Cassa e gestione bancaria \> Previsione di cassa**) per inserire impostazioni che supportano l'uso di dati esterni nelle previsioni di cassa.

Per ulteriori informazioni sulla configurazione, vedi [Previsione di cassa](../cash-bank-management/cash-flow-forecasting.md).

Per immettere dati esterni per le previsioni di cassa, puoi utilizzare l'esperienza Apri in Excel per immettere e modificare dati esterni. Seleziona il pulsante **Dati esterni** e quindi seleziona **Aggiungi dati esterni** o **Modifica dati esterni esistenti**. Quando il file Microsoft Excel viene aperto, puoi inserire le informazioni nei seguenti campi:

- **ID immissione**
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
