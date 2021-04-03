---
title: Richiesta di informazioni migliorata sulla liquidazione dare/avere
description: Questo argomento spiega come visualizzare le informazioni relative alla fatturazione e ai pagamenti in un formato comodo e semplice.
author: ilkond
manager: AnnBe
ms.date: 11/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 5b62ebb4aed6e749fa2429c656172c8b20dc0297
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239615"
---
# <a name="improved-inquiry-on-debitcredit-settlement"></a>Richiesta di informazioni migliorata sulla liquidazione dare/avere

[!include [banner](../includes/banner.md)]

Questo argomento spiega come visualizzare le informazioni relative alla fatturazione e ai pagamenti in un formato comodo e semplice.

## <a name="prerequisites"></a>Prerequisiti

Per poter utilizzare questa funzionalità è necessario soddisfare i seguenti requisiti:

- L'indirizzo principale della persona giuridica deve essere in Italia.
- Nell'area di lavoro **Gestione funzionalità**, attivare la funzionalità **Miglioramento della richiesta informazioni sulle liquidazioni a debito o credito**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).

## <a name="use-the-invoicepayments-list-page"></a>Utilizzare la pagina Elenco fatture/pagamenti

Eseguire uno dei passaggi riportati di seguito per aprire la pagina elenco **Fatture/pagamenti**: 

- Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**. Quindi, nella scheda **Fattura** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Fatture/pagamenti**.
- Andare a **Contabilità fornitori \>Fornitori \> Tutti i fornitori**. Quindi, nella scheda **Fattura** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Fatture/pagamenti**.

La griglia nella parte superiore della pagina mostra le fatture cliente o le fatture fornitore. Queste fatture sono ordinate per numero e data della fattura. 

La griglia nella parte inferiore della pagina mostra le transazioni di addebito e credito del cliente o fornitore selezionato. Questi tipi di transazione includono fatture, pagamenti e transazioni di rivalutazione in valuta estera. Qualsiasi saldo diverso da zero per le fatture è evidenziato in rosso.

![Pagina Elenco fatture/pagamenti](media/emea-ita-exil-DC-inquiry-vendor-invoice-payment.png)

Nel riquadro azioni selezionare **Parametri** per impostare un filtro in modo che la pagina elenco **Fatture/pagamenti** mostri solo i dati specifici.

![Finestra di dialogo a discesa dei parametri](media/emea-ita-exil-DC-inquiry-parameters.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]