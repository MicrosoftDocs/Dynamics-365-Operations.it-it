---
title: Registrare le scritture contabili di rettifica della transizione in Leasing cespite
description: In questo argomento viene descritta la funzionalità che consente di trasferire un portafoglio di leasing ai nuovi standard contabili di leasing, Accounting Standards Codification Topic 842 (ASC 842) e International Financial Reporting Standard 16 (IFRS 16).
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7ed62f52753a6697a7547ada0317041669cf3506
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207207"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a>Registrare le scritture contabili di rettifica della transizione in Leasing cespite

[!include [banner](../includes/banner.md)]

Questo argomento descrive la funzionalità che consente di trasferire un portafoglio leasing ai nuovi standard contabili di leasing: Accounting Standards Codification Topic 842 (ASC 842), che è lo standard in Generally Accepted Accounting Principles negli Stati Uniti (US GAAP) e International Financial Reporting Standard 16 (IFRS 16).

Per informazioni su come configurare un libro per la transizione ai nuovi standard, vedi [Configurare libri di leasing](set-up-lease-books.md).

Quando crei una scrittura contabile di rettifica di transizione, viene generata una scrittura contabile. Questa voce riflette l'impatto dello stato patrimoniale derivante dalla registrazione del leasing secondo i nuovi principi a quella data. Il valore contabile a tale data viene addebitato sul conto dell'attivo appropriato e accreditato sul conto delle passività. La differenza viene addebitata o accreditata sugli utili non distribuiti.

Per registrare una rettifica di transizione in conformità con i nuovi principi contabili, attieniti alla seguente procedura.

1. Nella pagina **Riepilogo leasing**, seleziona il leasing, quindi seleziona **Libri**.
2. Nel libro, seleziona **Scadenziario pagamenti**.
3. Nella finestra di dialogo **Scadenziario pagamenti**, seleziona **Conferma**. Quindi, chiudi la finestra di dialogo.
4. Seleziona **Rettifica di transizione**.

    > [!NOTE]
    > È possibile creare una rettifica di transizione solo per i libri di leasing assegnati a un libro in cui il campo **Libro di transizione** è disponibile. Se il valore nel campo **Inizio del leasing** è successivo alla data di transizione, il valore nel campo **Rettifica di transizione** non verrà aggiornato.

5. Per visualizzare la scrittura contabile, seleziona **Giornale di registrazione leasing cespiti**.
6. Seleziona il nuovo giornale di registrazione, quindi seleziona **Registra**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]