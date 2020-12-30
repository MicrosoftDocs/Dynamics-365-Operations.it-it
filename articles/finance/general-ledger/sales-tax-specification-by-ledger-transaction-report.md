---
title: Specifica IVA per report transazione contabile
description: In questo argomento viene spiegato come utilizzare il report Specifica IVA per transazione contabile per visualizzare e stampare informazioni sulle transazioni contabili per le quali viene calcolata l'IVA.
author: ericwang
manager: Ann Beebe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 438a640124e778b839c660f5e161efa22c319af0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444635"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a>Specifica IVA per report transazione contabile
[!include [banner](../includes/banner.md)]

In questo argomento viene spiegato come utilizzare il report **Specifica IVA per transazione contabile** per visualizzare e stampare informazioni sulle transazioni contabili per le quali viene calcolata l'IVA.

## <a name="tax-accounts-vs-non-tax-accounts"></a>Conti fiscali e conti non fiscali

Nel report **Specifica IVA per transazione contabile** sono presenti le transazioni IVA per i conti fiscali e conti non fiscali. Questi conti vengono classificati nel seguente modo:

- **Conto fiscale** - Un conto viene considerato conto fiscale quando viene registrata una transazione IVA e il conto principale nella riga giornale di registrazione **IVA** è un conto fiscale, ad esempio un conto IVA a debito o un conto IVA a credito.
- **Conto non fiscale** - Un conto viene considerato conto non fiscale quando viene registrata una transazione IVA e il conto principale nella transazione originale è un conto non fiscale, ad esempio un conto ricavi o un conto spese.

Per i conti IVA, le colonne **Origine**, **IVA a credito** e **IVA a debito** del report mostrano **0** (zero). Per i conti non fiscali, in queste colonne sono riportati gli importi.

## <a name="filtering-the-data-on-the-report"></a>Filtrare i dati nel report

Quando si genera il report, sono disponibili i seguenti campi predefiniti. È possibile utilizzare questi campi per filtrare i dati visualizzati nel report.

| Campo                      | Descrizione |
|----------------------------|-------------|
| Data                       | Utilizzare i campi nelle sezioni **A** e **Da** per definire un intervallo di date per le transazioni IVA. |
| Conto principale               | Utilizzare i campi nelle sezioni **A** e **Da** per definire un intervallo di conti principali. |
| Codice IVA             | Utilizzare i campi nelle sezioni **A** e **Da** per definire un intervallo di codici IVA. |
| Raggruppamento                   | Specificare se il report deve essere raggruppato per conto CoGe o codice IVA. |
| Subtotale per codice IVA | Impostare questa opzione su **Sì** per visualizzare i subtotali per codice IVA. |
| Solo totali                | Impostare questa opzione su **Sì** per visualizzare solo i totali. |
| Solo conti principali         | Impostare questa opzione su **Sì** per includere nel report solo i conti principali. |

## <a name="showing-only-non-tax-accounts-on-the-report"></a>Mostrare nel report solo i conti non fiscali

Per visualizzare solo i conti non fiscali nel report, impostare una condizione di filtro, ad esempio un asterisco (\*), come illustrato nella figura seguente.

![Report con i conti non fiscali](media/taxspecperledgertrans.png)
