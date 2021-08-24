---
title: Il record TaxTrans non viene generato
description: Questo argomento fornisce informazioni sulla risoluzione dei problemi che possono essere utili quando un record TaxTrans non viene generato.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 82b00387e39b88e1ab2bc27d9dbc4e36aac3a7a605c04669171997ba236ae39a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751304"
---
# <a name="taxtrans-record-isnt-generated"></a>Il record TaxTrans non viene generato

[!include [banner](../includes/banner.md)]

Se selezioni **IVA registrata** per una transazione, ma la pagina **IVA registrata** non mostra alcuna riga di imposta o manca di una riga di imposta, il record **TaxTrans** potrebbe non essere stato generato.

[![Pagina IVA registrata senza voci.](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)

Per risolvere questo problema, seguire i passaggi nelle sezioni seguenti come richiesto.

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a>Controllare l'IVA prima di registrare la transazione

1. Prima di registrare la transazione, nella pagina **Registrazione fattura**, selezionare **IVA** per controllare il calcolo.

    [![Pulsante IVA nella pagina Registrazione fattura.](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)

2. Nella pagina **Transazioni IVA provvisorie** rivedere il risultato del calcolo. Se non viene calcolata alcuna imposta, vedere [L'imposta non viene calcolata o l'importo dell'imposta è zero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a>Trovare il record TaxTrans in tutta l'IVA registrata

1. Passare a **Imposta** \> **Richieste di informazioni e report** \> **Richieste di informazioni su IVA** > **IVA registrata**.
2. Nell'intestazione di colonna **Giustificativo** selezionare il simbolo del filtro per trovare il record **TaxTrans**.
3. Se trovi i record IVA che stai cercando, controlla la data. Se la data è diversa dalla data dell'intestazione del giornale di registrazione, crea una richiesta di assistenza Microsoft per ulteriore supporto.

    [![Pagina IVA registrata.](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)

## <a name="debug-to-check-details"></a>Eseguire il debug per verificare i dettagli

1. Per informazioni su come eseguire il debug e determinare se **TmpTaxWorkTrans** e **TaxUncommitted** sono generati correttamente, vedere [Valore di campo errato in TaxTrans](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).
2. Se **TaxTmpWorkTrans** o **TaxUncommitted** viene generato correttamente, aggiungi un punto di interruzione in corrispondenza di **TaxPost::SaveAndPost()** e **Tax::SaveAndPost** per eseguire il debug del motivo per cui **TaxTrans** non è inserito.

    [![Punti di interruzione aggiunti nel codice.](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)

    [![Risultati dei punti di interruzione aggiunti.](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)

## <a name="determine-whether-customization-exists"></a>Determinare se esiste la personalizzazione

Se hai completato i passaggi nelle sezioni precedenti ma non hai riscontrato alcun problema, determina se esiste la personalizzazione. Se non esiste alcuna personalizzazione, creare una richiesta di assistenza Microsoft per ulteriore supporto.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
