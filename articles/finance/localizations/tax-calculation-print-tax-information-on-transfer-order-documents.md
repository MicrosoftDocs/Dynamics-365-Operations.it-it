---
title: Stampare le informazioni delle imposte sui documenti dell'ordine di trasferimento
description: Questo argomento spiega come stampare le informazioni sulle imposte determinate dal servizio di calcolo delle imposte sui documenti dell'ordine di trasferimento.
author: Kai-Cloud
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-10-12
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: e74336270ab46fc19adb4c797745c9582028391a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687473"
---
# <a name="print-tax-information-on-transfer-order-documents"></a>Stampare le informazioni delle imposte sui documenti dell'ordine di trasferimento

[!include [banner](../../includes/banner.md)]

Questo argomento spiega come stampare le informazioni sulle imposte sui documenti dell'ordine di trasferimento. Puoi stampare il documento di fattura proforma di un ordine di trasferimento per i trasferimenti di magazzino considerati fornitura intracomunitaria e acquisizioni intracomunitarie ai sensi delle normative dell'imposta sul valore aggiunto (IVA) dell'Unione europea (UE). 

I seguenti dati rilevanti ai fini fiscali vengono aggiunti ai documenti dell'ordine di trasferimento:

- I nomi e gli indirizzi di partenza e di arrivo per il trasferimento delle scorte
- I codici fiscali del fornitore e del destinatario
- Il prezzo unitario e la base imponibile dei beni forniti
- Il codice imposta, l'aliquota fiscale, l'importo dell'imposta e le direttive fiscali

È necessario completare i seguenti passaggi principali per configurare questi dati.

1. [Abilita e imposta la funzione delle imposte per gli ordini di trasferimento](tasks/Tax-feature-support-for-transfer-order.md).
2. [Crea e imposta più numeri di partita IVA per una persona giuridica](emea-multiple-vat-registration-numbers.md).
3. Imposta il codice di esenzione, la descrizione, le direttive fiscali e stampa il codice nei codici imposta. Per questo esempio, vengono creati e sincronizzati in Microsoft Microsoft Dynamics 365 Finance tre codici imposta: **NL-Exempt**, **BE-RC-21**, e **BE-RC+21**.

    1. In Finance, vai a **Imposta** \> **Impostazione** \> **IVA** \> **Codici di esenzione IVA**.
    2. Seleziona **Modifica** e inserisci una descrizione per il codice di esenzione **EC**. Ad esempio, inserisci **Spedizioni CE esentasse con numero di partita IVA**.
    3. Vai a **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA**.
    4. Seleziona il codice imposta **BE-RC-21** quindi seleziona **Direttive fiscali**.
    5. Selezionare **Nuovo**.
    6. Nel campo **Lingua** seleziona **EN-US**. Poi, nel campo **Testo** immetti **Documento che prevede il trasferimento di beni ai sensi dell'articolo 138. 2. c) della Direttiva UE IVA 2006/112/CE**.
    7. Chiudere la pagina.
    8. Nella scheda dettaglio **Generale** nel campo **Stampa** seleziona **Aliquota IVA**.
    8. Seleziona il codice imposta **NL-Exempt** e poi, nella scheda dettaglio **Generale** nel campo **Stampa** seleziona **Aliquota IVA**.

    > [!NOTE] 
    > Il codice imposta, l'aliquota fiscale e la descrizione dell'esenzione fiscale non vengono stampati sui documenti dell'ordine di trasferimento se non vengono mantenute la descrizione del codice di esenzione o le direttive fiscali per il codice imposta.

## <a name="print-the-transfer-order---shipment-document"></a>Stampare l'ordine di trasferimento - documento di spedizione

Dopo che un trasferimento è stato spedito, segui questi passaggi per stampare l'ordine di trasferimento - documento di spedizione.

1. Vai a **Gestione inventario** \> **Richieste di informazioni e report** \> **Ordini di trasferimento** \> **Spedizione**.
2. Nella scheda **Parametri** nel gruppo **Stampa** abilita **Informazioni fiscali**.
3. Nella scheda **Record da includere** seleziona **Filtro**, seleziona il numero dell'ordine di trasferimento, quindi seleziona **ok**.
4. Seleziona **OK** per stampare l'ordine di trasferimento - documento di spedizione.

## <a name="print-the-transfer-order---receipt-document"></a>Stampare l'ordine di trasferimento - documento di ricevimento

Dopo che un trasferimento è stato ricevuto, segui questi passaggi per stampare l'ordine di trasferimento - documento di ricevimento.

1. Vai a **Gestione inventario** \> **Richieste di informazioni e report** \> **Ordini di trasferimento** \> **Ricevimento**.
2. Nella scheda **Parametri** nel gruppo **Stampa** abilita **Informazioni fiscali**.
3. Nella scheda **Record da includere** seleziona **Filtro**, seleziona il numero dell'ordine di trasferimento, quindi seleziona **ok**.
4. Seleziona **OK** per stampare l'ordine di trasferimento - documento di ricevimento.

## <a name="print-the-transfer-overview-document"></a>Stampare il documento Panoramica dei trasferimenti

Segui questi passaggi per stampare il documento Panoramica dei trasferimenti.

> [!NOTE]
> Le informazioni fiscali sono disponibili solo quando l'ordine di trasferimento è stato spedito o ricevuto.

1. Vai a **Gestione inventario** \> **Richieste di informazioni e report** \> **Ordini di trasferimento** \> **Panoramica dei trasferimenti**.
2. Nella scheda **Parametri** nel gruppo **Stampa** abilita **Informazioni fiscali**.
3. Nella scheda **Record da includere** seleziona **Filtro**, seleziona il numero dell'ordine di trasferimento, quindi seleziona **ok**.
4. Seleziona **OK** per stampare il documento Panoramica dei trasferimenti.

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
