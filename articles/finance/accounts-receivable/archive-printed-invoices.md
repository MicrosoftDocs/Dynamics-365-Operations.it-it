---
title: Archiviare le fatture cliente stampate con numeri hash
description: In questo articolo viene descritto come abilitare l'archiviazione per archiviare le fatture cliente stampate con numeri hash.
author: mrolecki
ms.date: 09/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.custom: 539093
ms.search.form: ''
ms.openlocfilehash: 4c9bd7ead1615a4e6b0e8e672e858312ba518b56
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291671"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a>Archiviare le fatture cliente stampate con numeri hash

[!include [banner](../includes/banner.md)]

In alcuni paesi, esiste un requisito legale per memorizzare i numeri hash calcolati nel sistema insieme alla stampa di alcuni documenti. I numeri hash possono essere utilizzati per il reporting alle autorità e durante gli audit.

In questo articolo viene descritto come configurare l'archiviazione per archiviare fatture cliente stampate con numeri hash.

## <a name="prerequisites"></a>Prerequisiti

- Nell'area di lavoro **Gestione funzionalità**, attivare la funzionalità **Archivia fatture cliente stampate con numeri hash**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Configurare i formati stampabili dei documenti necessari in **Gestione stampa**.

Questa funzionalità è applicabile ai seguenti documenti.

**Contabilità clienti**
- Fattura cliente
- Nota di credito cliente
- Fattura a testo libero
- Nota di accredito a testo libero

**Gestione progetti e contabilità**
- Fattura progetto
- Nota di accredito progetto

## <a name="configure-customer-master-data"></a>Configurare i dati master dei clienti
Completare i seguenti passaggi per configurare i dati del cliente e attivare la possibilità di salvare automaticamente le fatture stampate come allegati.

1. Selezionare **Contabilità clienti** > **Tutti i clienti**. 
2. Seleziona un cliente e nella Scheda dettaglio **Fattura e consegna**, nella sezione **FATTURA ELETTRONICA**, nel campo **Allegato fattura elettronica**, selezionare **Sì**.

## <a name="print-invoices"></a>Stampare fatture
È possibile registrare e stampare qualsiasi nota di accredito o fattura a testo libero, cliente e di progetto per il cliente configurato nella procedura precedente.

Aprire la pagina **Allegati** per la fattura stampata. Nella Scheda dettaglio **Allegato**, nel gruppo di campi **Dettagli aggiuntivi**, nel campo **Numero hash documento** trovare il numero hash memorizzato calcolato per la fattura stampata.

![Numero hash allegato.](media/attach-hash-num.jpg)

