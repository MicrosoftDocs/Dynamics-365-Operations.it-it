---
title: Liquidazione provvigione su pagamento
description: Questo argomento fornisce informazioni sulla liquidazione delle provvigioni sui pagamenti.
author: ilkond
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 185de8cde62deecc328d893e6e2903de3a72d8d8
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6348454"
---
# <a name="commission-settlement-on-payments"></a>Liquidazione provvigione su pagamento

[!include [banner](../includes/banner.md)]

In Italia, le società in genere non liquidano le provvigioni agli agenti di vendita quando vengono emesse le fatture. Liquidano le provvigioni quando i clienti pagano l'intero saldo delle fatture.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter utilizzare la funzionalità per la liquidazione delle provvigioni su pagamenti, devono essere soddisfatti i seguenti prerequisiti:

- L'indirizzo principale della persona giuridica deve essere in Italia.
- La funzionalità **Liquidazione delle provvigioni sui pagamenti** deve essere attivata nell'area di lavoro **Gestione delle funzionalità**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="a-namedefault-commission-settlement-periodset-up-the-default-commission-settlement-method"></a><a name="default-commission-settlement-period">Impostare il metodo di liquidazione delle provvigioni predefinito

1. Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**.
2. Nella pagina **Parametri contabilità clienti**, nella scheda **Liquidazione** nella scheda dettaglio **Altro**, nel campo **Liquidazione delle provvigioni**, selezionare il metodo di liquidazione delle provvigioni predefinito che viene utilizzato quando viene creato un ordine cliente:

    - **Su fattura** - Le provvigioni vengono addebitate durante il processo di fatturazione.
    - **Su pagamento** - Le provvigioni vengono addebitate durante il processo di pagamento.

![Parametri contabilità clienti.](media/emea-ita-exil-commission-setup-parameters.PNG)

## <a name="set-up-commission-calculations"></a>Impostare i calcoli della provvigione

È possibile impostare il calcolo delle provvigioni per una provvigione **Su pagamento** andando a **Vendite e marketing** \> **Provvigioni** \> **Calcolo provvigione**.

![Impostare il calcolo della provvigione.](media/emea-ita-exil-commission-%20calculation-setup.PNG)

Se l'opzione **Soglie di pagamento** nella sezione **Provvigioni su pagamento** è impostata su **Sì**, è possibile specificare due limiti (soglie) per i calcoli delle provvigioni:

- Se l'importo della provvigione raggiunto (in percentuale dell'importo raggiungibile) è più basso del limite inferiore, non vengono accumulate commissioni.
- Quando viene raggiunto il limite superiore, viene accumulato l'intero importo raggiungibile.

Tra i due limiti, le provvigioni vengono accumulate in modo regolare.

### <a name="example"></a>Esempio

Considerare l'esempio riportato di seguito.

- **Importo totale della fattura:** € 1.000
- **Limite inferiore:** 10 %
- **Limite superiore:** 80 %

Vengono effettuati i seguenti pagamenti:

- € 50 (5 % dell'importo totale della fattura): poiché le provvigioni sono inferiori al limite inferiore del 10 %, non si verifica alcun accumulo.
- € 100 (10 % dell'importo totale della fattura): la fattura viene liquidata al 15 %. Pertanto, le provvigioni maturano a questa percentuale.
- € 500 (50 % dell'importo totale della fattura): la fattura viene liquidata al 65 %. Le provvigioni maturano anche al 65 %.
- € 200 (20 % dell'importo totale della fattura): la fattura viene liquidata al 85 %. Poiché questa cifra supera il limite superiore, le provvigioni vengono completamente liquidate al 100 %.
- Ulteriori pagamenti non modificano l'importo maturato, poiché tale importo ha già raggiunto il limite superiore. Tuttavia, le transazioni di attribuzione per competenza vengono comunque create.

È possibile aggiungere un'altra impostazione al singolo agente che appartiene a un gruppo specifico. Nei calcoli delle provvigioni, l'impostazione sugli agenti (dipendenti) ha una priorità più alta rispetto all'impostazione sulle vendite.

## <a name="set-the-commission-settlement-and-preview-commission-transactions-on-the-sales-order-page"></a>Impostare la liquidazione delle provvigioni e visualizzare in anteprima le transazioni delle provvigioni nella pagina Ordine cliente

Dopo aver creato un ordine cliente, un utente può aggiornare la liquidazione della provvigione nell'intestazione dell'ordine cliente.

1. Andare a **Contabilità clienti** \> **Ordini** \> **Tutti gli ordini cliente**.
2. Selezionare e aprire un ordine cliente.
3. Nella pagina **Dettagli ordine cliente**, nella visualizzazione **Intestazione**, nella scheda dettaglio **Impostazione** aggiornare il valore del campo **Liquidazione delle provvigioni** come richiesto.

![Liquidazione delle provvigioni sull'ordine cliente.](media/emea-ita-exil-commission-sales-order.png)

Per impostazione predefinita, il valore del campo **delle provvigioni** è ereditato dalla pagina **Parametri contabilità clienti**. Per ulteriori informazioni, vedere [Impostare il metodo di liquidazione delle provvigioni predefinito](#default-commission-settlement-period).

È inoltre possibile visualizzare in anteprima il calcolo della provvigione di vendita da un ordine cliente per ordini aperti o fatturati. Nella pagina **Dettagli ordine cliente**, nella scheda **Generale**, selezionare **Informazioni correlate** \> **Anteprima provvigione**.

![Anteprima delle transazioni delle provvigioni.](media/emea-ita-exil-commission-preview.PNG)

> [!NOTE]
> Un utente può combinare gli ordini cliente in un'unica fattura se tutti gli ordini cliente per la fatturazione hanno lo stesso valore di **Liquidazione delle provvigioni** nell'intestazione dell'ordine cliente.

### <a name="get-an-overview-of-commission-transactions-on-a-sales-order-invoice"></a>Ottenere una panoramica delle transazioni delle provvigioni su una fattura dell'ordine cliente

È inoltre possibile visualizzare le transazioni delle provvigioni nella pagina **Giornale di registrazione fatture**.

1. Andare a **Contabilità clienti** \> **Richieste di informazioni e report** \> **Fatture** \> **Giornale di registrazione fatture**.
2. Nella scheda **Fattura**, selezionare **Dettagli** \> **Transazioni delle provvigioni**.

> [!NOTE]
> Quando si registra la fattura, il sistema crea le transazioni di provvigione e giustificativo. Se il valore del campo **Liquidazione delle provvigioni** è **Su fattura** nell'intestazione dell'ordine cliente, il sistema crea un record **Liquidazione**. Se il valore nel campo **Liquidazione delle provvigioni** è **Su pagamento** nell'intestazione dell'ordine cliente, il record **Liquidazione** viene creato solo dopo che la fattura e il pagamento sono stati liquidati.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]