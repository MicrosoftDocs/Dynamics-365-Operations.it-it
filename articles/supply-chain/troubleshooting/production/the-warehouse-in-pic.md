---
title: Il magazzino nel giornale di registrazione distinte di prelievo non viene aggiornato in una riga DBA.
description: Il magazzino nel giornale di registrazione distinte di prelievo non viene aggiornato in una riga della distinta di prelievo (DBA).
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 970930bbdd30b57a8374de7810bb3ece8cb19a7010b5ef19d90bfc39d09f172b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740553"
---
# <a name="the-warehouse-in-the-picking-list-journal-isnt-updated-on-a-bom-line"></a>Il magazzino nel giornale di registrazione distinte di prelievo non viene aggiornato in una riga DBA

Numero KB: 4614848

## <a name="symptoms"></a>Sintomi

Il magazzino nel giornale di registrazione distinte di prelievo non viene aggiornato in una riga della distinta di prelievo (DBA).

## <a name="resolution"></a>Risoluzione

Il sistema si comporta come previsto. Se viene creata una riga del giornale di registrazione distinte di prelievo che ha un riferimento (tramite l'ID lotto) a una riga della distinta base di produzione, il magazzino nella riga della DBA di produzione non verrà aggiornato se la dimensione del magazzino nella riga del giornale di registrazione distinte di produzione viene modificata successivamente.
