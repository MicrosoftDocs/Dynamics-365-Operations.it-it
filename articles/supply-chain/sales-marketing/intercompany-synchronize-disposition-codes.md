---
title: Sincronizzare i codici smaltimento
description: In questo articolo viene descritta la sincronizzazione dei codici smaltimento per il commercio interaziendale
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: d347181dd6ba12de0e114d74d43cd46230ba4fb7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905662"
---
# <a name="synchronize-intercompany-disposition-codes"></a>Sincronizzare i codici smaltimento interaziendali

[!include [banner](../../includes/banner.md)]

Per supportare i resi interaziendali, in Microsoft Dynamics 365 Supply Chain Management è possibile mappare i codici smaltimento definiti esternamente ai corrispondenti codici smaltimento interni. Quando viene impostata una catena interaziendale, le azioni di smaltimento nelle due società mappate devono essere identiche. In caso contrario, il processo di sincronizzazione avrà esito negativo.

## <a name="about-disposition-codes-for-three-legged-direct-returns"></a>Informazioni sui codici smaltimento per resi diretti basati su transazioni a tre

I codici smaltimento vengono sincronizzati dalla riga dell'ordine cliente interaziendale alla riga dell'ordine cliente originario. Tuttavia, la sincronizzazione ha un solo effetto immediato sulla riga ordine cliente originale. Tale effetto è l'eliminazione degli addebiti vari in base al codice smaltimento e l'impostazione di addebiti vari nella società A, ovvero la società che crea l'ordine di reso.

In una catena di consegne dirette basata su transazioni a tre, tutte le azioni di smaltimento sono supportate nella riga dell'ordine cliente interaziendale. Se un prodotto viene restituito al cliente, tuttavia, è necessario confermare che l'indirizzo di consegna nell'ordine di reso corrisponda all'indirizzo di consegna del cliente specificato nell'ordine originario.

> [!NOTE]
> I codici smaltimento non sono presenti negli ordini fornitore. Pertanto, la sincronizzazione di codici smaltimento dall'ordine cliente interaziendale all'ordine di reso originario deve essere eseguita da ordine cliente a ordine cliente.

## <a name="replacing-returned-items"></a>Sostituzione di resi

Se un reso viene sostituito e nella società B è già stato creato un ordine sostitutivo, non è possibile selezionare un codice smaltimento e nella società A non viene creato alcun ordine sostitutivo aggiuntivo.

## <a name="rules-for-intercompany-direct-deliveries"></a>Regole per le consegne dirette interaziendali

In scenari che prevedono consegne dirette interaziendali, per gli ordini di reso originari si applicano le regole generali descritte di seguito.

- Se l'azione di smaltimento sottostante nella riga dell'ordine cliente originario è Credito e scarto, Avere o Reso a cliente, l'azione di smaltimento applicata sarà Avere. Il codice dell'azione Reso a cliente determinerà tuttavia l'impostazione dell'importo netto su 0 (zero) nella riga esistente e nella riga sincronizzata dall'ordine cliente interaziendale. Le righe di scarto non vengono mai sincronizzate. Quando viene aggiunta una riga a un ordine cliente interaziendale, non viene mai sincronizzata per un ordine cliente con una quantità positiva e un'azione di smaltimento di tipo scarto (ad esempio, Credito e scarto o Sostituzione e scarto).
- Se l'azione di smaltimento sottostante è Sostituzione e credito o Sostituzione e scarto, non verrà ignorata e verrà trattata come un'azione di smaltimento di tipo Sostituzione e credito o Sostituzione e scarto, anche se non viene creata alcuna riga scarto nella società A né alcun ordine sostitutivo nella società B (la società che riceve l'articolo reso). Viene creato un ordine sostitutivo nella società A solo quando viene eseguito l'aggiornamento di un documento di trasporto.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
