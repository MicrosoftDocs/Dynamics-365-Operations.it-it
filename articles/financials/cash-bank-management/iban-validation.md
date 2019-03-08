---
title: Gestire la convalida del conto IBAN (International Bank Account Number)
description: Questo argomento spiega come gestire la convalida del conto IBAN (International Bank Account Number).
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 19e0528b95952de8e5503c361efcfeca4c529caf
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "360005"
---
# <a name="manage-international-bank-account-number-iban-validation"></a>Gestire la convalida IBAN (International Bank Account Number)

[!include [banner](../includes/banner.md)]

La convalida IBAN (International Bank Account Number) aumenta la convalida che viene effettuata quando si aggiunge un IBAN a un conto bancario.

Le informazioni sulla struttura dell'IBAN vengono archiviate in Microsoft Dynamics 365 for Finance and Operations. Quelle informazioni vengono caricate automaticamente durante la prima utilizzo dell'IBAN sui conti bancari. Contengono la lunghezza IBAN, le posizioni iniziali del numero di conto bancario e il numero di registrazione e la lunghezza del numero e del numero di registrazione del conto bancario.

## <a name="set-up-iban-structures"></a>Impostare le strutture IBAN

1. Passare a **Gestione cassa e banche \> Impostazioni \> Strutture IBAN**.
2. Si noti che le strutture IBAN per ogni paese o area sono state impostate automaticamente.
3. Se si desidera personalizzare le strutture per un paese o un'area geografica specifica, è possibile modificarle.
4. Le definizioni delle strutture saranno parte di ogni nuova versione. È possibile utilizzare il menu **Reimposta strutture** per caricare le definizioni più recenti dopo ogni aggiornamento.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Convalidare la struttura IBAN in un conto bancario

1. Passare a **Gestione cassa e banche \> Conti bancari \> Conti bancari**.
2. Creare un conto bancario.
3. Nella Scheda dettaglio **Informazioni aggiuntive** immettere un IBAN.

    Se la lunghezza IBAN non corrisponde alla lunghezza definita per ciascun paese/area geografica, verrà visualizzato un messaggio di avviso. Non è possibile procedere se la lunghezza dell'IBAN non corrisponde alla lunghezza specificata nella struttura IBAN.

    La convalida verifica inoltre che il numero di conto bancario corrisponda alla parte dell'IBAN che rappresenta il numero di conto bancario. Se il numero di conto bancario non corrisponde, viene visualizzato un messaggio di avviso. Questo messaggio è solo un avviso. È possibile continuare nonostante il numero di conto bancario non corrisponda.

    La convalida verifica inoltre che il numero di registrazione banca corrisponda alla parte dell'IBAN che rappresenta il numero di registrazione banca. Il numero di registrazione include un numero banca e spesso una succursale bancaria aggiuntiva. Se il numero di registrazione banca non corrisponde, viene visualizzato un messaggio di avviso. Questo messaggio è solo un avviso. È possibile continuare nonostante il numero di registrazione banca non corrisponda.
