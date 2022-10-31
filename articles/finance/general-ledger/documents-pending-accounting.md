---
title: Documenti in attesa della contabilità
description: In questo articolo viene descritto come utilizzare la funzionalità nella pagina Documenti in attesa della contabilità.
author: ryanCCarlson2
ms.date: 09/02/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: f37d46659b2fc5bf9933719811a7b90cc4e80f52
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709251"
---
# <a name="documents-pending-accounting"></a>Documenti in attesa della contabilità

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come utilizzare la funzionalità nella pagina **Documenti in attesa della contabilità**.

In Microsoft Dynamics 365 Finance 10.0.30 è disponibile la funzionalità **Prestazioni migliorate per il framework di contabilità dei documenti di origine**. Questa funzionalità migliora i processi di registrazione dei documenti di origine abilitati, a partire dal processo di registrazione per le fatture a testo libero.

Quando la funzionalità è abilitata, l'inserimento del documento nel giornale di registrazione secondario viene eseguito separatamente dalla generazione contabile o dal processo di *inserimento nel giornale di registrazione* che crea i dettagli contabili completi trasferiti alla contabilità generale. Nel processo di registrazione della fattura a testo libero, ad esempio, la fattura cliente nel modulo **Contabilità clienti** viene registrata prima che venga generata la contabilità completa. Questa funzionalità con prestazioni avanzate consente di registrare le fatture dei clienti più rapidamente quando la generazione della contabilità è ritardata.

Nella pagina **Documenti in attesa della contabilità** sono disponibili i pulsanti seguenti.

- **Genera contabilità**: consente di inviare un documento attualmente in attesa di generazione dell'account per l'inserimento nel giornale di registrazione.
- **Visualizza distribuzioni**: visualizza le distribuzioni contabili per un documento selezionato nell'elenco.
- **Visualizza log degli errori**: visualizza i dettagli dei messaggi di errore esistenti per un documento in cui lo stato contabile indica errori. È possibile visualizzare gli stessi dettagli del messaggio di errore selezionando il collegamento **Registro errori** sulla riga del documento.

La generazione della contabilità viene eseguita da un processo in background di automazione dei processi denominato **Processore del framework di contabilità**. Per altre informazioni sull'impostazione e la configurazione di tutte le automazioni dei processi, vedere [Automazione dei processi](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
