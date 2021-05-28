---
title: Descrizioni predefinite per la contabilità generale
description: Le descrizioni predefinite possono essere utilizzate per aggiornare il campo Descrizione nelle registrazioni dei giustificativi nella contabilità generale.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 25dd72c86b22b50eccef22a5d2cbcfcf04280684
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021614"
---
# <a name="default-descriptions-for-the-general-ledger"></a>Descrizioni predefinite per la contabilità generale

[!include [banner](../../includes/banner.md)]

Le descrizioni predefinite possono essere utilizzate per aggiornare il campo **Descrizione** nelle registrazioni dei giustificativi nella contabilità generale. Questa funzionalità è stata migliorata per essere utilizzata con il modulo Costo sbarcato.

Per impostare le descrizioni predefinite per le registrazioni contabili, vai a **Amministrazione organizzativa\> Impostare \> Descrizioni predefinite**.

La tabella seguente elenca i nuovi valori aggiunti per il campo **Descrizione** nella pagina **Descrizioni predefinite** per supportare il modulo Costo sbarcato.

| Tipo di descrizione | Note |
|---|---|
| Determinazione costi di importazione - Rateo costi | Quando viene registrata una fattura di ordine fornitore, viene elaborata un rateo dei costi per i costi di viaggio stimati. È possibile specificare descrizioni predefinite per aggiungere il numero di viaggio alla descrizione. Usa *%4* per il numero di spedizione. |
| Determinazione costi di importazione - Ordine merci in transito | Se si utilizza l'elaborazione in transito, la fattura dell'ordine fornitore viene registrata e le merci vengono registrate in un conto merci in transito. È possibile specificare descrizioni predefinite per aggiungere il numero dell'ordine in transito alla descrizione. Usa *%4* per il numero dell'ordine in transito. |
| Magazzino - Chiusura - Rettifica | Quando viene elaborata una fattura della contabilità fornitori per i costi di viaggio, viene elaborata una rettifica magazzino per i costi di viaggio stimati. È possibile specificare descrizioni predefinite per aggiungere il numero di viaggio alla descrizione. Usa *%4* per il numero di spedizione. |

Per ulteriori informazioni su come utilizzare la pagina **Descrizioni predefinite**, vedi [Impostare descrizioni predefinite per la registrazione automatica](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).
