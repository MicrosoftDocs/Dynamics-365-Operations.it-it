---
title: Home page di contabilità fornitori
description: In questo argomento viene fornita una panoramica della contabilità fornitori.
author: ShylaThompson
manager: AnnBe
ms.date: 02/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom: 21901
ms.assetid: 1e4c2ac4-077b-4678-8733-5cec8f6ff659
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: a0195c6776b5065d98b6b1d4d9795248c6bf4c74
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972157"
---
# <a name="accounts-payable-home-page"></a>Home page di contabilità fornitori

[!include [banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica della contabilità fornitori. 

È possibile immettere manualmente le fatture fornitore o riceverle elettronicamente tramite un'entità di dati. Dopo che le fatture sono state immesse o ricevute, è possibile esaminarle e approvarle utilizzando un giornale di approvazione fatture o la pagina **Fattura fornitore**. È possibile utilizzare l'abbinamento fatture, i criteri di fattura fornitore e il flusso di lavoro per automatizzare il processo di revisione, in modo che le fatture che soddisfano determinati criteri vengano approvate automaticamente e le rimanenti fatture vengano contrassegnate per essere riviste da un utente autorizzato.

**Processi aziendali**

[![Diagramma di processi aziendali](./media/AP-process.PNG)](./media/AP-process.PNG)

## <a name="set-up-accounts-payable"></a>Impostare la contabilità fornitori

Impostare gruppi di fornitori, fornitori, profili di registrazione, varie opzioni di pagamento e parametri relativi a fornitori, spese, consegne, destinazioni, effetti passivi e altri tipi di informazioni sulla contabilità fornitori. 

[Configurare la panoramica contabilità fornitori](accounts-payable-overview.md)

[Distribuzioni contabili e scritture contabili nel giornale di registrazione secondario per le fatture fornitore](accounting-distributions-subledger-journal-entries-vendor-invoices.md) 

[Rivalutazione valuta estera per la contabilità fornitori e la contabilità clienti](../cash-bank-management/foreign-currency-revaluation-accounts-payable-accounts-receivable.md)

## <a name="configure-vendor-invoices"></a>Configurare le fatture fornitore

Utilizzare la contabilità fornitori per tenere traccia delle fatture e delle spese in uscita riguardanti i fornitori.

[Panoramica abbinamento fatture della contabilità fornitori](accounts-payable-invoice-matching.md)

[Profili registrazione fornitori](vendor-posting-profiles.md)

[Impostare la convalida dell'abbinamento fatture della contabilità fornitori](tasks/set-up-accounts-payable-invoice-matching-validation.md)

[Criteri di abbinamento a tre elementi di verifica](three-way-matching-policies.md)

[Abbinamento fatture e ordini fornitore interaziendali](invoice-matching-intercompany-purchase-orders.md)

[Panoramica della risoluzione delle discrepanze durante l'abbinamento dei totali fatture](resolve-invoice-totals-invoice-matching-discrepancies.md)

[Conti di contropartita predefiniti per i giornali di registrazione fatture fornitore e i giornali di registrazione approvazione fatture](default-offset-accounts-vendor-invoice-journals.md)

[Approvazioni fatture per dispositivi mobili](mobile-invoice-approvals.md)

[Area di lavoro fatturazione di collaborazione fornitore](vendor-portal-invoicing-workspace.md)

[Automazione fattura fornitore](vendor-invoice-automation.md)

## <a name="configure-vendor-payments"></a>Configurare i pagamenti fornitore 

Assegnare un tipo di pagamento definito dal sistema, ad esempio assegno, pagamento elettrico o effetto passivo, a un metodo di pagamento definito dall'utente. I tipi di pagamento sono facoltativi, ma sono utili per convalidare i pagamenti elettronici e se si desidera determinare rapidamente il pagamento da utilizzare. 

[Area di lavoro pagamenti fornitore](vendor-payments-workspace.md)

[Definire commissioni pagamento fornitore](tasks/define-vendor-payment-fees.md)

[Definire termini di pagamento fornitore](tasks/define-vendor-payment-terms.md)

[Panoramica dei pagamenti sicuri](positive-pay-overview.md)

[Impostare e generare file pagamenti sicuri](set-up-generate-positive-pay-files.md)

[Creare pagamenti fornitore utilizzando una proposta di pagamento](create-vendor-payments-payment-proposal.md)

[Pagamenti fornitore per un importo parziale](vendor-payments-partial-amount.md)

[Applicare uno sconto maggiore dello sconto calcolato per un pagamento fornitore](take-discount-more-calculated-discount-vendor-payment.md)

[Applicare uno sconto di cassa fuori dal periodo di sconto di cassa](take-cash-discount-outside-cash-discount-timeframe.md)

[Creazione di report elettronici per assegni fornitore di esempio](electronic-reporting-sample-vendor-checks.md)

[Stornare un pagamento fornitore](reverse-vendor-payment.md)

[Fatture di pagamento anticipato e pagamenti anticipati a confronto](prepayments-invoices-vs-prepayments.md)

[Pagamenti centralizzati per la contabilità fornitori](centralized-payments-accounts-payable.md)

## <a name="settlements"></a>Liquidazioni

Negli argomenti riportati di seguito vengono fornite informazioni sulle liquidazioni. La liquidazione è il processo di facilitazione dei pagamenti con fatture. 

[Configurare la liquidazione](../cash-bank-management/configure-settlement.md)

[Liquidare un pagamento fornitore parziale prima della data dello sconto con un pagamento finale dopo la data dello sconto](settle-partial-vendor-payment-before-discount-or-final-payment-after.md)

[Liquidare un pagamento fornitore parziale con sconti sulle note di accredito fornitore](settle-partial-vendor-payment-discounts-vendor-credit-notes.md)

[Liquidare un pagamento fornitore parziale con più periodi di sconto](settle-partial-vendor-payment-multiple-discount-periods.md)

[Liquidare un pagamento fornitore parziale e liquidare completamente il pagamento finale prima della data dello sconto](settle-partial-vendor-payment-or-final-payment-before-discount.md)

[Giustificativo singolo con più record cliente o fornitore](single-voucher-multiple-customer-vendor-records.md)



### <a name="additional-resources"></a>Risorse aggiuntive

#### <a name="whats-new-and-in-development"></a>Novità rilasciate e in via di sviluppo

Passare ai [piani di rilascio di Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2010158) per visualizzare le nuove funzionalità pianificate. 

#### <a name="blogs"></a>Blog

Per opinioni, notizie e altre informazioni sulla contabilità fornitori e su altre soluzioni, fare riferimento al [blog di Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) e al [blog di Dynamics 365 Finance - Financials](https://community.dynamics.com/365/financeandoperations/b/financials).

Il [blog della community di partner di Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) offre ai partner Microsoft Dynamics una singola risorsa per conoscere le novità e le tendenze di Dynamics 365.

#### <a name="community-blogs"></a>Blog della community

[Come gestire la contabilità fornitori in Dynamics 365 Finance](https://financefunction.tech/2019/02/15/how-to-manage-payables-in-dynamics-365-for-finance-and-operations)

#### <a name="task-guides"></a>Guide attività
Informazioni aggiuntive sono disponibili come guide attività nell'applicazione. Per accedere alle guide attività, fare clic sul pulsante ? su qualsiasi pagina.

#### <a name="videos"></a>Video

Vedere i video dimostrativi disponibili nel [canale di Microsoft Dynamics 365 su YouTube](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).






[!INCLUDE[footer-include](../../includes/footer-banner.md)]