---
title: Note spese e più approvatori
description: In questo argomento vengono fornite informazioni sui report di spesa che richiedono l'approvazione da parte di più persone.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1483de5405895d60f0cb302ab622758b2b05d2ca
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "362420"
---
# <a name="expense-reports-and-multiple-approvers"></a>Note spese e più approvatori

[!include [banner](../includes/banner.md)]

In base ai criteri di approvazione di spesa dell'organizzazione, potrebbe essere necessario che più di una persona approvi una nota spese che viene inviata da un dipendente. Quando si imposta il processo del flusso di lavoro per l'approvazione della nota spese, è possibile aggiungere elementi del flusso di lavoro che includono le attività o le operazioni per uno o più approvatori della nota spese. Ad esempio, è possibile richiedere che tutte le note spese vengano approvate prima dall'amministratore del dipendente che ha inviato il report e quindi dal coordinatore della contabilità fornitori.

Se si decide di richiedere più approvatori della nota spese, è possibile aggiungere elementi del flusso di lavoro in uno dei seguenti modi:

- Aggiungere un elemento di approvazione che include un passaggio. Ad esempio, il passaggio potrebbe richiedere che una nota spese venga assegnata a un gruppo di utenti e approvata dal 50 percento dei membri del gruppo di utenti.
- Aggiungere un elemento di approvazione che include più passaggi. Ad esempio, l'elemento di approvazione potrebbe includere i seguenti passaggi:

    1. Il responsabile del dipendente che ha inviato la nota spese la approva.
    2. Un addetto della contabilità fornitori verifica le ricevute e le voci della nota spese.
    3. Il proprietario del budget approva la nota spese.

- Aggiungere più elementi di approvazione, ciascuno dei quali include un passaggio. Ad esempio, è possibile aggiungere un elemento di approvazione distinto per ognuno dei seguenti passaggi:

    1. Il manager del dipendente approva la nota spese.
    2. Il proprietario del budget approva la nota spese.
