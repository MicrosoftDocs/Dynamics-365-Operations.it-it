---
title: Utilizzare Importazione/esportazione rapida
description: "Lo scopo di Importazione/esportazione rapida è consentire di importare ed esportare con meno passaggi."
author: margoc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: 
ms.technology: ax-2012
audience: Application User
ms.reviewer: margoc
ms.search.scope: AX 2012 R3 CU8, UnifiedOperations
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 121d8f757e2d5453308d8846bd299f3db339db67
ms.contentlocale: it-it
ms.lasthandoff: 07/18/2017

---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a><span data-ttu-id="e1f54-103">Eseguire lo strumento di trasferimento di dati di test (beta) per Dynamics AX (AX 2012)</span><span class="sxs-lookup"><span data-stu-id="e1f54-103">Run the Test Data Transfer Tool (beta) for Dynamics AX (AX 2012)</span></span>

[!include[banner](../../includes/banner.md)]


<span data-ttu-id="e1f54-104">Lo scopo di Importazione/esportazione rapida è consentire di importare ed esportare con meno passaggi.</span><span class="sxs-lookup"><span data-stu-id="e1f54-104">The purpose of Quick import export is to let you import and export with fewer steps.</span></span>

<span data-ttu-id="e1f54-105">Abbiamo aggiunto la funzionalità Importazione/esportazione rapida per consentire agli utenti di importare o esportare processi semplici che desiderano eseguire rapidamente.</span><span class="sxs-lookup"><span data-stu-id="e1f54-105">We added the Quick Import Export feature to let users import or export simple jobs that they want to execute quickly.</span></span> <span data-ttu-id="e1f54-106">Idealmente, questa funzionalità viene utilizzata in scenari in cui un file viene automaticamente mappato al sistema e l'utente non deve eseguire mapping avanzati o creare ripetuti processi di importazione o esportazione.</span><span class="sxs-lookup"><span data-stu-id="e1f54-106">Ideally this feature is used in scenarios in which a file automatically maps to the system and user does not need to go through advanced mapping or create repeated import or export jobs.</span></span>

-   <span data-ttu-id="e1f54-107">Questa funzionalità supporta l'utilizzo sia di entità predefinite che personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e1f54-107">This feature supports working with both out-of-the-box and custom entities.</span></span>
-   <span data-ttu-id="e1f54-108">È possibile importare da file e, se si utilizza un'origine dati ODBC, è possibile selezionare una query da utilizzare per definire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="e1f54-108">You can import from files, and if you are using an ODBC data source, you can select a query to use to define your import.</span></span>
-   <span data-ttu-id="e1f54-109">È necessario avere precedentemente definito i formati di origine dati per AX o File e sapere dove si trovano.</span><span class="sxs-lookup"><span data-stu-id="e1f54-109">You must have previously defined source data formats for either AX or File, and know where they are located.</span></span>
-   <span data-ttu-id="e1f54-110">Non è necessario creare un gruppo di elaborazione per l'utilizzo di Importazione/esportazione rapida, ne verrà automaticamente creato uno dal sistema quando viene eseguito il processo di importazione o esportazione.</span><span class="sxs-lookup"><span data-stu-id="e1f54-110">You do not need to create a processing group to use quick import/export, one will be automatically created by the system when executing the import or export job.</span></span> <span data-ttu-id="e1f54-111">È inoltre possibile scegliere di mantenere lo storico dei dati importati da Importazione/esportazione rapida.</span><span class="sxs-lookup"><span data-stu-id="e1f54-111">You can also choose keep the history of the data imported by the quick import/export.</span></span>

  <span data-ttu-id="e1f54-112">Notare che Importazione/esportazione rapida presuppone che si abbia familiarità con i concetti di DIXF.</span><span class="sxs-lookup"><span data-stu-id="e1f54-112">Note that Quick import export assumes that you are familiar with the concepts of DIXF.</span></span>




