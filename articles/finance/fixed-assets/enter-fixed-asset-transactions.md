---
title: Opzioni di transazione cespiti
description: Questo articolo descrive i metodi diversi disponibili per creare le transazioni cespiti.
author: moaamer
ms.date: 08/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: roschlom
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 129f88037691096c22478e4f186667a502e394ec
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2021
ms.locfileid: "7674476"
---
# <a name="fixed-asset-transaction-options"></a>Opzioni di transazione cespiti

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

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

### <a name="options-for-entering-fixed-asset-transaction-types"></a>Opzioni per l'immissione di tipi di transazioni cespiti


| Tipo di transazione                    | Modulo                   | Opzioni                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| Acquisizione, Rettifica acquisizione | Cespiti             | Cespiti, Scorte a cespiti   |
|                                     | Contabilità generale           | Giornale di registrazione generale                           |
|                                     | Contabilità fornitori         | Giornale di registrazione fatture, Giornale di approvazione fatture |
|                                     | Approvvigionamento | Ordine acquisto                            |
| Ammortamento                        | Cespiti             | Cespiti                              |
|                                     | Contabilità generale           | Giornale di registrazione generale                           |
| Gestione dismissione                            | Cespiti             | Cespiti                              |
|                                     | Contabilità generale           | Giornale di registrazione generale                           |
|                                     | Contabilità clienti      | Fattura a testo libero                         |

Il valore residuo non viene aggiornato per i periodi di ammortamento di un cespite quando una riga del giornale di registrazione dei tipi di transazioni di ammortamento viene creata manualmente o importata mediante un'entità di dati. Il valore residuo viene aggiornato quando il processo della proposta di ammortamento viene utilizzato per creare la riga del giornale di registrazione.

Per ulteriori informazioni, vedere [Integrazione dei cespiti](fixed-asset-integration.md).

Il sistema impedisce di registrare l'ammortamento due volte nello stesso periodo. Ad esempio, se due utenti creano separatamente proposte di ammortamento per gennaio, l'ammortamento del primo utente verrà registrato nel primo giornale di registrazione. Quando il secondo utente registra l'ammortamento nel secondo giornale di registrazione, il sistema controlla la data dell'ultima esecuzione dell'ammortamento e non registrerà una seconda volta l'ammortamento per lo stesso periodo.

### <a name="transactions-that-require-a-different-voucher-number"></a>Transazioni che richiedono un numero di giustificativo diverso

Le seguenti transazioni cespiti utilizzeranno numeri di giustificativo diversi:

- Viene effettuata un'acquisizione aggiuntiva su un cespite e viene calcolata la rideterminazione dell'ammortamento.
- Un cespite viene diviso.
- Viene abilitato un parametro per calcolare l'ammortamento su dismissione e quindi viene dismesso il cespite.
- Una data di messa in servizio di un cespite è precedente alla data di acquisizione. Di conseguenza, una rettifica dell'ammortamento viene registrata.

> [!NOTE]
> Quando immetti le transazioni, assicurati che tutte le transazioni si applichino allo stesso cespite. Il giustificativo non viene pubblicato se include più di un cespite, anche se il campo **Nuovo giustificativo** è impostato su **Un solo numero di giustificativo** nella pagina **Nomi giornale di registrazione** nella contabilità generale. Se includi più di un cespite nel giustificativo, verrà visualizzato il messaggio "Può essere presente una sola transazione cespiti per giustificativo" e non sarà possibile registrare il giustificativo.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
