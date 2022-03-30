---
title: Calcolo TDS sulle fatture
description: Questo argomento fornisce un riferimento per le transazioni in cui l'imposta dedotta all'origine (TDS) viene calcolata a livello di fattura.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 5a4c3e13eba76db2fae1f66560a2fea68d9a3c5f
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407949"
---
# <a name="tds-calculation-on-invoices"></a>Calcolo TDS sulle fatture

[!include [banner](../includes/banner.md)]

Questo argomento fornisce un riferimento per le transazioni in cui l'imposta dedotta all'origine (TDS) viene calcolata a livello di fattura.

| Numero di serie | Tipo di transazione                                 | Importo transazione | Nome pagina e percorso di selezione                                 | Tipo di conto e tipo di conto di contropartita                         |
| ------------- | ------------------------------------------------ | ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1.            | Acquisto effettuato da spese di registrazione/fornitore   | Dare o Avere  | Pagina Giornali di registrazione generali (Contabilità generale> Scritture contabili > Giornali di registrazione generali), Pagina Giornale di approvazione fatture (Contabilità fornitori > Fatture > Approvazione fattura), Pagina Giornale di registrazione fatture (Contabilità fornitori > Fatture > Giornale di registrazione fatture) | CoGe (Dare)  Fornitore (Avere)  La ritenuta d'acconto viene calcolata per la combinazione Fornitore-CoGe solo quando il conto CoGe ha il tipo di registrazione **Contanti**  **all'acquisto**. |
| 2.            | Acquisto effettuato da spese cliente/di registrazione | Dare o Avere  | Pagina Giornali di registrazione generali (Contabilità generale> Scritture contabili > Giornali di registrazione generali), Pagina Giornale di registrazione fatture (Contabilità fornitori > Fatture > Giornale di registrazione fatture) | CoGe (Dare)  Fornitore (Avere)                                 |
| 3.            | Acquisto di cespiti dal fornitore              | Dare o Avere  | Pagina Giornali di registrazione generali (Contabilità generale> Scritture contabili > Giornali di registrazione generali), Pagina Giornale di registrazione del registro fatture (Contabilità fornitori > Fatture > Registro fatture), Pagina Giornale di registrazione fatture (Contabilità fornitori > Fatture > Giornale di registrazione fatture) | Cespiti (Dare) Fornitore (Avere)                             |
| 4.            | Acquisto di cespiti dal cliente            | Dare o Avere  | Pagina Giornali di registrazione generali (Contabilità generale> Scritture contabili > Giornali di registrazione generali), Pagina Giornale di registrazione fatture (Contabilità fornitori > Fatture > Giornale di registrazione fatture) | Cespiti (Dare) Cliente (Avere)                           |
| 5            | Fattura di acquisto (TDS a debito)                  |                    | Pagina Ordine fornitore (Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore) |                                                              |
| 6            | Fattura di vendita (TDS a credito)                  |                    | Pagina Ordine cliente (Contabilità clienti> Ordini> Tutti gli ordini cliente), Pagina Fattura a testo libero (Contabilità clienti> Fatture> Tutte le fatture a testo libero) |                                                              |
