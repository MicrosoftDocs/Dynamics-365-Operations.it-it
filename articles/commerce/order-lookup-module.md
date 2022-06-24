---
title: Modulo di ricerca ordini
description: In questo articolo viene descritto il modulo di ricerca ordini e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: c83463d9a0ece9605b0d22bee2a1c76057c8ed05
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869432"
---
# <a name="order-lookup-module"></a>Modulo di ricerca ordini

[!include [banner](includes/banner.md)]

In questo articolo viene descritto il modulo di ricerca ordini e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.

Il modulo di ricerca ordini consente ai clienti di cercare gli ordini che hanno effettuato su un sito di e-commerce. Viene usato nell'ambito della funzionalità [Abilitare la ricerca di ordini per il checkout come guest](order-lookup-guest.md). Il modulo di ricerca degli ordini può essere utilizzato per cercare gli ordini inviati tramite un sito di e-commerce, il punto vendita al dettaglio (POS) o un servizio clienti. Il modulo può recuperare gli ordini inviati sia da utenti guest sia da utenti registrati.

L'illustrazione seguente mostra un esempio del modulo di cui viene eseguito il rendering dal modulo di ricerca ordini. Quando i clienti compilano il modulo e selezionano **Trova ordine**, vengono reindirizzati alla pagina dei dettagli dell'ordine.

![Modulo di ricerca ordini su una pagina.](./media/OrderLookup_module.PNG)

## <a name="order-lookup-module-properties"></a>Proprietà del modulo di ricerca ordini

| Nome proprietà     | Valore     | descrizione |
|-------------------|-----------|-------------|
| Intestazione           | Testo      | Intestazione che appare nella parte superiore del modulo (ad esempio "Trova ordine"). |
| RTF         | RTF | Testo esplicativo facoltativo che appare sotto l'intestazione. |
| Tipo di stato dell'ordine | Enum      | <p>Seleziona il tipo di informazioni richieste al cliente oltre all'ID di conferma dell'ordine. Attualmente sono supportati valori seguenti:</p><ul><li><b>E-mail</b>: nel modulo è incluso un campo in cui i clienti possono inserire l'indirizzo e-mail che hanno utilizzato quando hanno effettuato l'ordine.</li><li><b>Nessuno</b>: non viene richiesta alcuna informazione oltre all'ID di conferma dell'ordine.</li></ul> |

## <a name="add-an-order-lookup-module-to-a-page"></a>Aggiungere un modulo di ricerca ordini a una pagina

Il modulo di ricerca ordini può essere aggiunto al corpo di qualsiasi pagina del sito di e-commerce. Se si desidera utilizzare il modulo di ricerca ordini per abilitare la ricerca per il checkout come guest, assicurarsi di aggiungerlo a una pagina che non richieda l'accesso dell'utente. Per trovare l'impostazione **È necessario l'accesso?** nella visualizzazione ad albero del generatore di siti di Commerce, selezionare lo slot **Pagina predefinita (richiesta)** ed esaminare la parte inferiore del riquadro destro.

## <a name="additional-resources"></a>Risorse aggiuntive

[Abilitare la ricerca di ordini per il checkout come guest](order-lookup-guest.md)

[Panoramica della libreria moduli](starter-kit-overview.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
