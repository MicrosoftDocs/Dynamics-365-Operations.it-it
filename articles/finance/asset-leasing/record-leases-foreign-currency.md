---
title: Registrare i leasing in valuta estera
description: In questo argomento viene illustrato come registrare i leasing in valute diverse dalla valuta contabile o di dichiarazione.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 7f1f9153d627eba4c3c79a764cffec6a2f008818
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819748"
---
# <a name="record-leases-in-foreign-currencies"></a>Registrare i leasing in valuta estera

[!include [banner](../includes/banner.md)]

I conti del leasing di cespiti per i leasing che sono in valute diverse dalla valuta di contabilizzazione o dalla valuta di dichiarazione sono stabiliti nella pagina **Impostazione contabilità generale**. Tutti i leasing devono essere inseriti nella valuta della transazione. In altre parole, devono essere inseriti nella valuta specificata nel contratto di leasing. In questo argomento viene illustrato come registrare i leasing in valute diverse dalla valuta contabile o di dichiarazione.

Se si immette un leasing in una valuta estera, l'asset Right of use (ROU) viene ammortizzato sia nella valuta contabile che in quella di dichiarazione. Queste valute sono configurate nella pagina **Impostazione contabilità generale**. Questo comportamento viene utilizzato anche in Cespiti. Quando crei un leasing in una valuta estera, seleziona la valuta della transazione nel campo **Valuta**.

Il tasso di cambio della valuta contabile è il valore predefinito nel campo **Tipo di tasso di cambio valuta contabile**. Il tasso di cambio della valuta di dichiarazione cè il valore predefinito nel campo **Tipo di tasso di cambio valuta di dichiarazione**. Questi tassi di cambio erano in vigore alla data di inizio del contratto di leasing. I campi **Tasso di cambio valuta contabile** e **Tasso di cambio valuta di dichiarazione** sono nella scheda dettaglio **Informazioni sul campio finanziarie e di reporting** della pagina **Dettagli leasing**.

1. Seleziona la casella di controllo **Tasso fisso** per sovrascrivere il tasso di cambio immesso automaticamente, quindi immetti il nuovo tasso.
2. Negli altri campi, inserisci le informazioni richieste per il leasing, quindi seleziona **Crea scadenziari**.
3. Nella nuova pagina **Dettagli leasing**, seleziona **Libri**.
4. Nella pagina **Libro di leasing**, nella scheda **Infomazioni sul cambio finanziarie e di reporting**, verificare i valori di **Asset right of use iniziale in valuta contabile** e **Asset right of use iniziale in valuta di dichiarazione**. Ciascuno di questi campi mostra il dell'asset ROU tradotto nella valuta corrispondente. Questi campi vengono aggiornati ogni volta che si modificano le informazioni finanziarie. Seleziona **Crea scadenziari** prima di confermare lo scadenziario di pagamento.

    La scrittura contabile di riconoscimento iniziale registra l'asset ROU che utilizza i tassi di cambio delle valute elencati nel leasing. La scrittura contabile include anche i valori dei campi **Asset right of use iniziale in valuta contabile** e **Asset right of use iniziale in valuta di dichiarazione**.

## <a name="subsequent-measurement-for-foreign-currency-leases"></a>Misura successiva per leasing in valuta estera

Il piano di ammortamento mostra gli importi delle spese di ammortamento previste nella valuta di dichiarazione, nella valuta contabile e nella valuta della transazione.

Per visualizzare i saldi degli asset ROU e gli importi di ammortamento nella valuta di dichiarazione o in quella contabile, apri la pagian **Piano di ammortamento dei cespiti** e seleziona la casella di controllo **Mostra importi in valuta contabile** o **Mostra importi in valuta di dichiarazione**.

Quando si creano le scritture contabili delle spese di ammortamento per un leasing denominato in una valuta estera, la voce utilizza i tassi di cambio elencati nel leasing. La scrittura contabile include anche i valori dei campi **Asset right of use iniziale in valuta contabile** e **Asset right of use iniziale in valuta di dichiarazione**.

L'importo finale della spesa di ammortamento può essere calcolato utilizzando un tasso di cambio leggermente diverso, in modo che l'asset ROU venga completamente ammortizzato sia nella valuta contabile che nella valuta di dichiarazione.

Se il leasing è stato riclassificato come **Passività sui contratti**, il sistema cancella automaticamente i tassi di cambio delle valute contabili e di dichiarazione, se sono già state definite.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]