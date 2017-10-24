--- 
title: Eseguire un formato che utilizza gli intervalli espandibili orizzontalmente per aggiungere colonne in modo dinamico ai report di Excel per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la generazione di report come file di fogli di lavoro (Excel) OPENXML in cui le colonne richieste possono essere create in modo dinamico come intervalli espandibili orizzontalmente."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.openlocfilehash: 8e5c53905b903bc5242625283f3b093144243cf9
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="run-a-format-that-uses-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-for-electronic-reporting-er"></a><span data-ttu-id="d98c9-103">Eseguire un formato che utilizza gli intervalli espandibili orizzontalmente per aggiungere colonne in modo dinamico ai report di Excel per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="d98c9-103">Run a format that uses horizontally-expandable ranges to dynamically add columns in Excel reports for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d98c9-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la generazione di report come file di fogli di lavoro (Excel) OPENXML in cui le colonne richieste possono essere create in modo dinamico come intervalli espandibili orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="d98c9-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="d98c9-105">Queste operazioni possono essere eseguite nella società DEMF.</span><span class="sxs-lookup"><span data-stu-id="d98c9-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="d98c9-106">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura 'ER Usare intervalli espandibili orizzontalmente per aggiungere colonne in modo dinamico in report di Excel (parte 1: progettare il formato)'.</span><span class="sxs-lookup"><span data-stu-id="d98c9-106">To complete these steps, you must first complete the steps in the “ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)” procedure.</span></span>

<span data-ttu-id="d98c9-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="d98c9-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="find-created-format"></a><span data-ttu-id="d98c9-108">Trovare il formato creato</span><span class="sxs-lookup"><span data-stu-id="d98c9-108">Find created format</span></span>
1. <span data-ttu-id="d98c9-109">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="d98c9-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="d98c9-110">Nella struttura espandere 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="d98c9-110">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="d98c9-111">Nella struttura selezionare 'Modello di esempio dimensioni finanziarie\Report di esempio con intervalli espandibili orizzontalmente'.</span><span class="sxs-lookup"><span data-stu-id="d98c9-111">In the tree, select 'Financial dimensions sample model\Sample report with horizontally expandable ranges'.</span></span>

## <a name="execute-format-to-create-excel-output"></a><span data-ttu-id="d98c9-112">Eseguire il formato per creare l'output di Excel</span><span class="sxs-lookup"><span data-stu-id="d98c9-112">Execute format to create Excel output</span></span>
1. <span data-ttu-id="d98c9-113">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="d98c9-113">Click Run.</span></span>
2. <span data-ttu-id="d98c9-114">Nel campo Nome dimensione, digitare 'BusinessUnit;CostCenter;Department'.</span><span class="sxs-lookup"><span data-stu-id="d98c9-114">In the Dimension name field, type 'BusinessUnit;CostCenter;Department'.</span></span>
    * <span data-ttu-id="d98c9-115">Nel campo Nome dimensione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d98c9-115">In the Dimension name field, enter or select a value.</span></span>  <span data-ttu-id="d98c9-116">Per selezionare tutte le dimensioni della società corrente, immettere quanto segue: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="d98c9-116">To select all dimensions for the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
3. <span data-ttu-id="d98c9-117">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="d98c9-117">Expand the Records to include section.</span></span>
4. <span data-ttu-id="d98c9-118">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="d98c9-118">Click Filter.</span></span>
5. <span data-ttu-id="d98c9-119">Selezionare la riga relativa alla tabella Giornale di registrazione contabile e il campo Numero batch giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d98c9-119">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
6. <span data-ttu-id="d98c9-120">Nel campo Criteri digitare '00057..00058'.</span><span class="sxs-lookup"><span data-stu-id="d98c9-120">In the Criteria field, type '00057..00058'.</span></span>
    * <span data-ttu-id="d98c9-121">00057..00058</span><span class="sxs-lookup"><span data-stu-id="d98c9-121">00057..00058</span></span>  
7. <span data-ttu-id="d98c9-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d98c9-122">Click OK.</span></span>
8. <span data-ttu-id="d98c9-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d98c9-123">Click OK.</span></span>
    * <span data-ttu-id="d98c9-124">Esaminare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="d98c9-124">Review the generated output.</span></span> <span data-ttu-id="d98c9-125">Si noti che il file di Excel appena creato contiene lo stesso numero di colonne selezionate per le dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="d98c9-125">Note that the newly created Excel file contains the same number of columns that were selected for financial dimensions.</span></span> <span data-ttu-id="d98c9-126">L'intestazione del report nelle colonne rappresenta i nomi delle dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="d98c9-126">The report header in those columns represents financial dimensions’ names.</span></span> <span data-ttu-id="d98c9-127">Le righe delle transazioni nelle colonne rappresentano le dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="d98c9-127">The transactions’ lines in those columns represent financial dimensions.</span></span> <span data-ttu-id="d98c9-128">Eseguire questo report e selezionare dimensioni diverse per vedere che il report non dipende dal numero di dimensioni selezionate o dal numero di dimensioni configurate per l'istanza di Dynamics 365 for Finance and Operations, Enterprise edition.</span><span class="sxs-lookup"><span data-stu-id="d98c9-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations, Enterprise edition instance.</span></span>  


