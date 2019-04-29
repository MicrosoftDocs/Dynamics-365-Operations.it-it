---
title: Configurare l'integrazione delle retribuzioni tra Talent e Dayforce
description: In questo argomento viene descritto come configurare l'integrazione tra Microsoft Dynamics 365 for Talent e Ceridian Dayforce in modo da poter elaborare è un ciclo di pagamenti.
author: andreabichsel
manager: AnnBe
ms.date: 03/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9a88bf61dbb12520b555ceb7363b1c646d95386e
ms.sourcegitcommit: 204e4554e409c39fbbf7b273ad138ce2809931a8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2019
ms.locfileid: "898446"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="4cf74-103">Configurare l'integrazione retribuzioni tra Talent e Dayforce</span><span class="sxs-lookup"><span data-stu-id="4cf74-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4cf74-104">L'integrazione tra Microsoft Dynamics 365 for Talent e Ceridian Dayforce si basa su vari passaggi di configurazione descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4cf74-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="4cf74-105">È necessario configurare l'integrazione sia in Talent che in Dayforce prima di poter elaborare un ciclo di pagamenti.</span><span class="sxs-lookup"><span data-stu-id="4cf74-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="4cf74-106">Quando si utilizza un servizio, ad esempio Dayforce, per completare i cicli di pagamenti, è necessario abilitare l'integrazione in Talent.</span><span class="sxs-lookup"><span data-stu-id="4cf74-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="4cf74-107">L'integrazione richiede dati specifici da Talent.</span><span class="sxs-lookup"><span data-stu-id="4cf74-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="4cf74-108">Di conseguenza, è necessario verificare che i dati che vengono mappati a Dayforce siano configurati in Talent in modo che supporti l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="4cf74-109">L'integrazione utilizza le seguenti categorie generiche di dati:</span><span class="sxs-lookup"><span data-stu-id="4cf74-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="4cf74-110">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="4cf74-110">Human resources data</span></span>
- <span data-ttu-id="4cf74-111">Dati di compensazione</span><span class="sxs-lookup"><span data-stu-id="4cf74-111">Compensation data</span></span>
- <span data-ttu-id="4cf74-112">Data di retribuzione, ad esempio i cicli di pagamenti, i periodi retributivi e i codici reddito</span><span class="sxs-lookup"><span data-stu-id="4cf74-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="4cf74-113">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-113">Worker data</span></span>

<span data-ttu-id="4cf74-114">In questo argomento vengono descritti i passaggi che è necessario completare per abilitare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="4cf74-115">E vengono descritti i tipi di dati e i dettagli di configurazione necessari all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="4cf74-116">Abilitare l'integrazione</span><span class="sxs-lookup"><span data-stu-id="4cf74-116">Enable the integration</span></span>

<span data-ttu-id="4cf74-117">In Talent è necessario attivare l'integrazione e immettere le informazioni di configurazione per connettersi a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="4cf74-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="4cf74-118">Se si desidera che la transazione contabile prodotta venga importata in Microsoft Dynamics 365 for Finance and Operations, è necessario impostare anche un conto di archiviazione di Microsoft Azure e immettere la stringa di connessione di Archiviazione di Azure in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4cf74-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="4cf74-119">Per attivare l'integrazione in Talent, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="4cf74-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="4cf74-120">Nella pagina **Amministrazione sistema** selezionare **Configurazione di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="4cf74-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="4cf74-121">Immettere l'endpoint FTP (File Transfer Protocol) e il percorso protetto della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="4cf74-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="4cf74-122">Immettere il nome utente e la password dell'utente che accederà al percorso protetto dell'endpoint e della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="4cf74-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="4cf74-123">Verificare la connessione, secondo le esigenze, e impostare l'opzione **Abilita integrazione retribuzioni** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="4cf74-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="4cf74-124">Quando l'integrazione viene attivata, vengono creati i file e il pacchetto di esportazione dei dati e viene impostata la frequenza.</span><span class="sxs-lookup"><span data-stu-id="4cf74-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="4cf74-125">È possibile cambiare la frequenza in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="4cf74-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="4cf74-126">Per altre informazioni sugli account di Archiviazione di Azure e sulle stringhe di connessione di Archiviazione di Azure, vedere gli argomenti di Azure seguenti:</span><span class="sxs-lookup"><span data-stu-id="4cf74-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="4cf74-127">Account di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="4cf74-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="4cf74-128">Configurare le stringhe di connessione di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="4cf74-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="4cf74-129">Configurare i dati</span><span class="sxs-lookup"><span data-stu-id="4cf74-129">Configure your data</span></span> 

<span data-ttu-id="4cf74-130">Per elaborare le retribuzioni, è necessario configurare i dati di Risorse umane in Talent.</span><span class="sxs-lookup"><span data-stu-id="4cf74-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="4cf74-131">È necessario impostare i dati dell'organizzazione, ad esempio mansioni e posizioni, insieme alle informazioni sui benefit e sulle compensazioni.</span><span class="sxs-lookup"><span data-stu-id="4cf74-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="4cf74-132">Queste informazioni includono informazioni sull'impiego, la retribuzione e le detrazioni che sono richieste per generare la retribuzione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="4cf74-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="4cf74-133">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="4cf74-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="4cf74-134">Benefit</span><span class="sxs-lookup"><span data-stu-id="4cf74-134">Benefits</span></span> 

<span data-ttu-id="4cf74-135">Le risorse umane dispongono di strumenti per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori.</span><span class="sxs-lookup"><span data-stu-id="4cf74-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="4cf74-136">Quando si creano i benefit, tenere presenti i seguenti dati e configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="4cf74-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="4cf74-137">Piani di benefit</span><span class="sxs-lookup"><span data-stu-id="4cf74-137">Benefit plans</span></span>

- <span data-ttu-id="4cf74-138">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-138">Plan (required)</span></span>
- <span data-ttu-id="4cf74-139">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-139">Type (required)</span></span>
- <span data-ttu-id="4cf74-140">Impatto retribuzioni (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-140">Payroll impact (required)</span></span>
- <span data-ttu-id="4cf74-141">Recupera arretrati</span><span class="sxs-lookup"><span data-stu-id="4cf74-141">Recover arrears</span></span>
- <span data-ttu-id="4cf74-142">Metodo di detrazione</span><span class="sxs-lookup"><span data-stu-id="4cf74-142">Deduction method</span></span>
- <span data-ttu-id="4cf74-143">Priorità detrazione</span><span class="sxs-lookup"><span data-stu-id="4cf74-143">Deduction priority</span></span>
- <span data-ttu-id="4cf74-144">Periodo limite</span><span class="sxs-lookup"><span data-stu-id="4cf74-144">Limit period</span></span>
- <span data-ttu-id="4cf74-145">Importo limite</span><span class="sxs-lookup"><span data-stu-id="4cf74-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="4cf74-146">Benefit</span><span class="sxs-lookup"><span data-stu-id="4cf74-146">Benefits</span></span>

- <span data-ttu-id="4cf74-147">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-147">Plan (required)</span></span>
- <span data-ttu-id="4cf74-148">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-148">Type (required)</span></span>
- <span data-ttu-id="4cf74-149">Opzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-149">Option (required)</span></span>
- <span data-ttu-id="4cf74-150">ID benefit (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-150">Benefit ID (required)</span></span>
- <span data-ttu-id="4cf74-151">Frequenza</span><span class="sxs-lookup"><span data-stu-id="4cf74-151">Frequency</span></span>
- <span data-ttu-id="4cf74-152">Base</span><span class="sxs-lookup"><span data-stu-id="4cf74-152">Basis</span></span>
- <span data-ttu-id="4cf74-153">Importo o coefficiente</span><span class="sxs-lookup"><span data-stu-id="4cf74-153">Amount or rate</span></span>
- <span data-ttu-id="4cf74-154">Codice di reddito</span><span class="sxs-lookup"><span data-stu-id="4cf74-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="4cf74-155">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="4cf74-155">Supported frequencies</span></span> 

- <span data-ttu-id="4cf74-156">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="4cf74-156">Weekly</span></span>
- <span data-ttu-id="4cf74-157">Bisettimanale</span><span class="sxs-lookup"><span data-stu-id="4cf74-157">Bi-weekly</span></span>
- <span data-ttu-id="4cf74-158">Quindicinale</span><span class="sxs-lookup"><span data-stu-id="4cf74-158">Semi-monthly</span></span>
- <span data-ttu-id="4cf74-159">Ogni mese</span><span class="sxs-lookup"><span data-stu-id="4cf74-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="4cf74-160">Basi supportate</span><span class="sxs-lookup"><span data-stu-id="4cf74-160">Supported bases</span></span> 

- <span data-ttu-id="4cf74-161">Importo fisso</span><span class="sxs-lookup"><span data-stu-id="4cf74-161">Fixed amount</span></span>
- <span data-ttu-id="4cf74-162">Percentuale di redditi</span><span class="sxs-lookup"><span data-stu-id="4cf74-162">Percent of earnings</span></span>
- <span data-ttu-id="4cf74-163">Ore di produzione</span><span class="sxs-lookup"><span data-stu-id="4cf74-163">Productive hours</span></span>

<span data-ttu-id="4cf74-164">Dayforce crea le seguenti detrazioni, in base all'impatto delle retribuzioni definito nel piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="4cf74-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="4cf74-165">Selezione in Talent</span><span class="sxs-lookup"><span data-stu-id="4cf74-165">Selection in Talent</span></span>        | <span data-ttu-id="4cf74-166">Risultato in Dayforce</span><span class="sxs-lookup"><span data-stu-id="4cf74-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="4cf74-167">Nessuna</span><span class="sxs-lookup"><span data-stu-id="4cf74-167">None</span></span>                       | <span data-ttu-id="4cf74-168">Non viene creata alcuna detrazione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="4cf74-169">Solo detrazione</span><span class="sxs-lookup"><span data-stu-id="4cf74-169">Deduction only</span></span>             | <span data-ttu-id="4cf74-170">Viene creata una detrazione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="4cf74-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="4cf74-171">Solo contribuzione</span><span class="sxs-lookup"><span data-stu-id="4cf74-171">Contribution only</span></span>          | <span data-ttu-id="4cf74-172">Viene creata una detrazione del datore di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4cf74-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="4cf74-173">Detrazione e contribuzione</span><span class="sxs-lookup"><span data-stu-id="4cf74-173">Deduction and contribution</span></span> | <span data-ttu-id="4cf74-174">Vengono create detrazioni del datore di lavoro e del dipendente.</span><span class="sxs-lookup"><span data-stu-id="4cf74-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="4cf74-175">Per altre informazioni su come definire e gestire un programma di benefit, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4cf74-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="4cf74-176">Realizzare un programma di benefit per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="4cf74-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="4cf74-177">Creare un nuovo benefit</span><span class="sxs-lookup"><span data-stu-id="4cf74-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="4cf74-178">Definire regole e criteri di idoneità ai benefit</span><span class="sxs-lookup"><span data-stu-id="4cf74-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="4cf74-179">Iscrivere e rimuovere benefit da lavoratori</span><span class="sxs-lookup"><span data-stu-id="4cf74-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="4cf74-180">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="4cf74-180">Compensation</span></span> 

<span data-ttu-id="4cf74-181">La gestione delle retribuzioni consente di controllare la liquidazione dei premi e della retribuzione base.</span><span class="sxs-lookup"><span data-stu-id="4cf74-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="4cf74-182">La retribuzione di base fissa di un dipendente e gli aumenti per merito sono controllati mediante piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="4cf74-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="4cf74-183">È possibile controllare il pagamento degli incentivi, ad esempio il pagamento dei bonus, dei premi produttività, dei diritti di opzione, delle sovvenzioni, oltre che dei premi una tantum, tramite i piani di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="4cf74-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="4cf74-184">Dayforce utilizza le informazioni sulla compensazione per calcolare la retribuzione annuale o oraria di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="4cf74-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="4cf74-185">I piani di retribuzione fissa e conversioni della retribuzione sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="4cf74-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="4cf74-186">I dipendenti devono essere associati a un piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="4cf74-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="4cf74-187">Per ulteriori informazioni sui piani di retribuzione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4cf74-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="4cf74-188">Creare i piani di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="4cf74-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="4cf74-189">Creare i piani di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="4cf74-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="4cf74-190">Sviluppare una struttura e piani di stipendi/retribuzioni</span><span class="sxs-lookup"><span data-stu-id="4cf74-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="4cf74-191">Processo retributivo</span><span class="sxs-lookup"><span data-stu-id="4cf74-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="4cf74-192">Definire il processo retributivo e calcolare i risultati</span><span class="sxs-lookup"><span data-stu-id="4cf74-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="4cf74-193">Iscrivere un dipendente a un piano di retribuzione fisso</span><span class="sxs-lookup"><span data-stu-id="4cf74-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="4cf74-194">Iscrivere un dipendente a un piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="4cf74-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="4cf74-195">Mansioni</span><span class="sxs-lookup"><span data-stu-id="4cf74-195">Jobs</span></span> 

<span data-ttu-id="4cf74-196">Una mansione è una raccolta delle attività e delle responsabilità proprie della persona assegnata a una mansione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="4cf74-197">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="4cf74-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="4cf74-198">Impostazione dei componenti di una mansione</span><span class="sxs-lookup"><span data-stu-id="4cf74-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="4cf74-199">Definire nuovi processi</span><span class="sxs-lookup"><span data-stu-id="4cf74-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="4cf74-200">Posizioni</span><span class="sxs-lookup"><span data-stu-id="4cf74-200">Positions</span></span>

<span data-ttu-id="4cf74-201">Una posizione è una singola istanza di un processo.</span><span class="sxs-lookup"><span data-stu-id="4cf74-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="4cf74-202">Ad esempio, la posizione "Manager vendite (Est") è una delle posizioni associate alla mansione "Manager vendite".</span><span class="sxs-lookup"><span data-stu-id="4cf74-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="4cf74-203">Una posizione è presente in un reparto.</span><span class="sxs-lookup"><span data-stu-id="4cf74-203">A position exists in a department.</span></span> <span data-ttu-id="4cf74-204">È possibile associare un solo lavoratore a ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="4cf74-205">Tenere a mente i seguenti dati e la configurazione quando si impostano le posizioni:</span><span class="sxs-lookup"><span data-stu-id="4cf74-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="4cf74-206">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-206">Position (required)</span></span>
- <span data-ttu-id="4cf74-207">Descrizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-207">Description (required)</span></span>
- <span data-ttu-id="4cf74-208">Mansione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-208">Job (required)</span></span>
- <span data-ttu-id="4cf74-209">Reparto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-209">Department (required)</span></span>
- <span data-ttu-id="4cf74-210">Tipo di posizione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-210">Position type (required)</span></span>
- <span data-ttu-id="4cf74-211">Equivalente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="4cf74-211">Full-time equivalent</span></span>
- <span data-ttu-id="4cf74-212">Ore regolari annuali (obbligatorie)</span><span class="sxs-lookup"><span data-stu-id="4cf74-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="4cf74-213">Pagamento in base alla persona giuridica (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="4cf74-214">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="4cf74-214">Pay cycle (required)</span></span>
- <span data-ttu-id="4cf74-215">Dimensione finanziaria predefinita - Centro di costo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="4cf74-216">Assegnazione del lavoratore - Lavoratore, inizio assegnazione, fine assegnazione, codice motivo</span><span class="sxs-lookup"><span data-stu-id="4cf74-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="4cf74-217">Se nello stesso reparto più posizioni sono associate alla stessa mansione, vengono consolidate in una singola posizione in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="4cf74-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="4cf74-218">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="4cf74-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="4cf74-219">Organizzare la forza lavoro utilizzando i reparti, le mansioni e le posizioni</span><span class="sxs-lookup"><span data-stu-id="4cf74-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="4cf74-220">Impostare le posizioni</span><span class="sxs-lookup"><span data-stu-id="4cf74-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="4cf74-221">Reparti</span><span class="sxs-lookup"><span data-stu-id="4cf74-221">Departments</span></span>

<span data-ttu-id="4cf74-222">Un reparto è un'unità operativa che rappresenta una categoria o un'area operativa di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="4cf74-223">Un reparto è responsabile di una specifica area dell'organizzazione, ad esempio la vendita, la contabilità o le risorse umane.</span><span class="sxs-lookup"><span data-stu-id="4cf74-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="4cf74-224">È possibile utilizzare i reparti per creare report sulle aree operative.</span><span class="sxs-lookup"><span data-stu-id="4cf74-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="4cf74-225">I reparti possono essere responsabili di profitti e perdite.</span><span class="sxs-lookup"><span data-stu-id="4cf74-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="4cf74-226">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="4cf74-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="4cf74-227">Creare un reparto e associarlo alla gerarchia reparti</span><span class="sxs-lookup"><span data-stu-id="4cf74-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="4cf74-228">Definire nuovi reparti</span><span class="sxs-lookup"><span data-stu-id="4cf74-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="4cf74-229">Cicli e periodi retributivi</span><span class="sxs-lookup"><span data-stu-id="4cf74-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="4cf74-230">Un ciclo retributivo determina la frequenza di elaborazione delle retribuzioni e i giorni specifici in cui i lavoratori vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="4cf74-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="4cf74-231">Un ciclo retributivo può essere ad esempio mensile e i dipendenti possono essere pagati l'ultimo giorno del mese.</span><span class="sxs-lookup"><span data-stu-id="4cf74-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="4cf74-232">Un ciclo retributivo può in alternativa essere settimanale e i dipendenti possono essere pagati il giovedì successivo alla fine del periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="4cf74-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="4cf74-233">I cicli retributivi vengono assegnati alle posizioni per controllare quando i lavoratori in tali posizioni vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="4cf74-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="4cf74-234">Dopo aver creato i cicli retributivi, è possibile generare periodi retributivi per ogni ciclo.</span><span class="sxs-lookup"><span data-stu-id="4cf74-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="4cf74-235">Ogni periodo retributivo include una data di pagamento predefinita in base alle informazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="4cf74-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="4cf74-236">Tuttavia, è possibile modificare la data di pagamento predefinita in un periodo retributivo per consentire eccezioni, ad esempio quando la data di pagamento cade in un giorno festivo.</span><span class="sxs-lookup"><span data-stu-id="4cf74-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="4cf74-237">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="4cf74-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="4cf74-238">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="4cf74-238">Pay cycle (required)</span></span>
- <span data-ttu-id="4cf74-239">Frequenza ciclo retributivo (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="4cf74-240">Data di inizio del periodo (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="4cf74-241">Data di pagamento predefinita (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="4cf74-242">Queste informazioni sono integrate con Dayforce come gruppi retributivi e sono separata in base al paese o alla regione per ogni ciclo retributivo.</span><span class="sxs-lookup"><span data-stu-id="4cf74-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="4cf74-243">Prima dell'integrazione è necessario generare almeno un periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="4cf74-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="4cf74-244">Dayforce genera calendari di gruppi retributivi e date di pagamento, in base alla data di inizio del primo periodo retributivo e alla data di pagamento predefinita che viene impostata in Talent.</span><span class="sxs-lookup"><span data-stu-id="4cf74-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="4cf74-245">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="4cf74-245">Earning codes</span></span>

<span data-ttu-id="4cf74-246">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="4cf74-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="4cf74-247">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="4cf74-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="4cf74-248">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="4cf74-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="4cf74-249">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-249">Earning Code (required)</span></span>
- <span data-ttu-id="4cf74-250">descrizione</span><span class="sxs-lookup"><span data-stu-id="4cf74-250">Description</span></span>
- <span data-ttu-id="4cf74-251">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="4cf74-251">Unit of measure</span></span>
- <span data-ttu-id="4cf74-252">Produttivo</span><span class="sxs-lookup"><span data-stu-id="4cf74-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="4cf74-253">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-253">Worker data</span></span>

<span data-ttu-id="4cf74-254">I record per i diversi tipi di lavoratori a disposizione sono importanti per i sistemi di gestione delle risorse umane e delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="4cf74-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="4cf74-255">Le informazioni immesse possono essere utilizzate per tenere traccia di informazioni personali e sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="4cf74-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="4cf74-256">È possibile gestire le seguenti informazioni per i lavoratori:</span><span class="sxs-lookup"><span data-stu-id="4cf74-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="4cf74-257">**Base** - Gestire le informazioni di base su un lavoratore, ad esempio le informazioni sui contatti, le informazioni demografiche, le informazioni di identificazione, le informazioni sulla famiglia, lo stato di servizio militare, le informazioni sull'espatrio, e i contatti personali e di emergenza.</span><span class="sxs-lookup"><span data-stu-id="4cf74-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="4cf74-258">**Impiego** - Consente di gestire le informazioni sull'impiego di un lavoratore, ad esempio rapporto con l'organizzazione o la società, assegnazione della posizione, date di inizio e fine, idoneità al lavoro, condizioni di impiego, pensionamento, ferie e trasferimento.</span><span class="sxs-lookup"><span data-stu-id="4cf74-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="4cf74-259">**Congedo e assenza** - Consente di gestire le informazioni sulle assenze di un lavoratore, ad esempio calendari di lavoro, transazioni assenze e impostazione assenze.</span><span class="sxs-lookup"><span data-stu-id="4cf74-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="4cf74-260">**Retribuzioni** - Consente di gestire le informazioni sui piani di retribuzione di un lavoratore, ad esempio registrazione del piano, premi, prestazioni, provvigione, dati fiscali, pensionamento e detrazioni sullo stipendio.</span><span class="sxs-lookup"><span data-stu-id="4cf74-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="4cf74-261">Quando si immettono le informazioni su un lavoratore, tenere presenti i seguenti dati e le configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="4cf74-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="4cf74-262">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="4cf74-262">General information</span></span>

- <span data-ttu-id="4cf74-263">Numero dipendente (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-263">Personnel number (required)</span></span>
- <span data-ttu-id="4cf74-264">Nome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-264">First name (required)</span></span>
- <span data-ttu-id="4cf74-265">Cognome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-265">Last name (required)</span></span>
- <span data-ttu-id="4cf74-266">Secondo nome</span><span class="sxs-lookup"><span data-stu-id="4cf74-266">Middle name</span></span>
- <span data-ttu-id="4cf74-267">Data di anzianità</span><span class="sxs-lookup"><span data-stu-id="4cf74-267">Seniority date</span></span>
- <span data-ttu-id="4cf74-268">Nome noto</span><span class="sxs-lookup"><span data-stu-id="4cf74-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="4cf74-269">Informazioni personali</span><span class="sxs-lookup"><span data-stu-id="4cf74-269">Personal information</span></span>

- <span data-ttu-id="4cf74-270">Stato civile (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-270">Marital status (required)</span></span>
- <span data-ttu-id="4cf74-271">Data di nascita (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-271">Birth date (required)</span></span>
- <span data-ttu-id="4cf74-272">Sesso (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-272">Gender (required)</span></span>
- <span data-ttu-id="4cf74-273">Persona disabile</span><span class="sxs-lookup"><span data-stu-id="4cf74-273">Person with disabilities</span></span>
- <span data-ttu-id="4cf74-274">Nazionalità paese regione (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="4cf74-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="4cf74-275">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="4cf74-275">Address information</span></span>

- <span data-ttu-id="4cf74-276">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-276">Primary (required)</span></span>
- <span data-ttu-id="4cf74-277">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-277">Country/region (required)</span></span>
- <span data-ttu-id="4cf74-278">Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-278">Postal code (required)</span></span>
- <span data-ttu-id="4cf74-279">Numero civico (obbligatorio) (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="4cf74-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="4cf74-280">Informazioni aggiuntive sull'indirizzo (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="4cf74-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="4cf74-281">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-281">City (required)</span></span>
- <span data-ttu-id="4cf74-282">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-282">State (required)</span></span>
- <span data-ttu-id="4cf74-283">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="4cf74-284">Informazioni contatto</span><span class="sxs-lookup"><span data-stu-id="4cf74-284">Contact information</span></span> 

- <span data-ttu-id="4cf74-285">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-285">Primary (required)</span></span>
- <span data-ttu-id="4cf74-286">Numero contatto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-286">Contact number (required)</span></span>
- <span data-ttu-id="4cf74-287">Interno</span><span class="sxs-lookup"><span data-stu-id="4cf74-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="4cf74-288">Informazioni sulle retribuzioni e codici di reddito</span><span class="sxs-lookup"><span data-stu-id="4cf74-288">Payroll information and earning codes</span></span>

<span data-ttu-id="4cf74-289">Ai dipendenti possono essere assegnati redditi specifici a una determinata frequenza di pagamento e un metodo di pagamento preferito.</span><span class="sxs-lookup"><span data-stu-id="4cf74-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="4cf74-290">I campi seguenti vengono utilizzati in Dayforce per garantire che le preferenze e le impostazioni vengano utilizzate.</span><span class="sxs-lookup"><span data-stu-id="4cf74-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="4cf74-291">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="4cf74-291">Earning codes</span></span>

- <span data-ttu-id="4cf74-292">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-292">Position (required)</span></span>
- <span data-ttu-id="4cf74-293">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-293">Earning Code (required)</span></span>
- <span data-ttu-id="4cf74-294">Frequenza (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-294">Frequency (required)</span></span>
- <span data-ttu-id="4cf74-295">Importo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="4cf74-296">Informazioni retribuzioni</span><span class="sxs-lookup"><span data-stu-id="4cf74-296">Payroll information</span></span>

- <span data-ttu-id="4cf74-297">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="4cf74-297">Payment Method</span></span>
- <span data-ttu-id="4cf74-298">Area economica (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-298">Economic Region (required)</span></span>
- <span data-ttu-id="4cf74-299">ID benefit dipendente</span><span class="sxs-lookup"><span data-stu-id="4cf74-299">Employee Benefits ID</span></span>
- <span data-ttu-id="4cf74-300">Numero documento identità (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-300">National ID Number (required)</span></span>
- <span data-ttu-id="4cf74-301">Numero servizio militare</span><span class="sxs-lookup"><span data-stu-id="4cf74-301">Military Service Number</span></span>
- <span data-ttu-id="4cf74-302">ID turno (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-302">Shift ID (required)</span></span>
- <span data-ttu-id="4cf74-303">Numero imposta (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-303">Tax Number (required)</span></span>
- <span data-ttu-id="4cf74-304">ID sindacato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-304">Union ID (required)</span></span>
- <span data-ttu-id="4cf74-305">ID giorno lavorativo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-305">Work Day ID (required)</span></span>
- <span data-ttu-id="4cf74-306">Numero permesso di lavoro</span><span class="sxs-lookup"><span data-stu-id="4cf74-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="4cf74-307">Per il metodo di pagamento, il Messico supporta **Contante**, **Assegno** (l'assegno fisico della società) e **Pagamento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="4cf74-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="4cf74-308">Se non viene specificato alcun metodo di pagamento, **Assegno** è 'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4cf74-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="4cf74-309">Dettagli impiego</span><span class="sxs-lookup"><span data-stu-id="4cf74-309">Employment details</span></span>

<span data-ttu-id="4cf74-310">Lo storico dei dettagli impiego viene utilizzato come informazioni chiave da cui derivare gli stati di assunzione, termine e riassunzione di un dipendente Dayforce.</span><span class="sxs-lookup"><span data-stu-id="4cf74-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="4cf74-311">Dayforce supporta solo un record di impiego attivo alla volta.</span><span class="sxs-lookup"><span data-stu-id="4cf74-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="4cf74-312">Data di inizio impiego (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-312">Employment start date (required)</span></span>
- <span data-ttu-id="4cf74-313">Data di fine impiego</span><span class="sxs-lookup"><span data-stu-id="4cf74-313">Employment end date</span></span>
- <span data-ttu-id="4cf74-314">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="4cf74-314">Start date</span></span>
- <span data-ttu-id="4cf74-315">Data di inizio rettificata</span><span class="sxs-lookup"><span data-stu-id="4cf74-315">Adjusted start date</span></span>
- <span data-ttu-id="4cf74-316">Data fine rapporto (obbligatoria con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="4cf74-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="4cf74-317">Motivo fine rapporto (obbligatorio con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="4cf74-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="4cf74-318">Le date chiave del dipendente sono derivate utilizzando le informazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="4cf74-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="4cf74-319">Talent</span><span class="sxs-lookup"><span data-stu-id="4cf74-319">Talent</span></span>                | <span data-ttu-id="4cf74-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="4cf74-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="4cf74-321">Data di assunzione più recente</span><span class="sxs-lookup"><span data-stu-id="4cf74-321">Most recent hire date</span></span> | <span data-ttu-id="4cf74-322">Inizio dell'impiego del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="4cf74-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="4cf74-323">Data fine rapporto</span><span class="sxs-lookup"><span data-stu-id="4cf74-323">Termination date</span></span>      | <span data-ttu-id="4cf74-324">Data di fine rapporto del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="4cf74-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="4cf74-325">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="4cf74-325">Start date</span></span>            | <span data-ttu-id="4cf74-326">Data di inizio rettificata, data di inizio o inizio dell'impiego del record corrente dello storico di impiego non attivo</span><span class="sxs-lookup"><span data-stu-id="4cf74-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="4cf74-327">Data di assunzione originale</span><span class="sxs-lookup"><span data-stu-id="4cf74-327">Original hire date</span></span>    | <span data-ttu-id="4cf74-328">Inizio dell'impiego del record dello storico di impiego meno recente</span><span class="sxs-lookup"><span data-stu-id="4cf74-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="4cf74-329">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="4cf74-329">Compensation</span></span>

<span data-ttu-id="4cf74-330">Un piano di retribuzione fissa deve essere associato alla posizione primaria di ogni dipendente durante un periodo di impiego.</span><span class="sxs-lookup"><span data-stu-id="4cf74-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="4cf74-331">Questo periodo inizia alla data in cui il dipendente è stato assunto (o la data di inizio dell'impiego) e continua fino alla fine del rapporto.</span><span class="sxs-lookup"><span data-stu-id="4cf74-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="4cf74-332">Data di validità (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-332">Effective Date (required)</span></span>
- <span data-ttu-id="4cf74-333">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="4cf74-333">Expiration date</span></span>
- <span data-ttu-id="4cf74-334">Retribuzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-334">Pay Rate (required)</span></span>
- <span data-ttu-id="4cf74-335">Conversioni retribuzione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="4cf74-336">Equivalente annuale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="4cf74-337">Equivalente orario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="4cf74-338">Se un dipendente a ore ha più posizioni, la retribuzione fissa della posizione primaria viene importata in Dayforce come il tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="4cf74-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="4cf74-339">Per le posizioni non principali, la tariffa oraria viene salvata nella posizione corrispondente in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="4cf74-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="4cf74-340">Se un dipendente stipendiato ha più posizioni, la tariffa oraria cumulativa e lo stipendio annuale di tutte le posizioni attive vengono calcolati e utilizzati come tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="4cf74-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="4cf74-341">Numeri di identificazione</span><span class="sxs-lookup"><span data-stu-id="4cf74-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="4cf74-342">Numero di Previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="4cf74-342">Social Security identifier</span></span> 

<span data-ttu-id="4cf74-343">Ogni dipendente deve avere un identificatore primario.</span><span class="sxs-lookup"><span data-stu-id="4cf74-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="4cf74-344">Questo identificatore deve essere di tipo identificatore **SSN**.</span><span class="sxs-lookup"><span data-stu-id="4cf74-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="4cf74-345">In Dayforce, viene ricavato automaticamente come identificatore di previdenza sociale del dipendente per l'assunzione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="4cf74-346">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-346">Primary (required)</span></span>
- <span data-ttu-id="4cf74-347">Tipo di identificazione = "SSN"</span><span class="sxs-lookup"><span data-stu-id="4cf74-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="4cf74-348">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="4cf74-348">Issued Date</span></span>
- <span data-ttu-id="4cf74-349">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="4cf74-349">Expiration Date</span></span>

<span data-ttu-id="4cf74-350">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **SSN**.</span><span class="sxs-lookup"><span data-stu-id="4cf74-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="4cf74-351">Tuttavia, solo il record che è contrassegnato come **Primario** viene integrato in Dayforce, a prescindere che il numero sia attivo o scaduto.</span><span class="sxs-lookup"><span data-stu-id="4cf74-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="4cf74-352">Esborsi e conti bancari</span><span class="sxs-lookup"><span data-stu-id="4cf74-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="4cf74-353">È necessario immettere informazioni sul conto bancario valide per un dipendente che scelga di essere pagato tramite trasferimenti di conto bancario.</span><span class="sxs-lookup"><span data-stu-id="4cf74-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="4cf74-354">Talent</span><span class="sxs-lookup"><span data-stu-id="4cf74-354">Talent</span></span>                         | <span data-ttu-id="4cf74-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="4cf74-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="4cf74-356">Numero conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="4cf74-357">Codice SWIFT (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-357">SWIFT code (required)</span></span>          | <span data-ttu-id="4cf74-358">Campo **ID banca** utilizzato durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="4cf74-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="4cf74-359">Codice filiale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="4cf74-360">Tipo di conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-360">Bank account type (required)</span></span>   | <span data-ttu-id="4cf74-361">Campo **Tipo di conto** utilizzando durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="4cf74-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="4cf74-362">I valori supportati includono **Controllo** e **Retribuzioni**.</span><span class="sxs-lookup"><span data-stu-id="4cf74-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="4cf74-363">I dipendenti che scelgono di essere pagati tramite trasferimenti di conto bancario devono fornire un collegamento a un conto rimanente che è sotto la persona giuridica che ha l'indirizzo primario in Messico ed è associato a un conto bancario valido presso una banca messicana.</span><span class="sxs-lookup"><span data-stu-id="4cf74-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="4cf74-364">Tutti gli altri account non di rimanenze verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="4cf74-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="4cf74-365">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="4cf74-365">Address information</span></span>

<span data-ttu-id="4cf74-366">Ogni dipendente deve avere un'ubicazione primaria.</span><span class="sxs-lookup"><span data-stu-id="4cf74-366">Every employee must have one primary location.</span></span> <span data-ttu-id="4cf74-367">In Dayforce, questa ubicazione viene utilizzata per determinare la principale residenza del dipendente a scopo fiscale.</span><span class="sxs-lookup"><span data-stu-id="4cf74-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="4cf74-368">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-368">Primary (required)</span></span>
- <span data-ttu-id="4cf74-369">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-369">Country/region (required)</span></span>
- <span data-ttu-id="4cf74-370">CAP/Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="4cf74-371">Via (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-371">Street (required)</span></span>
- <span data-ttu-id="4cf74-372">Numero civico (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-372">Street Number (required)</span></span>
- <span data-ttu-id="4cf74-373">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="4cf74-373">Building Complement</span></span>
- <span data-ttu-id="4cf74-374">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-374">City (required)</span></span>
- <span data-ttu-id="4cf74-375">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-375">State (required)</span></span>
- <span data-ttu-id="4cf74-376">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="4cf74-377">Configurare i dati per generare le retribuzioni negli Stati Uniti e in Canada</span><span class="sxs-lookup"><span data-stu-id="4cf74-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="4cf74-378">Se si desidera generare la retribuzione per i dipendenti negli Stati Uniti e in Canada, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="4cf74-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="4cf74-379">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="4cf74-379">Departments are required on positions.</span></span>
- <span data-ttu-id="4cf74-380">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="4cf74-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="4cf74-381">È possibile configurare Talent per far sì che Posizioni specifichi un reparto.</span><span class="sxs-lookup"><span data-stu-id="4cf74-381">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="4cf74-382">A tale scopo, andare a **Posizioni condivise Risorse umane > Posizioni > Richiedi reparti su posizioni**.</span><span class="sxs-lookup"><span data-stu-id="4cf74-382">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="4cf74-383">Si consiglia di applicare questa impostazione per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-383">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="4cf74-384">Tipi di lavoro</span><span class="sxs-lookup"><span data-stu-id="4cf74-384">Job types</span></span>

<span data-ttu-id="4cf74-385">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="4cf74-385">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="4cf74-386">I tipi di mansione sono necessari per elaborare le retribuzioni negli Stati Uniti e in Canada.</span><span class="sxs-lookup"><span data-stu-id="4cf74-386">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="4cf74-387">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="4cf74-387">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="4cf74-388">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="4cf74-388">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="4cf74-389">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="4cf74-389">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="4cf74-390">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="4cf74-390">Job type</span></span>   | <span data-ttu-id="4cf74-391">descrizione</span><span class="sxs-lookup"><span data-stu-id="4cf74-391">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="4cf74-392">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="4cf74-392">Hourly</span></span>     | <span data-ttu-id="4cf74-393">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="4cf74-393">Hourly</span></span>      |
| <span data-ttu-id="4cf74-394">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="4cf74-394">Salaried</span></span>   | <span data-ttu-id="4cf74-395">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="4cf74-395">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="4cf74-396">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="4cf74-396">Position types</span></span> 

<span data-ttu-id="4cf74-397">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="4cf74-397">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="4cf74-398">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="4cf74-398">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="4cf74-399">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="4cf74-399">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="4cf74-400">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="4cf74-400">Position type</span></span>   | <span data-ttu-id="4cf74-401">descrizione</span><span class="sxs-lookup"><span data-stu-id="4cf74-401">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="4cf74-402">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="4cf74-402">Full-time</span></span>       | <span data-ttu-id="4cf74-403">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="4cf74-403">Full time employee</span></span> |
| <span data-ttu-id="4cf74-404">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="4cf74-404">Part-time</span></span>       | <span data-ttu-id="4cf74-405">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="4cf74-405">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="4cf74-406">Codici causale</span><span class="sxs-lookup"><span data-stu-id="4cf74-406">Reason codes</span></span>

<span data-ttu-id="4cf74-407">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="4cf74-407">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="4cf74-408">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="4cf74-408">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="4cf74-409">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="4cf74-409">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="4cf74-410">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="4cf74-410">Reason code</span></span>    | <span data-ttu-id="4cf74-411">descrizione</span><span class="sxs-lookup"><span data-stu-id="4cf74-411">Description</span></span>      | <span data-ttu-id="4cf74-412">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="4cf74-412">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="4cf74-413">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="4cf74-413">RESIGNATION</span></span>    | <span data-ttu-id="4cf74-414">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="4cf74-414">Resignation</span></span>      | <span data-ttu-id="4cf74-415">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-415">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-416">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="4cf74-416">TERMINATION</span></span>    | <span data-ttu-id="4cf74-417">Fine</span><span class="sxs-lookup"><span data-stu-id="4cf74-417">Termination</span></span>      | <span data-ttu-id="4cf74-418">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-418">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-419">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="4cf74-419">RETIREMENT</span></span>     | <span data-ttu-id="4cf74-420">Pensione</span><span class="sxs-lookup"><span data-stu-id="4cf74-420">Retirement</span></span>       | <span data-ttu-id="4cf74-421">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-421">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-422">OTHER</span><span class="sxs-lookup"><span data-stu-id="4cf74-422">OTHER</span></span>          | <span data-ttu-id="4cf74-423">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="4cf74-423">Other Reasons</span></span>    | <span data-ttu-id="4cf74-424">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-424">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-425">DEATH</span><span class="sxs-lookup"><span data-stu-id="4cf74-425">DEATH</span></span>          | <span data-ttu-id="4cf74-426">Decesso</span><span class="sxs-lookup"><span data-stu-id="4cf74-426">Death</span></span>            | <span data-ttu-id="4cf74-427">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-427">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-428">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="4cf74-428">LEAVEOFABSENCE</span></span> | <span data-ttu-id="4cf74-429">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="4cf74-429">Leave of Absence</span></span> | <span data-ttu-id="4cf74-430">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-430">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-431">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="4cf74-431">CONTRACTEND</span></span>    | <span data-ttu-id="4cf74-432">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="4cf74-432">End of Contract</span></span>  | <span data-ttu-id="4cf74-433">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-433">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-434">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="4cf74-434">SALARYCHANGE</span></span>   | <span data-ttu-id="4cf74-435">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="4cf74-435">Change of Salary</span></span> | <span data-ttu-id="4cf74-436">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="4cf74-436">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="4cf74-437">Stato civile</span><span class="sxs-lookup"><span data-stu-id="4cf74-437">Marital status</span></span>

<span data-ttu-id="4cf74-438">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-438">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="4cf74-439">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="4cf74-439">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="4cf74-440">Talent</span><span class="sxs-lookup"><span data-stu-id="4cf74-440">Talent</span></span>                 | <span data-ttu-id="4cf74-441">Dayforce</span><span class="sxs-lookup"><span data-stu-id="4cf74-441">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="4cf74-442">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="4cf74-442">Married</span></span>                | <span data-ttu-id="4cf74-443">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="4cf74-443">Married</span></span>              |
| <span data-ttu-id="4cf74-444">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="4cf74-444">Single</span></span>                 | <span data-ttu-id="4cf74-445">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="4cf74-445">Single</span></span>               |
| <span data-ttu-id="4cf74-446">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="4cf74-446">Widowed</span></span>                | <span data-ttu-id="4cf74-447">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="4cf74-447">Widowed</span></span>              |
| <span data-ttu-id="4cf74-448">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="4cf74-448">Divorced</span></span>               | <span data-ttu-id="4cf74-449">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="4cf74-449">Divorced</span></span>             |
| <span data-ttu-id="4cf74-450">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="4cf74-450">Registered Partnership</span></span> | <span data-ttu-id="4cf74-451">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="4cf74-451">Domestic Partnership</span></span> |
| <span data-ttu-id="4cf74-452">Nessuna</span><span class="sxs-lookup"><span data-stu-id="4cf74-452">None</span></span>                   | <span data-ttu-id="4cf74-453">Nessuna</span><span class="sxs-lookup"><span data-stu-id="4cf74-453">None</span></span>                 |
| <span data-ttu-id="4cf74-454">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="4cf74-454">Cohabiting</span></span>             | <span data-ttu-id="4cf74-455">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="4cf74-455">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="4cf74-456">Genere</span><span class="sxs-lookup"><span data-stu-id="4cf74-456">Gender</span></span>

<span data-ttu-id="4cf74-457">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-457">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="4cf74-458">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="4cf74-458">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="4cf74-459">Talent</span><span class="sxs-lookup"><span data-stu-id="4cf74-459">Talent</span></span>       | <span data-ttu-id="4cf74-460">Dayforce</span><span class="sxs-lookup"><span data-stu-id="4cf74-460">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="4cf74-461">Maschio</span><span class="sxs-lookup"><span data-stu-id="4cf74-461">Male</span></span>         | <span data-ttu-id="4cf74-462">Maschio</span><span class="sxs-lookup"><span data-stu-id="4cf74-462">Male</span></span>            |
| <span data-ttu-id="4cf74-463">Femmina</span><span class="sxs-lookup"><span data-stu-id="4cf74-463">Female</span></span>       | <span data-ttu-id="4cf74-464">Femmina</span><span class="sxs-lookup"><span data-stu-id="4cf74-464">Female</span></span>          |
| <span data-ttu-id="4cf74-465">Non specifico</span><span class="sxs-lookup"><span data-stu-id="4cf74-465">Non-specific</span></span> | <span data-ttu-id="4cf74-466">*Non supportato*</span><span class="sxs-lookup"><span data-stu-id="4cf74-466">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="4cf74-467">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="4cf74-467">Earning codes</span></span>

<span data-ttu-id="4cf74-468">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="4cf74-468">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="4cf74-469">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="4cf74-469">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="4cf74-470">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="4cf74-470">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="4cf74-471">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="4cf74-471">Supported frequencies</span></span>

- <span data-ttu-id="4cf74-472">Tutti</span><span class="sxs-lookup"><span data-stu-id="4cf74-472">All</span></span>
- <span data-ttu-id="4cf74-473">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="4cf74-473">EVERYPAY</span></span>
- <span data-ttu-id="4cf74-474">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="4cf74-474">EACHPAYPERIOD</span></span>
- <span data-ttu-id="4cf74-475">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="4cf74-475">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="4cf74-476">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="4cf74-476">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="4cf74-477">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-477">1OFMTH</span></span>
- <span data-ttu-id="4cf74-478">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-478">LASTOFMTH</span></span>
- <span data-ttu-id="4cf74-479">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-479">2OFMTH</span></span>
- <span data-ttu-id="4cf74-480">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-480">3OFMTH</span></span>
- <span data-ttu-id="4cf74-481">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-481">4OFMTH</span></span>
- <span data-ttu-id="4cf74-482">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-482">5OFMTH</span></span>
- <span data-ttu-id="4cf74-483">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-483">1N2OFMTH</span></span>
- <span data-ttu-id="4cf74-484">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-484">3N4OFMTH</span></span>
- <span data-ttu-id="4cf74-485">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-485">1N3OFMTH</span></span>
- <span data-ttu-id="4cf74-486">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-486">1N4OFMTH</span></span>
- <span data-ttu-id="4cf74-487">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-487">2N3OFMTH</span></span>
- <span data-ttu-id="4cf74-488">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-488">2N4OFMTH</span></span>
- <span data-ttu-id="4cf74-489">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-489">1N2N3OFMTH</span></span>
- <span data-ttu-id="4cf74-490">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-490">1N2N4OFMTH</span></span>
- <span data-ttu-id="4cf74-491">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-491">1N3N4OFMTH</span></span>
- <span data-ttu-id="4cf74-492">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-492">2N3N4OFMTH</span></span>
- <span data-ttu-id="4cf74-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="4cf74-494">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="4cf74-494">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="4cf74-495">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="4cf74-495">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="4cf74-496">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="4cf74-496">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="4cf74-497">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="4cf74-497">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="4cf74-498">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="4cf74-498">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="4cf74-499">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="4cf74-499">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="4cf74-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="4cf74-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="4cf74-501">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="4cf74-501">Addresses</span></span>

<span data-ttu-id="4cf74-502">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="4cf74-502">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="4cf74-503">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="4cf74-503">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="4cf74-504">Talent</span><span class="sxs-lookup"><span data-stu-id="4cf74-504">Talent</span></span>          | <span data-ttu-id="4cf74-505">Dayforce</span><span class="sxs-lookup"><span data-stu-id="4cf74-505">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="4cf74-506">Paese</span><span class="sxs-lookup"><span data-stu-id="4cf74-506">Country/Region</span></span>  | <span data-ttu-id="4cf74-507">Codice paese</span><span class="sxs-lookup"><span data-stu-id="4cf74-507">Country Code</span></span>          |
| <span data-ttu-id="4cf74-508">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="4cf74-508">Zip/Postal Code</span></span> | <span data-ttu-id="4cf74-509">CAP</span><span class="sxs-lookup"><span data-stu-id="4cf74-509">Postal Code</span></span>           |
| <span data-ttu-id="4cf74-510">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="4cf74-510">State</span></span>           | <span data-ttu-id="4cf74-511">Codice stato</span><span class="sxs-lookup"><span data-stu-id="4cf74-511">State Code</span></span>            |
| <span data-ttu-id="4cf74-512">Città</span><span class="sxs-lookup"><span data-stu-id="4cf74-512">City</span></span>            | <span data-ttu-id="4cf74-513">Città</span><span class="sxs-lookup"><span data-stu-id="4cf74-513">City</span></span>                  |
| <span data-ttu-id="4cf74-514">Regione</span><span class="sxs-lookup"><span data-stu-id="4cf74-514">County</span></span>          | <span data-ttu-id="4cf74-515">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="4cf74-515">County (Municipality)</span></span> |
| <span data-ttu-id="4cf74-516">Via</span><span class="sxs-lookup"><span data-stu-id="4cf74-516">Street</span></span>          | <span data-ttu-id="4cf74-517">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="4cf74-517">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="4cf74-518">Regioni fiscali</span><span class="sxs-lookup"><span data-stu-id="4cf74-518">Tax regions</span></span>

<span data-ttu-id="4cf74-519">Le regioni fiscali vengono utilizzate per determinare l'imposta appropriata che deve essere applicata durante la generazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="4cf74-519">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="4cf74-520">Le regioni fiscali vengono mappate in Dayforce come indirizzi di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-520">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="4cf74-521">La regione fiscale predefinita deve essere associata alla posizione attiva del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="4cf74-521">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="4cf74-522">Regione fiscale (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-522">Tax region (required)</span></span>
- <span data-ttu-id="4cf74-523">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-523">Country/Region (required)</span></span>
- <span data-ttu-id="4cf74-524">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="4cf74-524">State (required)</span></span>
- <span data-ttu-id="4cf74-525">Regione</span><span class="sxs-lookup"><span data-stu-id="4cf74-525">County</span></span> 
- <span data-ttu-id="4cf74-526">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="4cf74-526">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="4cf74-527">Configurare i dati per generare le retribuzioni in Messico</span><span class="sxs-lookup"><span data-stu-id="4cf74-527">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="4cf74-528">Se si desidera generare la retribuzione per i dipendenti in Messico, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="4cf74-528">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="4cf74-529">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="4cf74-529">Departments are required on positions.</span></span>
- <span data-ttu-id="4cf74-530">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="4cf74-530">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="4cf74-531">Tipi di posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="4cf74-531">Job types</span></span>

<span data-ttu-id="4cf74-532">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="4cf74-532">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="4cf74-533">Tipi di mansione necessari per elaborare le retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="4cf74-533">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="4cf74-534">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="4cf74-534">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="4cf74-535">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="4cf74-535">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="4cf74-536">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="4cf74-536">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="4cf74-537">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="4cf74-537">Job type</span></span>   | <span data-ttu-id="4cf74-538">descrizione</span><span class="sxs-lookup"><span data-stu-id="4cf74-538">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="4cf74-539">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="4cf74-539">Hourly</span></span>     | <span data-ttu-id="4cf74-540">Su base oraria MX</span><span class="sxs-lookup"><span data-stu-id="4cf74-540">MX Hourly</span></span>   |
| <span data-ttu-id="4cf74-541">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="4cf74-541">Salaried</span></span>   | <span data-ttu-id="4cf74-542">Stipendiato MX</span><span class="sxs-lookup"><span data-stu-id="4cf74-542">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="4cf74-543">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="4cf74-543">Position types</span></span> 

<span data-ttu-id="4cf74-544">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="4cf74-544">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="4cf74-545">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="4cf74-545">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="4cf74-546">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="4cf74-546">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="4cf74-547">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="4cf74-547">Position type</span></span>   | <span data-ttu-id="4cf74-548">descrizione</span><span class="sxs-lookup"><span data-stu-id="4cf74-548">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="4cf74-549">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="4cf74-549">Full-time</span></span>       | <span data-ttu-id="4cf74-550">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="4cf74-550">Full time employee</span></span> |
| <span data-ttu-id="4cf74-551">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="4cf74-551">Part-time</span></span>       | <span data-ttu-id="4cf74-552">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="4cf74-552">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="4cf74-553">Codici causale</span><span class="sxs-lookup"><span data-stu-id="4cf74-553">Reason codes</span></span>

<span data-ttu-id="4cf74-554">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="4cf74-554">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="4cf74-555">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="4cf74-555">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="4cf74-556">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="4cf74-556">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="4cf74-557">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="4cf74-557">Reason code</span></span>            | <span data-ttu-id="4cf74-558">descrizione</span><span class="sxs-lookup"><span data-stu-id="4cf74-558">Description</span></span>                    | <span data-ttu-id="4cf74-559">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="4cf74-559">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="4cf74-560">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="4cf74-560">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="4cf74-561">Partenza prima della prima retribuzione</span><span class="sxs-lookup"><span data-stu-id="4cf74-561">Departure before first payroll</span></span> | <span data-ttu-id="4cf74-562">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-562">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-563">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="4cf74-563">RESIGNATION</span></span>            | <span data-ttu-id="4cf74-564">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="4cf74-564">Resignation</span></span>                    | <span data-ttu-id="4cf74-565">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-565">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-566">PENSION</span><span class="sxs-lookup"><span data-stu-id="4cf74-566">PENSION</span></span>                | <span data-ttu-id="4cf74-567">Pensionamento</span><span class="sxs-lookup"><span data-stu-id="4cf74-567">Pension</span></span>                        | <span data-ttu-id="4cf74-568">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-568">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-569">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="4cf74-569">TERMINATION</span></span>            | <span data-ttu-id="4cf74-570">Fine</span><span class="sxs-lookup"><span data-stu-id="4cf74-570">Termination</span></span>                    | <span data-ttu-id="4cf74-571">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-571">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-572">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="4cf74-572">RETIREMENT</span></span>             | <span data-ttu-id="4cf74-573">Pensione</span><span class="sxs-lookup"><span data-stu-id="4cf74-573">Retirement</span></span>                     | <span data-ttu-id="4cf74-574">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-574">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-575">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="4cf74-575">ABSENTEE</span></span>               | <span data-ttu-id="4cf74-576">Assente</span><span class="sxs-lookup"><span data-stu-id="4cf74-576">Absentee</span></span>                       | <span data-ttu-id="4cf74-577">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-577">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-578">OTHER</span><span class="sxs-lookup"><span data-stu-id="4cf74-578">OTHER</span></span>                  | <span data-ttu-id="4cf74-579">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="4cf74-579">Other Reasons</span></span>                  | <span data-ttu-id="4cf74-580">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-580">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-581">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="4cf74-581">CLOSURE</span></span>                | <span data-ttu-id="4cf74-582">Chiusura attività</span><span class="sxs-lookup"><span data-stu-id="4cf74-582">Business Closure</span></span>               | <span data-ttu-id="4cf74-583">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-583">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-584">DEATH</span><span class="sxs-lookup"><span data-stu-id="4cf74-584">DEATH</span></span>                  | <span data-ttu-id="4cf74-585">Decesso</span><span class="sxs-lookup"><span data-stu-id="4cf74-585">Death</span></span>                          | <span data-ttu-id="4cf74-586">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-586">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-587">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="4cf74-587">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="4cf74-588">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="4cf74-588">Leave of Absence</span></span>               | <span data-ttu-id="4cf74-589">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-589">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-590">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="4cf74-590">CONTRACTEND</span></span>            | <span data-ttu-id="4cf74-591">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="4cf74-591">End of Contract</span></span>                | <span data-ttu-id="4cf74-592">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="4cf74-592">Terminate worker</span></span>     |
| <span data-ttu-id="4cf74-593">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="4cf74-593">SALARYCHANGE</span></span>           | <span data-ttu-id="4cf74-594">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="4cf74-594">Change of Salary</span></span>               | <span data-ttu-id="4cf74-595">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="4cf74-595">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="4cf74-596">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="4cf74-596">Terms of employment</span></span>

<span data-ttu-id="4cf74-597">Le condizioni di impiego vengono utilizzate per creare categorie di termini di impiego.</span><span class="sxs-lookup"><span data-stu-id="4cf74-597">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="4cf74-598">I termini vengono mappati in Dayforce come valori degli indicatori di impiego.</span><span class="sxs-lookup"><span data-stu-id="4cf74-598">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="4cf74-599">I seguenti termini di impiego e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="4cf74-599">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="4cf74-600">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="4cf74-600">Terms of employment</span></span>   | <span data-ttu-id="4cf74-601">descrizione</span><span class="sxs-lookup"><span data-stu-id="4cf74-601">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="4cf74-602">Regolare</span><span class="sxs-lookup"><span data-stu-id="4cf74-602">Regular</span></span>               | <span data-ttu-id="4cf74-603">Regolare</span><span class="sxs-lookup"><span data-stu-id="4cf74-603">Regular</span></span>     |
| <span data-ttu-id="4cf74-604">Diretto</span><span class="sxs-lookup"><span data-stu-id="4cf74-604">Direct</span></span>                | <span data-ttu-id="4cf74-605">Diretto</span><span class="sxs-lookup"><span data-stu-id="4cf74-605">Direct</span></span>      |
| <span data-ttu-id="4cf74-606">Internato</span><span class="sxs-lookup"><span data-stu-id="4cf74-606">Internship</span></span>            | <span data-ttu-id="4cf74-607">Internato</span><span class="sxs-lookup"><span data-stu-id="4cf74-607">Internship</span></span>  |
| <span data-ttu-id="4cf74-608">Permanente</span><span class="sxs-lookup"><span data-stu-id="4cf74-608">Permanent</span></span>             | <span data-ttu-id="4cf74-609">Permanente</span><span class="sxs-lookup"><span data-stu-id="4cf74-609">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="4cf74-610">Stato civile</span><span class="sxs-lookup"><span data-stu-id="4cf74-610">Marital status</span></span>

<span data-ttu-id="4cf74-611">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-611">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="4cf74-612">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="4cf74-612">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="4cf74-613">Talent</span><span class="sxs-lookup"><span data-stu-id="4cf74-613">Talent</span></span>                 | <span data-ttu-id="4cf74-614">Dayforce</span><span class="sxs-lookup"><span data-stu-id="4cf74-614">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="4cf74-615">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="4cf74-615">Married</span></span>                | <span data-ttu-id="4cf74-616">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="4cf74-616">Married</span></span>                   |
| <span data-ttu-id="4cf74-617">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="4cf74-617">Single</span></span>                 | <span data-ttu-id="4cf74-618">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="4cf74-618">Single</span></span>                    |
| <span data-ttu-id="4cf74-619">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="4cf74-619">Widowed</span></span>                | <span data-ttu-id="4cf74-620">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="4cf74-620">Widowed</span></span>                   |
| <span data-ttu-id="4cf74-621">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="4cf74-621">Divorced</span></span>               | <span data-ttu-id="4cf74-622">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="4cf74-622">Divorced</span></span>                  |
| <span data-ttu-id="4cf74-623">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="4cf74-623">Registered Partnership</span></span> | <span data-ttu-id="4cf74-624">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="4cf74-624">Domestic Partnership</span></span>      |
| <span data-ttu-id="4cf74-625">Nessuna</span><span class="sxs-lookup"><span data-stu-id="4cf74-625">None</span></span>                   | <span data-ttu-id="4cf74-626">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="4cf74-626">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="4cf74-627">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="4cf74-627">Cohabiting</span></span>             | <span data-ttu-id="4cf74-628">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="4cf74-628">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="4cf74-629">Genere</span><span class="sxs-lookup"><span data-stu-id="4cf74-629">Gender</span></span>

<span data-ttu-id="4cf74-630">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-630">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="4cf74-631">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="4cf74-631">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="4cf74-632">Talent</span><span class="sxs-lookup"><span data-stu-id="4cf74-632">Talent</span></span>       | <span data-ttu-id="4cf74-633">Dayforce</span><span class="sxs-lookup"><span data-stu-id="4cf74-633">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="4cf74-634">Maschio</span><span class="sxs-lookup"><span data-stu-id="4cf74-634">Male</span></span>         | <span data-ttu-id="4cf74-635">Maschio</span><span class="sxs-lookup"><span data-stu-id="4cf74-635">Male</span></span>                      |
| <span data-ttu-id="4cf74-636">Femmina</span><span class="sxs-lookup"><span data-stu-id="4cf74-636">Female</span></span>       | <span data-ttu-id="4cf74-637">Femmina</span><span class="sxs-lookup"><span data-stu-id="4cf74-637">Female</span></span>                    |
| <span data-ttu-id="4cf74-638">Non specifico</span><span class="sxs-lookup"><span data-stu-id="4cf74-638">Non-specific</span></span> | <span data-ttu-id="4cf74-639">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="4cf74-639">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="4cf74-640">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="4cf74-640">Payment method</span></span>

<span data-ttu-id="4cf74-641">I metodi di pagamento offrono al dipendente e all'azienda un modo per descrivere la modalità di pagamento dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="4cf74-641">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="4cf74-642">I metodi di pagamento vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-642">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="4cf74-643">Nella tabella seguente vengono illustrati in che modo i metodi di pagamento vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="4cf74-643">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="4cf74-644">Talent</span><span class="sxs-lookup"><span data-stu-id="4cf74-644">Talent</span></span>             | <span data-ttu-id="4cf74-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="4cf74-645">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="4cf74-646">In contanti</span><span class="sxs-lookup"><span data-stu-id="4cf74-646">Cash</span></span>               | <span data-ttu-id="4cf74-647">In contanti</span><span class="sxs-lookup"><span data-stu-id="4cf74-647">Cash</span></span>                      |
| <span data-ttu-id="4cf74-648">Pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="4cf74-648">Electronic Payment</span></span> | <span data-ttu-id="4cf74-649">Trasferimenti</span><span class="sxs-lookup"><span data-stu-id="4cf74-649">Transfer</span></span>                  |
| <span data-ttu-id="4cf74-650">Verifica</span><span class="sxs-lookup"><span data-stu-id="4cf74-650">Check</span></span>              | <span data-ttu-id="4cf74-651">Assegno</span><span class="sxs-lookup"><span data-stu-id="4cf74-651">Cheque</span></span>                    |
| <span data-ttu-id="4cf74-652">Assegno circolare</span><span class="sxs-lookup"><span data-stu-id="4cf74-652">Bank Draft</span></span>         | <span data-ttu-id="4cf74-653">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="4cf74-653">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="4cf74-654">Altro</span><span class="sxs-lookup"><span data-stu-id="4cf74-654">Other</span></span>              | <span data-ttu-id="4cf74-655">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="4cf74-655">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="4cf74-656">Tipo di conto bancario</span><span class="sxs-lookup"><span data-stu-id="4cf74-656">Bank account type</span></span>

<span data-ttu-id="4cf74-657">I tipi di conto bancario vengono utilizzati per i pagamenti elettronici ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="4cf74-657">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="4cf74-658">I tipi di conto bancario vengono mappati in Dayforce come informazioni sul conto di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="4cf74-658">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="4cf74-659">I tipi di conto bancario vengono convertiti, come appropriato, nei valori accettati per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="4cf74-659">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="4cf74-660">Talent</span><span class="sxs-lookup"><span data-stu-id="4cf74-660">Talent</span></span>            | <span data-ttu-id="4cf74-661">Dayforce</span><span class="sxs-lookup"><span data-stu-id="4cf74-661">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="4cf74-662">Conto corrente</span><span class="sxs-lookup"><span data-stu-id="4cf74-662">Checking Account</span></span>  | <span data-ttu-id="4cf74-663">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="4cf74-663">CheckingAccount</span></span>           |
| <span data-ttu-id="4cf74-664">Conto retribuzioni</span><span class="sxs-lookup"><span data-stu-id="4cf74-664">Payroll Account</span></span>   | <span data-ttu-id="4cf74-665">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="4cf74-665">PayrollAccount</span></span>            |
| <span data-ttu-id="4cf74-666">Conto di risparmio</span><span class="sxs-lookup"><span data-stu-id="4cf74-666">Savings Account</span></span>   | <span data-ttu-id="4cf74-667">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="4cf74-667">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="4cf74-668">Conto Bankgirot</span><span class="sxs-lookup"><span data-stu-id="4cf74-668">BankGirot account</span></span> | <span data-ttu-id="4cf74-669">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="4cf74-669">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="4cf74-670">Conto PlusGirot</span><span class="sxs-lookup"><span data-stu-id="4cf74-670">PlusGirot account</span></span> | <span data-ttu-id="4cf74-671">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="4cf74-671">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="4cf74-672">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="4cf74-672">Earning codes</span></span>

<span data-ttu-id="4cf74-673">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="4cf74-673">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="4cf74-674">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="4cf74-674">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="4cf74-675">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="4cf74-675">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="4cf74-676">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="4cf74-676">Supported frequencies</span></span>

- <span data-ttu-id="4cf74-677">Tutti</span><span class="sxs-lookup"><span data-stu-id="4cf74-677">All</span></span>
- <span data-ttu-id="4cf74-678">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="4cf74-678">EVERYPAY</span></span>
- <span data-ttu-id="4cf74-679">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="4cf74-679">EACHPAYPERIOD</span></span>
- <span data-ttu-id="4cf74-680">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="4cf74-680">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="4cf74-681">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="4cf74-681">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="4cf74-682">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-682">1OFMTH</span></span>
- <span data-ttu-id="4cf74-683">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-683">LASTOFMTH</span></span>
- <span data-ttu-id="4cf74-684">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-684">2OFMTH</span></span>
- <span data-ttu-id="4cf74-685">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-685">3OFMTH</span></span>
- <span data-ttu-id="4cf74-686">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-686">4OFMTH</span></span>
- <span data-ttu-id="4cf74-687">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-687">5OFMTH</span></span>
- <span data-ttu-id="4cf74-688">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-688">1N2OFMTH</span></span>
- <span data-ttu-id="4cf74-689">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-689">3N4OFMTH</span></span>
- <span data-ttu-id="4cf74-690">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-690">1N3OFMTH</span></span>
- <span data-ttu-id="4cf74-691">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-691">1N4OFMTH</span></span>
- <span data-ttu-id="4cf74-692">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-692">2N3OFMTH</span></span>
- <span data-ttu-id="4cf74-693">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-693">2N4OFMTH</span></span>
- <span data-ttu-id="4cf74-694">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-694">1N2N3OFMTH</span></span>
- <span data-ttu-id="4cf74-695">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-695">1N2N4OFMTH</span></span>
- <span data-ttu-id="4cf74-696">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-696">1N3N4OFMTH</span></span>
- <span data-ttu-id="4cf74-697">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-697">2N3N4OFMTH</span></span>
- <span data-ttu-id="4cf74-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="4cf74-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="4cf74-699">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="4cf74-699">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="4cf74-700">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="4cf74-700">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="4cf74-701">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="4cf74-701">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="4cf74-702">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="4cf74-702">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="4cf74-703">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="4cf74-703">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="4cf74-704">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="4cf74-704">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="4cf74-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="4cf74-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="4cf74-706">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="4cf74-706">Addresses</span></span>

<span data-ttu-id="4cf74-707">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="4cf74-707">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="4cf74-708">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="4cf74-708">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="4cf74-709">Talent</span><span class="sxs-lookup"><span data-stu-id="4cf74-709">Talent</span></span>              | <span data-ttu-id="4cf74-710">Dayforce</span><span class="sxs-lookup"><span data-stu-id="4cf74-710">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="4cf74-711">Paese</span><span class="sxs-lookup"><span data-stu-id="4cf74-711">Country/Region</span></span>      | <span data-ttu-id="4cf74-712">Codice paese</span><span class="sxs-lookup"><span data-stu-id="4cf74-712">Country Code</span></span>          |
| <span data-ttu-id="4cf74-713">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="4cf74-713">Zip/Postal Code</span></span>     | <span data-ttu-id="4cf74-714">CAP</span><span class="sxs-lookup"><span data-stu-id="4cf74-714">Postal Code</span></span>           |
| <span data-ttu-id="4cf74-715">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="4cf74-715">State</span></span>               | <span data-ttu-id="4cf74-716">Codice stato</span><span class="sxs-lookup"><span data-stu-id="4cf74-716">State Code</span></span>            |
| <span data-ttu-id="4cf74-717">Città</span><span class="sxs-lookup"><span data-stu-id="4cf74-717">City</span></span>                | <span data-ttu-id="4cf74-718">Città</span><span class="sxs-lookup"><span data-stu-id="4cf74-718">City</span></span>                  |
| <span data-ttu-id="4cf74-719">Regione</span><span class="sxs-lookup"><span data-stu-id="4cf74-719">County</span></span>              | <span data-ttu-id="4cf74-720">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="4cf74-720">County (Municipality)</span></span> |
| <span data-ttu-id="4cf74-721">Via</span><span class="sxs-lookup"><span data-stu-id="4cf74-721">Street</span></span>              | <span data-ttu-id="4cf74-722">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="4cf74-722">Address Line 1</span></span>        |
| <span data-ttu-id="4cf74-723">Numero civico</span><span class="sxs-lookup"><span data-stu-id="4cf74-723">Street Number</span></span>       | <span data-ttu-id="4cf74-724">Riga indirizzo 2</span><span class="sxs-lookup"><span data-stu-id="4cf74-724">Address Line 2</span></span>        |
| <span data-ttu-id="4cf74-725">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="4cf74-725">Building Complement</span></span> | <span data-ttu-id="4cf74-726">Riga indirizzo 5</span><span class="sxs-lookup"><span data-stu-id="4cf74-726">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="4cf74-727">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="4cf74-727">Passport number</span></span>

<span data-ttu-id="4cf74-728">I dipendenti possono indicare le informazioni sul passaporto.</span><span class="sxs-lookup"><span data-stu-id="4cf74-728">Employees can declare passport information.</span></span> <span data-ttu-id="4cf74-729">Queste informazioni sono del tipo di identificazione **Passaporto** e vengono integrate in Dayforce come parte delle informazioni di un dipendente specifiche per il Messico.</span><span class="sxs-lookup"><span data-stu-id="4cf74-729">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="4cf74-730">Tipo di identificazione = "Passaporto"</span><span class="sxs-lookup"><span data-stu-id="4cf74-730">Identification Type = "Passport"</span></span>
- <span data-ttu-id="4cf74-731">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="4cf74-731">Issued Date</span></span>
- <span data-ttu-id="4cf74-732">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="4cf74-732">Expiration Date</span></span>

<span data-ttu-id="4cf74-733">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **Passaporto**.</span><span class="sxs-lookup"><span data-stu-id="4cf74-733">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="4cf74-734">Tuttavia, solo l'immissione del passaporto attivo corrente viene integrata in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="4cf74-734">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="4cf74-735">Se tutte le immissioni di passaporto sono scadute, in Dayforce viene integrato il passaporto di emissione più recente.</span><span class="sxs-lookup"><span data-stu-id="4cf74-735">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
