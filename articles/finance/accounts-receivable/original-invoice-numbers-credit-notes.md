---
title: Riferimenti a fatture originali nelle note di credito
description: Questo argomento spiega come impostare e stampare i numeri di fattura originali nelle note di credito correlate.
author: ilkond
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 04a4fc96cb7de60052b17e36c33ad5d5be322be4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207353"
---
# <a name="references-to-original-invoices-in-credit-notes"></a>Riferimenti a fatture originali nelle note di credito

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

In alcuni paesi e regioni, esiste un requisito legale per cui le note di credito stampate devono includere i riferimenti alle fatture originali. Questo argomento spiega come impostare e stampare i numeri di fattura originali nelle note di credito correlate.

## <a name="prerequisites"></a>Prerequisiti

- Nell'area di lavoro **Gestione funzionalità**, attiva la funzionalità **Layout fatturazione crediti per report fatture di vendita e progetto** caratteristica. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).
- I formati stampabili dei documenti richiesti devono essere configurati in Gestione stampa.

La funzionalità descritta in questo argomento si applica ai seguenti documenti:

**Contabilità clienti**

- Nota di accredito a testo libero
- Nota di credito cliente

**Gestione progetti e contabilità**

- Nota di accredito progetto

## <a name="configure-accounts-receivable-parameters"></a>Configurare i parametri di contabilità clienti

Segui questi passaggi per impostare il parametro che controlla se i riferimenti alle fatture originali vengono stampati nelle note di credito correlate.

1. Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**.
2. Nella scheda **Aggiornamenti** nella scheda dettaglio **Fattura** imposta l'opzione **Applica il layout di fatturazione delle note di accredito nei report delle fatture di vendita e di progetto** su **Sì**.

![Configurazione dei parametri di contabilità clienti](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a>Definire i riferimenti alle fatture originali

Utilizza le seguenti procedure per definire i riferimenti alle fatture originali, in base al tipo di documento.

### <a name="free-text-credit-note"></a>Nota di accredito a testo libero

1. Passare a **Contabilità clienti** \> **Fatture** \> **Tutte le fatture a testo libero**.
2. Crea una nuova nota di credito o seleziona una nota di credito esistente.
3. Apri la fattura.
4. Nel riquadro azioni, nel gruppo **Genera** della scheda **Funzioni**, seleziona **Fatturazione note di accredito**.
5. Immetti il riferimento alla fattura originale e seleziona il motivo della correzione.

![Definizione del riferimento per una fattura a testo libero](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a>Nota di credito cliente

1. Andare a **Contabilità clienti** \> **Ordini** \> **Tutti gli ordini cliente**.
2. Seleziona e apri l'ordine di vendita fatturato che deve essere corretto.
3. Nel riquadro azioni, nel gruppo **Nota di accredito** della scheda **Vendi** fai clic su **Nota di accredito**.
4. Immetti il motivo della correzione. Il riferimento alla fattura originale viene stabilito automaticamente.

![Definizione del riferimento per un ordine cliente](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a>Nota di accredito progetto

1. Vai a **Gestione progetti e contabilità** \> **Fatture progetto** \> **Fatture progetto**.
2. Seleziona e apri la fattura di progetto che deve essere corretta.
3. Nel riquadro azioni, nel gruppo **Fattura progetto** della scheda **Funzioni**, seleziona **Seleziona per nota di accredito**.
4. Seleziona **Fatturazione note di accredito**.
5. Immetti il motivo della correzione. Il riferimento alla fattura originale viene stabilito automaticamente.

![Definizione del riferimento per una fattura di progetto](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a>Stampa di note di accredito

Quando stampi le note di credito di progetto, del cliente e testo libero, includeranno il riferimento alla fattura originale e il motivo della correzione.

![Nota di credito stampata](media/credit-note-FTI.jpg)

> [!NOTE]
> Assicurati che i formati stampabili dei documenti siano correttamente configurati, ipotizzando che vengano stampati i riferimenti alle fatture originali.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]