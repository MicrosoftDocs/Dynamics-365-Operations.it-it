---
title: 'ER Utilizzare le dimensioni finanziarie come origine dati (Parte 4: eseguire il report)'
description: In questo argomento viene descritto come configurare un modello di Creazione di report elettronici (ER) per utilizzare le dimensioni finanziarie come origine dati per i report ER. (Parte 4)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a06936da71d7b05f312a99c8c11d148403d29c3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752390"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a><span data-ttu-id="75a48-104">ER Utilizzare le dimensioni finanziarie come origine dati (Parte 4: eseguire il report)</span><span class="sxs-lookup"><span data-stu-id="75a48-104">ER Use financial dimensions as a data source (Part 4 - Run the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="75a48-105">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.</span><span class="sxs-lookup"><span data-stu-id="75a48-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="75a48-106">Queste operazioni possono essere eseguite nella società DEMF.</span><span class="sxs-lookup"><span data-stu-id="75a48-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="75a48-107">Per effettuare questi passaggi, è innanzitutto necessario completare i passaggi nella procedura "ER Usare dimensioni finanziarie come origine dati (parte 3: progettare il report)".</span><span class="sxs-lookup"><span data-stu-id="75a48-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 3: Design the report)" procedure.</span></span> <span data-ttu-id="75a48-108">È inoltre necessario configurare i tipi di documento predefiniti nella pagina Parametri per la creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="75a48-108">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="75a48-109">I tipi di documento predefiniti vengono impostati anche quando si scarica e importa qualsiasi configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="75a48-109">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="75a48-110">Eseguire un report</span><span class="sxs-lookup"><span data-stu-id="75a48-110">Run report</span></span>
1. <span data-ttu-id="75a48-111">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="75a48-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="75a48-112">Nella struttura espandere 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="75a48-112">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="75a48-113">Nella struttura selezionare 'Modello di esempio dimensioni finanziarie\Report dei giornali di registrazione di contabilità generale'.</span><span class="sxs-lookup"><span data-stu-id="75a48-113">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="75a48-114">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="75a48-114">Click Run.</span></span>
<span data-ttu-id="75a48-115">![Pagina delle configurazioni ER](../media/er-financial-dimensions-guides-run1.png)</span><span class="sxs-lookup"><span data-stu-id="75a48-115">![ER configurations page](../media/er-financial-dimensions-guides-run1.png)</span></span>
5. <span data-ttu-id="75a48-116">Nel campo Nome dimensione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="75a48-116">In the Dimension name field, enter or select a value.</span></span>
    * <span data-ttu-id="75a48-117">Per selezionare tutte le dimensioni della società corrente, immettere le seguenti informazioni: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="75a48-117">To select all dimensions in the current company, enter the following information:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
![Pagina delle configurazioni ER](../media/er-financial-dimensions-guides-run2.png)
6. <span data-ttu-id="75a48-119">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="75a48-119">Expand the Records to include section.</span></span>
7. <span data-ttu-id="75a48-120">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="75a48-120">Click Filter.</span></span>
8. <span data-ttu-id="75a48-121">Selezionare la riga relativa alla tabella Giornale di registrazione contabile e il campo Numero batch giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="75a48-121">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="75a48-122">Nel campo Criteri digitare '00057'.</span><span class="sxs-lookup"><span data-stu-id="75a48-122">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="75a48-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="75a48-123">Click OK.</span></span>
11. <span data-ttu-id="75a48-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="75a48-124">Click OK.</span></span>
<span data-ttu-id="75a48-125">![Pagina delle configurazioni ER](../media/er-financial-dimensions-guides-run3.png)</span><span class="sxs-lookup"><span data-stu-id="75a48-125">![ER configurations page](../media/er-financial-dimensions-guides-run3.png)</span></span>
    * <span data-ttu-id="75a48-126">Esaminare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="75a48-126">Review the generated output.</span></span> <span data-ttu-id="75a48-127">Per ciascuna transazione del batch selezionato, le dimensioni finanziarie del set di dimensioni corrispondente vengono presentate.</span><span class="sxs-lookup"><span data-stu-id="75a48-127">For each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="75a48-128">Eseguire questo report e selezionare dimensioni diverse per vedere che il report non dipende dal numero di dimensioni selezionate o dal numero di dimensioni configurate per questa istanza.</span><span class="sxs-lookup"><span data-stu-id="75a48-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  
![Pagina delle configurazioni ER](../media/er-financial-dimensions-guides-run4.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]