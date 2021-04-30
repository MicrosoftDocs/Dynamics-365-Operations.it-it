---
title: Fattura fiscale per le merci consegnate gratuitamente
description: Questo argomento fornisce informazioni sulle fatture imposta per le merci che sono state consegnate gratuitamente.
author: ilkond
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: mrolecki
ms.search.validFrom: 2019-11-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 86fd4cb7ef8490ce3239f6cfec80fec02cd53ad7
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894750"
---
# <a name="tax-invoice-for-goods-delivered-for-free"></a>Fattura fiscale per le merci consegnate gratuitamente

[!include [banner](../includes/banner.md)]

Questo argomento descrive come gestire le merci che sono state consegnate gratuitamente. La funzionalità disponibile tramite **Fattura fiscale per le merci consegnate gratuitamente** consente di generare fatture che includono le parole "Fattura gratuita". Il totale di queste fatture equivale solo all'importo delle imposte.

Per generare queste fatture, è necessario impostare le causali per la consegna che possono essere utilizzate nell'ordine cliente.

Queste fatture possono essere utilizzate in due casi, a seconda di chi paga le tasse sugli articoli:

- La tua azienda paga l'imposta sulle vendite e il sistema genera una fattura automatica e voci contabili per il pagamento.
- Il cliente paga l'imposta sulle vendite.

la causale della consegna sulla fattura determina il caso da utilizzare.

## <a name="prerequisites"></a>Prerequisiti

- L'indirizzo principale della persona giuridica deve essere in Italia.
- Nell'area di lavoro **Gestione funzionalità**, attivare la funzionalità **Fattura fiscale per le merci consegnate gratuitamente**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-the-summary-update-parameters"></a>Impostare i parametri di aggiornamento riepilogativo

È possibile impostare i parametri di aggiornamento riepilogativo solo se è disponibile una causale della consegna sia per il documento di trasporto che per la fattura.

1. Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**.
2. Sulla scheda **Aggiornamento riepilogativo**, selezionare **Parametri di aggiornamento riepilogativo**.
3. Il parametro di aggiornamento riepilogativo **Causale consegna** deve essere selezionato sia per i documenti di trasporto che per le fatture. Sulla scheda **Fattura**, nell'elenco **Disponibili**, selezionare **Causale consegna**. Quindi selezionare il pulsante freccia destra per spostare **Causale consegna** nell'elenco **Selezionato**. Ripetere questo passaggio sulla scheda **Documento di trasporto**.

![Parametri aggiornamento riepilogativo](media/emea-ita-exil-free-goods-summary-update-parameters.jpg)

## <a name="set-up-a-sales-for-free-account"></a>Configura un account Vendite gratuite

Attenersi alla seguente procedura per configurare l'account di contabilità per le vendite gratuite.

1. Andare a **Gestione scorte**\>**Impostazioni**\>**Registrazione**\>**Registrazione**.
2. Selezionare l'opzione **Vendite gratuite**.
3. Impostare l'account principale selezionando le relazioni e i codici conto richiesti.

![Account Vendite gratuite](media/emea-ita-exil-free-goods-sales-free-account.jpg)

## <a name="set-up-miscellaneous-charges"></a>Impostare le spese varie

Le spese varie non sono sempre richieste o desiderate quando vengono emesse fatture di vendite gratuite. Seguire questa procedura per escludere le spese varie quando vengono generate automaticamente.

1. Andare a **Contabilità clienti** \> **Impostazione spese** \> **Codice spese**.
2. Selezionare o creare un codice spese esistente.
2. Impostare l'opzione **Escludi spese nelle fatture gratuite** su **Sì**.

![Codici di spese](media/emea-ita-exil-free-goods-charges-codes.jpg)

## <a name="set-up-delivery-reasons"></a>Impostare i motivi della consegna

1. Andare a **Vendite e marketing** \> **Impostazioni** \> **Distribuzione** \> **Causali per la consegna**.
2. Selezionare la casella di controllo **Merci gratuite**.
3. Nel campo **Conto fattura**, selezionare l'account cliente che rappresenta l'azienda.
4. Nel campo **Termini di pagamento** specificare i termini di pagamento in contanti.

![Causali per la consegna](media/emea-ita-exil-free-goods-delivery-reason.jpg)

> [!NOTE]
> La società emette una fattura automatica per contabilizzare le imposte richieste per le merci che vengono consegnate gratuitamente. Oltre alla registrazione della fattura, devono essere generate le voci contabili per il pagamento. Per rendere disponibile tale processo, è necessario disporre di un account cliente che rappresenti la propria azienda. In questo caso, il conto fattura in un ordine cliente verrà impostato sul conto cliente dell'azienda per impostazione predefinita. Pertanto, la fattura emessa sarà una fattura automatica. Quando si specificano i termini di pagamento in contanti, il pagamento si verifica in aggiunta alla fattura automatica. Infine, la transazione del cliente viene chiusa e l'importo viene registrato nel conto di cassa specificato nel campo **Modalità di pagamento**. Questo campo verrà inoltre impostato per impostazione predefinita su un'intestazione dell'ordine cliente.
>
> Se il cliente paga le tasse, i campi **Conto fatture** e **Termini di pagamento** devono essere lasciati vuoti.

## <a name="posting-tax-invoices-for-goods-delivered-for-free"></a>Registrazione delle fatture imposte per le merci consegnate gratuitamente

Quando si crea un ordine cliente per merci consegnate gratuitamente, il motivo di consegna specificato determina se viene generata una fattura automatica per l'azienda o se viene generata una fattura per il cliente. Se si utilizzano termini di pagamento in contanti, le voci della contabilità di pagamento verranno create anche quando si registra la fattura di vendita.

## <a name="printing-tax-invoices-for-goods-delivered-for-free"></a>Stampa delle fatture imposte per le merci consegnate gratuitamente

La stampa della fattura mostrerà il titolo **Fattura gratuita**. Inoltre, agli articoli verrà aggiunto il prefisso **Articolo gratuito:** se il flag **Merci gratuite** è attivo sul motivo di consegna utilizzato per l'ordine.

![Stampa della fattura gratuita](media/emea-ita-exil-free-tax-invoice-printout.jpg)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]