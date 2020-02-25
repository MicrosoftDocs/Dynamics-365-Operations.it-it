---
title: Elaborare l'idoneità di iscrizione
description: In questo articolo viene descritto come eseguire l'elaborazione dell'idoneità di iscrizione.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0344c48460a7d1540481e09ba106526e119de72b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009489"
---
# <a name="process-enrollment-eligibility"></a>Elaborare l'idoneità di iscrizione

[!include [banner](includes/preview-feature.md)]

In questo articolo viene descritto come eseguire l'elaborazione dell'idoneità di iscrizione.

1. Nell'area di lavoro **Gestione benefit**, sotto **Elaborazione**, selezionare **Elaborazione idoneità iscrizione**.

2. Nella finestra di dialogo **Esegui elaborazione idoneità iscrizione a benefit**, specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | Periodo di iscrizione | Il periodo di iscrizione per il quale elaborare l'idoneità di iscrizione. |
   | Persona giuridica | La persona giuridica per la quale elaborare l'idoneità di iscrizione. |
   | Lavoro | Il lavoratore per il quale elaborare l'idoneità di iscrizione. Se questo campo viene lasciato vuoto, l'idoneità di iscrizione verrà elaborata per tutti i lavoratori. |
   | Piano di benefit | Il piano di benefit per il quale elaborare l'idoneità di iscrizione.

3. Se si desidera eseguire l'elaborazione in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:

   1. Immettere le informazioni per l'elaborazione.

   2. Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.

   3. Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.

   4. Selezionare **OK**. l'elaborazione verrà eseguita con i parametri impostati.

4. Selezionare **OK**.
