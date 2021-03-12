---
title: Opzioni di transazione cespiti
description: Questo articolo descrive i metodi diversi disponibili per creare le transazioni cespiti.
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: roschlom
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 494087bc7a1247999d3f63dcdc0a0f403dcfdb2d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978691"
---
# <a name="fixed-asset-transaction-options"></a>Opzioni di transazione cespiti

[!include [banner](../includes/banner.md)]

Questo articolo descrive i metodi diversi disponibili per creare le transazioni cespiti.

È possibile impostare i cespiti in modo da integrarli con la contabilità fornitori, la contabilità clienti, l'approvvigionamento e la contabilità generale. È inoltre possibile trasferire gli articoli in Gestione articoli ai cespiti se si desidera utilizzare gli articoli internamente.

## <a name="accounts-payable"></a>Contabilità fornitori
È possibile immettere le transazioni cespiti nella pagina Giustificativo giornale di registrazione. È possibile aprire questa pagina dalla pagina Giornale di registrazione fatture. È inoltre possibile aprire la pagina Giornale di registrazione fatture dalla pagina Giornale di approvazione fatture. Nel campo Tipo di conto di contropartita selezionare Cespiti. Quindi, nel campo Conto di contropartita selezionare un numero cespiti. Nella scheda Cespiti immettere i valori nei campi Tipo di transazione e Libro.

## <a name="accounts-receivable"></a>Contabilità clienti
È possibile immettere le transazioni cespiti nella pagina Fattura a testo libero.  Nella pagina Fattura a testo libero, nella griglia Righe fattura, selezionare una voce. Fare clic sulla scheda dettaglio Dettagli riga. Immettere il numero cespite e il libro per la transazione di dismissione. Nelle fatture a testo libero il tipo di transazione cespiti è sempre Vendita di dismissione.

## <a name="procurement-and-sourcing"></a>Approvvigionamento
È possibile immettere le transazioni cespiti nella pagina Ordine acquisto. Immettere le informazioni necessarie per creare un ordine fornitore, quindi fare clic su OK. Nella pagina Ordine fornitore, fare clic sulla Scheda dettaglio Dettagli riga. Quindi, nella scheda Cespiti, immettere le informazioni sui cespiti. 

Per registrare una transazione di acquisizione di un cespite esistente, specificare il numero cespite, il libro e il tipo di transazione. Il cespite non può essere registrato se una di queste informazioni manca. Per registrare una transazione di acquisizione per un nuovo cespite, selezionare l'opzione Nuovo cespite?, quindi selezionare il gruppo di cespiti a cui assegnare il nuovo cespite. Se tuttavia l'articolo appartiene a un gruppo di modelli inventariali in cui viene utilizzato un modello inventariale Costo standard, non sarà disponibile alcun campo relativo a cespiti per una riga. Inoltre, le opzioni definite nella pagina Parametri cespiti determinano se è possibile registrare transazioni di acquisizione dai moduli di acquisto. 

L'utilizzo del giornale di registrazione Ordine fornitore o Scorte a cespiti per l'acquisizione dei cespiti influisce sul valore di magazzino..

## <a name="general-ledger"></a>Contabilità generale
Nella pagina Giornale di registrazione generale può essere registrato qualsiasi tipo di transazione cespiti. È inoltre possibile utilizzare i giornali di registrazione in Cespiti per registrare le transazioni cespiti.

## <a name="options-for-entering-fixed-asset-transaction-types"></a>Opzioni per l'immissione di tipi di transazioni cespiti


| Tipo di transazione                    | Modulo                   | Opzioni                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| Acquisizione, Rettifica acquisizione | Cespiti             | Cespiti, Scorte a cespiti   |
|                                     | Contabilità generale           | Giornale di registrazione generale                           |
|                                     | Contabilità fornitori         | Giornale di registrazione fatture, Giornale di approvazione fatture |
|                                     | Approvvigionamento | Ordine acquisto                            |
| Ammortamento                        | Cespiti             | Cespiti                              |
|                                     | Contabilità generale           | Giornale di registrazione generale                           |
| Gestione dismissione                            | Cespiti             | Cespiti                              |
| ** **                               | Contabilità generale           | Giornale di registrazione generale                           |
| ** **                               | Contabilità clienti      | Fattura a testo libero                         |


Il valore residuo dei periodi di ammortamento del cespite non viene aggiornato quando una riga del giornale dei tipi di transazioni di ammortamento viene creata manualmente o importata mediante un'entità di dati. Questo valore viene aggiornato quando il processo della proposta di ammortamento viene utilizzato per creare la riga del giornale.

Per ulteriori informazioni, vedere [Integrazione dei cespiti](fixed-asset-integration.md).
