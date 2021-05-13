---
title: Il peso deve essere positivo
description: Il peso deve essere positivo
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dcbcde3143cb509b68b277cb7c709263e2659b5b
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924305"
---
# <a name="weight-must-be-positive"></a>Il peso deve essere positivo

Codice di errore: WeightMustBePositive

## <a name="symptoms"></a>Sintomi

Il sistema mostra il seguente messaggio di errore:

> Il peso deve essere positivo

## <a name="cause"></a>Causa

Il campo **Peso lordo** è impostato su *0* (zero) o un valore negativo.

## <a name="resolution"></a>Risoluzione

Per specificare un peso, effettuare uno dei seguenti passaggi:

- Nel campo **Peso lordo**, impostare un valore. Quindi selezionare un'unità dall'elenco a discesa.
- Selezionare **Ottieni peso sistema** per calcolare il valore **Peso lordo**.
