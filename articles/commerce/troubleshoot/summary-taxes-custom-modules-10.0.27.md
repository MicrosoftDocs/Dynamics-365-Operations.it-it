---
title: Il totale parziale del riepilogo ordine non include le imposte sugli addebiti quando si utilizzano moduli di riepilogo ordine personalizzati
description: Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando si utilizzano moduli di riepilogo dell'ordine personalizzati e il totale parziale del riepilogo dell'ordine non include le imposte sugli addebiti nello scenario "prezzo IVA inclusa".
author: gvrmohanreddy
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-04-22
ms.openlocfilehash: 260dcb6bc1585615195e32adfcd1da6bfbca294e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848839"
---
# <a name="order-summary-subtotal-doesnt-include-taxes-on-charges-when-using-customized-order-summary-modules"></a>Il totale parziale del riepilogo ordine non include le imposte sugli addebiti quando si utilizzano moduli di riepilogo ordine personalizzati

Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando si utilizzano moduli di riepilogo dell'ordine personalizzati e il totale parziale del riepilogo dell'ordine non include le imposte sugli addebiti nello scenario "prezzo IVA inclusa".

## <a name="description"></a>Description

A partire da Microsoft Dynamics 365 Commerce versione 10.0.27, sono state apportate le seguenti modifiche allo scenario "prezzo IVA inclusa" per fornire un'esperienza coerente nei moduli di riepilogo degli ordini nelle pagine dei siti di e-commerce.

- Sono stati aggiunti due nuovi campi: **TaxOnShippingCharge** e **TaxOnNonShippingCharges**.
- Le API **GetSalesOrderBySalesId** e **GetSalesOrderByTransactionId** hanno valori accurati per i seguenti campi nello scenario "prezzo IVA inclusa":

    - SubtotalSalesAmount
    - SubtotalAmountWithoutTax
    - SubtotalAmount
    - ShippingChargeAmount
    - OtherChargeAmount

Tuttavia, se utilizzi moduli di riepilogo degli ordini personalizzati, queste modifiche potrebbero influire sui valori dei totali parziali del riepilogo degli ordini escludendo le imposte sugli addebiti.

## <a name="resolution"></a>Risoluzione

Se stai utilizzando moduli di riepilogo dell'ordine personalizzati e non desideri ereditare le modifiche apportate allo scenario "prezzo IVA inclusa" in Commerce versione 10.0.27 e successive, segui le istruzioni in questa sezione.

Ritornando al comportamento di riepilogo dell'ordine precedente (prima della versione 10.0.27) dei campi **salesTransaction.SubtotalAmount** e **salesTransaction.SubtotalAmountWithoutTax**, si ripristina l'inclusione dell'importo totale dell'imposta di addebito (**TaxOnShippingCharge** e **TaxOnNonShippingCharges**) negli importi subtotali (**SubtotalAmount** e **SubtotalAmountWithoutTax**).

Per ripristinare il comportamento di riepilogo dell'ordine precedente, attieniti alla seguente procedura.

1. In Commerce headquarters, apri la pagina dei parametri di commercio (**Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Parametri \> Parametri di commercio**).
1. Nel riquadro di spostamento a sinistra, seleziona **Parametri di configurazione**.
1. Aggiungi i seguenti parametri di configurazione e imposta il valore di ciascuno su **vero**:

    - IsLegacyTaxOnChargeInSubtotalAmountIncludedInTaxIncusiveEnabled
    - IsLegacyOrderSummaryHydrationEnabled

> [!NOTE]
> Se hai già utilizzato il parametro di configurazione **IsUpdatedPriceIncludesTaxSubtotalCalculationEnabled** e vuoi mantenere lo stesso comportamento per la proprietà **order.NetAmountWithoutTax**, dovresti anche aggiungere il parametro di configurazione **IsLegacyPriceIncludesTaxNetAmountWithoutTaxCalculationEnabled** e impostarne il valore su **vero**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Nascondere i dettagli imposte nei riepiloghi degli ordini](../hide-taxes-breakup.md)
