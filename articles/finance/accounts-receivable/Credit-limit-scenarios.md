---
title: Scenari dei limiti di credito
description: In questo articolo viene descritto il processo di verifica del limite di credito di un cliente appartenente a un gruppo di clienti con limite di credito.
author: JodiChristiansen
ms.date: 06/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-06-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 60b17a6b7f57b468610974ae9bd05b7db3584cc1
ms.sourcegitcommit: 85141b21ac90f3db1b378c21f9c7f3d8f74e182f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2022
ms.locfileid: "9130257"
---
# <a name="credit-limit-scenarios"></a>Scenari dei limiti di credito

In Gestione crediti, un limite di credito può essere assegnato ai clienti a livello di cliente. A ogni cliente può essere assegnato un *gruppo di clienti con limite di credito*, e ogni gruppo ha un limite di credito. Pertanto, un limite di credito può essere assegnato ai clienti anche a livello di gruppo. Tutti i clienti assegnati allo stesso gruppo di credito cliente hanno lo stesso limite di credito.

In generale, i limiti di credito di gruppo vengono verificati prima dei singoli limiti di credito. Non sempre il limite di credito individuale sostituisce il limite di credito di gruppo.

In questo articolo vengono descritti cinque scenari correlati ai gruppi di credito cliente e ai limiti di credito individuali.

## <a name="the-customer-group-credit-limit-is-more-than-the-individual-credit-limit"></a>Il limite di credito del gruppo di clienti è superiore rispetto al limite di credito individuale

Ad esempio, il cliente ha un limite di credito individuale di $ 10.000. Il cliente è assegnato a un gruppo di credito cliente e il limite di credito del gruppo è di $ 15.000. In questo caso, il "limite di credito effettivo" del cliente è $ 10.000, perché l'importo è inferiore al limite del gruppo. Le regole di blocco verificano prima il limite del gruppo. Successivamente, verificano il limite individuale. Qualsiasi ordine di vendita superiore a $ 10.000 verrà bloccato.

## <a name="the-individual-credit-limit-is-more-than-the-customer-group-credit-limit"></a>Il limite di credito individuale è superiore rispetto al limite di credito del gruppo di clienti

Ad esempio, il cliente ha un limite di credito individuale di $ 20.000. Il cliente è assegnato a un gruppo di credito cliente e il limite di credito del gruppo è di $ 15.000. In questo caso, il limite di credito effettivo del cliente è $ 15.000, perché le regole di blocco verificano sempre per primo il limite del gruppo. Qualsiasi ordine di vendita superiore a $ 15.000 verrà bloccato.

## <a name="the-individual-credit-limit-is-set-to-000-and-mandatory-credit-limit-is-set-to-yes"></a>Il limite di credito individuale è impostato su 0,00 e il valore Limite di credito obbligatorio è impostato su Sì

Se il cliente ha un limite di credito individuale impostato su **0,00** e l'opzione **Limite di credito obbligatorio** è impostata su **Sì**, il limite di credito effettivo del cliente è $ 0,00, anche se il cliente è assegnato a un gruppo di credito clienti. In questo modo, il cliente può far parte di un gruppo, ma tutti gli ordini andranno a Gestione del credito.

## <a name="the-individual-credit-limit-is-set-to-000-and-unlimited-credit-limit-is-set-to-yes"></a>Il limite di credito individuale è impostato su 0,00 e il valore Limite di credito illimitato è impostato su Sì

Se il cliente ha un limite di credito individuale impostato su **0,00** ma l'opzione **Limite di credito illimitato** è impostata su **Sì**, il cliente avrà credito illimitato, anche se è assegnato a un gruppo di credito clienti.

## <a name="the-individual-credit-limit-is-set-to-000-and-the-customer-is-part-of-a-customer-credit-group"></a>Il limite di credito individuale è impostato su 0,00 e il cliente fa parte di un gruppo di credito clienti

Ad esempio, il cliente ha un limite di credito individuale impostato su **0,00**, l'opzione **Credito illimitato** è impostata su **No** e l'opzione **Limite di credito obbligatorio** è impostata su **No**. Il cliente è assegnato a un gruppo di credito cliente e il limite di credito del gruppo è di $ 15.000. In questo caso, il limite di credito effettivo del cliente è il limite del gruppo, ovvero $ 15.000. Pertanto, qualsiasi ordine di vendita superiore a tale importo verrà bloccato. Questo comportamento permette di gestire il limite di credito a livello di gruppo di credito clienti anziché a livello di singolo cliente. Tutti i clienti assegnati allo stesso gruppo hanno lo stesso limite di credito.
