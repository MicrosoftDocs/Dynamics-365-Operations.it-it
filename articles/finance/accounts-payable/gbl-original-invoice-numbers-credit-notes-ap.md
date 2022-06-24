---
title: Riferimento a fatture originali nelle note di accredito (fatture fornitore)
description: Questo articolo descrive come creare un riferimento a una fattura originale quando si crea una nota di accredito.
author: v-oloski
ms.date: 09/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2021-09-23
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e05dddf056d86513d86ea925349f60ca25f191ca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901491"
---
# <a name="reference-original-invoices-in-credit-notes-vendor-invoices"></a>Riferimento a fatture originali nelle note di accredito (fatture fornitore)

[!include [banner](../includes/banner.md)]

Questo articolo descrive come creare un riferimento a una fattura originale quando si crea una nota di accredito.

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

Utilizzare le seguenti procedure per definire un riferimento a una fattura originale nei tipi di documenti aziendali specificati.

### <a name="vendor-credit-note-purchase-order"></a>Nota di accredito fornitore (ordine fornitore)

1. Andare a **Contabilità fornitori** \> **Ordini fornitore** \> **Tutti gli ordini fornitore**.
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
