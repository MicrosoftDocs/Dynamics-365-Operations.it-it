---
title: Configurare l'integrazione delle retribuzioni tra Talent e Dayforce
description: In questo argomento viene descritto come configurare l'integrazione tra Microsoft Dynamics 365 for Talent e Ceridian Dayforce in modo da poter elaborare è un ciclo di pagamenti.
author: jcart1106
manager: AnnBe
ms.date: 07/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: fcddf82cffb9f0ba94b83eb21809b810585ebc9e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "304973"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="411f6-103">Configurare l'integrazione retribuzioni tra Talent e Dayforce</span><span class="sxs-lookup"><span data-stu-id="411f6-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="411f6-104">L'integrazione tra Microsoft Dynamics 365 for Talent e Ceridian Dayforce si basa su vari passaggi di configurazione descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="411f6-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="411f6-105">È necessario configurare l'integrazione sia in Talent che in Dayforce prima di poter elaborare un ciclo di pagamenti.</span><span class="sxs-lookup"><span data-stu-id="411f6-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="411f6-106">Quando si utilizza un servizio, ad esempio Dayforce, per completare i cicli di pagamenti, è necessario abilitare l'integrazione in Talent.</span><span class="sxs-lookup"><span data-stu-id="411f6-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="411f6-107">L'integrazione richiede dati specifici da Talent.</span><span class="sxs-lookup"><span data-stu-id="411f6-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="411f6-108">Di conseguenza, è necessario verificare che i dati che vengono mappati a Dayforce siano configurati in Talent in modo che supporti l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="411f6-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="411f6-109">L'integrazione utilizza le seguenti categorie generiche di dati:</span><span class="sxs-lookup"><span data-stu-id="411f6-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="411f6-110">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="411f6-110">Human resources data</span></span>
- <span data-ttu-id="411f6-111">Dati di compensazione</span><span class="sxs-lookup"><span data-stu-id="411f6-111">Compensation data</span></span>
- <span data-ttu-id="411f6-112">Data di retribuzione, ad esempio i cicli di pagamenti, i periodi retributivi e i codici reddito</span><span class="sxs-lookup"><span data-stu-id="411f6-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="411f6-113">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-113">Worker data</span></span>

<span data-ttu-id="411f6-114">In questo argomento vengono descritti i passaggi che è necessario completare per abilitare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="411f6-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="411f6-115">E vengono descritti i tipi di dati e i dettagli di configurazione necessari all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="411f6-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="411f6-116">Abilitare l'integrazione</span><span class="sxs-lookup"><span data-stu-id="411f6-116">Enable the integration</span></span>

<span data-ttu-id="411f6-117">In Talent è necessario attivare l'integrazione e immettere le informazioni di configurazione per connettersi a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="411f6-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="411f6-118">Se si desidera che la transazione contabile prodotta venga importata in Microsoft Dynamics 365 for Finance and Operations, è necessario impostare anche un conto di archiviazione di Microsoft Azure e immettere la stringa di connessione di Archiviazione di Azure in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="411f6-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="411f6-119">Per attivare l'integrazione in Talent, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="411f6-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="411f6-120">Nella pagina **Amministrazione sistema** selezionare **Configurazione di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="411f6-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="411f6-121">Immettere l'endpoint FTP (File Transfer Protocol) e il percorso protetto della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="411f6-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="411f6-122">Immettere il nome utente e la password dell'utente che accederà al percorso protetto dell'endpoint e della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="411f6-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="411f6-123">Verificare la connessione, secondo le esigenze, e impostare l'opzione **Abilita integrazione retribuzioni** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="411f6-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="411f6-124">Quando l'integrazione viene attivata, vengono creati i file e il pacchetto di esportazione dei dati e viene impostata la frequenza.</span><span class="sxs-lookup"><span data-stu-id="411f6-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="411f6-125">È possibile cambiare la frequenza in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="411f6-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="411f6-126">Per altre informazioni sugli account di Archiviazione di Azure e sulle stringhe di connessione di Archiviazione di Azure, vedere gli argomenti di Azure seguenti:</span><span class="sxs-lookup"><span data-stu-id="411f6-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="411f6-127">Account di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="411f6-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="411f6-128">Configurare le stringhe di connessione di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="411f6-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="411f6-129">Configurare i dati</span><span class="sxs-lookup"><span data-stu-id="411f6-129">Configure your data</span></span> 

<span data-ttu-id="411f6-130">Per elaborare le retribuzioni, è necessario configurare i dati di Risorse umane in Talent.</span><span class="sxs-lookup"><span data-stu-id="411f6-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="411f6-131">È necessario impostare i dati dell'organizzazione, ad esempio mansioni e posizioni, insieme alle informazioni sui benefit e sulle compensazioni.</span><span class="sxs-lookup"><span data-stu-id="411f6-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="411f6-132">Queste informazioni includono informazioni sull'impiego, la retribuzione e le detrazioni che sono richieste per generare la retribuzione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="411f6-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="411f6-133">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="411f6-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="411f6-134">Benefit</span><span class="sxs-lookup"><span data-stu-id="411f6-134">Benefits</span></span> 

<span data-ttu-id="411f6-135">Le risorse umane dispongono di strumenti per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori.</span><span class="sxs-lookup"><span data-stu-id="411f6-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="411f6-136">Quando si creano i benefit, tenere presenti i seguenti dati e configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="411f6-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="411f6-137">Piani di benefit</span><span class="sxs-lookup"><span data-stu-id="411f6-137">Benefit plans</span></span>

- <span data-ttu-id="411f6-138">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-138">Plan (required)</span></span>
- <span data-ttu-id="411f6-139">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-139">Type (required)</span></span>
- <span data-ttu-id="411f6-140">Impatto retribuzioni (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-140">Payroll impact (required)</span></span>
- <span data-ttu-id="411f6-141">Recupera arretrati</span><span class="sxs-lookup"><span data-stu-id="411f6-141">Recover arrears</span></span>
- <span data-ttu-id="411f6-142">Metodo di detrazione</span><span class="sxs-lookup"><span data-stu-id="411f6-142">Deduction method</span></span>
- <span data-ttu-id="411f6-143">Priorità detrazione</span><span class="sxs-lookup"><span data-stu-id="411f6-143">Deduction priority</span></span>
- <span data-ttu-id="411f6-144">Periodo limite</span><span class="sxs-lookup"><span data-stu-id="411f6-144">Limit period</span></span>
- <span data-ttu-id="411f6-145">Importo limite</span><span class="sxs-lookup"><span data-stu-id="411f6-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="411f6-146">Benefit</span><span class="sxs-lookup"><span data-stu-id="411f6-146">Benefits</span></span>

- <span data-ttu-id="411f6-147">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-147">Plan (required)</span></span>
- <span data-ttu-id="411f6-148">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-148">Type (required)</span></span>
- <span data-ttu-id="411f6-149">Opzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-149">Option (required)</span></span>
- <span data-ttu-id="411f6-150">ID benefit (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-150">Benefit ID (required)</span></span>
- <span data-ttu-id="411f6-151">Frequenza</span><span class="sxs-lookup"><span data-stu-id="411f6-151">Frequency</span></span>
- <span data-ttu-id="411f6-152">Base</span><span class="sxs-lookup"><span data-stu-id="411f6-152">Basis</span></span>
- <span data-ttu-id="411f6-153">Importo o coefficiente</span><span class="sxs-lookup"><span data-stu-id="411f6-153">Amount or rate</span></span>
- <span data-ttu-id="411f6-154">Codice di reddito</span><span class="sxs-lookup"><span data-stu-id="411f6-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="411f6-155">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="411f6-155">Supported frequencies</span></span> 

- <span data-ttu-id="411f6-156">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="411f6-156">Weekly</span></span>
- <span data-ttu-id="411f6-157">Bisettimanale</span><span class="sxs-lookup"><span data-stu-id="411f6-157">Bi-weekly</span></span>
- <span data-ttu-id="411f6-158">Quindicinale</span><span class="sxs-lookup"><span data-stu-id="411f6-158">Semi-monthly</span></span>
- <span data-ttu-id="411f6-159">Ogni mese</span><span class="sxs-lookup"><span data-stu-id="411f6-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="411f6-160">Basi supportate</span><span class="sxs-lookup"><span data-stu-id="411f6-160">Supported bases</span></span> 

- <span data-ttu-id="411f6-161">Importo fisso</span><span class="sxs-lookup"><span data-stu-id="411f6-161">Fixed amount</span></span>
- <span data-ttu-id="411f6-162">Percentuale di redditi</span><span class="sxs-lookup"><span data-stu-id="411f6-162">Percent of earnings</span></span>
- <span data-ttu-id="411f6-163">Ore di produzione</span><span class="sxs-lookup"><span data-stu-id="411f6-163">Productive hours</span></span>

<span data-ttu-id="411f6-164">Dayforce crea le seguenti detrazioni, in base all'impatto delle retribuzioni definito nel piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="411f6-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="411f6-165">Selezione in Talent</span><span class="sxs-lookup"><span data-stu-id="411f6-165">Selection in Talent</span></span>        | <span data-ttu-id="411f6-166">Risultato in Dayforce</span><span class="sxs-lookup"><span data-stu-id="411f6-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="411f6-167">Nessuna</span><span class="sxs-lookup"><span data-stu-id="411f6-167">None</span></span>                       | <span data-ttu-id="411f6-168">Non viene creata alcuna detrazione.</span><span class="sxs-lookup"><span data-stu-id="411f6-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="411f6-169">Solo detrazione</span><span class="sxs-lookup"><span data-stu-id="411f6-169">Deduction only</span></span>             | <span data-ttu-id="411f6-170">Viene creata una detrazione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="411f6-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="411f6-171">Solo contribuzione</span><span class="sxs-lookup"><span data-stu-id="411f6-171">Contribution only</span></span>          | <span data-ttu-id="411f6-172">Viene creata una detrazione del datore di lavoro.</span><span class="sxs-lookup"><span data-stu-id="411f6-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="411f6-173">Detrazione e contribuzione</span><span class="sxs-lookup"><span data-stu-id="411f6-173">Deduction and contribution</span></span> | <span data-ttu-id="411f6-174">Vengono create detrazioni del datore di lavoro e del dipendente.</span><span class="sxs-lookup"><span data-stu-id="411f6-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="411f6-175">Per altre informazioni su come definire e gestire un programma di benefit, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="411f6-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="411f6-176">Realizzare un programma di benefit per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="411f6-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="411f6-177">Creare un nuovo benefit</span><span class="sxs-lookup"><span data-stu-id="411f6-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="411f6-178">Definire regole e criteri di idoneità ai benefit</span><span class="sxs-lookup"><span data-stu-id="411f6-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="411f6-179">Iscrivere e rimuovere benefit da lavoratori</span><span class="sxs-lookup"><span data-stu-id="411f6-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="411f6-180">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="411f6-180">Compensation</span></span> 

<span data-ttu-id="411f6-181">La gestione delle retribuzioni consente di controllare la liquidazione dei premi e della retribuzione base.</span><span class="sxs-lookup"><span data-stu-id="411f6-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="411f6-182">La retribuzione di base fissa di un dipendente e gli aumenti per merito sono controllati mediante piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="411f6-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="411f6-183">È possibile controllare il pagamento degli incentivi, ad esempio il pagamento dei bonus, dei premi produttività, dei diritti di opzione, delle sovvenzioni, oltre che dei premi una tantum, tramite i piani di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="411f6-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="411f6-184">Dayforce utilizza le informazioni sulla compensazione per calcolare la retribuzione annuale o oraria di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="411f6-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="411f6-185">I piani di retribuzione fissa e conversioni della retribuzione sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="411f6-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="411f6-186">I dipendenti devono essere associati a un piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="411f6-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="411f6-187">Per ulteriori informazioni sui piani di retribuzione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="411f6-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="411f6-188">Creare i piani di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="411f6-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="411f6-189">Creare i piani di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="411f6-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="411f6-190">Sviluppare una struttura e piani di stipendi/retribuzioni</span><span class="sxs-lookup"><span data-stu-id="411f6-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="411f6-191">Processo retributivo</span><span class="sxs-lookup"><span data-stu-id="411f6-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="411f6-192">Definire il processo retributivo e calcolare i risultati</span><span class="sxs-lookup"><span data-stu-id="411f6-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="411f6-193">Iscrivere un dipendente a un piano di retribuzione fisso</span><span class="sxs-lookup"><span data-stu-id="411f6-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="411f6-194">Iscrivere un dipendente a un piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="411f6-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="411f6-195">Mansioni</span><span class="sxs-lookup"><span data-stu-id="411f6-195">Jobs</span></span> 

<span data-ttu-id="411f6-196">Una mansione è una raccolta delle attività e delle responsabilità proprie della persona assegnata a una mansione.</span><span class="sxs-lookup"><span data-stu-id="411f6-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="411f6-197">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="411f6-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="411f6-198">Impostazione dei componenti di una mansione</span><span class="sxs-lookup"><span data-stu-id="411f6-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="411f6-199">Definire nuovi processi</span><span class="sxs-lookup"><span data-stu-id="411f6-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="411f6-200">Posizioni</span><span class="sxs-lookup"><span data-stu-id="411f6-200">Positions</span></span>

<span data-ttu-id="411f6-201">Una posizione è una singola istanza di un processo.</span><span class="sxs-lookup"><span data-stu-id="411f6-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="411f6-202">Ad esempio, la posizione "Manager vendite (Est") è una delle posizioni associate alla mansione "Manager vendite".</span><span class="sxs-lookup"><span data-stu-id="411f6-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="411f6-203">Una posizione è presente in un reparto.</span><span class="sxs-lookup"><span data-stu-id="411f6-203">A position exists in a department.</span></span> <span data-ttu-id="411f6-204">È possibile associare un solo lavoratore a ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="411f6-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="411f6-205">Tenere a mente i seguenti dati e la configurazione quando si impostano le posizioni:</span><span class="sxs-lookup"><span data-stu-id="411f6-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="411f6-206">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-206">Position (required)</span></span>
- <span data-ttu-id="411f6-207">Descrizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-207">Description (required)</span></span>
- <span data-ttu-id="411f6-208">Mansione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-208">Job (required)</span></span>
- <span data-ttu-id="411f6-209">Reparto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-209">Department (required)</span></span>
- <span data-ttu-id="411f6-210">Tipo di posizione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-210">Position type (required)</span></span>
- <span data-ttu-id="411f6-211">Equivalente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="411f6-211">Full-time equivalent</span></span>
- <span data-ttu-id="411f6-212">Ore regolari annuali (obbligatorie)</span><span class="sxs-lookup"><span data-stu-id="411f6-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="411f6-213">Pagamento in base alla persona giuridica (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="411f6-214">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="411f6-214">Pay cycle (required)</span></span>
- <span data-ttu-id="411f6-215">Dimensione finanziaria predefinita - Centro di costo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="411f6-216">Assegnazione del lavoratore - Lavoratore, inizio assegnazione, fine assegnazione, codice motivo</span><span class="sxs-lookup"><span data-stu-id="411f6-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="411f6-217">Se nello stesso reparto più posizioni sono associate alla stessa mansione, vengono consolidate in una singola posizione in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="411f6-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="411f6-218">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="411f6-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="411f6-219">Organizzare la forza lavoro utilizzando i reparti, le mansioni e le posizioni</span><span class="sxs-lookup"><span data-stu-id="411f6-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="411f6-220">Impostare le posizioni</span><span class="sxs-lookup"><span data-stu-id="411f6-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="411f6-221">Reparti</span><span class="sxs-lookup"><span data-stu-id="411f6-221">Departments</span></span>

<span data-ttu-id="411f6-222">Un reparto è un'unità operativa che rappresenta una categoria o un'area operativa di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="411f6-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="411f6-223">Un reparto è responsabile di una specifica area dell'organizzazione, ad esempio la vendita, la contabilità o le risorse umane.</span><span class="sxs-lookup"><span data-stu-id="411f6-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="411f6-224">È possibile utilizzare i reparti per creare report sulle aree operative.</span><span class="sxs-lookup"><span data-stu-id="411f6-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="411f6-225">I reparti possono essere responsabili di profitti e perdite.</span><span class="sxs-lookup"><span data-stu-id="411f6-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="411f6-226">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="411f6-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="411f6-227">Creare un reparto e associarlo alla gerarchia reparti</span><span class="sxs-lookup"><span data-stu-id="411f6-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="411f6-228">Definire nuovi reparti</span><span class="sxs-lookup"><span data-stu-id="411f6-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="411f6-229">Cicli e periodi retributivi</span><span class="sxs-lookup"><span data-stu-id="411f6-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="411f6-230">Un ciclo retributivo determina la frequenza di elaborazione delle retribuzioni e i giorni specifici in cui i lavoratori vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="411f6-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="411f6-231">Un ciclo retributivo può essere ad esempio mensile e i dipendenti possono essere pagati l'ultimo giorno del mese.</span><span class="sxs-lookup"><span data-stu-id="411f6-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="411f6-232">Un ciclo retributivo può in alternativa essere settimanale e i dipendenti possono essere pagati il giovedì successivo alla fine del periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="411f6-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="411f6-233">I cicli retributivi vengono assegnati alle posizioni per controllare quando i lavoratori in tali posizioni vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="411f6-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="411f6-234">Dopo aver creato i cicli retributivi, è possibile generare periodi retributivi per ogni ciclo.</span><span class="sxs-lookup"><span data-stu-id="411f6-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="411f6-235">Ogni periodo retributivo include una data di pagamento predefinita in base alle informazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="411f6-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="411f6-236">Tuttavia, è possibile modificare la data di pagamento predefinita in un periodo retributivo per consentire eccezioni, ad esempio quando la data di pagamento cade in un giorno festivo.</span><span class="sxs-lookup"><span data-stu-id="411f6-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="411f6-237">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="411f6-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="411f6-238">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="411f6-238">Pay cycle (required)</span></span>
- <span data-ttu-id="411f6-239">Frequenza ciclo retributivo (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="411f6-240">Data di inizio del periodo (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="411f6-241">Data di pagamento predefinita (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="411f6-242">Queste informazioni sono integrate con Dayforce come gruppi retributivi e sono separata in base al paese o alla regione per ogni ciclo retributivo.</span><span class="sxs-lookup"><span data-stu-id="411f6-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="411f6-243">Prima dell'integrazione è necessario generare almeno un periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="411f6-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="411f6-244">Dayforce genera calendari di gruppi retributivi e date di pagamento, in base alla data di inizio del primo periodo retributivo e alla data di pagamento predefinita che viene impostata in Talent.</span><span class="sxs-lookup"><span data-stu-id="411f6-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="411f6-245">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="411f6-245">Earning codes</span></span>

<span data-ttu-id="411f6-246">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="411f6-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="411f6-247">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="411f6-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="411f6-248">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="411f6-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="411f6-249">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-249">Earning Code (required)</span></span>
- <span data-ttu-id="411f6-250">descrizione</span><span class="sxs-lookup"><span data-stu-id="411f6-250">Description</span></span>
- <span data-ttu-id="411f6-251">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="411f6-251">Unit of measure</span></span>
- <span data-ttu-id="411f6-252">Produttivo</span><span class="sxs-lookup"><span data-stu-id="411f6-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="411f6-253">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-253">Worker data</span></span>

<span data-ttu-id="411f6-254">I record per i diversi tipi di lavoratori a disposizione sono importanti per i sistemi di gestione delle risorse umane e delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="411f6-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="411f6-255">Le informazioni immesse possono essere utilizzate per tenere traccia di informazioni personali e sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="411f6-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="411f6-256">È possibile gestire le seguenti informazioni per i lavoratori:</span><span class="sxs-lookup"><span data-stu-id="411f6-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="411f6-257">**Base** - Gestire le informazioni di base su un lavoratore, ad esempio le informazioni sui contatti, le informazioni demografiche, le informazioni di identificazione, le informazioni sulla famiglia, lo stato di servizio militare, le informazioni sull'espatrio, e i contatti personali e di emergenza.</span><span class="sxs-lookup"><span data-stu-id="411f6-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="411f6-258">**Impiego** - Consente di gestire le informazioni sull'impiego di un lavoratore, ad esempio rapporto con l'organizzazione o la società, assegnazione della posizione, date di inizio e fine, idoneità al lavoro, condizioni di impiego, pensionamento, ferie e trasferimento.</span><span class="sxs-lookup"><span data-stu-id="411f6-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="411f6-259">**Congedo e assenza** - Consente di gestire le informazioni sulle assenze di un lavoratore, ad esempio calendari di lavoro, transazioni assenze e impostazione assenze.</span><span class="sxs-lookup"><span data-stu-id="411f6-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="411f6-260">**Retribuzioni** - Consente di gestire le informazioni sui piani di retribuzione di un lavoratore, ad esempio registrazione del piano, premi, prestazioni, provvigione, dati fiscali, pensionamento e detrazioni sullo stipendio.</span><span class="sxs-lookup"><span data-stu-id="411f6-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="411f6-261">Quando si immettono le informazioni su un lavoratore, tenere presenti i seguenti dati e le configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="411f6-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="411f6-262">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="411f6-262">General information</span></span>

- <span data-ttu-id="411f6-263">Numero dipendente (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-263">Personnel number (required)</span></span>
- <span data-ttu-id="411f6-264">Nome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-264">First name (required)</span></span>
- <span data-ttu-id="411f6-265">Cognome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-265">Last name (required)</span></span>
- <span data-ttu-id="411f6-266">Secondo nome</span><span class="sxs-lookup"><span data-stu-id="411f6-266">Middle name</span></span>
- <span data-ttu-id="411f6-267">Data di anzianità</span><span class="sxs-lookup"><span data-stu-id="411f6-267">Seniority date</span></span>
- <span data-ttu-id="411f6-268">Nome noto</span><span class="sxs-lookup"><span data-stu-id="411f6-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="411f6-269">Informazioni personali</span><span class="sxs-lookup"><span data-stu-id="411f6-269">Personal information</span></span>

- <span data-ttu-id="411f6-270">Stato civile (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-270">Marital status (required)</span></span>
- <span data-ttu-id="411f6-271">Data di nascita (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-271">Birth date (required)</span></span>
- <span data-ttu-id="411f6-272">Sesso (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-272">Gender (required)</span></span>
- <span data-ttu-id="411f6-273">Persona disabile</span><span class="sxs-lookup"><span data-stu-id="411f6-273">Person with disabilities</span></span>
- <span data-ttu-id="411f6-274">Nazionalità paese regione (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="411f6-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="411f6-275">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="411f6-275">Address information</span></span>

- <span data-ttu-id="411f6-276">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-276">Primary (required)</span></span>
- <span data-ttu-id="411f6-277">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-277">Country/region (required)</span></span>
- <span data-ttu-id="411f6-278">Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-278">Postal code (required)</span></span>
- <span data-ttu-id="411f6-279">Numero civico (obbligatorio) (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="411f6-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="411f6-280">Informazioni aggiuntive sull'indirizzo (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="411f6-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="411f6-281">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-281">City (required)</span></span>
- <span data-ttu-id="411f6-282">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-282">State (required)</span></span>
- <span data-ttu-id="411f6-283">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="411f6-284">Informazioni contatto</span><span class="sxs-lookup"><span data-stu-id="411f6-284">Contact information</span></span> 

- <span data-ttu-id="411f6-285">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-285">Primary (required)</span></span>
- <span data-ttu-id="411f6-286">Numero contatto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-286">Contact number (required)</span></span>
- <span data-ttu-id="411f6-287">Interno</span><span class="sxs-lookup"><span data-stu-id="411f6-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="411f6-288">Informazioni sulle retribuzioni e codici di reddito</span><span class="sxs-lookup"><span data-stu-id="411f6-288">Payroll information and earning codes</span></span>

<span data-ttu-id="411f6-289">Ai dipendenti possono essere assegnati redditi specifici a una determinata frequenza di pagamento e un metodo di pagamento preferito.</span><span class="sxs-lookup"><span data-stu-id="411f6-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="411f6-290">I campi seguenti vengono utilizzati in Dayforce per garantire che le preferenze e le impostazioni vengano utilizzate.</span><span class="sxs-lookup"><span data-stu-id="411f6-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="411f6-291">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="411f6-291">Earning codes</span></span>

- <span data-ttu-id="411f6-292">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-292">Position (required)</span></span>
- <span data-ttu-id="411f6-293">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-293">Earning Code (required)</span></span>
- <span data-ttu-id="411f6-294">Frequenza (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-294">Frequency (required)</span></span>
- <span data-ttu-id="411f6-295">Importo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="411f6-296">Informazioni retribuzioni</span><span class="sxs-lookup"><span data-stu-id="411f6-296">Payroll information</span></span>

- <span data-ttu-id="411f6-297">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="411f6-297">Payment Method</span></span>
- <span data-ttu-id="411f6-298">Area economica (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-298">Economic Region (required)</span></span>
- <span data-ttu-id="411f6-299">ID benefit dipendente</span><span class="sxs-lookup"><span data-stu-id="411f6-299">Employee Benefits ID</span></span>
- <span data-ttu-id="411f6-300">Numero documento identità (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-300">National ID Number (required)</span></span>
- <span data-ttu-id="411f6-301">Numero servizio militare</span><span class="sxs-lookup"><span data-stu-id="411f6-301">Military Service Number</span></span>
- <span data-ttu-id="411f6-302">ID turno (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-302">Shift ID (required)</span></span>
- <span data-ttu-id="411f6-303">Numero imposta (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-303">Tax Number (required)</span></span>
- <span data-ttu-id="411f6-304">ID sindacato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-304">Union ID (required)</span></span>
- <span data-ttu-id="411f6-305">ID giorno lavorativo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-305">Work Day ID (required)</span></span>
- <span data-ttu-id="411f6-306">Numero permesso di lavoro</span><span class="sxs-lookup"><span data-stu-id="411f6-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="411f6-307">Per il metodo di pagamento, il Messico supporta **Contante**, **Assegno** (l'assegno fisico della società) e **Pagamento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="411f6-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="411f6-308">Se non viene specificato alcun metodo di pagamento, **Assegno** è 'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="411f6-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="411f6-309">Dettagli impiego</span><span class="sxs-lookup"><span data-stu-id="411f6-309">Employment details</span></span>

<span data-ttu-id="411f6-310">Lo storico dei dettagli impiego viene utilizzato come informazioni chiave da cui derivare gli stati di assunzione, termine e riassunzione di un dipendente Dayforce.</span><span class="sxs-lookup"><span data-stu-id="411f6-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="411f6-311">Dayforce supporta solo un record di impiego attivo alla volta.</span><span class="sxs-lookup"><span data-stu-id="411f6-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="411f6-312">Data di inizio impiego (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-312">Employment start date (required)</span></span>
- <span data-ttu-id="411f6-313">Data di fine impiego</span><span class="sxs-lookup"><span data-stu-id="411f6-313">Employment end date</span></span>
- <span data-ttu-id="411f6-314">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="411f6-314">Start date</span></span>
- <span data-ttu-id="411f6-315">Data di inizio rettificata</span><span class="sxs-lookup"><span data-stu-id="411f6-315">Adjusted start date</span></span>
- <span data-ttu-id="411f6-316">Data fine rapporto (obbligatoria con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="411f6-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="411f6-317">Motivo fine rapporto (obbligatorio con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="411f6-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="411f6-318">Le date chiave del dipendente sono derivate utilizzando le informazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="411f6-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="411f6-319">Talent</span><span class="sxs-lookup"><span data-stu-id="411f6-319">Talent</span></span>                | <span data-ttu-id="411f6-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="411f6-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="411f6-321">Data di assunzione più recente</span><span class="sxs-lookup"><span data-stu-id="411f6-321">Most recent hire date</span></span> | <span data-ttu-id="411f6-322">Inizio dell'impiego del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="411f6-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="411f6-323">Data fine rapporto</span><span class="sxs-lookup"><span data-stu-id="411f6-323">Termination date</span></span>      | <span data-ttu-id="411f6-324">Data di fine rapporto del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="411f6-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="411f6-325">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="411f6-325">Start date</span></span>            | <span data-ttu-id="411f6-326">Data di inizio rettificata, data di inizio o inizio dell'impiego del record corrente dello storico di impiego non attivo</span><span class="sxs-lookup"><span data-stu-id="411f6-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="411f6-327">Data di assunzione originale</span><span class="sxs-lookup"><span data-stu-id="411f6-327">Original hire date</span></span>    | <span data-ttu-id="411f6-328">Inizio dell'impiego del record dello storico di impiego meno recente</span><span class="sxs-lookup"><span data-stu-id="411f6-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="411f6-329">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="411f6-329">Compensation</span></span>

<span data-ttu-id="411f6-330">Un piano di retribuzione fissa deve essere associato alla posizione primaria di ogni dipendente durante un periodo di impiego.</span><span class="sxs-lookup"><span data-stu-id="411f6-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="411f6-331">Questo periodo inizia alla data in cui il dipendente è stato assunto (o la data di inizio dell'impiego) e continua fino alla fine del rapporto.</span><span class="sxs-lookup"><span data-stu-id="411f6-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="411f6-332">Data di validità (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-332">Effective Date (required)</span></span>
- <span data-ttu-id="411f6-333">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="411f6-333">Expiration date</span></span>
- <span data-ttu-id="411f6-334">Retribuzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-334">Pay Rate (required)</span></span>
- <span data-ttu-id="411f6-335">Conversioni retribuzione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="411f6-336">Equivalente annuale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="411f6-337">Equivalente orario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="411f6-338">Se un dipendente a ore ha più posizioni, la retribuzione fissa della posizione primaria viene importata in Dayforce come il tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="411f6-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="411f6-339">Per le posizioni non principali, la tariffa oraria viene salvata nella posizione corrispondente in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="411f6-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="411f6-340">Se un dipendente stipendiato ha più posizioni, la tariffa oraria cumulativa e lo stipendio annuale di tutte le posizioni attive vengono calcolati e utilizzati come tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="411f6-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="411f6-341">Numeri di identificazione</span><span class="sxs-lookup"><span data-stu-id="411f6-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="411f6-342">Numero di Previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="411f6-342">Social Security identifier</span></span> 

<span data-ttu-id="411f6-343">Ogni dipendente deve avere un identificatore primario.</span><span class="sxs-lookup"><span data-stu-id="411f6-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="411f6-344">Questo identificatore deve essere di tipo identificatore **SSN**.</span><span class="sxs-lookup"><span data-stu-id="411f6-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="411f6-345">In Dayforce, viene ricavato automaticamente come identificatore di previdenza sociale del dipendente per l'assunzione.</span><span class="sxs-lookup"><span data-stu-id="411f6-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="411f6-346">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-346">Primary (required)</span></span>
- <span data-ttu-id="411f6-347">Tipo di identificazione = "SSN"</span><span class="sxs-lookup"><span data-stu-id="411f6-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="411f6-348">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="411f6-348">Issued Date</span></span>
- <span data-ttu-id="411f6-349">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="411f6-349">Expiration Date</span></span>

<span data-ttu-id="411f6-350">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **SSN**.</span><span class="sxs-lookup"><span data-stu-id="411f6-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="411f6-351">Tuttavia, solo il record che è contrassegnato come **Primario** viene integrato in Dayforce, a prescindere che il numero sia attivo o scaduto.</span><span class="sxs-lookup"><span data-stu-id="411f6-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="411f6-352">Esborsi e conti bancari</span><span class="sxs-lookup"><span data-stu-id="411f6-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="411f6-353">È necessario immettere informazioni sul conto bancario valide per un dipendente che scelga di essere pagato tramite trasferimenti di conto bancario.</span><span class="sxs-lookup"><span data-stu-id="411f6-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="411f6-354">Talent</span><span class="sxs-lookup"><span data-stu-id="411f6-354">Talent</span></span>                         | <span data-ttu-id="411f6-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="411f6-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="411f6-356">Numero conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="411f6-357">Codice SWIFT (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-357">SWIFT code (required)</span></span>          | <span data-ttu-id="411f6-358">Campo **ID banca** utilizzato durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="411f6-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="411f6-359">Codice filiale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="411f6-360">Tipo di conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-360">Bank account type (required)</span></span>   | <span data-ttu-id="411f6-361">Campo **Tipo di conto** utilizzando durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="411f6-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="411f6-362">I valori supportati includono **Controllo** e **Retribuzioni**.</span><span class="sxs-lookup"><span data-stu-id="411f6-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="411f6-363">I dipendenti che scelgono di essere pagati tramite trasferimenti di conto bancario devono fornire un collegamento a un conto rimanente che è sotto la persona giuridica che ha l'indirizzo primario in Messico ed è associato a un conto bancario valido presso una banca messicana.</span><span class="sxs-lookup"><span data-stu-id="411f6-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="411f6-364">Tutti gli altri account non di rimanenze verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="411f6-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="411f6-365">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="411f6-365">Address information</span></span>

<span data-ttu-id="411f6-366">Ogni dipendente deve avere un'ubicazione primaria.</span><span class="sxs-lookup"><span data-stu-id="411f6-366">Every employee must have one primary location.</span></span> <span data-ttu-id="411f6-367">In Dayforce, questa ubicazione viene utilizzata per determinare la principale residenza del dipendente a scopo fiscale.</span><span class="sxs-lookup"><span data-stu-id="411f6-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="411f6-368">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-368">Primary (required)</span></span>
- <span data-ttu-id="411f6-369">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-369">Country/region (required)</span></span>
- <span data-ttu-id="411f6-370">CAP/Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="411f6-371">Via (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-371">Street (required)</span></span>
- <span data-ttu-id="411f6-372">Numero civico (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-372">Street Number (required)</span></span>
- <span data-ttu-id="411f6-373">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="411f6-373">Building Complement</span></span>
- <span data-ttu-id="411f6-374">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-374">City (required)</span></span>
- <span data-ttu-id="411f6-375">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-375">State (required)</span></span>
- <span data-ttu-id="411f6-376">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="411f6-377">Configurare i dati per generare le retribuzioni negli Stati Uniti e in Canada</span><span class="sxs-lookup"><span data-stu-id="411f6-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="411f6-378">Se si desidera generare la retribuzione per i dipendenti negli Stati Uniti e in Canada, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="411f6-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="411f6-379">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="411f6-379">Departments are required on positions.</span></span>
- <span data-ttu-id="411f6-380">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="411f6-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="411f6-381">Tipi di posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="411f6-381">Job types</span></span>

<span data-ttu-id="411f6-382">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="411f6-382">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="411f6-383">I tipi di mansione sono necessari per elaborare le retribuzioni negli Stati Uniti e in Canada.</span><span class="sxs-lookup"><span data-stu-id="411f6-383">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="411f6-384">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="411f6-384">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="411f6-385">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="411f6-385">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="411f6-386">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="411f6-386">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="411f6-387">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="411f6-387">Job type</span></span>   | <span data-ttu-id="411f6-388">descrizione</span><span class="sxs-lookup"><span data-stu-id="411f6-388">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="411f6-389">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="411f6-389">Hourly</span></span>     | <span data-ttu-id="411f6-390">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="411f6-390">Hourly</span></span>      |
| <span data-ttu-id="411f6-391">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="411f6-391">Salaried</span></span>   | <span data-ttu-id="411f6-392">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="411f6-392">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="411f6-393">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="411f6-393">Position types</span></span> 

<span data-ttu-id="411f6-394">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="411f6-394">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="411f6-395">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="411f6-395">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="411f6-396">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="411f6-396">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="411f6-397">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="411f6-397">Position type</span></span>   | <span data-ttu-id="411f6-398">descrizione</span><span class="sxs-lookup"><span data-stu-id="411f6-398">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="411f6-399">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="411f6-399">Full-time</span></span>       | <span data-ttu-id="411f6-400">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="411f6-400">Full time employee</span></span> |
| <span data-ttu-id="411f6-401">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="411f6-401">Part-time</span></span>       | <span data-ttu-id="411f6-402">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="411f6-402">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="411f6-403">Codici causale</span><span class="sxs-lookup"><span data-stu-id="411f6-403">Reason codes</span></span>

<span data-ttu-id="411f6-404">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="411f6-404">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="411f6-405">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="411f6-405">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="411f6-406">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="411f6-406">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="411f6-407">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="411f6-407">Reason code</span></span>    | <span data-ttu-id="411f6-408">descrizione</span><span class="sxs-lookup"><span data-stu-id="411f6-408">Description</span></span>      | <span data-ttu-id="411f6-409">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="411f6-409">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="411f6-410">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="411f6-410">RESIGNATION</span></span>    | <span data-ttu-id="411f6-411">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="411f6-411">Resignation</span></span>      | <span data-ttu-id="411f6-412">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-412">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-413">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="411f6-413">TERMINATION</span></span>    | <span data-ttu-id="411f6-414">Fine</span><span class="sxs-lookup"><span data-stu-id="411f6-414">Termination</span></span>      | <span data-ttu-id="411f6-415">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-415">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-416">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="411f6-416">RETIREMENT</span></span>     | <span data-ttu-id="411f6-417">Pensione</span><span class="sxs-lookup"><span data-stu-id="411f6-417">Retirement</span></span>       | <span data-ttu-id="411f6-418">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-418">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-419">OTHER</span><span class="sxs-lookup"><span data-stu-id="411f6-419">OTHER</span></span>          | <span data-ttu-id="411f6-420">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="411f6-420">Other Reasons</span></span>    | <span data-ttu-id="411f6-421">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-421">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-422">DEATH</span><span class="sxs-lookup"><span data-stu-id="411f6-422">DEATH</span></span>          | <span data-ttu-id="411f6-423">Decesso</span><span class="sxs-lookup"><span data-stu-id="411f6-423">Death</span></span>            | <span data-ttu-id="411f6-424">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-424">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-425">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="411f6-425">LEAVEOFABSENCE</span></span> | <span data-ttu-id="411f6-426">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="411f6-426">Leave of Absence</span></span> | <span data-ttu-id="411f6-427">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-427">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-428">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="411f6-428">CONTRACTEND</span></span>    | <span data-ttu-id="411f6-429">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="411f6-429">End of Contract</span></span>  | <span data-ttu-id="411f6-430">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-430">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-431">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="411f6-431">SALARYCHANGE</span></span>   | <span data-ttu-id="411f6-432">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="411f6-432">Change of Salary</span></span> | <span data-ttu-id="411f6-433">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="411f6-433">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="411f6-434">Stato civile</span><span class="sxs-lookup"><span data-stu-id="411f6-434">Marital status</span></span>

<span data-ttu-id="411f6-435">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="411f6-435">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="411f6-436">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="411f6-436">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="411f6-437">Talent</span><span class="sxs-lookup"><span data-stu-id="411f6-437">Talent</span></span>                 | <span data-ttu-id="411f6-438">Dayforce</span><span class="sxs-lookup"><span data-stu-id="411f6-438">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="411f6-439">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="411f6-439">Married</span></span>                | <span data-ttu-id="411f6-440">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="411f6-440">Married</span></span>              |
| <span data-ttu-id="411f6-441">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="411f6-441">Single</span></span>                 | <span data-ttu-id="411f6-442">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="411f6-442">Single</span></span>               |
| <span data-ttu-id="411f6-443">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="411f6-443">Widowed</span></span>                | <span data-ttu-id="411f6-444">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="411f6-444">Widowed</span></span>              |
| <span data-ttu-id="411f6-445">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="411f6-445">Divorced</span></span>               | <span data-ttu-id="411f6-446">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="411f6-446">Divorced</span></span>             |
| <span data-ttu-id="411f6-447">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="411f6-447">Registered Partnership</span></span> | <span data-ttu-id="411f6-448">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="411f6-448">Domestic Partnership</span></span> |
| <span data-ttu-id="411f6-449">Nessuna</span><span class="sxs-lookup"><span data-stu-id="411f6-449">None</span></span>                   | <span data-ttu-id="411f6-450">Nessuna</span><span class="sxs-lookup"><span data-stu-id="411f6-450">None</span></span>                 |
| <span data-ttu-id="411f6-451">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="411f6-451">Cohabiting</span></span>             | <span data-ttu-id="411f6-452">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="411f6-452">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="411f6-453">Genere</span><span class="sxs-lookup"><span data-stu-id="411f6-453">Gender</span></span>

<span data-ttu-id="411f6-454">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="411f6-454">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="411f6-455">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="411f6-455">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="411f6-456">Talent</span><span class="sxs-lookup"><span data-stu-id="411f6-456">Talent</span></span>       | <span data-ttu-id="411f6-457">Dayforce</span><span class="sxs-lookup"><span data-stu-id="411f6-457">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="411f6-458">Maschio</span><span class="sxs-lookup"><span data-stu-id="411f6-458">Male</span></span>         | <span data-ttu-id="411f6-459">Maschio</span><span class="sxs-lookup"><span data-stu-id="411f6-459">Male</span></span>            |
| <span data-ttu-id="411f6-460">Femmina</span><span class="sxs-lookup"><span data-stu-id="411f6-460">Female</span></span>       | <span data-ttu-id="411f6-461">Femmina</span><span class="sxs-lookup"><span data-stu-id="411f6-461">Female</span></span>          |
| <span data-ttu-id="411f6-462">Non specifico</span><span class="sxs-lookup"><span data-stu-id="411f6-462">Non-specific</span></span> | <span data-ttu-id="411f6-463">*Non supportato*</span><span class="sxs-lookup"><span data-stu-id="411f6-463">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="411f6-464">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="411f6-464">Earning codes</span></span>

<span data-ttu-id="411f6-465">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="411f6-465">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="411f6-466">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="411f6-466">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="411f6-467">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="411f6-467">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="411f6-468">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="411f6-468">Supported frequencies</span></span>

- <span data-ttu-id="411f6-469">Tutti</span><span class="sxs-lookup"><span data-stu-id="411f6-469">All</span></span>
- <span data-ttu-id="411f6-470">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="411f6-470">EVERYPAY</span></span>
- <span data-ttu-id="411f6-471">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="411f6-471">EACHPAYPERIOD</span></span>
- <span data-ttu-id="411f6-472">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="411f6-472">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="411f6-473">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="411f6-473">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="411f6-474">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-474">1OFMTH</span></span>
- <span data-ttu-id="411f6-475">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-475">LASTOFMTH</span></span>
- <span data-ttu-id="411f6-476">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-476">2OFMTH</span></span>
- <span data-ttu-id="411f6-477">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-477">3OFMTH</span></span>
- <span data-ttu-id="411f6-478">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-478">4OFMTH</span></span>
- <span data-ttu-id="411f6-479">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-479">5OFMTH</span></span>
- <span data-ttu-id="411f6-480">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-480">1N2OFMTH</span></span>
- <span data-ttu-id="411f6-481">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-481">3N4OFMTH</span></span>
- <span data-ttu-id="411f6-482">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-482">1N3OFMTH</span></span>
- <span data-ttu-id="411f6-483">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-483">1N4OFMTH</span></span>
- <span data-ttu-id="411f6-484">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-484">2N3OFMTH</span></span>
- <span data-ttu-id="411f6-485">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-485">2N4OFMTH</span></span>
- <span data-ttu-id="411f6-486">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-486">1N2N3OFMTH</span></span>
- <span data-ttu-id="411f6-487">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-487">1N2N4OFMTH</span></span>
- <span data-ttu-id="411f6-488">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-488">1N3N4OFMTH</span></span>
- <span data-ttu-id="411f6-489">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-489">2N3N4OFMTH</span></span>
- <span data-ttu-id="411f6-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-490">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="411f6-491">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="411f6-491">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="411f6-492">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="411f6-492">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="411f6-493">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="411f6-493">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="411f6-494">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="411f6-494">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="411f6-495">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="411f6-495">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="411f6-496">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="411f6-496">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="411f6-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="411f6-497">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="411f6-498">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="411f6-498">Addresses</span></span>

<span data-ttu-id="411f6-499">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="411f6-499">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="411f6-500">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="411f6-500">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="411f6-501">Talent</span><span class="sxs-lookup"><span data-stu-id="411f6-501">Talent</span></span>          | <span data-ttu-id="411f6-502">Dayforce</span><span class="sxs-lookup"><span data-stu-id="411f6-502">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="411f6-503">Paese</span><span class="sxs-lookup"><span data-stu-id="411f6-503">Country/Region</span></span>  | <span data-ttu-id="411f6-504">Codice paese</span><span class="sxs-lookup"><span data-stu-id="411f6-504">Country Code</span></span>          |
| <span data-ttu-id="411f6-505">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="411f6-505">Zip/Postal Code</span></span> | <span data-ttu-id="411f6-506">CAP</span><span class="sxs-lookup"><span data-stu-id="411f6-506">Postal Code</span></span>           |
| <span data-ttu-id="411f6-507">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="411f6-507">State</span></span>           | <span data-ttu-id="411f6-508">Codice stato</span><span class="sxs-lookup"><span data-stu-id="411f6-508">State Code</span></span>            |
| <span data-ttu-id="411f6-509">Città</span><span class="sxs-lookup"><span data-stu-id="411f6-509">City</span></span>            | <span data-ttu-id="411f6-510">Città</span><span class="sxs-lookup"><span data-stu-id="411f6-510">City</span></span>                  |
| <span data-ttu-id="411f6-511">Regione</span><span class="sxs-lookup"><span data-stu-id="411f6-511">County</span></span>          | <span data-ttu-id="411f6-512">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="411f6-512">County (Municipality)</span></span> |
| <span data-ttu-id="411f6-513">Via</span><span class="sxs-lookup"><span data-stu-id="411f6-513">Street</span></span>          | <span data-ttu-id="411f6-514">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="411f6-514">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="411f6-515">Regioni fiscali</span><span class="sxs-lookup"><span data-stu-id="411f6-515">Tax regions</span></span>

<span data-ttu-id="411f6-516">Le regioni fiscali vengono utilizzate per determinare l'imposta appropriata che deve essere applicata durante la generazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="411f6-516">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="411f6-517">Le regioni fiscali vengono mappate in Dayforce come indirizzi di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="411f6-517">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="411f6-518">La regione fiscale predefinita deve essere associata alla posizione attiva del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="411f6-518">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="411f6-519">Regione fiscale (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-519">Tax region (required)</span></span>
- <span data-ttu-id="411f6-520">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-520">Country/Region (required)</span></span>
- <span data-ttu-id="411f6-521">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="411f6-521">State (required)</span></span>
- <span data-ttu-id="411f6-522">Regione</span><span class="sxs-lookup"><span data-stu-id="411f6-522">County</span></span> 
- <span data-ttu-id="411f6-523">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="411f6-523">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="411f6-524">Configurare i dati per generare le retribuzioni in Messico</span><span class="sxs-lookup"><span data-stu-id="411f6-524">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="411f6-525">Se si desidera generare la retribuzione per i dipendenti in Messico, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="411f6-525">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="411f6-526">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="411f6-526">Departments are required on positions.</span></span>
- <span data-ttu-id="411f6-527">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="411f6-527">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="411f6-528">Tipi di posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="411f6-528">Job types</span></span>

<span data-ttu-id="411f6-529">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="411f6-529">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="411f6-530">Tipi di mansione necessari per elaborare le retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="411f6-530">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="411f6-531">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="411f6-531">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="411f6-532">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="411f6-532">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="411f6-533">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="411f6-533">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="411f6-534">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="411f6-534">Job type</span></span>   | <span data-ttu-id="411f6-535">descrizione</span><span class="sxs-lookup"><span data-stu-id="411f6-535">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="411f6-536">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="411f6-536">Hourly</span></span>     | <span data-ttu-id="411f6-537">Su base oraria MX</span><span class="sxs-lookup"><span data-stu-id="411f6-537">MX Hourly</span></span>   |
| <span data-ttu-id="411f6-538">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="411f6-538">Salaried</span></span>   | <span data-ttu-id="411f6-539">Stipendiato MX</span><span class="sxs-lookup"><span data-stu-id="411f6-539">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="411f6-540">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="411f6-540">Position types</span></span> 

<span data-ttu-id="411f6-541">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="411f6-541">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="411f6-542">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="411f6-542">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="411f6-543">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="411f6-543">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="411f6-544">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="411f6-544">Position type</span></span>   | <span data-ttu-id="411f6-545">descrizione</span><span class="sxs-lookup"><span data-stu-id="411f6-545">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="411f6-546">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="411f6-546">Full-time</span></span>       | <span data-ttu-id="411f6-547">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="411f6-547">Full time employee</span></span> |
| <span data-ttu-id="411f6-548">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="411f6-548">Part-time</span></span>       | <span data-ttu-id="411f6-549">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="411f6-549">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="411f6-550">Codici causale</span><span class="sxs-lookup"><span data-stu-id="411f6-550">Reason codes</span></span>

<span data-ttu-id="411f6-551">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="411f6-551">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="411f6-552">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="411f6-552">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="411f6-553">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="411f6-553">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="411f6-554">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="411f6-554">Reason code</span></span>            | <span data-ttu-id="411f6-555">descrizione</span><span class="sxs-lookup"><span data-stu-id="411f6-555">Description</span></span>                    | <span data-ttu-id="411f6-556">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="411f6-556">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="411f6-557">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="411f6-557">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="411f6-558">Partenza prima della prima retribuzione</span><span class="sxs-lookup"><span data-stu-id="411f6-558">Departure before first payroll</span></span> | <span data-ttu-id="411f6-559">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-559">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-560">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="411f6-560">RESIGNATION</span></span>            | <span data-ttu-id="411f6-561">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="411f6-561">Resignation</span></span>                    | <span data-ttu-id="411f6-562">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-562">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-563">PENSION</span><span class="sxs-lookup"><span data-stu-id="411f6-563">PENSION</span></span>                | <span data-ttu-id="411f6-564">Pensionamento</span><span class="sxs-lookup"><span data-stu-id="411f6-564">Pension</span></span>                        | <span data-ttu-id="411f6-565">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-565">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-566">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="411f6-566">TERMINATION</span></span>            | <span data-ttu-id="411f6-567">Fine</span><span class="sxs-lookup"><span data-stu-id="411f6-567">Termination</span></span>                    | <span data-ttu-id="411f6-568">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-568">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-569">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="411f6-569">RETIREMENT</span></span>             | <span data-ttu-id="411f6-570">Pensione</span><span class="sxs-lookup"><span data-stu-id="411f6-570">Retirement</span></span>                     | <span data-ttu-id="411f6-571">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-571">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-572">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="411f6-572">ABSENTEE</span></span>               | <span data-ttu-id="411f6-573">Assente</span><span class="sxs-lookup"><span data-stu-id="411f6-573">Absentee</span></span>                       | <span data-ttu-id="411f6-574">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-574">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-575">OTHER</span><span class="sxs-lookup"><span data-stu-id="411f6-575">OTHER</span></span>                  | <span data-ttu-id="411f6-576">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="411f6-576">Other Reasons</span></span>                  | <span data-ttu-id="411f6-577">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-577">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-578">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="411f6-578">CLOSURE</span></span>                | <span data-ttu-id="411f6-579">Chiusura attività</span><span class="sxs-lookup"><span data-stu-id="411f6-579">Business Closure</span></span>               | <span data-ttu-id="411f6-580">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-580">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-581">DEATH</span><span class="sxs-lookup"><span data-stu-id="411f6-581">DEATH</span></span>                  | <span data-ttu-id="411f6-582">Decesso</span><span class="sxs-lookup"><span data-stu-id="411f6-582">Death</span></span>                          | <span data-ttu-id="411f6-583">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-583">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-584">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="411f6-584">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="411f6-585">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="411f6-585">Leave of Absence</span></span>               | <span data-ttu-id="411f6-586">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-586">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-587">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="411f6-587">CONTRACTEND</span></span>            | <span data-ttu-id="411f6-588">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="411f6-588">End of Contract</span></span>                | <span data-ttu-id="411f6-589">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="411f6-589">Terminate worker</span></span>     |
| <span data-ttu-id="411f6-590">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="411f6-590">SALARYCHANGE</span></span>           | <span data-ttu-id="411f6-591">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="411f6-591">Change of Salary</span></span>               | <span data-ttu-id="411f6-592">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="411f6-592">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="411f6-593">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="411f6-593">Terms of employment</span></span>

<span data-ttu-id="411f6-594">Le condizioni di impiego vengono utilizzate per creare categorie di termini di impiego.</span><span class="sxs-lookup"><span data-stu-id="411f6-594">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="411f6-595">I termini vengono mappati in Dayforce come valori degli indicatori di impiego.</span><span class="sxs-lookup"><span data-stu-id="411f6-595">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="411f6-596">I seguenti termini di impiego e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="411f6-596">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="411f6-597">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="411f6-597">Terms of employment</span></span>   | <span data-ttu-id="411f6-598">descrizione</span><span class="sxs-lookup"><span data-stu-id="411f6-598">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="411f6-599">Regolare</span><span class="sxs-lookup"><span data-stu-id="411f6-599">Regular</span></span>               | <span data-ttu-id="411f6-600">Regolare</span><span class="sxs-lookup"><span data-stu-id="411f6-600">Regular</span></span>     |
| <span data-ttu-id="411f6-601">Diretto</span><span class="sxs-lookup"><span data-stu-id="411f6-601">Direct</span></span>                | <span data-ttu-id="411f6-602">Diretto</span><span class="sxs-lookup"><span data-stu-id="411f6-602">Direct</span></span>      |
| <span data-ttu-id="411f6-603">Internato</span><span class="sxs-lookup"><span data-stu-id="411f6-603">Internship</span></span>            | <span data-ttu-id="411f6-604">Internato</span><span class="sxs-lookup"><span data-stu-id="411f6-604">Internship</span></span>  |
| <span data-ttu-id="411f6-605">Permanente</span><span class="sxs-lookup"><span data-stu-id="411f6-605">Permanent</span></span>             | <span data-ttu-id="411f6-606">Permanente</span><span class="sxs-lookup"><span data-stu-id="411f6-606">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="411f6-607">Stato civile</span><span class="sxs-lookup"><span data-stu-id="411f6-607">Marital status</span></span>

<span data-ttu-id="411f6-608">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="411f6-608">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="411f6-609">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="411f6-609">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="411f6-610">Talent</span><span class="sxs-lookup"><span data-stu-id="411f6-610">Talent</span></span>                 | <span data-ttu-id="411f6-611">Dayforce</span><span class="sxs-lookup"><span data-stu-id="411f6-611">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="411f6-612">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="411f6-612">Married</span></span>                | <span data-ttu-id="411f6-613">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="411f6-613">Married</span></span>                   |
| <span data-ttu-id="411f6-614">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="411f6-614">Single</span></span>                 | <span data-ttu-id="411f6-615">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="411f6-615">Single</span></span>                    |
| <span data-ttu-id="411f6-616">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="411f6-616">Widowed</span></span>                | <span data-ttu-id="411f6-617">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="411f6-617">Widowed</span></span>                   |
| <span data-ttu-id="411f6-618">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="411f6-618">Divorced</span></span>               | <span data-ttu-id="411f6-619">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="411f6-619">Divorced</span></span>                  |
| <span data-ttu-id="411f6-620">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="411f6-620">Registered Partnership</span></span> | <span data-ttu-id="411f6-621">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="411f6-621">Domestic Partnership</span></span>      |
| <span data-ttu-id="411f6-622">Nessuna</span><span class="sxs-lookup"><span data-stu-id="411f6-622">None</span></span>                   | <span data-ttu-id="411f6-623">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="411f6-623">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="411f6-624">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="411f6-624">Cohabiting</span></span>             | <span data-ttu-id="411f6-625">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="411f6-625">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="411f6-626">Genere</span><span class="sxs-lookup"><span data-stu-id="411f6-626">Gender</span></span>

<span data-ttu-id="411f6-627">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="411f6-627">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="411f6-628">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="411f6-628">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="411f6-629">Talent</span><span class="sxs-lookup"><span data-stu-id="411f6-629">Talent</span></span>       | <span data-ttu-id="411f6-630">Dayforce</span><span class="sxs-lookup"><span data-stu-id="411f6-630">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="411f6-631">Maschio</span><span class="sxs-lookup"><span data-stu-id="411f6-631">Male</span></span>         | <span data-ttu-id="411f6-632">Maschio</span><span class="sxs-lookup"><span data-stu-id="411f6-632">Male</span></span>                      |
| <span data-ttu-id="411f6-633">Femmina</span><span class="sxs-lookup"><span data-stu-id="411f6-633">Female</span></span>       | <span data-ttu-id="411f6-634">Femmina</span><span class="sxs-lookup"><span data-stu-id="411f6-634">Female</span></span>                    |
| <span data-ttu-id="411f6-635">Non specifico</span><span class="sxs-lookup"><span data-stu-id="411f6-635">Non-specific</span></span> | <span data-ttu-id="411f6-636">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="411f6-636">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="411f6-637">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="411f6-637">Payment method</span></span>

<span data-ttu-id="411f6-638">I metodi di pagamento offrono al dipendente e all'azienda un modo per descrivere la modalità di pagamento dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="411f6-638">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="411f6-639">I metodi di pagamento vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="411f6-639">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="411f6-640">Nella tabella seguente vengono illustrati in che modo i metodi di pagamento vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="411f6-640">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="411f6-641">Talent</span><span class="sxs-lookup"><span data-stu-id="411f6-641">Talent</span></span>             | <span data-ttu-id="411f6-642">Dayforce</span><span class="sxs-lookup"><span data-stu-id="411f6-642">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="411f6-643">In contanti</span><span class="sxs-lookup"><span data-stu-id="411f6-643">Cash</span></span>               | <span data-ttu-id="411f6-644">In contanti</span><span class="sxs-lookup"><span data-stu-id="411f6-644">Cash</span></span>                      |
| <span data-ttu-id="411f6-645">Pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="411f6-645">Electronic Payment</span></span> | <span data-ttu-id="411f6-646">Trasferimenti</span><span class="sxs-lookup"><span data-stu-id="411f6-646">Transfer</span></span>                  |
| <span data-ttu-id="411f6-647">Verifica</span><span class="sxs-lookup"><span data-stu-id="411f6-647">Check</span></span>              | <span data-ttu-id="411f6-648">Assegno</span><span class="sxs-lookup"><span data-stu-id="411f6-648">Cheque</span></span>                    |
| <span data-ttu-id="411f6-649">Assegno circolare</span><span class="sxs-lookup"><span data-stu-id="411f6-649">Bank Draft</span></span>         | <span data-ttu-id="411f6-650">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="411f6-650">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="411f6-651">Altro</span><span class="sxs-lookup"><span data-stu-id="411f6-651">Other</span></span>              | <span data-ttu-id="411f6-652">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="411f6-652">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="411f6-653">Tipo di conto bancario</span><span class="sxs-lookup"><span data-stu-id="411f6-653">Bank account type</span></span>

<span data-ttu-id="411f6-654">I tipi di conto bancario vengono utilizzati per i pagamenti elettronici ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="411f6-654">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="411f6-655">I tipi di conto bancario vengono mappati in Dayforce come informazioni sul conto di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="411f6-655">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="411f6-656">I tipi di conto bancario vengono convertiti, come appropriato, nei valori accettati per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="411f6-656">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="411f6-657">Talent</span><span class="sxs-lookup"><span data-stu-id="411f6-657">Talent</span></span>            | <span data-ttu-id="411f6-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="411f6-658">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="411f6-659">Conto corrente</span><span class="sxs-lookup"><span data-stu-id="411f6-659">Checking Account</span></span>  | <span data-ttu-id="411f6-660">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="411f6-660">CheckingAccount</span></span>           |
| <span data-ttu-id="411f6-661">Conto retribuzioni</span><span class="sxs-lookup"><span data-stu-id="411f6-661">Payroll Account</span></span>   | <span data-ttu-id="411f6-662">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="411f6-662">PayrollAccount</span></span>            |
| <span data-ttu-id="411f6-663">Conto di risparmio</span><span class="sxs-lookup"><span data-stu-id="411f6-663">Savings Account</span></span>   | <span data-ttu-id="411f6-664">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="411f6-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="411f6-665">Conto Bankgirot</span><span class="sxs-lookup"><span data-stu-id="411f6-665">BankGirot account</span></span> | <span data-ttu-id="411f6-666">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="411f6-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="411f6-667">Conto PlusGirot</span><span class="sxs-lookup"><span data-stu-id="411f6-667">PlusGirot account</span></span> | <span data-ttu-id="411f6-668">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="411f6-668">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="411f6-669">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="411f6-669">Earning codes</span></span>

<span data-ttu-id="411f6-670">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="411f6-670">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="411f6-671">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="411f6-671">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="411f6-672">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="411f6-672">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="411f6-673">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="411f6-673">Supported frequencies</span></span>

- <span data-ttu-id="411f6-674">Tutti</span><span class="sxs-lookup"><span data-stu-id="411f6-674">All</span></span>
- <span data-ttu-id="411f6-675">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="411f6-675">EVERYPAY</span></span>
- <span data-ttu-id="411f6-676">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="411f6-676">EACHPAYPERIOD</span></span>
- <span data-ttu-id="411f6-677">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="411f6-677">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="411f6-678">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="411f6-678">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="411f6-679">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-679">1OFMTH</span></span>
- <span data-ttu-id="411f6-680">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-680">LASTOFMTH</span></span>
- <span data-ttu-id="411f6-681">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-681">2OFMTH</span></span>
- <span data-ttu-id="411f6-682">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-682">3OFMTH</span></span>
- <span data-ttu-id="411f6-683">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-683">4OFMTH</span></span>
- <span data-ttu-id="411f6-684">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-684">5OFMTH</span></span>
- <span data-ttu-id="411f6-685">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-685">1N2OFMTH</span></span>
- <span data-ttu-id="411f6-686">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-686">3N4OFMTH</span></span>
- <span data-ttu-id="411f6-687">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-687">1N3OFMTH</span></span>
- <span data-ttu-id="411f6-688">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-688">1N4OFMTH</span></span>
- <span data-ttu-id="411f6-689">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-689">2N3OFMTH</span></span>
- <span data-ttu-id="411f6-690">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-690">2N4OFMTH</span></span>
- <span data-ttu-id="411f6-691">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-691">1N2N3OFMTH</span></span>
- <span data-ttu-id="411f6-692">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-692">1N2N4OFMTH</span></span>
- <span data-ttu-id="411f6-693">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-693">1N3N4OFMTH</span></span>
- <span data-ttu-id="411f6-694">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-694">2N3N4OFMTH</span></span>
- <span data-ttu-id="411f6-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="411f6-695">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="411f6-696">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="411f6-696">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="411f6-697">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="411f6-697">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="411f6-698">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="411f6-698">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="411f6-699">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="411f6-699">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="411f6-700">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="411f6-700">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="411f6-701">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="411f6-701">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="411f6-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="411f6-702">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="411f6-703">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="411f6-703">Addresses</span></span>

<span data-ttu-id="411f6-704">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="411f6-704">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="411f6-705">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="411f6-705">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="411f6-706">Talent</span><span class="sxs-lookup"><span data-stu-id="411f6-706">Talent</span></span>              | <span data-ttu-id="411f6-707">Dayforce</span><span class="sxs-lookup"><span data-stu-id="411f6-707">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="411f6-708">Paese</span><span class="sxs-lookup"><span data-stu-id="411f6-708">Country/Region</span></span>      | <span data-ttu-id="411f6-709">Codice paese</span><span class="sxs-lookup"><span data-stu-id="411f6-709">Country Code</span></span>          |
| <span data-ttu-id="411f6-710">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="411f6-710">Zip/Postal Code</span></span>     | <span data-ttu-id="411f6-711">CAP</span><span class="sxs-lookup"><span data-stu-id="411f6-711">Postal Code</span></span>           |
| <span data-ttu-id="411f6-712">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="411f6-712">State</span></span>               | <span data-ttu-id="411f6-713">Codice stato</span><span class="sxs-lookup"><span data-stu-id="411f6-713">State Code</span></span>            |
| <span data-ttu-id="411f6-714">Città</span><span class="sxs-lookup"><span data-stu-id="411f6-714">City</span></span>                | <span data-ttu-id="411f6-715">Città</span><span class="sxs-lookup"><span data-stu-id="411f6-715">City</span></span>                  |
| <span data-ttu-id="411f6-716">Regione</span><span class="sxs-lookup"><span data-stu-id="411f6-716">County</span></span>              | <span data-ttu-id="411f6-717">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="411f6-717">County (Municipality)</span></span> |
| <span data-ttu-id="411f6-718">Via</span><span class="sxs-lookup"><span data-stu-id="411f6-718">Street</span></span>              | <span data-ttu-id="411f6-719">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="411f6-719">Address Line 1</span></span>        |
| <span data-ttu-id="411f6-720">Numero civico</span><span class="sxs-lookup"><span data-stu-id="411f6-720">Street Number</span></span>       | <span data-ttu-id="411f6-721">Riga indirizzo 2</span><span class="sxs-lookup"><span data-stu-id="411f6-721">Address Line 2</span></span>        |
| <span data-ttu-id="411f6-722">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="411f6-722">Building Complement</span></span> | <span data-ttu-id="411f6-723">Riga indirizzo 5</span><span class="sxs-lookup"><span data-stu-id="411f6-723">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="411f6-724">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="411f6-724">Passport number</span></span>

<span data-ttu-id="411f6-725">I dipendenti possono indicare le informazioni sul passaporto.</span><span class="sxs-lookup"><span data-stu-id="411f6-725">Employees can declare passport information.</span></span> <span data-ttu-id="411f6-726">Queste informazioni sono del tipo di identificazione **Passaporto** e vengono integrate in Dayforce come parte delle informazioni di un dipendente specifiche per il Messico.</span><span class="sxs-lookup"><span data-stu-id="411f6-726">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="411f6-727">Tipo di identificazione = "Passaporto"</span><span class="sxs-lookup"><span data-stu-id="411f6-727">Identification Type = "Passport"</span></span>
- <span data-ttu-id="411f6-728">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="411f6-728">Issued Date</span></span>
- <span data-ttu-id="411f6-729">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="411f6-729">Expiration Date</span></span>

<span data-ttu-id="411f6-730">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **Passaporto**.</span><span class="sxs-lookup"><span data-stu-id="411f6-730">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="411f6-731">Tuttavia, solo l'immissione del passaporto attivo corrente viene integrata in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="411f6-731">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="411f6-732">Se tutte le immissioni di passaporto sono scadute, in Dayforce viene integrato il passaporto di emissione più recente.</span><span class="sxs-lookup"><span data-stu-id="411f6-732">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
