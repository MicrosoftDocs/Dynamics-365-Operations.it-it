---
title: 'ER Utilizzare intervalli espandibili orizzontalmente per aggiungere dinamicamente le colonne in report di Excel (Parte 2: eseguire il formato)'
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la generazione di report come file di fogli di lavoro (Excel) OPENXML in cui le colonne richieste possono essere create in modo dinamico come intervalli espandibili orizzontalmente.
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
ms.openlocfilehash: 33c1a3134659bb66a67166fec3d7f53af0aa4c6c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "361063"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2-run-format"></a><span data-ttu-id="3b089-103">ER utilizzare intervalli espandibili orizzontalmente per aggiungere dinamicamente le colonne in report di Excel (parte 2: eseguire il formato)</span><span class="sxs-lookup"><span data-stu-id="3b089-103">ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 2: Run format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3b089-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la generazione di report come file di fogli di lavoro (Excel) OPENXML in cui le colonne richieste possono essere create in modo dinamico come intervalli espandibili orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="3b089-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="3b089-105">Queste operazioni possono essere eseguite nella società DEMF.</span><span class="sxs-lookup"><span data-stu-id="3b089-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="3b089-106">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura 'ER Usare intervalli espandibili orizzontalmente per aggiungere colonne in modo dinamico in report di Excel (parte 1: progettare il formato)'.</span><span class="sxs-lookup"><span data-stu-id="3b089-106">To complete these steps, you must first complete the steps in the “ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)” procedure.</span></span>

<span data-ttu-id="3b089-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="3b089-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="find-created-format"></a><span data-ttu-id="3b089-108">Trovare il formato creato</span><span class="sxs-lookup"><span data-stu-id="3b089-108">Find created format</span></span>
1. <span data-ttu-id="3b089-109">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="3b089-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="3b089-110">Nella struttura espandere 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="3b089-110">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="3b089-111">Nella struttura selezionare 'Modello di esempio dimensioni finanziarie\Report di esempio con intervalli espandibili orizzontalmente'.</span><span class="sxs-lookup"><span data-stu-id="3b089-111">In the tree, select 'Financial dimensions sample model\Sample report with horizontally expandable ranges'.</span></span>

## <a name="execute-format-to-create-excel-output"></a><span data-ttu-id="3b089-112">Eseguire il formato per creare l'output di Excel</span><span class="sxs-lookup"><span data-stu-id="3b089-112">Execute format to create Excel output</span></span>
1. <span data-ttu-id="3b089-113">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="3b089-113">Click Run.</span></span>
2. <span data-ttu-id="3b089-114">Nel campo Nome dimensione, digitare 'BusinessUnit;CostCenter;Department'.</span><span class="sxs-lookup"><span data-stu-id="3b089-114">In the Dimension name field, type 'BusinessUnit;CostCenter;Department'.</span></span>
    * <span data-ttu-id="3b089-115">Nel campo Nome dimensione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="3b089-115">In the Dimension name field, enter or select a value.</span></span>  <span data-ttu-id="3b089-116">Per selezionare tutte le dimensioni della società corrente, immettere quanto segue: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="3b089-116">To select all dimensions for the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
3. <span data-ttu-id="3b089-117">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="3b089-117">Expand the Records to include section.</span></span>
4. <span data-ttu-id="3b089-118">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="3b089-118">Click Filter.</span></span>
5. <span data-ttu-id="3b089-119">Selezionare la riga relativa alla tabella Giornale di registrazione contabile e il campo Numero batch giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="3b089-119">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
6. <span data-ttu-id="3b089-120">Nel campo Criteri digitare '00057..00058'.</span><span class="sxs-lookup"><span data-stu-id="3b089-120">In the Criteria field, type '00057..00058'.</span></span>
    * <span data-ttu-id="3b089-121">00057..00058</span><span class="sxs-lookup"><span data-stu-id="3b089-121">00057..00058</span></span>  
7. <span data-ttu-id="3b089-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3b089-122">Click OK.</span></span>
8. <span data-ttu-id="3b089-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3b089-123">Click OK.</span></span>
    * <span data-ttu-id="3b089-124">Esaminare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="3b089-124">Review the generated output.</span></span> <span data-ttu-id="3b089-125">Si noti che il file di Excel appena creato contiene lo stesso numero di colonne selezionate per le dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="3b089-125">Note that the newly created Excel file contains the same number of columns that were selected for financial dimensions.</span></span> <span data-ttu-id="3b089-126">L'intestazione del report nelle colonne rappresenta i nomi delle dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="3b089-126">The report header in those columns represents financial dimensions’ names.</span></span> <span data-ttu-id="3b089-127">Le righe delle transazioni nelle colonne rappresentano le dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="3b089-127">The transactions’ lines in those columns represent financial dimensions.</span></span> <span data-ttu-id="3b089-128">Eseguire questo report e selezionare dimensioni diverse per vedere che il report non dipende dal numero di dimensioni selezionate o dal numero di dimensioni configurate per l'istanza di Dynamics 365 for Finance and Operations, edizione Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3b089-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations, Enterprise edition instance.</span></span>  

