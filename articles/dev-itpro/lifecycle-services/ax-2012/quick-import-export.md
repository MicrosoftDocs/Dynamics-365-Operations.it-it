---
title: Importazione/esportazione rapida
description: Lo scopo di Importazione/esportazione rapida è consentire di importare ed esportare con meno passaggi.
author: margoc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: AX 2012
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.openlocfilehash: 7655de1399c49328bae1736c796325e546796bd5
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850513"
---
# <a name="quick-import-export"></a><span data-ttu-id="abf5a-103">Importazione/esportazione rapida</span><span class="sxs-lookup"><span data-stu-id="abf5a-103">Quick import export</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="abf5a-104">Lo scopo di Importazione/esportazione rapida è consentire di importare ed esportare con meno passaggi.</span><span class="sxs-lookup"><span data-stu-id="abf5a-104">The purpose of Quick import export is to let you import and export with fewer steps.</span></span>

<span data-ttu-id="abf5a-105">Abbiamo aggiunto la funzionalità Importazione/esportazione rapida per consentire agli utenti di importare o esportare processi semplici che desiderano eseguire rapidamente.</span><span class="sxs-lookup"><span data-stu-id="abf5a-105">We added the Quick Import Export feature to let users import or export simple jobs that they want to execute quickly.</span></span> <span data-ttu-id="abf5a-106">Idealmente, questa funzionalità viene utilizzata in scenari in cui un file viene automaticamente mappato al sistema e l'utente non deve eseguire mapping avanzati o creare ripetuti processi di importazione o esportazione.</span><span class="sxs-lookup"><span data-stu-id="abf5a-106">Ideally this feature is used in scenarios in which a file automatically maps to the system and user does not need to go through advanced mapping or create repeated import or export jobs.</span></span>

- <span data-ttu-id="abf5a-107">Questa funzionalità supporta l'utilizzo sia di entità predefinite che personalizzate.</span><span class="sxs-lookup"><span data-stu-id="abf5a-107">This feature supports working with both out-of-the-box and custom entities.</span></span>
- <span data-ttu-id="abf5a-108">È possibile importare da file e, se si utilizza un'origine dati ODBC, è possibile selezionare una query da utilizzare per definire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="abf5a-108">You can import from files, and if you are using an ODBC data source, you can select a query to use to define your import.</span></span>
- <span data-ttu-id="abf5a-109">È necessario avere precedentemente definito i formati di origine dati per AX o File e sapere dove si trovano.</span><span class="sxs-lookup"><span data-stu-id="abf5a-109">You must have previously defined source data formats for either AX or File, and know where they are located.</span></span>
- <span data-ttu-id="abf5a-110">Non è necessario creare un gruppo di elaborazione per l'utilizzo di Importazione/esportazione rapida, ne verrà automaticamente creato uno dal sistema quando viene eseguito il processo di importazione o esportazione.</span><span class="sxs-lookup"><span data-stu-id="abf5a-110">You do not need to create a processing group to use quick import/export, one will be automatically created by the system when executing the import or export job.</span></span> <span data-ttu-id="abf5a-111">È inoltre possibile scegliere di mantenere lo storico dei dati importati da Importazione/esportazione rapida.</span><span class="sxs-lookup"><span data-stu-id="abf5a-111">You can also choose keep the history of the data imported by the quick import/export.</span></span>

  <span data-ttu-id="abf5a-112">Notare che Importazione/esportazione rapida presuppone che si abbia familiarità con i concetti di DIXF.</span><span class="sxs-lookup"><span data-stu-id="abf5a-112">Note that Quick import export assumes that you are familiar with the concepts of DIXF.</span></span>



