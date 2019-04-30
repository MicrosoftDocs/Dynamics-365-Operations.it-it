---
title: Iscrivere un dipendente a un piano di retribuzione fisso
description: Il responsabile di retribuzione e benefit può assegnare i dipendenti a piani di retribuzione fissa per la gestione delle retribuzioni base.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee0ba197ee47d2a2da2372b12291e5625ddc9ba1
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "859945"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a>Iscrivere un dipendente a un piano di retribuzione fisso

[!include [task guide banner](../../includes/task-guide-banner.md)]

Il responsabile di retribuzione e benefit può assegnare i dipendenti a piani di retribuzione fissa per la gestione delle retribuzioni base. In questa procedura si presuppone che un piano fisso sia stato creato e sia attivo e che le regole di idoneità sono state impostate per il piano. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Per avviare la procedura, andare a Risorse umane > Lavoratori > Dipendenti > Retribuzione > Piano fisso

1. Fare clic su Nuovo.
2. Nel campo Azione selezionare un'azione di retribuzione fissa di tipo Assunzione/Riassunzione per descrivere la modifica della retribuzione del dipendente.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nel campo Posizione fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Il livello visualizzato deriva dal livello retributivo della mansione nella posizione. Il livello deve essere impostato sulla mansione prima che la retribuzione possa essere assegnata al dipendente.  
6. Nel campo Piano selezionare il piano di retribuzione fissa per il dipendente. La ricerca del piano viene filtrata per indicare solo i piani per cui il dipendente è idoneo in base alle regole di idoneità.
7. Nell'elenco trovare e selezionare il record desiderato.
    * Le date di validità e di scadenza per la retribuzione derivano per impostazione predefinita dalle date di inizio e di fine dell'assegnazione di posizione del lavoratore. È possibile modificare tali date in base alle necessità.  
    * Se il piano di retribuzione fissa è un piano di tipo Fase, selezionare la fase contenente la tariffa retributiva corretta per il dipendente. Se il piano di retribuzione fissa è un piano di tipo Fascia o Scala, immettere la tariffa retributiva per il dipendente. La tariffa retributiva verrà convalidata rispetto alle impostazioni di tolleranza per il piano e ai punti di riferimento minimo e massimo per il livello retributivo della mansione.  
8. Fare clic su OK.

