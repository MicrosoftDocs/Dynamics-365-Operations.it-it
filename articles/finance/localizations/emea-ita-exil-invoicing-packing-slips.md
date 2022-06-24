---
title: Ordinare le righe fattura di vendita per documento di trasporto
description: Questo articolo spiega come impostare e stampare le fatture accompagnatorie che includono i dettagli dei documenti di trasporto richiesti.
author: ilkond
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: cd65b66a8f5fb7acc8cf65d6d86fc002eaa17abe
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858342"
---
# <a name="sort-sales-invoice-lines-by-packing-slip"></a>Ordinare le righe fattura di vendita per documento di trasporto

[!include [banner](../includes/banner.md)]

In Italia, le aziende devono spesso emettere *fatture accompagnatorie*. Le fatture accompagnatorie sono combinazioni di una fattura ordinaria e un documento di trasporto o bolla di accompagnamento (documento di trasporto o DDT).

## <a name="prerequisites"></a>Prerequisiti

- L'indirizzo principale della persona giuridica deve essere in Italia.
- Nell'area di lavoro **Gestione funzionalità**, verificare che la funzionalità **Ordinamento righe fattura fornitore per documento di trasporto** sia attivata. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Le fatture clienti devono utilizzare il nuovo layout **SalesInvoice.Report \_IT**. Andare a **Contabilità clienti** /> **Impostazioni** /> **Moduli** /> **Impostazione moduli**, quindi sulla scheda **Generale** selezionare **Gestione stampa**. Sulla pagina **Impostazione Gestione stampa**, sotto **Modulo - Contabilità clienti\> Fattura cliente** selezionare **Originale \<Default\>**. Quindi, nel campo **Formato report** selezionare **SalesInvoice.Report \_IT**.

    ![Nuovo layout selezionato per le fatture cliente.](media/emea-ita-exil-invoice-packing-slip-pic2.jpg)

> [!NOTE]
> Quando è attivata la funzione **Ordinamento righe fattura fornitore per documento di trasporto** è attivata, il sistema ignora l'impostazione della casella di controllo **Stampa specifiche documento di trasporto** sulla scheda **Fattura** della pagina **Impostazione moduli** ( **Contabilità clienti \>Impostazioni \>Moduli \> Impostazione moduli**). Anche se questa casella di controllo è selezionata, viene trattata come se fosse deselezionata.
>
> ![Casella di controllo Stampa specifiche documento di trasporto.](media/emea-ita-exil-invoice-packing-slip-pic3.jpg)

## <a name="printing-accompanying-invoices"></a>Stampa delle fatture accompagnatorie

Dopo aver attivato e impostato la funzionalità, il report sulla fattura stampato conterrà le righe della fattura raggruppate e ordinate per documento di trasporto.

![Esempio di fattura in cui le righe sono raggruppate e ordinate per documento di trasporto.](media/emea-ita-exil-invoice-packing-slip-pic.jpg)

> [!NOTE]
> Il nuovo layout è applicabile solo alle fatture basate su ordini cliente. Non è applicabile alle fatture a testo libero, poiché non utilizzano documenti di trasporto.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]