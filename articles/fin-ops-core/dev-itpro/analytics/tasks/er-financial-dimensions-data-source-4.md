---
title: 'ER Utilizzare le dimensioni finanziarie come origine dati (Parte 4: eseguire il report)'
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 27498fb8290fa18abd64d7f306e9c0bf4713a72f
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550136"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a><span data-ttu-id="97422-103">ER Utilizzare le dimensioni finanziarie come origine dati (Parte 4: eseguire il report)</span><span class="sxs-lookup"><span data-stu-id="97422-103">ER Use financial dimensions as a data source (Part 4 - Run the report)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="97422-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.</span><span class="sxs-lookup"><span data-stu-id="97422-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="97422-105">Queste operazioni possono essere eseguite nella società DEMF.</span><span class="sxs-lookup"><span data-stu-id="97422-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="97422-106">Per effettuare questi passaggi, è innanzitutto necessario completare i passaggi nella procedura 'ER Usare dimensioni finanziarie come origine dati (parte 3: progettare il report)'.</span><span class="sxs-lookup"><span data-stu-id="97422-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 3: Design the report)” procedure.</span></span> <span data-ttu-id="97422-107">È inoltre necessario configurare i tipi di documento predefiniti nella pagina Parametri per la creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="97422-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="97422-108">I tipi di documento predefiniti vengono impostati anche quando si scarica e importa qualsiasi configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="97422-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="97422-109">Eseguire un report</span><span class="sxs-lookup"><span data-stu-id="97422-109">Run report</span></span>
1. <span data-ttu-id="97422-110">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="97422-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="97422-111">Nella struttura espandere 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="97422-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="97422-112">Nella struttura selezionare 'Modello di esempio dimensioni finanziarie\Report dei giornali di registrazione di contabilità generale'.</span><span class="sxs-lookup"><span data-stu-id="97422-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="97422-113">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="97422-113">Click Run.</span></span>
5. <span data-ttu-id="97422-114">Nel campo Nome dimensione, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="97422-114">In the Dimension name field, In the Dimension name field, enter or select a value..</span></span>
    * <span data-ttu-id="97422-115">Per selezionare tutte le dimensioni della società corrente, immettere quanto segue: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="97422-115">To select all dimensions in the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
6. <span data-ttu-id="97422-116">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="97422-116">Expand the Records to include section.</span></span>
7. <span data-ttu-id="97422-117">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="97422-117">Click Filter.</span></span>
8. <span data-ttu-id="97422-118">Selezionare la riga relativa alla tabella Giornale di registrazione contabile e il campo Numero batch giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="97422-118">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="97422-119">Nel campo Criteri digitare '00057'.</span><span class="sxs-lookup"><span data-stu-id="97422-119">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="97422-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="97422-120">Click OK.</span></span>
11. <span data-ttu-id="97422-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="97422-121">Click OK.</span></span>
    * <span data-ttu-id="97422-122">Esaminare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="97422-122">Review the generated output.</span></span> <span data-ttu-id="97422-123">Tenere presente che per ciascuna transazione del batch selezionato, le dimensioni finanziarie del set di dimensioni corrispondente vengono presentate.</span><span class="sxs-lookup"><span data-stu-id="97422-123">Note that for each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="97422-124">Eseguire questo report e selezionare dimensioni diverse per vedere che il report non dipende dal numero di dimensioni selezionate o dal numero di dimensioni configurate per questa istanza.</span><span class="sxs-lookup"><span data-stu-id="97422-124">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  

