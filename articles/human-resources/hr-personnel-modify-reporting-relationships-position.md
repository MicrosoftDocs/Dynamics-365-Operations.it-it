---
title: Modificare le relazioni gerarchiche per una posizione
description: Questa procedura indica come modificare la relazione gerarchica di un dipendente.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1ad7220661677ce72168d20903486230411ec00f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688526"
---
# <a name="modify-reporting-relationships-for-a-position"></a>Modificare le relazioni gerarchiche per una posizione


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Questa procedura indica come modificare la relazione gerarchica di un dipendente. La relazione gerarchica può essere utilizzata per distribuire i documenti tramite il flusso di lavoro. La procedura illustra anche come assegnare il dipendente alle gerarchie aggiuntive. Ad esempio, un dipendente potrebbe far parte di un team di progetto con una relazione gerarchica informale a un supervisore di progetto. Le relazioni gerarchiche aggiuntive possono essere definite sulla posizione per soddisfare i diversi scenari di matrice o di progetto. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.

1. Andare a **Risorse umane** \> **Posizioni** \> **Posizioni**.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare in base al valore **000091** nel campo **Posizione**.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Espandere la sezione **Subordinato a**.
5. Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.
6. Nel campo **Subordinato a** immettere o selezionare un valore.
7. Selezionare **Crea**.
8. Espandere la sezione **Relazioni**.
9. Seleziona **Aggiungi**.
10. Selezionare la casella di controllo a sinistra della griglia.
11. Nel campo **Nome gerarchia** immettere o selezionare un valore (ad esempio, **Progetto**).
12. Nel campo **Subordinato a** immettere o selezionare un valore (ad esempio **000437**).
13. Seleziona **Salva**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
