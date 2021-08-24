---
title: Lettere di intento - Fatturazione di esportatori abituali
description: Questo argomento fornisce informazioni su come impostare lettere di intento e su come utilizzarle quando si emettono fatture.
author: ilkond
ms.date: 12/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 0e0367d91ce4b8d6dda4412527680a757c9431e4f0aacae62f0d73666eabcdda
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740869"
---
# <a name="intent-letters---invoicing-of-usual-exporters"></a>Lettere di intento - Fatturazione di esportatori abituali

[!include [banner](../includes/banner.md)]

Per ricevere una fornitura di beni o servizi esente da IVA in Italia, le società classificate come esportatori abituali devono inviare una dichiarazione di intento (una lettera numerata e datata) agli uffici tributari italiani e agli agenti doganali delle società.
 
## <a name="prerequisites"></a>Prerequisiti

Prima di fatturare, è necessario soddisfare i seguenti prerequisiti:

- L'indirizzo principale della persona giuridica deve essere in Italia.
- La funzionalità **Lettere di intento - Fatturazione di esportatori usuali** deve essere attivata nell'area di lavoro **Gestione funzionalità**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-accounts-receivable-parameters"></a>Impostazione dei parametri di Contabilità clienti

1. Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**.
2. Nella scheda **Contabilità generale e IVA** nella scheda dettaglio **Esportatori abituali**, nel campo **Fascia IVA esportatori abituali**, definire una fascia IVA che viene utilizzata solo per gli esportatori abituali.
3. Impostare l'opzione **Assegnazione automatica lettera di intento** su **Sì** per attivare l'assegnazione automatica delle lettere di intento durante la fatturazione.

![Impostazione dei parametri di Contabilità clienti.](media/emea-ita-exil-intent-AR-parm.jpg)

## <a name="set-up-sales-tax-codes"></a>Imposta i codici IVA

1. Selezionare **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA**.
2. Selezionare un codice IVA, quindi nella scheda dettaglio **Generale**, nella sezione **Fatturazione**, impostare l'opzione **Invia lettere di intento** su **Sì**.

![Impostazione di un codice IVA.](media/emea-ita-exil-intent-tax-setup.jpg)

## <a name="set-up-customers"></a>Impostare i clienti

1. Selezionare **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**.
2. Selezionare un cliente, quindi nella sezione **Fattura e consegna**, selezionare l'opzione **Esportatore abituale** per indicare che il cliente appartiene al gruppo di esportatori usuali.

## <a name="set-up-a-number-sequence-for-intent-letters"></a>Impostare una sequenza numerica per lettere di intento

1. Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**.
2. Nella scheda **Sequenze numeriche**, nel campo **Numero di lettera di intento** specificare il riferimento alla sequenza numerica che verrà utilizzata per numerare le lettere di intento.

## <a name="create-an-intent-letter"></a>Creare una lettera di intento

Seguire questi passaggi per creare una lettera di intento per un cliente selezionato.

1. Selezionare **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**.
2. Selezionare un cliente e quindi, nel riquadro azioni, nella scheda **Vendi**, nel gruppo **Impostazione** selezionare **Imposta** \> **Lettere di intento**.
3. Selezionare **Nuovo**.
4. Immettere i dati per la nuova lettera di intento.

In alternativa, puoi creare una lettera di intento per qualsiasi cliente applicabile selezionando **Contabilità clienti** \> **Lettere di intento** \> **Lettere di intento**.

Le seguenti azioni sono disponibili per lettere di intento esistenti:

- **Chiudi lettera di intento** - Chiude una lettera di intento aperta.
- **Annulla lettera di intento** - Annulla una lettera di intento. È necessario specificare il motivo dell'annullamento.
- **Aggiorna ordini cliente** - Aggiorna gli ordini cliente applicabili con riferimento a una lettera di intento.
- **Apri lettera di intento** - Apre una lettera di intento chiusa.
- **IVA registrata** - Mostra le transazioni IVA relative alla lettera di intento selezionata.

## <a name="using-intent-letters"></a>Utilizzare lettere di intento

Quando si crea un ordine cliente o una fattura a testo libero per un cliente classificato come esportatore usuale, se la data di creazione è nel periodo di validità della lettera di intento, il valore **Fascia IVA esportatori abituali** viene utilizzato nell'ordine o nella fattura. Inoltre, il numero della lettera di intento viene immesso se l'opzione **Assegnazione automatica lettera di intento** è impostata su **Sì**.

![Nuovo ordine cliente.](media/emea-ita-exil-intent-new-order.jpg)

L'importo della transazione fattura sarà soggetto al calcolo dell'IVA solo se non supera l'importo della lettera di intento.

I dettagli della lettera di intento saranno inclusi anche in un layout stampabile della fattura.

![Stampa fattura.](media/emea-ita-exil-intent-inv-print.jpg)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]