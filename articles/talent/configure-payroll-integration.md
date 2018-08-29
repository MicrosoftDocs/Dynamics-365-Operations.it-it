---
title: Configurare l'integrazione delle retribuzioni tra Talent e Dayforce
description: "In questo argomento viene descritto come configurare l'integrazione tra Microsoft Dynamics 365 for Talent e Ceridian Dayforce in modo da poter elaborare è un ciclo di pagamenti."
author: jcart1106
manager: AnnBe
ms.date: 07/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: fcddf82cffb9f0ba94b83eb21809b810585ebc9e
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="de1db-103">Configurare l'integrazione delle retribuzioni tra Talent e Dayforce</span><span class="sxs-lookup"><span data-stu-id="de1db-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="de1db-104">L'integrazione tra Microsoft Dynamics 365 for Talent e Ceridian Dayforce si basa su vari passaggi di configurazione descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="de1db-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="de1db-105">È necessario configurare l'integrazione sia in Talent che in Dayforce prima di poter elaborare un ciclo di pagamenti.</span><span class="sxs-lookup"><span data-stu-id="de1db-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="de1db-106">Quando si utilizza un servizio, ad esempio Dayforce, per completare i cicli di pagamenti, è necessario abilitare l'integrazione in Talent.</span><span class="sxs-lookup"><span data-stu-id="de1db-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="de1db-107">L'integrazione richiede dati specifici da Talent.</span><span class="sxs-lookup"><span data-stu-id="de1db-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="de1db-108">Di conseguenza, è necessario verificare che i dati che vengono mappati a Dayforce siano configurati in Talent in modo che supporti l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="de1db-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="de1db-109">L'integrazione utilizza le seguenti categorie generiche di dati:</span><span class="sxs-lookup"><span data-stu-id="de1db-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="de1db-110">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="de1db-110">Human resources data</span></span>
- <span data-ttu-id="de1db-111">Dati di compensazione</span><span class="sxs-lookup"><span data-stu-id="de1db-111">Compensation data</span></span>
- <span data-ttu-id="de1db-112">Data di retribuzione, ad esempio i cicli di pagamenti, i periodi retributivi e i codici reddito</span><span class="sxs-lookup"><span data-stu-id="de1db-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="de1db-113">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-113">Worker data</span></span>

<span data-ttu-id="de1db-114">In questo argomento vengono descritti i passaggi che è necessario completare per abilitare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="de1db-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="de1db-115">E vengono descritti i tipi di dati e i dettagli di configurazione necessari all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="de1db-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="de1db-116">Abilitare l'integrazione</span><span class="sxs-lookup"><span data-stu-id="de1db-116">Enable the integration</span></span>

<span data-ttu-id="de1db-117">In Talent è necessario attivare l'integrazione e immettere le informazioni di configurazione per connettersi a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de1db-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="de1db-118">Se si desidera che la transazione contabile prodotta venga importata in Microsoft Dynamics 365 for Finance and Operations, è necessario impostare anche un conto di archiviazione di Microsoft Azure e immettere la stringa di connessione di Archiviazione di Azure in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="de1db-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="de1db-119">Per attivare l'integrazione in Talent, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="de1db-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="de1db-120">Nella pagina **Amministrazione sistema** selezionare **Configurazione di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="de1db-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="de1db-121">Immettere l'endpoint FTP (File Transfer Protocol) e il percorso protetto della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="de1db-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="de1db-122">Immettere il nome utente e la password dell'utente che accederà al percorso protetto dell'endpoint e della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="de1db-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="de1db-123">Verificare la connessione, secondo le esigenze, e impostare l'opzione **Abilita integrazione retribuzioni** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="de1db-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="de1db-124">Quando l'integrazione viene attivata, vengono creati i file e il pacchetto di esportazione dei dati e viene impostata la frequenza.</span><span class="sxs-lookup"><span data-stu-id="de1db-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="de1db-125">È possibile cambiare la frequenza in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="de1db-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="de1db-126">Per altre informazioni sugli account di Archiviazione di Azure e sulle stringhe di connessione di Archiviazione di Azure, vedere gli argomenti di Azure seguenti:</span><span class="sxs-lookup"><span data-stu-id="de1db-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="de1db-127">Account di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="de1db-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="de1db-128">Configurare le stringhe di connessione di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="de1db-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="de1db-129">Configurare i dati</span><span class="sxs-lookup"><span data-stu-id="de1db-129">Configure your data</span></span> 

<span data-ttu-id="de1db-130">Per elaborare le retribuzioni, è necessario configurare i dati di Risorse umane in Talent.</span><span class="sxs-lookup"><span data-stu-id="de1db-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="de1db-131">È necessario impostare i dati dell'organizzazione, ad esempio mansioni e posizioni, insieme alle informazioni sui benefit e sulle compensazioni.</span><span class="sxs-lookup"><span data-stu-id="de1db-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="de1db-132">Queste informazioni includono informazioni sull'impiego, la retribuzione e le detrazioni che sono richieste per generare la retribuzione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="de1db-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="de1db-133">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="de1db-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="de1db-134">Benefit</span><span class="sxs-lookup"><span data-stu-id="de1db-134">Benefits</span></span> 

<span data-ttu-id="de1db-135">Le risorse umane dispongono di strumenti per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori.</span><span class="sxs-lookup"><span data-stu-id="de1db-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="de1db-136">Quando si creano i benefit, tenere presenti i seguenti dati e configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de1db-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="de1db-137">Piani di benefit</span><span class="sxs-lookup"><span data-stu-id="de1db-137">Benefit plans</span></span>

- <span data-ttu-id="de1db-138">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-138">Plan (required)</span></span>
- <span data-ttu-id="de1db-139">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-139">Type (required)</span></span>
- <span data-ttu-id="de1db-140">Impatto retribuzioni (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-140">Payroll impact (required)</span></span>
- <span data-ttu-id="de1db-141">Recupera arretrati</span><span class="sxs-lookup"><span data-stu-id="de1db-141">Recover arrears</span></span>
- <span data-ttu-id="de1db-142">Metodo di detrazione</span><span class="sxs-lookup"><span data-stu-id="de1db-142">Deduction method</span></span>
- <span data-ttu-id="de1db-143">Priorità detrazione</span><span class="sxs-lookup"><span data-stu-id="de1db-143">Deduction priority</span></span>
- <span data-ttu-id="de1db-144">Periodo limite</span><span class="sxs-lookup"><span data-stu-id="de1db-144">Limit period</span></span>
- <span data-ttu-id="de1db-145">Importo limite</span><span class="sxs-lookup"><span data-stu-id="de1db-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="de1db-146">Benefit</span><span class="sxs-lookup"><span data-stu-id="de1db-146">Benefits</span></span>

- <span data-ttu-id="de1db-147">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-147">Plan (required)</span></span>
- <span data-ttu-id="de1db-148">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-148">Type (required)</span></span>
- <span data-ttu-id="de1db-149">Opzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-149">Option (required)</span></span>
- <span data-ttu-id="de1db-150">ID benefit (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-150">Benefit ID (required)</span></span>
- <span data-ttu-id="de1db-151">Frequenza</span><span class="sxs-lookup"><span data-stu-id="de1db-151">Frequency</span></span>
- <span data-ttu-id="de1db-152">Base</span><span class="sxs-lookup"><span data-stu-id="de1db-152">Basis</span></span>
- <span data-ttu-id="de1db-153">Importo o coefficiente</span><span class="sxs-lookup"><span data-stu-id="de1db-153">Amount or rate</span></span>
- <span data-ttu-id="de1db-154">Codice di reddito</span><span class="sxs-lookup"><span data-stu-id="de1db-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="de1db-155">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="de1db-155">Supported frequencies</span></span> 

- <span data-ttu-id="de1db-156">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="de1db-156">Weekly</span></span>
- <span data-ttu-id="de1db-157">Bisettimanale</span><span class="sxs-lookup"><span data-stu-id="de1db-157">Bi-weekly</span></span>
- <span data-ttu-id="de1db-158">Quindicinale</span><span class="sxs-lookup"><span data-stu-id="de1db-158">Semi-monthly</span></span>
- <span data-ttu-id="de1db-159">Ogni mese</span><span class="sxs-lookup"><span data-stu-id="de1db-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="de1db-160">Basi supportate</span><span class="sxs-lookup"><span data-stu-id="de1db-160">Supported bases</span></span> 

- <span data-ttu-id="de1db-161">Importo fisso</span><span class="sxs-lookup"><span data-stu-id="de1db-161">Fixed amount</span></span>
- <span data-ttu-id="de1db-162">Percentuale di redditi</span><span class="sxs-lookup"><span data-stu-id="de1db-162">Percent of earnings</span></span>
- <span data-ttu-id="de1db-163">Ore di produzione</span><span class="sxs-lookup"><span data-stu-id="de1db-163">Productive hours</span></span>

<span data-ttu-id="de1db-164">Dayforce crea le seguenti detrazioni, in base all'impatto delle retribuzioni definito nel piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="de1db-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="de1db-165">Selezione in Talent</span><span class="sxs-lookup"><span data-stu-id="de1db-165">Selection in Talent</span></span>        | <span data-ttu-id="de1db-166">Risultato in Dayforce</span><span class="sxs-lookup"><span data-stu-id="de1db-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="de1db-167">Nessuna</span><span class="sxs-lookup"><span data-stu-id="de1db-167">None</span></span>                       | <span data-ttu-id="de1db-168">Non viene creata alcuna detrazione.</span><span class="sxs-lookup"><span data-stu-id="de1db-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="de1db-169">Solo detrazione</span><span class="sxs-lookup"><span data-stu-id="de1db-169">Deduction only</span></span>             | <span data-ttu-id="de1db-170">Viene creata una detrazione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="de1db-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="de1db-171">Solo contribuzione</span><span class="sxs-lookup"><span data-stu-id="de1db-171">Contribution only</span></span>          | <span data-ttu-id="de1db-172">Viene creata una detrazione del datore di lavoro.</span><span class="sxs-lookup"><span data-stu-id="de1db-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="de1db-173">Detrazione e contribuzione</span><span class="sxs-lookup"><span data-stu-id="de1db-173">Deduction and contribution</span></span> | <span data-ttu-id="de1db-174">Vengono create detrazioni del datore di lavoro e del dipendente.</span><span class="sxs-lookup"><span data-stu-id="de1db-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="de1db-175">Per altre informazioni su come definire e gestire un programma di benefit, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="de1db-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="de1db-176">Realizzare un programma di benefit per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="de1db-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="de1db-177">Creare un nuovo benefit</span><span class="sxs-lookup"><span data-stu-id="de1db-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="de1db-178">Definire regole e criteri di idoneità ai benefit</span><span class="sxs-lookup"><span data-stu-id="de1db-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="de1db-179">Iscrivere e rimuovere benefit da lavoratori</span><span class="sxs-lookup"><span data-stu-id="de1db-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="de1db-180">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="de1db-180">Compensation</span></span> 

<span data-ttu-id="de1db-181">La gestione delle retribuzioni consente di controllare la liquidazione dei premi e della retribuzione base.</span><span class="sxs-lookup"><span data-stu-id="de1db-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="de1db-182">La retribuzione di base fissa di un dipendente e gli aumenti per merito sono controllati mediante piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="de1db-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="de1db-183">È possibile controllare il pagamento degli incentivi, ad esempio il pagamento dei bonus, dei premi produttività, dei diritti di opzione, delle sovvenzioni, oltre che dei premi una tantum, tramite i piani di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="de1db-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="de1db-184">Dayforce utilizza le informazioni sulla compensazione per calcolare la retribuzione annuale o oraria di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="de1db-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="de1db-185">I piani di retribuzione fissa e conversioni della retribuzione sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="de1db-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="de1db-186">I dipendenti devono essere associati a un piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="de1db-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="de1db-187">Per ulteriori informazioni sui piani di retribuzione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="de1db-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="de1db-188">Creare i piani di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="de1db-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="de1db-189">Creare i piani di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="de1db-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="de1db-190">Sviluppare una struttura e piani di stipendi/retribuzioni</span><span class="sxs-lookup"><span data-stu-id="de1db-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="de1db-191">Processo retributivo</span><span class="sxs-lookup"><span data-stu-id="de1db-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="de1db-192">Definire il processo retributivo e calcolare i risultati</span><span class="sxs-lookup"><span data-stu-id="de1db-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="de1db-193">Iscrivere un dipendente a un piano di retribuzione fisso</span><span class="sxs-lookup"><span data-stu-id="de1db-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="de1db-194">Iscrivere un dipendente a un piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="de1db-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="de1db-195">Mansioni</span><span class="sxs-lookup"><span data-stu-id="de1db-195">Jobs</span></span> 

<span data-ttu-id="de1db-196">Una mansione è una raccolta delle attività e delle responsabilità proprie della persona assegnata a una mansione.</span><span class="sxs-lookup"><span data-stu-id="de1db-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="de1db-197">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="de1db-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="de1db-198">Impostazione dei componenti di una mansione</span><span class="sxs-lookup"><span data-stu-id="de1db-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="de1db-199">Definire nuovi processi</span><span class="sxs-lookup"><span data-stu-id="de1db-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="de1db-200">Posizioni</span><span class="sxs-lookup"><span data-stu-id="de1db-200">Positions</span></span>

<span data-ttu-id="de1db-201">Una posizione è una singola istanza di un processo.</span><span class="sxs-lookup"><span data-stu-id="de1db-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="de1db-202">Ad esempio, la posizione "Manager vendite (Est") è una delle posizioni associate alla mansione "Manager vendite".</span><span class="sxs-lookup"><span data-stu-id="de1db-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="de1db-203">Una posizione è presente in un reparto.</span><span class="sxs-lookup"><span data-stu-id="de1db-203">A position exists in a department.</span></span> <span data-ttu-id="de1db-204">È possibile associare un solo lavoratore a ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="de1db-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="de1db-205">Tenere a mente i seguenti dati e la configurazione quando si impostano le posizioni:</span><span class="sxs-lookup"><span data-stu-id="de1db-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="de1db-206">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-206">Position (required)</span></span>
- <span data-ttu-id="de1db-207">Descrizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-207">Description (required)</span></span>
- <span data-ttu-id="de1db-208">Mansione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-208">Job (required)</span></span>
- <span data-ttu-id="de1db-209">Reparto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-209">Department (required)</span></span>
- <span data-ttu-id="de1db-210">Tipo di posizione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-210">Position type (required)</span></span>
- <span data-ttu-id="de1db-211">Equivalente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="de1db-211">Full-time equivalent</span></span>
- <span data-ttu-id="de1db-212">Ore regolari annuali (obbligatorie)</span><span class="sxs-lookup"><span data-stu-id="de1db-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="de1db-213">Pagamento in base alla persona giuridica (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="de1db-214">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="de1db-214">Pay cycle (required)</span></span>
- <span data-ttu-id="de1db-215">Dimensione finanziaria predefinita - Centro di costo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="de1db-216">Assegnazione del lavoratore - Lavoratore, inizio assegnazione, fine assegnazione, codice motivo</span><span class="sxs-lookup"><span data-stu-id="de1db-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="de1db-217">Se nello stesso reparto più posizioni sono associate alla stessa mansione, vengono consolidate in una singola posizione in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de1db-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="de1db-218">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="de1db-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="de1db-219">Organizzare la forza lavoro utilizzando i reparti, le mansioni e le posizioni</span><span class="sxs-lookup"><span data-stu-id="de1db-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="de1db-220">Impostare le posizioni</span><span class="sxs-lookup"><span data-stu-id="de1db-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="de1db-221">Reparti</span><span class="sxs-lookup"><span data-stu-id="de1db-221">Departments</span></span>

<span data-ttu-id="de1db-222">Un reparto è un'unità operativa che rappresenta una categoria o un'area operativa di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="de1db-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="de1db-223">Un reparto è responsabile di una specifica area dell'organizzazione, ad esempio la vendita, la contabilità o le risorse umane.</span><span class="sxs-lookup"><span data-stu-id="de1db-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="de1db-224">È possibile utilizzare i reparti per creare report sulle aree operative.</span><span class="sxs-lookup"><span data-stu-id="de1db-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="de1db-225">I reparti possono essere responsabili di profitti e perdite.</span><span class="sxs-lookup"><span data-stu-id="de1db-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="de1db-226">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="de1db-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="de1db-227">Creare un reparto e associarlo alla gerarchia reparti</span><span class="sxs-lookup"><span data-stu-id="de1db-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="de1db-228">Definire nuovi reparti</span><span class="sxs-lookup"><span data-stu-id="de1db-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="de1db-229">Cicli e periodi retributivi</span><span class="sxs-lookup"><span data-stu-id="de1db-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="de1db-230">Un ciclo retributivo determina la frequenza di elaborazione delle retribuzioni e i giorni specifici in cui i lavoratori vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="de1db-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="de1db-231">Un ciclo retributivo può essere ad esempio mensile e i dipendenti possono essere pagati l'ultimo giorno del mese.</span><span class="sxs-lookup"><span data-stu-id="de1db-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="de1db-232">Un ciclo retributivo può in alternativa essere settimanale e i dipendenti possono essere pagati il giovedì successivo alla fine del periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="de1db-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="de1db-233">I cicli retributivi vengono assegnati alle posizioni per controllare quando i lavoratori in tali posizioni vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="de1db-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="de1db-234">Dopo aver creato i cicli retributivi, è possibile generare periodi retributivi per ogni ciclo.</span><span class="sxs-lookup"><span data-stu-id="de1db-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="de1db-235">Ogni periodo retributivo include una data di pagamento predefinita in base alle informazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="de1db-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="de1db-236">Tuttavia, è possibile modificare la data di pagamento predefinita in un periodo retributivo per consentire eccezioni, ad esempio quando la data di pagamento cade in un giorno festivo.</span><span class="sxs-lookup"><span data-stu-id="de1db-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="de1db-237">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="de1db-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="de1db-238">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="de1db-238">Pay cycle (required)</span></span>
- <span data-ttu-id="de1db-239">Frequenza ciclo retributivo (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="de1db-240">Data di inizio del periodo (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="de1db-241">Data di pagamento predefinita (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="de1db-242">Queste informazioni sono integrate con Dayforce come gruppi retributivi e sono separata in base al paese o alla regione per ogni ciclo retributivo.</span><span class="sxs-lookup"><span data-stu-id="de1db-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="de1db-243">Prima dell'integrazione è necessario generare almeno un periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="de1db-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="de1db-244">Dayforce genera calendari di gruppi retributivi e date di pagamento, in base alla data di inizio del primo periodo retributivo e alla data di pagamento predefinita che viene impostata in Talent.</span><span class="sxs-lookup"><span data-stu-id="de1db-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="de1db-245">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="de1db-245">Earning codes</span></span>

<span data-ttu-id="de1db-246">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="de1db-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="de1db-247">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="de1db-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="de1db-248">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="de1db-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="de1db-249">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-249">Earning Code (required)</span></span>
- <span data-ttu-id="de1db-250">descrizione</span><span class="sxs-lookup"><span data-stu-id="de1db-250">Description</span></span>
- <span data-ttu-id="de1db-251">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="de1db-251">Unit of measure</span></span>
- <span data-ttu-id="de1db-252">Produttivo</span><span class="sxs-lookup"><span data-stu-id="de1db-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="de1db-253">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-253">Worker data</span></span>

<span data-ttu-id="de1db-254">I record per i diversi tipi di lavoratori a disposizione sono importanti per i sistemi di gestione delle risorse umane e delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="de1db-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="de1db-255">Le informazioni immesse possono essere utilizzate per tenere traccia di informazioni personali e sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="de1db-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="de1db-256">È possibile gestire le seguenti informazioni per i lavoratori:</span><span class="sxs-lookup"><span data-stu-id="de1db-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="de1db-257">**Base** - Gestire le informazioni di base su un lavoratore, ad esempio le informazioni sui contatti, le informazioni demografiche, le informazioni di identificazione, le informazioni sulla famiglia, lo stato di servizio militare, le informazioni sull'espatrio, e i contatti personali e di emergenza.</span><span class="sxs-lookup"><span data-stu-id="de1db-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="de1db-258">**Impiego** - Consente di gestire le informazioni sull'impiego di un lavoratore, ad esempio rapporto con l'organizzazione o la società, assegnazione della posizione, date di inizio e fine, idoneità al lavoro, condizioni di impiego, pensionamento, ferie e trasferimento.</span><span class="sxs-lookup"><span data-stu-id="de1db-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="de1db-259">**Congedo e assenza** - Consente di gestire le informazioni sulle assenze di un lavoratore, ad esempio calendari di lavoro, transazioni assenze e impostazione assenze.</span><span class="sxs-lookup"><span data-stu-id="de1db-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="de1db-260">**Retribuzioni** - Consente di gestire le informazioni sui piani di retribuzione di un lavoratore, ad esempio registrazione del piano, premi, prestazioni, provvigione, dati fiscali, pensionamento e detrazioni sullo stipendio.</span><span class="sxs-lookup"><span data-stu-id="de1db-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="de1db-261">Quando si immettono le informazioni su un lavoratore, tenere presenti i seguenti dati e le configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de1db-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="de1db-262">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="de1db-262">General information</span></span>

- <span data-ttu-id="de1db-263">Numero dipendente (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-263">Personnel number (required)</span></span>
- <span data-ttu-id="de1db-264">Nome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-264">First name (required)</span></span>
- <span data-ttu-id="de1db-265">Cognome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-265">Last name (required)</span></span>
- <span data-ttu-id="de1db-266">Secondo nome</span><span class="sxs-lookup"><span data-stu-id="de1db-266">Middle name</span></span>
- <span data-ttu-id="de1db-267">Data di anzianità</span><span class="sxs-lookup"><span data-stu-id="de1db-267">Seniority date</span></span>
- <span data-ttu-id="de1db-268">Nome noto</span><span class="sxs-lookup"><span data-stu-id="de1db-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="de1db-269">Informazioni personali</span><span class="sxs-lookup"><span data-stu-id="de1db-269">Personal information</span></span>

- <span data-ttu-id="de1db-270">Stato civile (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-270">Marital status (required)</span></span>
- <span data-ttu-id="de1db-271">Data di nascita (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-271">Birth date (required)</span></span>
- <span data-ttu-id="de1db-272">Sesso (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-272">Gender (required)</span></span>
- <span data-ttu-id="de1db-273">Persona disabile</span><span class="sxs-lookup"><span data-stu-id="de1db-273">Person with disabilities</span></span>
- <span data-ttu-id="de1db-274">Nazionalità paese regione (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="de1db-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="de1db-275">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="de1db-275">Address information</span></span>

- <span data-ttu-id="de1db-276">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-276">Primary (required)</span></span>
- <span data-ttu-id="de1db-277">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-277">Country/region (required)</span></span>
- <span data-ttu-id="de1db-278">Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-278">Postal code (required)</span></span>
- <span data-ttu-id="de1db-279">Numero civico (obbligatorio) (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="de1db-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="de1db-280">Informazioni aggiuntive sull'indirizzo (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="de1db-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="de1db-281">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-281">City (required)</span></span>
- <span data-ttu-id="de1db-282">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-282">State (required)</span></span>
- <span data-ttu-id="de1db-283">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="de1db-284">Informazioni contatto</span><span class="sxs-lookup"><span data-stu-id="de1db-284">Contact information</span></span> 

- <span data-ttu-id="de1db-285">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-285">Primary (required)</span></span>
- <span data-ttu-id="de1db-286">Numero contatto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-286">Contact number (required)</span></span>
- <span data-ttu-id="de1db-287">Interno</span><span class="sxs-lookup"><span data-stu-id="de1db-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="de1db-288">Informazioni sulle retribuzioni e codici di reddito</span><span class="sxs-lookup"><span data-stu-id="de1db-288">Payroll information and earning codes</span></span>

<span data-ttu-id="de1db-289">Ai dipendenti possono essere assegnati redditi specifici a una determinata frequenza di pagamento e un metodo di pagamento preferito.</span><span class="sxs-lookup"><span data-stu-id="de1db-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="de1db-290">I campi seguenti vengono utilizzati in Dayforce per garantire che le preferenze e le impostazioni vengano utilizzate.</span><span class="sxs-lookup"><span data-stu-id="de1db-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="de1db-291">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="de1db-291">Earning codes</span></span>

- <span data-ttu-id="de1db-292">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-292">Position (required)</span></span>
- <span data-ttu-id="de1db-293">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-293">Earning Code (required)</span></span>
- <span data-ttu-id="de1db-294">Frequenza (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-294">Frequency (required)</span></span>
- <span data-ttu-id="de1db-295">Importo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="de1db-296">Informazioni retribuzioni</span><span class="sxs-lookup"><span data-stu-id="de1db-296">Payroll information</span></span>

- <span data-ttu-id="de1db-297">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="de1db-297">Payment Method</span></span>
- <span data-ttu-id="de1db-298">Area economica (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-298">Economic Region (required)</span></span>
- <span data-ttu-id="de1db-299">ID benefit dipendente</span><span class="sxs-lookup"><span data-stu-id="de1db-299">Employee Benefits ID</span></span>
- <span data-ttu-id="de1db-300">Numero documento identità (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-300">National ID Number (required)</span></span>
- <span data-ttu-id="de1db-301">Numero servizio militare</span><span class="sxs-lookup"><span data-stu-id="de1db-301">Military Service Number</span></span>
- <span data-ttu-id="de1db-302">ID turno (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-302">Shift ID (required)</span></span>
- <span data-ttu-id="de1db-303">Numero imposta (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-303">Tax Number (required)</span></span>
- <span data-ttu-id="de1db-304">ID sindacato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-304">Union ID (required)</span></span>
- <span data-ttu-id="de1db-305">ID giorno lavorativo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-305">Work Day ID (required)</span></span>
- <span data-ttu-id="de1db-306">Numero permesso di lavoro</span><span class="sxs-lookup"><span data-stu-id="de1db-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="de1db-307">Per il metodo di pagamento, il Messico supporta **Contante**, **Assegno** (l'assegno fisico della società) e **Pagamento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="de1db-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="de1db-308">Se non viene specificato alcun metodo di pagamento, **Assegno** è 'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="de1db-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="de1db-309">Dettagli impiego</span><span class="sxs-lookup"><span data-stu-id="de1db-309">Employment details</span></span>

<span data-ttu-id="de1db-310">Lo storico dei dettagli impiego viene utilizzato come informazioni chiave da cui derivare gli stati di assunzione, termine e riassunzione di un dipendente Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de1db-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="de1db-311">Dayforce supporta solo un record di impiego attivo alla volta.</span><span class="sxs-lookup"><span data-stu-id="de1db-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="de1db-312">Data di inizio impiego (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-312">Employment start date (required)</span></span>
- <span data-ttu-id="de1db-313">Data di fine impiego</span><span class="sxs-lookup"><span data-stu-id="de1db-313">Employment end date</span></span>
- <span data-ttu-id="de1db-314">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="de1db-314">Start date</span></span>
- <span data-ttu-id="de1db-315">Data di inizio rettificata</span><span class="sxs-lookup"><span data-stu-id="de1db-315">Adjusted start date</span></span>
- <span data-ttu-id="de1db-316">Data fine rapporto (obbligatoria con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="de1db-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="de1db-317">Motivo fine rapporto (obbligatorio con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="de1db-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="de1db-318">Le date chiave del dipendente sono derivate utilizzando le informazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="de1db-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="de1db-319">Talent</span><span class="sxs-lookup"><span data-stu-id="de1db-319">Talent</span></span>                | <span data-ttu-id="de1db-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de1db-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="de1db-321">Data di assunzione più recente</span><span class="sxs-lookup"><span data-stu-id="de1db-321">Most recent hire date</span></span> | <span data-ttu-id="de1db-322">Inizio dell'impiego del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="de1db-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="de1db-323">Data fine rapporto</span><span class="sxs-lookup"><span data-stu-id="de1db-323">Termination date</span></span>      | <span data-ttu-id="de1db-324">Data di fine rapporto del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="de1db-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="de1db-325">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="de1db-325">Start date</span></span>            | <span data-ttu-id="de1db-326">Data di inizio rettificata, data di inizio o inizio dell'impiego del record corrente dello storico di impiego non attivo</span><span class="sxs-lookup"><span data-stu-id="de1db-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="de1db-327">Data di assunzione originale</span><span class="sxs-lookup"><span data-stu-id="de1db-327">Original hire date</span></span>    | <span data-ttu-id="de1db-328">Inizio dell'impiego del record dello storico di impiego meno recente</span><span class="sxs-lookup"><span data-stu-id="de1db-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="de1db-329">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="de1db-329">Compensation</span></span>

<span data-ttu-id="de1db-330">Un piano di retribuzione fissa deve essere associato alla posizione primaria di ogni dipendente durante un periodo di impiego.</span><span class="sxs-lookup"><span data-stu-id="de1db-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="de1db-331">Questo periodo inizia alla data in cui il dipendente è stato assunto (o la data di inizio dell'impiego) e continua fino alla fine del rapporto.</span><span class="sxs-lookup"><span data-stu-id="de1db-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="de1db-332">Data di validità (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-332">Effective Date (required)</span></span>
- <span data-ttu-id="de1db-333">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="de1db-333">Expiration date</span></span>
- <span data-ttu-id="de1db-334">Retribuzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-334">Pay Rate (required)</span></span>
- <span data-ttu-id="de1db-335">Conversioni retribuzione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="de1db-336">Equivalente annuale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="de1db-337">Equivalente orario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="de1db-338">Se un dipendente a ore ha più posizioni, la retribuzione fissa della posizione primaria viene importata in Dayforce come il tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="de1db-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="de1db-339">Per le posizioni non principali, la tariffa oraria viene salvata nella posizione corrispondente in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de1db-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="de1db-340">Se un dipendente stipendiato ha più posizioni, la tariffa oraria cumulativa e lo stipendio annuale di tutte le posizioni attive vengono calcolati e utilizzati come tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="de1db-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="de1db-341">Numeri di identificazione</span><span class="sxs-lookup"><span data-stu-id="de1db-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="de1db-342">Numero di Previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="de1db-342">Social Security identifier</span></span> 

<span data-ttu-id="de1db-343">Ogni dipendente deve avere un identificatore primario.</span><span class="sxs-lookup"><span data-stu-id="de1db-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="de1db-344">Questo identificatore deve essere di tipo identificatore **SSN**.</span><span class="sxs-lookup"><span data-stu-id="de1db-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="de1db-345">In Dayforce, viene ricavato automaticamente come identificatore di previdenza sociale del dipendente per l'assunzione.</span><span class="sxs-lookup"><span data-stu-id="de1db-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="de1db-346">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-346">Primary (required)</span></span>
- <span data-ttu-id="de1db-347">Tipo di identificazione = "SSN"</span><span class="sxs-lookup"><span data-stu-id="de1db-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="de1db-348">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="de1db-348">Issued Date</span></span>
- <span data-ttu-id="de1db-349">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="de1db-349">Expiration Date</span></span>

<span data-ttu-id="de1db-350">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **SSN**.</span><span class="sxs-lookup"><span data-stu-id="de1db-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="de1db-351">Tuttavia, solo il record che è contrassegnato come **Primario** viene integrato in Dayforce, a prescindere che il numero sia attivo o scaduto.</span><span class="sxs-lookup"><span data-stu-id="de1db-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="de1db-352">Esborsi e conti bancari</span><span class="sxs-lookup"><span data-stu-id="de1db-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="de1db-353">È necessario immettere informazioni sul conto bancario valide per un dipendente che scelga di essere pagato tramite trasferimenti di conto bancario.</span><span class="sxs-lookup"><span data-stu-id="de1db-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="de1db-354">Talent</span><span class="sxs-lookup"><span data-stu-id="de1db-354">Talent</span></span>                         | <span data-ttu-id="de1db-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de1db-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="de1db-356">Numero conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="de1db-357">Codice SWIFT (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-357">SWIFT code (required)</span></span>          | <span data-ttu-id="de1db-358">Campo **ID banca** utilizzato durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="de1db-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="de1db-359">Codice filiale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="de1db-360">Tipo di conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-360">Bank account type (required)</span></span>   | <span data-ttu-id="de1db-361">Campo **Tipo di conto** utilizzando durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="de1db-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="de1db-362">I valori supportati includono **Controllo** e **Retribuzioni**.</span><span class="sxs-lookup"><span data-stu-id="de1db-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="de1db-363">I dipendenti che scelgono di essere pagati tramite trasferimenti di conto bancario devono fornire un collegamento a un conto rimanente che è sotto la persona giuridica che ha l'indirizzo primario in Messico ed è associato a un conto bancario valido presso una banca messicana.</span><span class="sxs-lookup"><span data-stu-id="de1db-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="de1db-364">Tutti gli altri account non di rimanenze verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="de1db-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="de1db-365">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="de1db-365">Address information</span></span>

<span data-ttu-id="de1db-366">Ogni dipendente deve avere un'ubicazione primaria.</span><span class="sxs-lookup"><span data-stu-id="de1db-366">Every employee must have one primary location.</span></span> <span data-ttu-id="de1db-367">In Dayforce, questa ubicazione viene utilizzata per determinare la principale residenza del dipendente a scopo fiscale.</span><span class="sxs-lookup"><span data-stu-id="de1db-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="de1db-368">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-368">Primary (required)</span></span>
- <span data-ttu-id="de1db-369">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-369">Country/region (required)</span></span>
- <span data-ttu-id="de1db-370">CAP/Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="de1db-371">Via (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-371">Street (required)</span></span>
- <span data-ttu-id="de1db-372">Numero civico (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-372">Street Number (required)</span></span>
- <span data-ttu-id="de1db-373">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="de1db-373">Building Complement</span></span>
- <span data-ttu-id="de1db-374">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-374">City (required)</span></span>
- <span data-ttu-id="de1db-375">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-375">State (required)</span></span>
- <span data-ttu-id="de1db-376">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="de1db-377">Configurare i dati per generare le retribuzioni negli Stati Uniti e in Canada</span><span class="sxs-lookup"><span data-stu-id="de1db-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="de1db-378">Se si desidera generare la retribuzione per i dipendenti negli Stati Uniti e in Canada, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="de1db-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="de1db-379">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="de1db-379">Departments are required on positions.</span></span>
- <span data-ttu-id="de1db-380">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="de1db-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="de1db-381">Tipi di posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="de1db-381">Job types</span></span>

<span data-ttu-id="de1db-382">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="de1db-382">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="de1db-383">I tipi di mansione sono necessari per elaborare le retribuzioni negli Stati Uniti e in Canada.</span><span class="sxs-lookup"><span data-stu-id="de1db-383">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="de1db-384">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="de1db-384">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="de1db-385">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="de1db-385">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="de1db-386">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="de1db-386">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="de1db-387">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="de1db-387">Job type</span></span>   | <span data-ttu-id="de1db-388">descrizione</span><span class="sxs-lookup"><span data-stu-id="de1db-388">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="de1db-389">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="de1db-389">Hourly</span></span>     | <span data-ttu-id="de1db-390">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="de1db-390">Hourly</span></span>      |
| <span data-ttu-id="de1db-391">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="de1db-391">Salaried</span></span>   | <span data-ttu-id="de1db-392">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="de1db-392">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="de1db-393">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="de1db-393">Position types</span></span> 

<span data-ttu-id="de1db-394">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="de1db-394">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="de1db-395">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="de1db-395">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="de1db-396">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="de1db-396">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="de1db-397">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="de1db-397">Position type</span></span>   | <span data-ttu-id="de1db-398">descrizione</span><span class="sxs-lookup"><span data-stu-id="de1db-398">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="de1db-399">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="de1db-399">Full-time</span></span>       | <span data-ttu-id="de1db-400">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="de1db-400">Full time employee</span></span> |
| <span data-ttu-id="de1db-401">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="de1db-401">Part-time</span></span>       | <span data-ttu-id="de1db-402">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="de1db-402">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="de1db-403">Codici causale</span><span class="sxs-lookup"><span data-stu-id="de1db-403">Reason codes</span></span>

<span data-ttu-id="de1db-404">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="de1db-404">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="de1db-405">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="de1db-405">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="de1db-406">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="de1db-406">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="de1db-407">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="de1db-407">Reason code</span></span>    | <span data-ttu-id="de1db-408">descrizione</span><span class="sxs-lookup"><span data-stu-id="de1db-408">Description</span></span>      | <span data-ttu-id="de1db-409">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="de1db-409">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="de1db-410">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="de1db-410">RESIGNATION</span></span>    | <span data-ttu-id="de1db-411">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="de1db-411">Resignation</span></span>      | <span data-ttu-id="de1db-412">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-412">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-413">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="de1db-413">TERMINATION</span></span>    | <span data-ttu-id="de1db-414">Fine</span><span class="sxs-lookup"><span data-stu-id="de1db-414">Termination</span></span>      | <span data-ttu-id="de1db-415">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-415">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-416">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="de1db-416">RETIREMENT</span></span>     | <span data-ttu-id="de1db-417">Pensione</span><span class="sxs-lookup"><span data-stu-id="de1db-417">Retirement</span></span>       | <span data-ttu-id="de1db-418">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-418">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-419">OTHER</span><span class="sxs-lookup"><span data-stu-id="de1db-419">OTHER</span></span>          | <span data-ttu-id="de1db-420">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="de1db-420">Other Reasons</span></span>    | <span data-ttu-id="de1db-421">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-421">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-422">DEATH</span><span class="sxs-lookup"><span data-stu-id="de1db-422">DEATH</span></span>          | <span data-ttu-id="de1db-423">Decesso</span><span class="sxs-lookup"><span data-stu-id="de1db-423">Death</span></span>            | <span data-ttu-id="de1db-424">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-424">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-425">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="de1db-425">LEAVEOFABSENCE</span></span> | <span data-ttu-id="de1db-426">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="de1db-426">Leave of Absence</span></span> | <span data-ttu-id="de1db-427">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-427">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-428">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="de1db-428">CONTRACTEND</span></span>    | <span data-ttu-id="de1db-429">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="de1db-429">End of Contract</span></span>  | <span data-ttu-id="de1db-430">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-430">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-431">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="de1db-431">SALARYCHANGE</span></span>   | <span data-ttu-id="de1db-432">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="de1db-432">Change of Salary</span></span> | <span data-ttu-id="de1db-433">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="de1db-433">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="de1db-434">Stato civile</span><span class="sxs-lookup"><span data-stu-id="de1db-434">Marital status</span></span>

<span data-ttu-id="de1db-435">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="de1db-435">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="de1db-436">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de1db-436">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="de1db-437">Talent</span><span class="sxs-lookup"><span data-stu-id="de1db-437">Talent</span></span>                 | <span data-ttu-id="de1db-438">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de1db-438">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="de1db-439">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="de1db-439">Married</span></span>                | <span data-ttu-id="de1db-440">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="de1db-440">Married</span></span>              |
| <span data-ttu-id="de1db-441">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="de1db-441">Single</span></span>                 | <span data-ttu-id="de1db-442">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="de1db-442">Single</span></span>               |
| <span data-ttu-id="de1db-443">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="de1db-443">Widowed</span></span>                | <span data-ttu-id="de1db-444">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="de1db-444">Widowed</span></span>              |
| <span data-ttu-id="de1db-445">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="de1db-445">Divorced</span></span>               | <span data-ttu-id="de1db-446">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="de1db-446">Divorced</span></span>             |
| <span data-ttu-id="de1db-447">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="de1db-447">Registered Partnership</span></span> | <span data-ttu-id="de1db-448">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="de1db-448">Domestic Partnership</span></span> |
| <span data-ttu-id="de1db-449">Nessuna</span><span class="sxs-lookup"><span data-stu-id="de1db-449">None</span></span>                   | <span data-ttu-id="de1db-450">Nessuna</span><span class="sxs-lookup"><span data-stu-id="de1db-450">None</span></span>                 |
| <span data-ttu-id="de1db-451">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="de1db-451">Cohabiting</span></span>             | <span data-ttu-id="de1db-452">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="de1db-452">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="de1db-453">Genere</span><span class="sxs-lookup"><span data-stu-id="de1db-453">Gender</span></span>

<span data-ttu-id="de1db-454">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="de1db-454">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="de1db-455">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de1db-455">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="de1db-456">Talent</span><span class="sxs-lookup"><span data-stu-id="de1db-456">Talent</span></span>       | <span data-ttu-id="de1db-457">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de1db-457">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="de1db-458">Maschio</span><span class="sxs-lookup"><span data-stu-id="de1db-458">Male</span></span>         | <span data-ttu-id="de1db-459">Maschio</span><span class="sxs-lookup"><span data-stu-id="de1db-459">Male</span></span>            |
| <span data-ttu-id="de1db-460">Femmina</span><span class="sxs-lookup"><span data-stu-id="de1db-460">Female</span></span>       | <span data-ttu-id="de1db-461">Femmina</span><span class="sxs-lookup"><span data-stu-id="de1db-461">Female</span></span>          |
| <span data-ttu-id="de1db-462">Non specifico</span><span class="sxs-lookup"><span data-stu-id="de1db-462">Non-specific</span></span> | <span data-ttu-id="de1db-463">*Non supportato*</span><span class="sxs-lookup"><span data-stu-id="de1db-463">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="de1db-464">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="de1db-464">Earning codes</span></span>

<span data-ttu-id="de1db-465">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="de1db-465">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="de1db-466">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="de1db-466">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="de1db-467">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="de1db-467">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="de1db-468">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="de1db-468">Supported frequencies</span></span>

- <span data-ttu-id="de1db-469">Tutti</span><span class="sxs-lookup"><span data-stu-id="de1db-469">All</span></span>
- <span data-ttu-id="de1db-470">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="de1db-470">EVERYPAY</span></span>
- <span data-ttu-id="de1db-471">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="de1db-471">EACHPAYPERIOD</span></span>
- <span data-ttu-id="de1db-472">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="de1db-472">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="de1db-473">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="de1db-473">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="de1db-474">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-474">1OFMTH</span></span>
- <span data-ttu-id="de1db-475">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-475">LASTOFMTH</span></span>
- <span data-ttu-id="de1db-476">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-476">2OFMTH</span></span>
- <span data-ttu-id="de1db-477">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-477">3OFMTH</span></span>
- <span data-ttu-id="de1db-478">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-478">4OFMTH</span></span>
- <span data-ttu-id="de1db-479">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-479">5OFMTH</span></span>
- <span data-ttu-id="de1db-480">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-480">1N2OFMTH</span></span>
- <span data-ttu-id="de1db-481">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-481">3N4OFMTH</span></span>
- <span data-ttu-id="de1db-482">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-482">1N3OFMTH</span></span>
- <span data-ttu-id="de1db-483">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-483">1N4OFMTH</span></span>
- <span data-ttu-id="de1db-484">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-484">2N3OFMTH</span></span>
- <span data-ttu-id="de1db-485">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-485">2N4OFMTH</span></span>
- <span data-ttu-id="de1db-486">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-486">1N2N3OFMTH</span></span>
- <span data-ttu-id="de1db-487">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-487">1N2N4OFMTH</span></span>
- <span data-ttu-id="de1db-488">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-488">1N3N4OFMTH</span></span>
- <span data-ttu-id="de1db-489">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-489">2N3N4OFMTH</span></span>
- <span data-ttu-id="de1db-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="de1db-491">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="de1db-491">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="de1db-492">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="de1db-492">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="de1db-493">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="de1db-493">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="de1db-494">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="de1db-494">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="de1db-495">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="de1db-495">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="de1db-496">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="de1db-496">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="de1db-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="de1db-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="de1db-498">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="de1db-498">Addresses</span></span>

<span data-ttu-id="de1db-499">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="de1db-499">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="de1db-500">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="de1db-500">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="de1db-501">Talent</span><span class="sxs-lookup"><span data-stu-id="de1db-501">Talent</span></span>          | <span data-ttu-id="de1db-502">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de1db-502">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="de1db-503">Paese</span><span class="sxs-lookup"><span data-stu-id="de1db-503">Country/Region</span></span>  | <span data-ttu-id="de1db-504">Codice paese</span><span class="sxs-lookup"><span data-stu-id="de1db-504">Country Code</span></span>          |
| <span data-ttu-id="de1db-505">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="de1db-505">Zip/Postal Code</span></span> | <span data-ttu-id="de1db-506">CAP</span><span class="sxs-lookup"><span data-stu-id="de1db-506">Postal Code</span></span>           |
| <span data-ttu-id="de1db-507">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="de1db-507">State</span></span>           | <span data-ttu-id="de1db-508">Codice stato</span><span class="sxs-lookup"><span data-stu-id="de1db-508">State Code</span></span>            |
| <span data-ttu-id="de1db-509">Città</span><span class="sxs-lookup"><span data-stu-id="de1db-509">City</span></span>            | <span data-ttu-id="de1db-510">Città</span><span class="sxs-lookup"><span data-stu-id="de1db-510">City</span></span>                  |
| <span data-ttu-id="de1db-511">Regione</span><span class="sxs-lookup"><span data-stu-id="de1db-511">County</span></span>          | <span data-ttu-id="de1db-512">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="de1db-512">County (Municipality)</span></span> |
| <span data-ttu-id="de1db-513">Via</span><span class="sxs-lookup"><span data-stu-id="de1db-513">Street</span></span>          | <span data-ttu-id="de1db-514">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="de1db-514">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="de1db-515">Regioni fiscali</span><span class="sxs-lookup"><span data-stu-id="de1db-515">Tax regions</span></span>

<span data-ttu-id="de1db-516">Le regioni fiscali vengono utilizzate per determinare l'imposta appropriata che deve essere applicata durante la generazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="de1db-516">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="de1db-517">Le regioni fiscali vengono mappate in Dayforce come indirizzi di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="de1db-517">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="de1db-518">La regione fiscale predefinita deve essere associata alla posizione attiva del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="de1db-518">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="de1db-519">Regione fiscale (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-519">Tax region (required)</span></span>
- <span data-ttu-id="de1db-520">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-520">Country/Region (required)</span></span>
- <span data-ttu-id="de1db-521">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="de1db-521">State (required)</span></span>
- <span data-ttu-id="de1db-522">Regione</span><span class="sxs-lookup"><span data-stu-id="de1db-522">County</span></span> 
- <span data-ttu-id="de1db-523">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="de1db-523">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="de1db-524">Configurare i dati per generare le retribuzioni in Messico</span><span class="sxs-lookup"><span data-stu-id="de1db-524">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="de1db-525">Se si desidera generare la retribuzione per i dipendenti in Messico, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="de1db-525">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="de1db-526">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="de1db-526">Departments are required on positions.</span></span>
- <span data-ttu-id="de1db-527">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="de1db-527">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="de1db-528">Tipi di posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="de1db-528">Job types</span></span>

<span data-ttu-id="de1db-529">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="de1db-529">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="de1db-530">Tipi di mansione necessari per elaborare le retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="de1db-530">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="de1db-531">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="de1db-531">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="de1db-532">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="de1db-532">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="de1db-533">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="de1db-533">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="de1db-534">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="de1db-534">Job type</span></span>   | <span data-ttu-id="de1db-535">descrizione</span><span class="sxs-lookup"><span data-stu-id="de1db-535">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="de1db-536">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="de1db-536">Hourly</span></span>     | <span data-ttu-id="de1db-537">Su base oraria MX</span><span class="sxs-lookup"><span data-stu-id="de1db-537">MX Hourly</span></span>   |
| <span data-ttu-id="de1db-538">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="de1db-538">Salaried</span></span>   | <span data-ttu-id="de1db-539">Stipendiato MX</span><span class="sxs-lookup"><span data-stu-id="de1db-539">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="de1db-540">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="de1db-540">Position types</span></span> 

<span data-ttu-id="de1db-541">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="de1db-541">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="de1db-542">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="de1db-542">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="de1db-543">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="de1db-543">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="de1db-544">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="de1db-544">Position type</span></span>   | <span data-ttu-id="de1db-545">descrizione</span><span class="sxs-lookup"><span data-stu-id="de1db-545">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="de1db-546">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="de1db-546">Full-time</span></span>       | <span data-ttu-id="de1db-547">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="de1db-547">Full time employee</span></span> |
| <span data-ttu-id="de1db-548">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="de1db-548">Part-time</span></span>       | <span data-ttu-id="de1db-549">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="de1db-549">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="de1db-550">Codici causale</span><span class="sxs-lookup"><span data-stu-id="de1db-550">Reason codes</span></span>

<span data-ttu-id="de1db-551">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="de1db-551">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="de1db-552">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="de1db-552">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="de1db-553">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="de1db-553">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="de1db-554">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="de1db-554">Reason code</span></span>            | <span data-ttu-id="de1db-555">descrizione</span><span class="sxs-lookup"><span data-stu-id="de1db-555">Description</span></span>                    | <span data-ttu-id="de1db-556">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="de1db-556">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="de1db-557">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="de1db-557">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="de1db-558">Partenza prima della prima retribuzione</span><span class="sxs-lookup"><span data-stu-id="de1db-558">Departure before first payroll</span></span> | <span data-ttu-id="de1db-559">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-559">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-560">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="de1db-560">RESIGNATION</span></span>            | <span data-ttu-id="de1db-561">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="de1db-561">Resignation</span></span>                    | <span data-ttu-id="de1db-562">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-562">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-563">PENSION</span><span class="sxs-lookup"><span data-stu-id="de1db-563">PENSION</span></span>                | <span data-ttu-id="de1db-564">Pensionamento</span><span class="sxs-lookup"><span data-stu-id="de1db-564">Pension</span></span>                        | <span data-ttu-id="de1db-565">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-565">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-566">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="de1db-566">TERMINATION</span></span>            | <span data-ttu-id="de1db-567">Fine</span><span class="sxs-lookup"><span data-stu-id="de1db-567">Termination</span></span>                    | <span data-ttu-id="de1db-568">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-568">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-569">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="de1db-569">RETIREMENT</span></span>             | <span data-ttu-id="de1db-570">Pensione</span><span class="sxs-lookup"><span data-stu-id="de1db-570">Retirement</span></span>                     | <span data-ttu-id="de1db-571">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-571">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-572">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="de1db-572">ABSENTEE</span></span>               | <span data-ttu-id="de1db-573">Assente</span><span class="sxs-lookup"><span data-stu-id="de1db-573">Absentee</span></span>                       | <span data-ttu-id="de1db-574">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-574">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-575">OTHER</span><span class="sxs-lookup"><span data-stu-id="de1db-575">OTHER</span></span>                  | <span data-ttu-id="de1db-576">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="de1db-576">Other Reasons</span></span>                  | <span data-ttu-id="de1db-577">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-577">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-578">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="de1db-578">CLOSURE</span></span>                | <span data-ttu-id="de1db-579">Chiusura attività</span><span class="sxs-lookup"><span data-stu-id="de1db-579">Business Closure</span></span>               | <span data-ttu-id="de1db-580">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-580">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-581">DEATH</span><span class="sxs-lookup"><span data-stu-id="de1db-581">DEATH</span></span>                  | <span data-ttu-id="de1db-582">Decesso</span><span class="sxs-lookup"><span data-stu-id="de1db-582">Death</span></span>                          | <span data-ttu-id="de1db-583">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-583">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-584">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="de1db-584">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="de1db-585">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="de1db-585">Leave of Absence</span></span>               | <span data-ttu-id="de1db-586">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-586">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-587">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="de1db-587">CONTRACTEND</span></span>            | <span data-ttu-id="de1db-588">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="de1db-588">End of Contract</span></span>                | <span data-ttu-id="de1db-589">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="de1db-589">Terminate worker</span></span>     |
| <span data-ttu-id="de1db-590">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="de1db-590">SALARYCHANGE</span></span>           | <span data-ttu-id="de1db-591">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="de1db-591">Change of Salary</span></span>               | <span data-ttu-id="de1db-592">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="de1db-592">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="de1db-593">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="de1db-593">Terms of employment</span></span>

<span data-ttu-id="de1db-594">Le condizioni di impiego vengono utilizzate per creare categorie di termini di impiego.</span><span class="sxs-lookup"><span data-stu-id="de1db-594">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="de1db-595">I termini vengono mappati in Dayforce come valori degli indicatori di impiego.</span><span class="sxs-lookup"><span data-stu-id="de1db-595">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="de1db-596">I seguenti termini di impiego e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="de1db-596">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="de1db-597">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="de1db-597">Terms of employment</span></span>   | <span data-ttu-id="de1db-598">descrizione</span><span class="sxs-lookup"><span data-stu-id="de1db-598">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="de1db-599">Regolare</span><span class="sxs-lookup"><span data-stu-id="de1db-599">Regular</span></span>               | <span data-ttu-id="de1db-600">Regolare</span><span class="sxs-lookup"><span data-stu-id="de1db-600">Regular</span></span>     |
| <span data-ttu-id="de1db-601">Diretto</span><span class="sxs-lookup"><span data-stu-id="de1db-601">Direct</span></span>                | <span data-ttu-id="de1db-602">Diretto</span><span class="sxs-lookup"><span data-stu-id="de1db-602">Direct</span></span>      |
| <span data-ttu-id="de1db-603">Internato</span><span class="sxs-lookup"><span data-stu-id="de1db-603">Internship</span></span>            | <span data-ttu-id="de1db-604">Internato</span><span class="sxs-lookup"><span data-stu-id="de1db-604">Internship</span></span>  |
| <span data-ttu-id="de1db-605">Permanente</span><span class="sxs-lookup"><span data-stu-id="de1db-605">Permanent</span></span>             | <span data-ttu-id="de1db-606">Permanente</span><span class="sxs-lookup"><span data-stu-id="de1db-606">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="de1db-607">Stato civile</span><span class="sxs-lookup"><span data-stu-id="de1db-607">Marital status</span></span>

<span data-ttu-id="de1db-608">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="de1db-608">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="de1db-609">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de1db-609">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="de1db-610">Talent</span><span class="sxs-lookup"><span data-stu-id="de1db-610">Talent</span></span>                 | <span data-ttu-id="de1db-611">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de1db-611">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="de1db-612">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="de1db-612">Married</span></span>                | <span data-ttu-id="de1db-613">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="de1db-613">Married</span></span>                   |
| <span data-ttu-id="de1db-614">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="de1db-614">Single</span></span>                 | <span data-ttu-id="de1db-615">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="de1db-615">Single</span></span>                    |
| <span data-ttu-id="de1db-616">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="de1db-616">Widowed</span></span>                | <span data-ttu-id="de1db-617">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="de1db-617">Widowed</span></span>                   |
| <span data-ttu-id="de1db-618">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="de1db-618">Divorced</span></span>               | <span data-ttu-id="de1db-619">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="de1db-619">Divorced</span></span>                  |
| <span data-ttu-id="de1db-620">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="de1db-620">Registered Partnership</span></span> | <span data-ttu-id="de1db-621">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="de1db-621">Domestic Partnership</span></span>      |
| <span data-ttu-id="de1db-622">Nessuna</span><span class="sxs-lookup"><span data-stu-id="de1db-622">None</span></span>                   | <span data-ttu-id="de1db-623">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="de1db-623">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="de1db-624">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="de1db-624">Cohabiting</span></span>             | <span data-ttu-id="de1db-625">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="de1db-625">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="de1db-626">Genere</span><span class="sxs-lookup"><span data-stu-id="de1db-626">Gender</span></span>

<span data-ttu-id="de1db-627">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="de1db-627">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="de1db-628">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de1db-628">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="de1db-629">Talent</span><span class="sxs-lookup"><span data-stu-id="de1db-629">Talent</span></span>       | <span data-ttu-id="de1db-630">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de1db-630">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="de1db-631">Maschio</span><span class="sxs-lookup"><span data-stu-id="de1db-631">Male</span></span>         | <span data-ttu-id="de1db-632">Maschio</span><span class="sxs-lookup"><span data-stu-id="de1db-632">Male</span></span>                      |
| <span data-ttu-id="de1db-633">Femmina</span><span class="sxs-lookup"><span data-stu-id="de1db-633">Female</span></span>       | <span data-ttu-id="de1db-634">Femmina</span><span class="sxs-lookup"><span data-stu-id="de1db-634">Female</span></span>                    |
| <span data-ttu-id="de1db-635">Non specifico</span><span class="sxs-lookup"><span data-stu-id="de1db-635">Non-specific</span></span> | <span data-ttu-id="de1db-636">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="de1db-636">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="de1db-637">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="de1db-637">Payment method</span></span>

<span data-ttu-id="de1db-638">I metodi di pagamento offrono al dipendente e all'azienda un modo per descrivere la modalità di pagamento dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="de1db-638">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="de1db-639">I metodi di pagamento vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="de1db-639">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="de1db-640">Nella tabella seguente vengono illustrati in che modo i metodi di pagamento vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de1db-640">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="de1db-641">Talent</span><span class="sxs-lookup"><span data-stu-id="de1db-641">Talent</span></span>             | <span data-ttu-id="de1db-642">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de1db-642">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="de1db-643">In contanti</span><span class="sxs-lookup"><span data-stu-id="de1db-643">Cash</span></span>               | <span data-ttu-id="de1db-644">In contanti</span><span class="sxs-lookup"><span data-stu-id="de1db-644">Cash</span></span>                      |
| <span data-ttu-id="de1db-645">Pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="de1db-645">Electronic Payment</span></span> | <span data-ttu-id="de1db-646">Trasferimenti</span><span class="sxs-lookup"><span data-stu-id="de1db-646">Transfer</span></span>                  |
| <span data-ttu-id="de1db-647">Verifica</span><span class="sxs-lookup"><span data-stu-id="de1db-647">Check</span></span>              | <span data-ttu-id="de1db-648">Assegno</span><span class="sxs-lookup"><span data-stu-id="de1db-648">Cheque</span></span>                    |
| <span data-ttu-id="de1db-649">Assegno circolare</span><span class="sxs-lookup"><span data-stu-id="de1db-649">Bank Draft</span></span>         | <span data-ttu-id="de1db-650">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="de1db-650">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="de1db-651">Altro</span><span class="sxs-lookup"><span data-stu-id="de1db-651">Other</span></span>              | <span data-ttu-id="de1db-652">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="de1db-652">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="de1db-653">Tipo di conto bancario</span><span class="sxs-lookup"><span data-stu-id="de1db-653">Bank account type</span></span>

<span data-ttu-id="de1db-654">I tipi di conto bancario vengono utilizzati per i pagamenti elettronici ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="de1db-654">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="de1db-655">I tipi di conto bancario vengono mappati in Dayforce come informazioni sul conto di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="de1db-655">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="de1db-656">I tipi di conto bancario vengono convertiti, come appropriato, nei valori accettati per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="de1db-656">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="de1db-657">Talent</span><span class="sxs-lookup"><span data-stu-id="de1db-657">Talent</span></span>            | <span data-ttu-id="de1db-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de1db-658">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="de1db-659">Conto corrente</span><span class="sxs-lookup"><span data-stu-id="de1db-659">Checking Account</span></span>  | <span data-ttu-id="de1db-660">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="de1db-660">CheckingAccount</span></span>           |
| <span data-ttu-id="de1db-661">Conto retribuzioni</span><span class="sxs-lookup"><span data-stu-id="de1db-661">Payroll Account</span></span>   | <span data-ttu-id="de1db-662">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="de1db-662">PayrollAccount</span></span>            |
| <span data-ttu-id="de1db-663">Conto di risparmio</span><span class="sxs-lookup"><span data-stu-id="de1db-663">Savings Account</span></span>   | <span data-ttu-id="de1db-664">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="de1db-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="de1db-665">Conto Bankgirot</span><span class="sxs-lookup"><span data-stu-id="de1db-665">BankGirot account</span></span> | <span data-ttu-id="de1db-666">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="de1db-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="de1db-667">Conto PlusGirot</span><span class="sxs-lookup"><span data-stu-id="de1db-667">PlusGirot account</span></span> | <span data-ttu-id="de1db-668">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="de1db-668">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="de1db-669">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="de1db-669">Earning codes</span></span>

<span data-ttu-id="de1db-670">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="de1db-670">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="de1db-671">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="de1db-671">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="de1db-672">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="de1db-672">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="de1db-673">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="de1db-673">Supported frequencies</span></span>

- <span data-ttu-id="de1db-674">Tutti</span><span class="sxs-lookup"><span data-stu-id="de1db-674">All</span></span>
- <span data-ttu-id="de1db-675">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="de1db-675">EVERYPAY</span></span>
- <span data-ttu-id="de1db-676">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="de1db-676">EACHPAYPERIOD</span></span>
- <span data-ttu-id="de1db-677">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="de1db-677">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="de1db-678">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="de1db-678">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="de1db-679">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-679">1OFMTH</span></span>
- <span data-ttu-id="de1db-680">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-680">LASTOFMTH</span></span>
- <span data-ttu-id="de1db-681">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-681">2OFMTH</span></span>
- <span data-ttu-id="de1db-682">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-682">3OFMTH</span></span>
- <span data-ttu-id="de1db-683">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-683">4OFMTH</span></span>
- <span data-ttu-id="de1db-684">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-684">5OFMTH</span></span>
- <span data-ttu-id="de1db-685">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-685">1N2OFMTH</span></span>
- <span data-ttu-id="de1db-686">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-686">3N4OFMTH</span></span>
- <span data-ttu-id="de1db-687">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-687">1N3OFMTH</span></span>
- <span data-ttu-id="de1db-688">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-688">1N4OFMTH</span></span>
- <span data-ttu-id="de1db-689">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-689">2N3OFMTH</span></span>
- <span data-ttu-id="de1db-690">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-690">2N4OFMTH</span></span>
- <span data-ttu-id="de1db-691">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-691">1N2N3OFMTH</span></span>
- <span data-ttu-id="de1db-692">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-692">1N2N4OFMTH</span></span>
- <span data-ttu-id="de1db-693">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-693">1N3N4OFMTH</span></span>
- <span data-ttu-id="de1db-694">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-694">2N3N4OFMTH</span></span>
- <span data-ttu-id="de1db-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="de1db-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="de1db-696">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="de1db-696">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="de1db-697">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="de1db-697">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="de1db-698">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="de1db-698">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="de1db-699">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="de1db-699">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="de1db-700">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="de1db-700">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="de1db-701">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="de1db-701">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="de1db-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="de1db-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="de1db-703">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="de1db-703">Addresses</span></span>

<span data-ttu-id="de1db-704">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="de1db-704">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="de1db-705">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="de1db-705">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="de1db-706">Talent</span><span class="sxs-lookup"><span data-stu-id="de1db-706">Talent</span></span>              | <span data-ttu-id="de1db-707">Dayforce</span><span class="sxs-lookup"><span data-stu-id="de1db-707">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="de1db-708">Paese</span><span class="sxs-lookup"><span data-stu-id="de1db-708">Country/Region</span></span>      | <span data-ttu-id="de1db-709">Codice paese</span><span class="sxs-lookup"><span data-stu-id="de1db-709">Country Code</span></span>          |
| <span data-ttu-id="de1db-710">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="de1db-710">Zip/Postal Code</span></span>     | <span data-ttu-id="de1db-711">CAP</span><span class="sxs-lookup"><span data-stu-id="de1db-711">Postal Code</span></span>           |
| <span data-ttu-id="de1db-712">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="de1db-712">State</span></span>               | <span data-ttu-id="de1db-713">Codice stato</span><span class="sxs-lookup"><span data-stu-id="de1db-713">State Code</span></span>            |
| <span data-ttu-id="de1db-714">Città</span><span class="sxs-lookup"><span data-stu-id="de1db-714">City</span></span>                | <span data-ttu-id="de1db-715">Città</span><span class="sxs-lookup"><span data-stu-id="de1db-715">City</span></span>                  |
| <span data-ttu-id="de1db-716">Regione</span><span class="sxs-lookup"><span data-stu-id="de1db-716">County</span></span>              | <span data-ttu-id="de1db-717">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="de1db-717">County (Municipality)</span></span> |
| <span data-ttu-id="de1db-718">Via</span><span class="sxs-lookup"><span data-stu-id="de1db-718">Street</span></span>              | <span data-ttu-id="de1db-719">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="de1db-719">Address Line 1</span></span>        |
| <span data-ttu-id="de1db-720">Numero civico</span><span class="sxs-lookup"><span data-stu-id="de1db-720">Street Number</span></span>       | <span data-ttu-id="de1db-721">Riga indirizzo 2</span><span class="sxs-lookup"><span data-stu-id="de1db-721">Address Line 2</span></span>        |
| <span data-ttu-id="de1db-722">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="de1db-722">Building Complement</span></span> | <span data-ttu-id="de1db-723">Riga indirizzo 5</span><span class="sxs-lookup"><span data-stu-id="de1db-723">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="de1db-724">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="de1db-724">Passport number</span></span>

<span data-ttu-id="de1db-725">I dipendenti possono indicare le informazioni sul passaporto.</span><span class="sxs-lookup"><span data-stu-id="de1db-725">Employees can declare passport information.</span></span> <span data-ttu-id="de1db-726">Queste informazioni sono del tipo di identificazione **Passaporto** e vengono integrate in Dayforce come parte delle informazioni di un dipendente specifiche per il Messico.</span><span class="sxs-lookup"><span data-stu-id="de1db-726">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="de1db-727">Tipo di identificazione = "Passaporto"</span><span class="sxs-lookup"><span data-stu-id="de1db-727">Identification Type = "Passport"</span></span>
- <span data-ttu-id="de1db-728">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="de1db-728">Issued Date</span></span>
- <span data-ttu-id="de1db-729">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="de1db-729">Expiration Date</span></span>

<span data-ttu-id="de1db-730">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **Passaporto**.</span><span class="sxs-lookup"><span data-stu-id="de1db-730">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="de1db-731">Tuttavia, solo l'immissione del passaporto attivo corrente viene integrata in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="de1db-731">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="de1db-732">Se tutte le immissioni di passaporto sono scadute, in Dayforce viene integrato il passaporto di emissione più recente.</span><span class="sxs-lookup"><span data-stu-id="de1db-732">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>

