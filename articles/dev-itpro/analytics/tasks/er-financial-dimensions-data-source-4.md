--- 
title: Eseguire un report che utilizza le dimensioni finanziarie come origine dati per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: cdecf5fb3f3047a56353ee6d4a8f94957f508e4b
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="run-a-report-that-uses-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a><span data-ttu-id="e65fe-103">Eseguire un report che utilizza le dimensioni finanziarie come origine dati per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="e65fe-103">Run a report that uses financial dimensions as a data source for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e65fe-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.</span><span class="sxs-lookup"><span data-stu-id="e65fe-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="e65fe-105">Queste operazioni possono essere eseguite nella società DEMF.</span><span class="sxs-lookup"><span data-stu-id="e65fe-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="e65fe-106">Per effettuare questi passaggi, è innanzitutto necessario completare i passaggi nella procedura 'ER Usare dimensioni finanziarie come origine dati (parte 3: progettare il report)'.</span><span class="sxs-lookup"><span data-stu-id="e65fe-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 3: Design the report)” procedure.</span></span> <span data-ttu-id="e65fe-107">È inoltre necessario configurare i tipi di documento predefiniti nella pagina Parametri per la creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="e65fe-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="e65fe-108">I tipi di documento predefiniti vengono impostati anche quando si scarica e importa qualsiasi configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="e65fe-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="e65fe-109">Eseguire un report</span><span class="sxs-lookup"><span data-stu-id="e65fe-109">Run report</span></span>
1. <span data-ttu-id="e65fe-110">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="e65fe-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="e65fe-111">Nella struttura espandere 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="e65fe-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="e65fe-112">Nella struttura selezionare 'Modello di esempio dimensioni finanziarie\Report dei giornali di registrazione di contabilità generale'.</span><span class="sxs-lookup"><span data-stu-id="e65fe-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="e65fe-113">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="e65fe-113">Click Run.</span></span>
5. <span data-ttu-id="e65fe-114">Nel campo Nome dimensione, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e65fe-114">In the Dimension name field, In the Dimension name field, enter or select a value..</span></span>
    * <span data-ttu-id="e65fe-115">Per selezionare tutte le dimensioni della società corrente, immettere quanto segue: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="e65fe-115">To select all dimensions in the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
6. <span data-ttu-id="e65fe-116">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="e65fe-116">Expand the Records to include section.</span></span>
7. <span data-ttu-id="e65fe-117">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="e65fe-117">Click Filter.</span></span>
8. <span data-ttu-id="e65fe-118">Selezionare la riga relativa alla tabella Giornale di registrazione contabile e il campo Numero batch giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="e65fe-118">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="e65fe-119">Nel campo Criteri digitare '00057'.</span><span class="sxs-lookup"><span data-stu-id="e65fe-119">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="e65fe-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e65fe-120">Click OK.</span></span>
11. <span data-ttu-id="e65fe-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e65fe-121">Click OK.</span></span>
    * <span data-ttu-id="e65fe-122">Esaminare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="e65fe-122">Review the generated output.</span></span> <span data-ttu-id="e65fe-123">Tenere presente che per ciascuna transazione del batch selezionato, le dimensioni finanziarie del set di dimensioni corrispondente vengono presentate.</span><span class="sxs-lookup"><span data-stu-id="e65fe-123">Note that for each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="e65fe-124">Eseguire questo report e selezionare dimensioni diverse per vedere che il report non dipende dal numero di dimensioni selezionate o dal numero di dimensioni configurate per l'istanza di Dynamics 365 for Finance and Operations, Enterprise edition.</span><span class="sxs-lookup"><span data-stu-id="e65fe-124">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations, Enterprise edition instance.</span></span>  


