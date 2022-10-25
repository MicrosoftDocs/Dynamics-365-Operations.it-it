---
title: Panoramica della soluzione Invoice Capture
description: In questo articolo vengono fornite informazioni sulla soluzione Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76441220b93744527f412110db536601a2fa1dd9
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691214"
---
# <a name="invoice-capture-solution"></a>Soluzione Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo articolo fornisce informazioni sulla soluzione Invoice Capture che crea automaticamente fatture fornitore da immagini di fatture digitali.

Il reparto Contabilità fornitori (AP) gestisce ed elabora le fatture per beni e servizi ricevuti. L'addetto alla contabilità fornitori verifica i dati sulle fatture fornitore per i seguenti motivi:

- Per evitare sforzi extra se sono necessarie rettifiche o correzioni durante la chiusura del periodo
- Per pagare le fatture dei fornitori in modo tempestivo e prevenire perdite finanziarie dovute a errori o frodi

Il riconoscimento ottico dei caratteri (OCR) è diventato ampiamente utilizzato da diversi settori negli ultimi anni. Ora è comune digitalizzare i testi stampati, in modo che possano essere modificati elettronicamente, ricercati, archiviati in modo più compatto e visualizzati online. Il testo digitale può essere utilizzato in processi di computer come il cognitive computing, la traduzione automatica, la sintesi vocale, i dati chiave e l'estrazione di testo.

L'evoluzione della tecnologia dell'intelligenza artificiale (AI) ha consentito alle moderne soluzioni OCR di leggere diversi formati di fattura di diversi fornitori senza richiedere molto intervento umano. Sempre più aziende stanno riconoscendo che possono risparmiare fatica e migliorare la precisione elaborando le fatture tramite l'automazione invece di eseguire l'elaborazione manuale.

## <a name="system-landscape"></a>Panoramica del sistema

L'illustrazione seguente mostra i componenti e i passaggi principali della soluzione Invoice Capture.

[![Componenti e passaggi nella soluzione Invoice Capture.](./media/Invoice-capture2.png)](./media/Invoice-capture2.png)

## <a name="required-roles"></a>Ruoli richiesti

La tabella seguente mostra i ruoli necessari per configurare e utilizzare la soluzione Invoice Capture.

| Ruolo          | Azioni | Sistemi | Nome dei ruoli |
|---------------|---------|---------|-----------|
| Amministratore | <ul><li>Configura gli ambienti in Microsoft Power Platform.</li><li>Distribuisci soluzioni in Microsoft Power Platform.</li><li>Configura le connessioni tra Dynamics 365 e AI Builder.</li><li>Configura le posizioni di Azure Data Lake Storage.</li></ul> | <ul><li>Dynamics 365</li><li>Microsoft Power Platform</li><li>Azure Data Lake Storage</li></ul> | <ul><li>Amministratore di Dynamics 365</li><li>Amministratore Power Platform</li><li>Proprietario dei dati del BLOB di archiviazione</li></ul> |
| Autore di intelligenza artificiale      | <ul><li>Mantieni i flussi.</li><li>Crea modelli di intelligenza artificiale personalizzati.</li></ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>Autori non professionisti</li></ul> |
| Addetto alla contabilità fornitori      | <ul><li>Rivedi e intraprendi azioni nell'area di gestione temporanea delle fatture fornitore.</li><ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>Nuovo ruolo di addetto alla contabilità fornitori in Power Platform</li></ul> |
| Addetto alla contabilità fornitori      | <ul><li>Esegui le operazioni quotidiane come addetto alla contabilità fornitori.</li><li>Accedi all'area di gestione temporanea delle fatture fornitore.</li></ul> | <ul><li>Dynamics 365</li></ul> | <ul><li>Addetto contabilità fornitori</li></ul> |
  
Per ulteriori informazioni sull'installazione di Invoice Capture, vedi [Installare Invoice Capture](../accounts-payable/install-invoice-capture.md).  
