---
title: Riferimento a fatture originali nelle note di accredito (fatture fornitore)
description: Questo articolo descrive come creare un riferimento a una fattura originale quando si crea una nota di accredito.
author: AdamTrukawka
ms.date: 09/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2021-09-23
ms.dyn365.ops.version: 10.0.20
ms.search.form: ''
ms.openlocfilehash: 39cf4eb7eef1a83abeb7bd44fa7b2abefee0806e
ms.sourcegitcommit: 8eb0cafe5ad20be2c4fff684e88d7d3f2249f820
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2022
ms.locfileid: "9409666"
---
# <a name="reference-original-invoices-in-credit-notes-vendor-invoices"></a>Riferimento a fatture originali nelle note di accredito (fatture fornitore)

[!include [banner](../includes/banner.md)]

In alcuni paesi e regioni, esiste un requisito legale per cui le note di credito o le routine di creazione di report stampate devono includere i riferimenti alle fatture originali. Questo articolo descrive come creare un riferimento a una fattura originale quando si crea una nota di accredito.

## <a name="prerequisites"></a>Prerequisiti

Nell'area di lavoro **Gestione funzionalità**, abilitare la funzionalità **Abilita fatturazione delle note di accredito per fatture fornitore**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

La funzionalità descritta in questo articolo si applica ai seguenti documenti aziendali.

**Contabilità fornitori:**

- Ordine fornitore
- Giornale di registrazione fatture
- Registro fatture

**Contabilità generale:**

- Giornale di registrazione generale

## <a name="define-a-reference-to-an-original-invoice"></a>Definire un riferimento a una fattura originale

La definizione di un riferimento a una fattura originale include i seguenti passaggi di alto livello:
1. Creare e registrare una fattura fornitore.
2. Crea un nota di credito fornitore.
3. Utilizzare la funzione Fatturazione note di accredito per collegare la fattura a una nota di credito.
4. Registrare la nota di credito.

Utilizzare le seguenti procedure per definire un riferimento a una fattura originale nei tipi di documenti aziendali specificati.

### <a name="vendor-credit-note-purchase-order"></a>Nota di accredito fornitore (ordine fornitore)

1. Vai a **Contabilità fornitori** > **Ordini fornitore** > **Tutti gli ordini fornitore**.
2. Creare un nuovo ordine fornitore o utilizzane uno esistente per creare una nota di accredito.
3. Nel riquadro azioni, nel gruppo **Genera** della scheda **Introduci**, seleziona **Fatturazione note di accredito**.
4. Immettere il motivo per la correzione e il riferimento alla fattura originale.

### <a name="vendor-credit-note-ledger-journals"></a>Nota di accredito fornitore (giornali di registrazione)

1. Eseguire uno dei passaggi riportati di seguito.

    - Andare a **Contabilità fornitori** \> **Giornali di registrazione fatture**.
    - Andare a **Contabilità fornitori** \> **Registro fatture**.
    - Andare a **Contabilità generale** \> **Inserimenti nel giornale di registrazione** \> **Giornali di registrazione generali**.

2. Creare un nuovo giornale di registrazione e nuove righe del giornale di registrazione.
3. Nel riquadro azioni, seleziona **Funzioni** \> **Fatturazione note di accredito**.
4. Immettere il motivo per la correzione e il riferimento alla fattura originale.

> [!NOTE]
> Il comando **Fatturazione note di accredito** comando è visibile in un giustificativo giornale di registrazione generale se il campo **Tipo di account** è impostato su **Fornitore**.
