---
title: Gruppi di crediti cliente
description: In questo argomento vengono fornite informazioni su gruppi di crediti cliente.
author: mikefalkner
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3cdf4f7e72a55292c64b7a9191974242aab85a90
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835318"
---
# <a name="customer-credit-groups"></a>Gruppi di crediti cliente

[!include [banner](../includes/banner.md)]

È possibile definire gruppi di clienti che hanno un limite di credito condiviso. Viene inoltre considerato il limite di credito individuale definito nel conto delle fatture cliente.

I membri di un gruppo di crediti cliente possono essere selezionati tra diverse persone giuridiche. Quando si aggiunge un cliente all'elenco di clienti nel gruppo di crediti cliente, la data di scadenza del limite di credito per ciascun cliente viene modificata nella data di scadenza assegnata al gruppo.

È possibile impostare gruppi di crediti cliente nella pagina **Gruppi di crediti cliente** (**Gestione crediti \> Gruppi di crediti cliente \> Gruppi di crediti cliente**).

1. Nei campi **Numero gruppo** e **Descrizione**, immettere un identificatore e una descrizione per il gruppo.
2. Nei campi **Limite di credito** e **Valuta**, immettere il limite di credito e la valuta da utilizzare quando il sistema controlla il limite di credito per qualsiasi membro del gruppo.
3. Nel campo **Scadenza limite di credito**, inserire la data di scadenza del limite di credito. I gruppi di crediti cliente devono avere una data di scadenza.

Dopo aver completato l'impostazione di un gruppo di crediti cliente, è possibile aggiungervi clienti specificando la relativa persona giuridica e l'ID conto cliente. Quando si aggiunge un nuovo cliente a un gruppo di crediti cliente, il sistema cerca lo stesso conto cliente in tutte le persone giuridiche e richiede di aggiungerlo al gruppo di crediti cliente.

Utilizzare il menu **Saldi con aging** per visualizzare i dettagli del saldo con aging per tutti i clienti di fatturazione in un gruppo di crediti cliente. La pagina **Saldo di aging** mostra un riepilogo dei saldi con aging per i conti cliente fattura.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]