---
title: Modificare le relazioni gerarchiche per una posizione
description: Questa procedura indica come modificare la relazione gerarchica di un dipendente.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a1afd2c1cdc2ebaa303030d01b3bbe5fd2af44f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178567"
---
# <a name="modify-reporting-relationships-for-a-position"></a>Modificare le relazioni gerarchiche per una posizione

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura indica come modificare la relazione gerarchica di un dipendente. La relazione gerarchica può essere utilizzata per distribuire i documenti tramite il flusso di lavoro. La procedura illustra anche come assegnare il dipendente alle gerarchie aggiuntive. Ad esempio, un dipendente potrebbe far parte di un team di progetto con una relazione gerarchica informale a un supervisore di progetto. Le relazioni gerarchiche aggiuntive possono essere definite sulla posizione per soddisfare i diversi scenari di matrice o di progetto. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.

1. Andare a Risorse umane > Posizioni > Posizioni.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare nel campo Posizione con un valore '000091'.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Espandere la sezione Subordinato a.
5. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
6. Nel campo Subordinato a immettere o selezionare un valore.
7. Fare clic su Crea.
8. Espandere la sezione Relazioni.
9. Scegliere Aggiungi.
10. Selezionare la casella di controllo a sinistra della griglia.
11. Nel campo Nome gerarchia immettere o selezionare un valore.
    * Esempio: Progetto  
12. Nel campo Subordinato a immettere o selezionare un valore.  Esempio: 000437
13. Fare clic su Salva.

