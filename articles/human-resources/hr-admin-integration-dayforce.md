---
title: Configurare l'integrazione con Dayforce
description: L'integrazione tra Microsoft Dynamics 365 Human Resources e Ceridian Dayforce si basa su vari passaggi di configurazione descritti in questo articolo. È necessario configurare l'integrazione sia in Human Resources che in Dayforce prima di poter elaborare un ciclo di pagamenti.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2d5f65672960716bee3f58c98ccce249fdbf8697
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467147"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="95da4-104">Configurare l'integrazione con Dayforce</span><span class="sxs-lookup"><span data-stu-id="95da4-104">Configure integration with Dayforce</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="95da4-105">L'integrazione tra Microsoft Dynamics 365 Human Resources e Ceridian Dayforce si basa su vari passaggi di configurazione descritti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="95da4-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="95da4-106">È necessario configurare l'integrazione sia in Human Resources che in Dayforce prima di poter elaborare un ciclo di pagamenti.</span><span class="sxs-lookup"><span data-stu-id="95da4-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="95da4-107">Quando si utilizza un servizio, ad esempio Dayforce, per completare i cicli di pagamenti, è necessario abilitare l'integrazione in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="95da4-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="95da4-108">L'integrazione richiede dati specifici da Human Resources.</span><span class="sxs-lookup"><span data-stu-id="95da4-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="95da4-109">Di conseguenza, è necessario verificare che i dati che vengono mappati a Dayforce siano configurati in Human Resources in modo che supporti l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="95da4-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="95da4-110">L'integrazione utilizza le seguenti categorie generiche di dati:</span><span class="sxs-lookup"><span data-stu-id="95da4-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="95da4-111">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="95da4-111">Human resources data</span></span>
- <span data-ttu-id="95da4-112">Dati di compensazione</span><span class="sxs-lookup"><span data-stu-id="95da4-112">Compensation data</span></span>
- <span data-ttu-id="95da4-113">Data di retribuzione, ad esempio i cicli di pagamenti, i periodi retributivi e i codici reddito</span><span class="sxs-lookup"><span data-stu-id="95da4-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="95da4-114">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-114">Worker data</span></span>

<span data-ttu-id="95da4-115">In questo articolo vengono descritti i passaggi che è necessario completare per abilitare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="95da4-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="95da4-116">E vengono descritti i tipi di dati e i dettagli di configurazione necessari all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="95da4-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="95da4-117">Abilitare l'integrazione</span><span class="sxs-lookup"><span data-stu-id="95da4-117">Enable the integration</span></span>

<span data-ttu-id="95da4-118">In Human Resources è necessario attivare l'integrazione e immettere le informazioni di configurazione per connettersi a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95da4-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="95da4-119">Se si desidera che la transazione contabile prodotta venga importata in Microsoft Dynamics 365 Finance, è necessario impostare anche un conto di archiviazione di Microsoft Azure e immettere la stringa di connessione di Archiviazione di Azure in Finance.</span><span class="sxs-lookup"><span data-stu-id="95da4-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="95da4-120">Per attivare l'integrazione in Human Resources, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="95da4-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="95da4-121">Nella pagina **Amministrazione sistema** selezionare **Configurazione di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="95da4-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="95da4-122">Immettere l'endpoint FTP (File Transfer Protocol) e il percorso protetto della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="95da4-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="95da4-123">Immettere il nome utente e la password dell'utente che accederà al percorso protetto dell'endpoint e della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="95da4-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="95da4-124">Verificare la connessione, secondo le esigenze, e impostare l'opzione **Abilita integrazione retribuzioni** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="95da4-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="95da4-125">Quando l'integrazione viene attivata, vengono creati i file e il pacchetto di esportazione dei dati e viene impostata la frequenza.</span><span class="sxs-lookup"><span data-stu-id="95da4-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="95da4-126">È possibile cambiare la frequenza in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="95da4-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="95da4-127">Per altre informazioni sugli account di Archiviazione di Azure e sulle stringhe di connessione di Archiviazione di Azure, vedere gli articoli di Azure seguenti:</span><span class="sxs-lookup"><span data-stu-id="95da4-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="95da4-128">Account di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="95da4-128">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="95da4-129">Configurare le stringhe di connessione di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="95da4-129">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="95da4-130">Dettagli tecnici quando l'integrazione delle retribuzioni è attivata</span><span class="sxs-lookup"><span data-stu-id="95da4-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="95da4-131">L'attivazione dell'integrazione delle retribuzioni comporta due effetti primari:</span><span class="sxs-lookup"><span data-stu-id="95da4-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="95da4-132">Viene creato un progetto di esportazione di dati denominato "Esportazione integrazione delle retribuzioni".</span><span class="sxs-lookup"><span data-stu-id="95da4-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="95da4-133">Questo progetto contiene le entità e i campi necessari per l'integrazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="95da4-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="95da4-134">Per esaminare il progetto, andare a **Amministrazione sistema**, selezionare il riquadro **Gestione dati** e infine aprire il progetto dati dall'elenco di progetti.</span><span class="sxs-lookup"><span data-stu-id="95da4-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="95da4-135">Questo processo batch esegue il progetto di esportazione dei dati, codifica il pacchetto dati risultante e trasferisce il file del pacchetto dati all'endpoint SFTP configurato nella schermata **Configurazione di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="95da4-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="95da4-136">Il pacchetto dati trasferito all'endpoint SFTP viene codificato utilizzando una chiave univoca per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="95da4-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="95da4-137">La chiave è un Azure Key Vault accessibile solo da Ceridian.</span><span class="sxs-lookup"><span data-stu-id="95da4-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="95da4-138">Non è possibile decrittografare ed esaminare il contenuto del pacchetto dati.</span><span class="sxs-lookup"><span data-stu-id="95da4-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="95da4-139">Se è necessario esaminare il contenuto del pacchetto dati, esportare manualmente il progetto dati "Esportazione integrazione delle retribuzioni", scaricarlo e quindi aprirlo.</span><span class="sxs-lookup"><span data-stu-id="95da4-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="95da4-140">L'esportazione manuale non comporta la crittografia o il trasferimento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="95da4-140">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="95da4-141">Configurare i dati</span><span class="sxs-lookup"><span data-stu-id="95da4-141">Configure your data</span></span> 

<span data-ttu-id="95da4-142">Per elaborare le retribuzioni, è necessario configurare i dati di Risorse umane in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="95da4-142">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="95da4-143">È necessario impostare i dati dell'organizzazione, ad esempio mansioni e posizioni, insieme alle informazioni sui benefit e sulle compensazioni.</span><span class="sxs-lookup"><span data-stu-id="95da4-143">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="95da4-144">Queste informazioni includono informazioni sull'impiego, la retribuzione e le detrazioni che sono richieste per generare la retribuzione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="95da4-144">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="95da4-145">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="95da4-145">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="95da4-146">Benefit</span><span class="sxs-lookup"><span data-stu-id="95da4-146">Benefits</span></span> 

<span data-ttu-id="95da4-147">Le risorse umane dispongono di strumenti per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori.</span><span class="sxs-lookup"><span data-stu-id="95da4-147">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="95da4-148">Quando si creano i benefit, tenere presenti i seguenti dati e configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95da4-148">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="95da4-149">Piani di benefit</span><span class="sxs-lookup"><span data-stu-id="95da4-149">Benefit plans</span></span>

- <span data-ttu-id="95da4-150">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-150">Plan (required)</span></span>
- <span data-ttu-id="95da4-151">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-151">Type (required)</span></span>
- <span data-ttu-id="95da4-152">Impatto retribuzioni (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-152">Payroll impact (required)</span></span>
- <span data-ttu-id="95da4-153">Recupera arretrati</span><span class="sxs-lookup"><span data-stu-id="95da4-153">Recover arrears</span></span>
- <span data-ttu-id="95da4-154">Metodo di detrazione</span><span class="sxs-lookup"><span data-stu-id="95da4-154">Deduction method</span></span>
- <span data-ttu-id="95da4-155">Priorità detrazione</span><span class="sxs-lookup"><span data-stu-id="95da4-155">Deduction priority</span></span>
- <span data-ttu-id="95da4-156">Periodo limite</span><span class="sxs-lookup"><span data-stu-id="95da4-156">Limit period</span></span>
- <span data-ttu-id="95da4-157">Importo limite</span><span class="sxs-lookup"><span data-stu-id="95da4-157">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="95da4-158">Benefit</span><span class="sxs-lookup"><span data-stu-id="95da4-158">Benefits</span></span>

- <span data-ttu-id="95da4-159">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-159">Plan (required)</span></span>
- <span data-ttu-id="95da4-160">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-160">Type (required)</span></span>
- <span data-ttu-id="95da4-161">Opzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-161">Option (required)</span></span>
- <span data-ttu-id="95da4-162">ID benefit (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-162">Benefit ID (required)</span></span>
- <span data-ttu-id="95da4-163">Frequenza</span><span class="sxs-lookup"><span data-stu-id="95da4-163">Frequency</span></span>
- <span data-ttu-id="95da4-164">Base</span><span class="sxs-lookup"><span data-stu-id="95da4-164">Basis</span></span>
- <span data-ttu-id="95da4-165">Importo o coefficiente</span><span class="sxs-lookup"><span data-stu-id="95da4-165">Amount or rate</span></span>
- <span data-ttu-id="95da4-166">Codice di reddito</span><span class="sxs-lookup"><span data-stu-id="95da4-166">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="95da4-167">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="95da4-167">Supported frequencies</span></span> 

- <span data-ttu-id="95da4-168">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="95da4-168">Weekly</span></span>
- <span data-ttu-id="95da4-169">Bisettimanale</span><span class="sxs-lookup"><span data-stu-id="95da4-169">Bi-weekly</span></span>
- <span data-ttu-id="95da4-170">Quindicinale</span><span class="sxs-lookup"><span data-stu-id="95da4-170">Semi-monthly</span></span>
- <span data-ttu-id="95da4-171">Ogni mese</span><span class="sxs-lookup"><span data-stu-id="95da4-171">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="95da4-172">Basi supportate</span><span class="sxs-lookup"><span data-stu-id="95da4-172">Supported bases</span></span> 

- <span data-ttu-id="95da4-173">Importo fisso</span><span class="sxs-lookup"><span data-stu-id="95da4-173">Fixed amount</span></span>
- <span data-ttu-id="95da4-174">Percentuale di redditi</span><span class="sxs-lookup"><span data-stu-id="95da4-174">Percent of earnings</span></span>
- <span data-ttu-id="95da4-175">Ore di produzione</span><span class="sxs-lookup"><span data-stu-id="95da4-175">Productive hours</span></span>

<span data-ttu-id="95da4-176">Dayforce crea le seguenti detrazioni, in base all'impatto delle retribuzioni definito nel piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="95da4-176">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="95da4-177">Selezione in Human Resources</span><span class="sxs-lookup"><span data-stu-id="95da4-177">Selection in Human Resources</span></span>        | <span data-ttu-id="95da4-178">Risultato in Dayforce</span><span class="sxs-lookup"><span data-stu-id="95da4-178">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="95da4-179">Nessuna</span><span class="sxs-lookup"><span data-stu-id="95da4-179">None</span></span>                       | <span data-ttu-id="95da4-180">Non viene creata alcuna detrazione.</span><span class="sxs-lookup"><span data-stu-id="95da4-180">No deduction is created.</span></span>                      |
| <span data-ttu-id="95da4-181">Solo detrazione</span><span class="sxs-lookup"><span data-stu-id="95da4-181">Deduction only</span></span>             | <span data-ttu-id="95da4-182">Viene creata una detrazione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="95da4-182">An employee deduction is created.</span></span>             |
| <span data-ttu-id="95da4-183">Solo contribuzione</span><span class="sxs-lookup"><span data-stu-id="95da4-183">Contribution only</span></span>          | <span data-ttu-id="95da4-184">Viene creata una detrazione del datore di lavoro.</span><span class="sxs-lookup"><span data-stu-id="95da4-184">An employer deduction is created.</span></span>             |
| <span data-ttu-id="95da4-185">Detrazione e contribuzione</span><span class="sxs-lookup"><span data-stu-id="95da4-185">Deduction and contribution</span></span> | <span data-ttu-id="95da4-186">Vengono create detrazioni del datore di lavoro e del dipendente.</span><span class="sxs-lookup"><span data-stu-id="95da4-186">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="95da4-187">Per altre informazioni su come definire e gestire un programma di benefit, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="95da4-187">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="95da4-188">Realizzare un programma di benefit per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="95da4-188">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="95da4-189">Crea un nuovo benefit</span><span class="sxs-lookup"><span data-stu-id="95da4-189">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="95da4-190">Definire regole e criteri di idoneità ai benefit</span><span class="sxs-lookup"><span data-stu-id="95da4-190">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="95da4-191">Iscrivere e rimuovere benefit da lavoratori</span><span class="sxs-lookup"><span data-stu-id="95da4-191">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="95da4-192">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="95da4-192">Compensation</span></span> 

<span data-ttu-id="95da4-193">La gestione delle retribuzioni consente di controllare la liquidazione dei premi e della retribuzione base.</span><span class="sxs-lookup"><span data-stu-id="95da4-193">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="95da4-194">La retribuzione di base fissa di un dipendente e gli aumenti per merito sono controllati mediante piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="95da4-194">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="95da4-195">È possibile controllare il pagamento degli incentivi, ad esempio il pagamento dei bonus, dei premi produttività, dei diritti di opzione, delle sovvenzioni, oltre che dei premi una tantum, tramite i piani di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="95da4-195">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="95da4-196">Dayforce utilizza le informazioni sulla compensazione per calcolare la retribuzione annuale o oraria di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="95da4-196">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="95da4-197">I piani di retribuzione fissa e conversioni della retribuzione sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="95da4-197">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="95da4-198">I dipendenti devono essere associati a un piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="95da4-198">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="95da4-199">Per ulteriori informazioni sui piani di retribuzione, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="95da4-199">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="95da4-200">Creare piani di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="95da4-200">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="95da4-201">Creare piani di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="95da4-201">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="95da4-202">Sviluppare una struttura e piani di stipendi/retribuzioni</span><span class="sxs-lookup"><span data-stu-id="95da4-202">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="95da4-203">Processo retributivo</span><span class="sxs-lookup"><span data-stu-id="95da4-203">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="95da4-204">Definire il processo retributivo e calcolare i risultati</span><span class="sxs-lookup"><span data-stu-id="95da4-204">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="95da4-205">Iscrivere un dipendente a un piano di retribuzione fisso</span><span class="sxs-lookup"><span data-stu-id="95da4-205">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="95da4-206">Iscrivere un dipendente a un piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="95da4-206">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="95da4-207">Mansioni</span><span class="sxs-lookup"><span data-stu-id="95da4-207">Jobs</span></span> 

<span data-ttu-id="95da4-208">Una mansione è una raccolta delle attività e delle responsabilità proprie della persona assegnata a una mansione.</span><span class="sxs-lookup"><span data-stu-id="95da4-208">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="95da4-209">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="95da4-209">For more information, see the following articles:</span></span>

- [<span data-ttu-id="95da4-210">Impostazione dei componenti di una mansione</span><span class="sxs-lookup"><span data-stu-id="95da4-210">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="95da4-211">Definire nuovi processi</span><span class="sxs-lookup"><span data-stu-id="95da4-211">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="95da4-212">Posizioni</span><span class="sxs-lookup"><span data-stu-id="95da4-212">Positions</span></span>

<span data-ttu-id="95da4-213">Una posizione è una singola istanza di un processo.</span><span class="sxs-lookup"><span data-stu-id="95da4-213">A position is an individual instance of a job.</span></span> <span data-ttu-id="95da4-214">Ad esempio, la posizione "Manager vendite (Est") è una delle posizioni associate alla mansione "Manager vendite".</span><span class="sxs-lookup"><span data-stu-id="95da4-214">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="95da4-215">Una posizione è presente in un reparto.</span><span class="sxs-lookup"><span data-stu-id="95da4-215">A position exists in a department.</span></span> <span data-ttu-id="95da4-216">È possibile associare un solo lavoratore a ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="95da4-216">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="95da4-217">Tenere a mente i seguenti dati e la configurazione quando si impostano le posizioni:</span><span class="sxs-lookup"><span data-stu-id="95da4-217">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="95da4-218">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-218">Position (required)</span></span>
- <span data-ttu-id="95da4-219">Descrizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-219">Description (required)</span></span>
- <span data-ttu-id="95da4-220">Mansione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-220">Job (required)</span></span>
- <span data-ttu-id="95da4-221">Reparto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-221">Department (required)</span></span>
- <span data-ttu-id="95da4-222">Tipo di posizione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-222">Position type (required)</span></span>
- <span data-ttu-id="95da4-223">Equivalente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="95da4-223">Full-time equivalent</span></span>
- <span data-ttu-id="95da4-224">Ore regolari annuali (obbligatorie)</span><span class="sxs-lookup"><span data-stu-id="95da4-224">Annual regular hours (required)</span></span>
- <span data-ttu-id="95da4-225">Pagamento in base alla persona giuridica (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-225">Paid by legal entity (required)</span></span>
- <span data-ttu-id="95da4-226">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="95da4-226">Pay cycle (required)</span></span>
- <span data-ttu-id="95da4-227">Dimensione finanziaria predefinita - Centro di costo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-227">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="95da4-228">Assegnazione del lavoratore - Lavoratore, inizio assegnazione, fine assegnazione, codice motivo</span><span class="sxs-lookup"><span data-stu-id="95da4-228">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="95da4-229">Se nello stesso reparto più posizioni sono associate alla stessa mansione, vengono consolidate in una singola posizione in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95da4-229">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="95da4-230">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="95da4-230">For more information, see the following articles:</span></span>

- [<span data-ttu-id="95da4-231">Organizzare la forza lavoro utilizzando i reparti, le mansioni e le posizioni</span><span class="sxs-lookup"><span data-stu-id="95da4-231">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="95da4-232">Impostare le posizioni</span><span class="sxs-lookup"><span data-stu-id="95da4-232">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="95da4-233">Reparti</span><span class="sxs-lookup"><span data-stu-id="95da4-233">Departments</span></span>

<span data-ttu-id="95da4-234">Un reparto è un'unità operativa che rappresenta una categoria o un'area operativa di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="95da4-234">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="95da4-235">Un reparto è responsabile di una specifica area dell'organizzazione, ad esempio la vendita, la contabilità o le risorse umane.</span><span class="sxs-lookup"><span data-stu-id="95da4-235">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="95da4-236">È possibile utilizzare i reparti per creare report sulle aree operative.</span><span class="sxs-lookup"><span data-stu-id="95da4-236">You can use departments to report on functional areas.</span></span> <span data-ttu-id="95da4-237">I reparti possono essere responsabili di profitti e perdite.</span><span class="sxs-lookup"><span data-stu-id="95da4-237">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="95da4-238">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="95da4-238">For more information, see the following articles:</span></span>

- [<span data-ttu-id="95da4-239">Creare un reparto e associarlo alla gerarchia reparti</span><span class="sxs-lookup"><span data-stu-id="95da4-239">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="95da4-240">Definire nuovi reparti</span><span class="sxs-lookup"><span data-stu-id="95da4-240">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="95da4-241">Cicli e periodi retributivi</span><span class="sxs-lookup"><span data-stu-id="95da4-241">Pay cycles and pay periods</span></span>

<span data-ttu-id="95da4-242">Un ciclo retributivo determina la frequenza di elaborazione delle retribuzioni e i giorni specifici in cui i lavoratori vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="95da4-242">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="95da4-243">Un ciclo retributivo può essere ad esempio mensile e i dipendenti possono essere pagati l'ultimo giorno del mese.</span><span class="sxs-lookup"><span data-stu-id="95da4-243">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="95da4-244">Un ciclo retributivo può in alternativa essere settimanale e i dipendenti possono essere pagati il giovedì successivo alla fine del periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="95da4-244">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="95da4-245">I cicli retributivi vengono assegnati alle posizioni per controllare quando i lavoratori in tali posizioni vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="95da4-245">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="95da4-246">Dopo aver creato i cicli retributivi, è possibile generare periodi retributivi per ogni ciclo.</span><span class="sxs-lookup"><span data-stu-id="95da4-246">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="95da4-247">Ogni periodo retributivo include una data di pagamento predefinita in base alle informazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="95da4-247">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="95da4-248">Tuttavia, è possibile modificare la data di pagamento predefinita in un periodo retributivo per consentire eccezioni, ad esempio quando la data di pagamento cade in un giorno festivo.</span><span class="sxs-lookup"><span data-stu-id="95da4-248">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="95da4-249">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="95da4-249">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="95da4-250">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="95da4-250">Pay cycle (required)</span></span>
- <span data-ttu-id="95da4-251">Frequenza ciclo retributivo (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-251">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="95da4-252">Data di inizio del periodo (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-252">Period start date (first pay period required)</span></span>
- <span data-ttu-id="95da4-253">Data di pagamento predefinita (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-253">Default payment date (first pay period required)</span></span>

<span data-ttu-id="95da4-254">Queste informazioni sono integrate con Dayforce come gruppi retributivi e sono separata in base al paese o alla regione per ogni ciclo retributivo.</span><span class="sxs-lookup"><span data-stu-id="95da4-254">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="95da4-255">Prima dell'integrazione è necessario generare almeno un periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="95da4-255">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="95da4-256">Dayforce genera calendari di gruppi retributivi e date di pagamento, in base alla data di inizio del primo periodo retributivo e alla data di pagamento predefinita che viene impostata in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="95da4-256">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="95da4-257">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="95da4-257">Earning codes</span></span>

<span data-ttu-id="95da4-258">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="95da4-258">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="95da4-259">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="95da4-259">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="95da4-260">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="95da4-260">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="95da4-261">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-261">Earning Code (required)</span></span>
- <span data-ttu-id="95da4-262">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95da4-262">Description</span></span>
- <span data-ttu-id="95da4-263">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="95da4-263">Unit of measure</span></span>
- <span data-ttu-id="95da4-264">Produttivo</span><span class="sxs-lookup"><span data-stu-id="95da4-264">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="95da4-265">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-265">Worker data</span></span>

<span data-ttu-id="95da4-266">I record per i diversi tipi di lavoratori a disposizione sono importanti per i sistemi di gestione delle risorse umane e delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="95da4-266">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="95da4-267">Le informazioni immesse possono essere utilizzate per tenere traccia di informazioni personali e sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="95da4-267">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="95da4-268">È possibile gestire le seguenti informazioni per i lavoratori:</span><span class="sxs-lookup"><span data-stu-id="95da4-268">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="95da4-269">**Base** - Gestire le informazioni di base su un lavoratore, ad esempio le informazioni sui contatti, le informazioni demografiche, le informazioni di identificazione, le informazioni sulla famiglia, lo stato di servizio militare, le informazioni sull'espatrio, e i contatti personali e di emergenza.</span><span class="sxs-lookup"><span data-stu-id="95da4-269">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="95da4-270">**Impiego** - Consente di gestire le informazioni sull'impiego di un lavoratore, ad esempio rapporto con l'organizzazione o la società, assegnazione della posizione, date di inizio e fine, idoneità al lavoro, condizioni di impiego, pensionamento, ferie e trasferimento.</span><span class="sxs-lookup"><span data-stu-id="95da4-270">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="95da4-271">**Congedo e assenza** - Consente di gestire le informazioni sulle assenze di un lavoratore, ad esempio calendari di lavoro, transazioni assenze e impostazione assenze.</span><span class="sxs-lookup"><span data-stu-id="95da4-271">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="95da4-272">**Retribuzioni** - Consente di gestire le informazioni sui piani di retribuzione di un lavoratore, ad esempio registrazione del piano, premi, prestazioni, provvigione, dati fiscali, pensionamento e detrazioni sullo stipendio.</span><span class="sxs-lookup"><span data-stu-id="95da4-272">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="95da4-273">Quando si immettono le informazioni su un lavoratore, tenere presenti i seguenti dati e le configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95da4-273">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="95da4-274">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="95da4-274">General information</span></span>

- <span data-ttu-id="95da4-275">Numero dipendente (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-275">Personnel number (required)</span></span>
- <span data-ttu-id="95da4-276">Nome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-276">First name (required)</span></span>
- <span data-ttu-id="95da4-277">Cognome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-277">Last name (required)</span></span>
- <span data-ttu-id="95da4-278">Secondo nome</span><span class="sxs-lookup"><span data-stu-id="95da4-278">Middle name</span></span>
- <span data-ttu-id="95da4-279">Data di anzianità</span><span class="sxs-lookup"><span data-stu-id="95da4-279">Seniority date</span></span>
- <span data-ttu-id="95da4-280">Nome noto</span><span class="sxs-lookup"><span data-stu-id="95da4-280">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="95da4-281">Informazioni personali</span><span class="sxs-lookup"><span data-stu-id="95da4-281">Personal information</span></span>

- <span data-ttu-id="95da4-282">Stato civile (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-282">Marital status (required)</span></span>
- <span data-ttu-id="95da4-283">Data di nascita (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-283">Birth date (required)</span></span>
- <span data-ttu-id="95da4-284">Sesso (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-284">Gender (required)</span></span>
- <span data-ttu-id="95da4-285">Persona disabile</span><span class="sxs-lookup"><span data-stu-id="95da4-285">Person with disabilities</span></span>
- <span data-ttu-id="95da4-286">Nazionalità paese regione (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="95da4-286">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="95da4-287">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="95da4-287">Address information</span></span>

- <span data-ttu-id="95da4-288">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-288">Primary (required)</span></span>
- <span data-ttu-id="95da4-289">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-289">Country/region (required)</span></span>
- <span data-ttu-id="95da4-290">Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-290">Postal code (required)</span></span>
- <span data-ttu-id="95da4-291">Numero civico (obbligatorio) (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="95da4-291">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="95da4-292">Informazioni aggiuntive sull'indirizzo (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="95da4-292">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="95da4-293">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-293">City (required)</span></span>
- <span data-ttu-id="95da4-294">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-294">State (required)</span></span>
- <span data-ttu-id="95da4-295">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-295">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="95da4-296">Informazioni contatto</span><span class="sxs-lookup"><span data-stu-id="95da4-296">Contact information</span></span> 

- <span data-ttu-id="95da4-297">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-297">Primary (required)</span></span>
- <span data-ttu-id="95da4-298">Numero contatto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-298">Contact number (required)</span></span>
- <span data-ttu-id="95da4-299">Interno</span><span class="sxs-lookup"><span data-stu-id="95da4-299">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="95da4-300">Informazioni sulle retribuzioni e codici di reddito</span><span class="sxs-lookup"><span data-stu-id="95da4-300">Payroll information and earning codes</span></span>

<span data-ttu-id="95da4-301">Ai dipendenti possono essere assegnati redditi specifici a una determinata frequenza di pagamento e un metodo di pagamento preferito.</span><span class="sxs-lookup"><span data-stu-id="95da4-301">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="95da4-302">I campi seguenti vengono utilizzati in Dayforce per garantire che le preferenze e le impostazioni vengano utilizzate.</span><span class="sxs-lookup"><span data-stu-id="95da4-302">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="95da4-303">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="95da4-303">Earning codes</span></span>

- <span data-ttu-id="95da4-304">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-304">Position (required)</span></span>
- <span data-ttu-id="95da4-305">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-305">Earning Code (required)</span></span>
- <span data-ttu-id="95da4-306">Frequenza (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-306">Frequency (required)</span></span>
- <span data-ttu-id="95da4-307">Importo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-307">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="95da4-308">Informazioni retribuzioni</span><span class="sxs-lookup"><span data-stu-id="95da4-308">Payroll information</span></span>

- <span data-ttu-id="95da4-309">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="95da4-309">Payment Method</span></span>
- <span data-ttu-id="95da4-310">Area economica (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-310">Economic Region (required)</span></span>
- <span data-ttu-id="95da4-311">ID benefit dipendente</span><span class="sxs-lookup"><span data-stu-id="95da4-311">Employee Benefits ID</span></span>
- <span data-ttu-id="95da4-312">Numero documento identità (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-312">National ID Number (required)</span></span>
- <span data-ttu-id="95da4-313">Numero servizio militare</span><span class="sxs-lookup"><span data-stu-id="95da4-313">Military Service Number</span></span>
- <span data-ttu-id="95da4-314">ID turno (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-314">Shift ID (required)</span></span>
- <span data-ttu-id="95da4-315">Numero imposta (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-315">Tax Number (required)</span></span>
- <span data-ttu-id="95da4-316">ID sindacato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-316">Union ID (required)</span></span>
- <span data-ttu-id="95da4-317">ID giorno lavorativo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-317">Work Day ID (required)</span></span>
- <span data-ttu-id="95da4-318">Numero permesso di lavoro</span><span class="sxs-lookup"><span data-stu-id="95da4-318">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="95da4-319">Per il metodo di pagamento, il Messico supporta **Contante**, **Assegno** (l'assegno fisico della società) e **Pagamento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="95da4-319">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="95da4-320">Se non viene specificato alcun metodo di pagamento, **Assegno** è 'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="95da4-320">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="95da4-321">Dettagli impiego</span><span class="sxs-lookup"><span data-stu-id="95da4-321">Employment details</span></span>

<span data-ttu-id="95da4-322">Lo storico dei dettagli impiego viene utilizzato come informazioni chiave da cui derivare gli stati di assunzione, termine e riassunzione di un dipendente Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95da4-322">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="95da4-323">Dayforce supporta solo un record di impiego attivo alla volta.</span><span class="sxs-lookup"><span data-stu-id="95da4-323">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="95da4-324">Data di inizio impiego (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-324">Employment start date (required)</span></span>
- <span data-ttu-id="95da4-325">Data di fine impiego</span><span class="sxs-lookup"><span data-stu-id="95da4-325">Employment end date</span></span>
- <span data-ttu-id="95da4-326">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="95da4-326">Start date</span></span>
- <span data-ttu-id="95da4-327">Data di inizio rettificata</span><span class="sxs-lookup"><span data-stu-id="95da4-327">Adjusted start date</span></span>
- <span data-ttu-id="95da4-328">Data fine rapporto (obbligatoria con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="95da4-328">Termination date (required upon termination)</span></span>
- <span data-ttu-id="95da4-329">Motivo fine rapporto (obbligatorio con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="95da4-329">Termination reason (required upon termination)</span></span>

<span data-ttu-id="95da4-330">Le date chiave del dipendente sono derivate utilizzando le informazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="95da4-330">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="95da4-331">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="95da4-331">Human Resources</span></span>                | <span data-ttu-id="95da4-332">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95da4-332">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="95da4-333">Data di assunzione più recente</span><span class="sxs-lookup"><span data-stu-id="95da4-333">Most recent hire date</span></span> | <span data-ttu-id="95da4-334">Inizio dell'impiego del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="95da4-334">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="95da4-335">Data fine rapporto</span><span class="sxs-lookup"><span data-stu-id="95da4-335">Termination date</span></span>      | <span data-ttu-id="95da4-336">Data di fine rapporto del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="95da4-336">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="95da4-337">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="95da4-337">Start date</span></span>            | <span data-ttu-id="95da4-338">Data di inizio rettificata, data di inizio o inizio dell'impiego del record corrente dello storico di impiego non attivo</span><span class="sxs-lookup"><span data-stu-id="95da4-338">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="95da4-339">Data di assunzione originale</span><span class="sxs-lookup"><span data-stu-id="95da4-339">Original hire date</span></span>    | <span data-ttu-id="95da4-340">Inizio dell'impiego del record dello storico di impiego meno recente</span><span class="sxs-lookup"><span data-stu-id="95da4-340">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="95da4-341">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="95da4-341">Compensation</span></span>

<span data-ttu-id="95da4-342">Un piano di retribuzione fissa deve essere associato alla posizione primaria di ogni dipendente durante un periodo di impiego.</span><span class="sxs-lookup"><span data-stu-id="95da4-342">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="95da4-343">Questo periodo inizia alla data in cui il dipendente è stato assunto (o la data di inizio dell'impiego) e continua fino alla fine del rapporto.</span><span class="sxs-lookup"><span data-stu-id="95da4-343">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="95da4-344">Data di validità (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-344">Effective Date (required)</span></span>
- <span data-ttu-id="95da4-345">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="95da4-345">Expiration date</span></span>
- <span data-ttu-id="95da4-346">Retribuzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-346">Pay Rate (required)</span></span>
- <span data-ttu-id="95da4-347">Conversioni retribuzione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-347">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="95da4-348">Equivalente annuale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-348">Annual equivalent (required)</span></span>
- <span data-ttu-id="95da4-349">Equivalente orario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-349">Hourly equivalent (required)</span></span>

<span data-ttu-id="95da4-350">Se un dipendente a ore ha più posizioni, la retribuzione fissa della posizione primaria viene importata in Dayforce come il tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="95da4-350">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="95da4-351">Per le posizioni non principali, la tariffa oraria viene salvata nella posizione corrispondente in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95da4-351">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="95da4-352">Se un dipendente stipendiato ha più posizioni, la tariffa oraria cumulativa e lo stipendio annuale di tutte le posizioni attive vengono calcolati e utilizzati come tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="95da4-352">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="95da4-353">Numeri di identificazione</span><span class="sxs-lookup"><span data-stu-id="95da4-353">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="95da4-354">Numero di Previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="95da4-354">Social Security identifier</span></span> 

<span data-ttu-id="95da4-355">Ogni dipendente deve avere un identificatore primario.</span><span class="sxs-lookup"><span data-stu-id="95da4-355">Every employee must have one primary identifier.</span></span> <span data-ttu-id="95da4-356">Questo identificatore deve essere di tipo identificatore **SSN**.</span><span class="sxs-lookup"><span data-stu-id="95da4-356">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="95da4-357">In Dayforce, viene ricavato automaticamente come identificatore di previdenza sociale del dipendente per l'assunzione.</span><span class="sxs-lookup"><span data-stu-id="95da4-357">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="95da4-358">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-358">Primary (required)</span></span>
- <span data-ttu-id="95da4-359">Tipo di identificazione = "SSN"</span><span class="sxs-lookup"><span data-stu-id="95da4-359">Identification Type = "SSN"</span></span>
- <span data-ttu-id="95da4-360">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="95da4-360">Issued Date</span></span>
- <span data-ttu-id="95da4-361">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="95da4-361">Expiration Date</span></span>

<span data-ttu-id="95da4-362">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **SSN**.</span><span class="sxs-lookup"><span data-stu-id="95da4-362">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="95da4-363">Tuttavia, solo il record che è contrassegnato come **Primario** viene integrato in Dayforce, a prescindere che il numero sia attivo o scaduto.</span><span class="sxs-lookup"><span data-stu-id="95da4-363">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="95da4-364">Esborsi e conti bancari</span><span class="sxs-lookup"><span data-stu-id="95da4-364">Bank accounts and disbursements</span></span>

<span data-ttu-id="95da4-365">È necessario immettere informazioni sul conto bancario valide per un dipendente che scelga di essere pagato tramite trasferimenti di conto bancario.</span><span class="sxs-lookup"><span data-stu-id="95da4-365">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="95da4-366">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="95da4-366">Human Resources</span></span>                         | <span data-ttu-id="95da4-367">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95da4-367">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="95da4-368">Numero conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-368">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="95da4-369">Codice SWIFT (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-369">SWIFT code (required)</span></span>          | <span data-ttu-id="95da4-370">Campo **ID banca** utilizzato durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="95da4-370">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="95da4-371">Codice filiale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-371">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="95da4-372">Tipo di conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-372">Bank account type (required)</span></span>   | <span data-ttu-id="95da4-373">Campo **Tipo di conto** utilizzando durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="95da4-373">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="95da4-374">I valori supportati includono **Controllo** e **Retribuzioni**.</span><span class="sxs-lookup"><span data-stu-id="95da4-374">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="95da4-375">I dipendenti che scelgono di essere pagati tramite trasferimenti di conto bancario devono fornire un collegamento a un conto rimanente che è sotto la persona giuridica che ha l'indirizzo primario in Messico ed è associato a un conto bancario valido presso una banca messicana.</span><span class="sxs-lookup"><span data-stu-id="95da4-375">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="95da4-376">Tutti gli altri account non di rimanenze verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="95da4-376">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="95da4-377">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="95da4-377">Address information</span></span>

<span data-ttu-id="95da4-378">Ogni dipendente deve avere un'ubicazione primaria.</span><span class="sxs-lookup"><span data-stu-id="95da4-378">Every employee must have one primary location.</span></span> <span data-ttu-id="95da4-379">In Dayforce, questa ubicazione viene utilizzata per determinare la principale residenza del dipendente a scopo fiscale.</span><span class="sxs-lookup"><span data-stu-id="95da4-379">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="95da4-380">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-380">Primary (required)</span></span>
- <span data-ttu-id="95da4-381">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-381">Country/region (required)</span></span>
- <span data-ttu-id="95da4-382">CAP/Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-382">Zip/postal code (required)</span></span>
- <span data-ttu-id="95da4-383">Via (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-383">Street (required)</span></span>
- <span data-ttu-id="95da4-384">Numero civico (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-384">Street Number (required)</span></span>
- <span data-ttu-id="95da4-385">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="95da4-385">Building Complement</span></span>
- <span data-ttu-id="95da4-386">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-386">City (required)</span></span>
- <span data-ttu-id="95da4-387">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-387">State (required)</span></span>
- <span data-ttu-id="95da4-388">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-388">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="95da4-389">Configurare i dati per generare le retribuzioni negli Stati Uniti e in Canada</span><span class="sxs-lookup"><span data-stu-id="95da4-389">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="95da4-390">Se si desidera generare la retribuzione per i dipendenti negli Stati Uniti e in Canada, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="95da4-390">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="95da4-391">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="95da4-391">Departments are required on positions.</span></span>
- <span data-ttu-id="95da4-392">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="95da4-392">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="95da4-393">È possibile configurare Human Resources per far sì che Posizioni specifichi un reparto.</span><span class="sxs-lookup"><span data-stu-id="95da4-393">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="95da4-394">A tale scopo, andare a **Posizioni condivise Risorse umane > Posizioni > Richiedi reparti su posizioni**.</span><span class="sxs-lookup"><span data-stu-id="95da4-394">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="95da4-395">Si consiglia di applicare questa impostazione per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="95da4-395">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="95da4-396">Tipi di lavoro</span><span class="sxs-lookup"><span data-stu-id="95da4-396">Job types</span></span>

<span data-ttu-id="95da4-397">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="95da4-397">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="95da4-398">I tipi di mansione sono necessari per elaborare le retribuzioni negli Stati Uniti e in Canada.</span><span class="sxs-lookup"><span data-stu-id="95da4-398">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="95da4-399">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="95da4-399">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="95da4-400">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="95da4-400">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="95da4-401">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="95da4-401">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="95da4-402">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="95da4-402">Job type</span></span>   | <span data-ttu-id="95da4-403">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95da4-403">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="95da4-404">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="95da4-404">Hourly</span></span>     | <span data-ttu-id="95da4-405">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="95da4-405">Hourly</span></span>      |
| <span data-ttu-id="95da4-406">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="95da4-406">Salaried</span></span>   | <span data-ttu-id="95da4-407">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="95da4-407">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="95da4-408">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="95da4-408">Position types</span></span> 

<span data-ttu-id="95da4-409">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="95da4-409">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="95da4-410">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="95da4-410">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="95da4-411">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="95da4-411">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="95da4-412">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="95da4-412">Position type</span></span>   | <span data-ttu-id="95da4-413">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95da4-413">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="95da4-414">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="95da4-414">Full-time</span></span>       | <span data-ttu-id="95da4-415">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="95da4-415">Full time employee</span></span> |
| <span data-ttu-id="95da4-416">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="95da4-416">Part-time</span></span>       | <span data-ttu-id="95da4-417">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="95da4-417">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="95da4-418">Codici causale</span><span class="sxs-lookup"><span data-stu-id="95da4-418">Reason codes</span></span>

<span data-ttu-id="95da4-419">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="95da4-419">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="95da4-420">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="95da4-420">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="95da4-421">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="95da4-421">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="95da4-422">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="95da4-422">Reason code</span></span>    | <span data-ttu-id="95da4-423">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95da4-423">Description</span></span>      | <span data-ttu-id="95da4-424">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="95da4-424">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="95da4-425">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="95da4-425">RESIGNATION</span></span>    | <span data-ttu-id="95da4-426">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="95da4-426">Resignation</span></span>      | <span data-ttu-id="95da4-427">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-427">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-428">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="95da4-428">TERMINATION</span></span>    | <span data-ttu-id="95da4-429">Fine</span><span class="sxs-lookup"><span data-stu-id="95da4-429">Termination</span></span>      | <span data-ttu-id="95da4-430">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-430">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-431">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="95da4-431">RETIREMENT</span></span>     | <span data-ttu-id="95da4-432">Pensione</span><span class="sxs-lookup"><span data-stu-id="95da4-432">Retirement</span></span>       | <span data-ttu-id="95da4-433">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-433">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-434">OTHER</span><span class="sxs-lookup"><span data-stu-id="95da4-434">OTHER</span></span>          | <span data-ttu-id="95da4-435">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="95da4-435">Other Reasons</span></span>    | <span data-ttu-id="95da4-436">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-436">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-437">DEATH</span><span class="sxs-lookup"><span data-stu-id="95da4-437">DEATH</span></span>          | <span data-ttu-id="95da4-438">Decesso</span><span class="sxs-lookup"><span data-stu-id="95da4-438">Death</span></span>            | <span data-ttu-id="95da4-439">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-439">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-440">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="95da4-440">LEAVEOFABSENCE</span></span> | <span data-ttu-id="95da4-441">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="95da4-441">Leave of Absence</span></span> | <span data-ttu-id="95da4-442">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-442">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-443">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="95da4-443">CONTRACTEND</span></span>    | <span data-ttu-id="95da4-444">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="95da4-444">End of Contract</span></span>  | <span data-ttu-id="95da4-445">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-445">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-446">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="95da4-446">SALARYCHANGE</span></span>   | <span data-ttu-id="95da4-447">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="95da4-447">Change of Salary</span></span> | <span data-ttu-id="95da4-448">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="95da4-448">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="95da4-449">Stato civile</span><span class="sxs-lookup"><span data-stu-id="95da4-449">Marital status</span></span>

<span data-ttu-id="95da4-450">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="95da4-450">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="95da4-451">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95da4-451">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="95da4-452">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="95da4-452">Human Resources</span></span>                 | <span data-ttu-id="95da4-453">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95da4-453">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="95da4-454">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="95da4-454">Married</span></span>                | <span data-ttu-id="95da4-455">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="95da4-455">Married</span></span>              |
| <span data-ttu-id="95da4-456">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="95da4-456">Single</span></span>                 | <span data-ttu-id="95da4-457">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="95da4-457">Single</span></span>               |
| <span data-ttu-id="95da4-458">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="95da4-458">Widowed</span></span>                | <span data-ttu-id="95da4-459">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="95da4-459">Widowed</span></span>              |
| <span data-ttu-id="95da4-460">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="95da4-460">Divorced</span></span>               | <span data-ttu-id="95da4-461">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="95da4-461">Divorced</span></span>             |
| <span data-ttu-id="95da4-462">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="95da4-462">Registered Partnership</span></span> | <span data-ttu-id="95da4-463">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="95da4-463">Domestic Partnership</span></span> |
| <span data-ttu-id="95da4-464">Nessuna</span><span class="sxs-lookup"><span data-stu-id="95da4-464">None</span></span>                   | <span data-ttu-id="95da4-465">Nessuna</span><span class="sxs-lookup"><span data-stu-id="95da4-465">None</span></span>                 |
| <span data-ttu-id="95da4-466">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="95da4-466">Cohabiting</span></span>             | <span data-ttu-id="95da4-467">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="95da4-467">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="95da4-468">Genere</span><span class="sxs-lookup"><span data-stu-id="95da4-468">Gender</span></span>

<span data-ttu-id="95da4-469">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="95da4-469">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="95da4-470">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95da4-470">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="95da4-471">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="95da4-471">Human Resources</span></span>       | <span data-ttu-id="95da4-472">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95da4-472">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="95da4-473">Maschio</span><span class="sxs-lookup"><span data-stu-id="95da4-473">Male</span></span>         | <span data-ttu-id="95da4-474">Maschio</span><span class="sxs-lookup"><span data-stu-id="95da4-474">Male</span></span>            |
| <span data-ttu-id="95da4-475">Femmina</span><span class="sxs-lookup"><span data-stu-id="95da4-475">Female</span></span>       | <span data-ttu-id="95da4-476">Femmina</span><span class="sxs-lookup"><span data-stu-id="95da4-476">Female</span></span>          |
| <span data-ttu-id="95da4-477">Non specifico</span><span class="sxs-lookup"><span data-stu-id="95da4-477">Non-specific</span></span> | <span data-ttu-id="95da4-478">*Non supportato*</span><span class="sxs-lookup"><span data-stu-id="95da4-478">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="95da4-479">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="95da4-479">Earning codes</span></span>

<span data-ttu-id="95da4-480">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="95da4-480">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="95da4-481">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="95da4-481">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="95da4-482">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="95da4-482">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="95da4-483">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="95da4-483">Supported frequencies</span></span>

- <span data-ttu-id="95da4-484">Tutti</span><span class="sxs-lookup"><span data-stu-id="95da4-484">All</span></span>
- <span data-ttu-id="95da4-485">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="95da4-485">EVERYPAY</span></span>
- <span data-ttu-id="95da4-486">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="95da4-486">EACHPAYPERIOD</span></span>
- <span data-ttu-id="95da4-487">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="95da4-487">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="95da4-488">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="95da4-488">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="95da4-489">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-489">1OFMTH</span></span>
- <span data-ttu-id="95da4-490">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-490">LASTOFMTH</span></span>
- <span data-ttu-id="95da4-491">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-491">2OFMTH</span></span>
- <span data-ttu-id="95da4-492">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-492">3OFMTH</span></span>
- <span data-ttu-id="95da4-493">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-493">4OFMTH</span></span>
- <span data-ttu-id="95da4-494">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-494">5OFMTH</span></span>
- <span data-ttu-id="95da4-495">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-495">1N2OFMTH</span></span>
- <span data-ttu-id="95da4-496">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-496">3N4OFMTH</span></span>
- <span data-ttu-id="95da4-497">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-497">1N3OFMTH</span></span>
- <span data-ttu-id="95da4-498">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-498">1N4OFMTH</span></span>
- <span data-ttu-id="95da4-499">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-499">2N3OFMTH</span></span>
- <span data-ttu-id="95da4-500">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-500">2N4OFMTH</span></span>
- <span data-ttu-id="95da4-501">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-501">1N2N3OFMTH</span></span>
- <span data-ttu-id="95da4-502">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-502">1N2N4OFMTH</span></span>
- <span data-ttu-id="95da4-503">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-503">1N3N4OFMTH</span></span>
- <span data-ttu-id="95da4-504">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-504">2N3N4OFMTH</span></span>
- <span data-ttu-id="95da4-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="95da4-506">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="95da4-506">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="95da4-507">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="95da4-507">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="95da4-508">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="95da4-508">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="95da4-509">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="95da4-509">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="95da4-510">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="95da4-510">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="95da4-511">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="95da4-511">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="95da4-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="95da4-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="95da4-513">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="95da4-513">Addresses</span></span>

<span data-ttu-id="95da4-514">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="95da4-514">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="95da4-515">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="95da4-515">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="95da4-516">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="95da4-516">Human Resources</span></span>          | <span data-ttu-id="95da4-517">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95da4-517">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="95da4-518">Paese/area geografica</span><span class="sxs-lookup"><span data-stu-id="95da4-518">Country/Region</span></span>  | <span data-ttu-id="95da4-519">Codice paese</span><span class="sxs-lookup"><span data-stu-id="95da4-519">Country Code</span></span>          |
| <span data-ttu-id="95da4-520">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="95da4-520">Zip/Postal Code</span></span> | <span data-ttu-id="95da4-521">CAP</span><span class="sxs-lookup"><span data-stu-id="95da4-521">Postal Code</span></span>           |
| <span data-ttu-id="95da4-522">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="95da4-522">State</span></span>           | <span data-ttu-id="95da4-523">Codice stato</span><span class="sxs-lookup"><span data-stu-id="95da4-523">State Code</span></span>            |
| <span data-ttu-id="95da4-524">Città</span><span class="sxs-lookup"><span data-stu-id="95da4-524">City</span></span>            | <span data-ttu-id="95da4-525">Città</span><span class="sxs-lookup"><span data-stu-id="95da4-525">City</span></span>                  |
| <span data-ttu-id="95da4-526">Regione</span><span class="sxs-lookup"><span data-stu-id="95da4-526">County</span></span>          | <span data-ttu-id="95da4-527">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="95da4-527">County (Municipality)</span></span> |
| <span data-ttu-id="95da4-528">Via</span><span class="sxs-lookup"><span data-stu-id="95da4-528">Street</span></span>          | <span data-ttu-id="95da4-529">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="95da4-529">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="95da4-530">Regioni fiscali</span><span class="sxs-lookup"><span data-stu-id="95da4-530">Tax regions</span></span>

<span data-ttu-id="95da4-531">Le regioni fiscali vengono utilizzate per determinare l'imposta appropriata che deve essere applicata durante la generazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="95da4-531">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="95da4-532">Le regioni fiscali vengono mappate in Dayforce come indirizzi di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="95da4-532">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="95da4-533">La regione fiscale predefinita deve essere associata alla posizione attiva del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="95da4-533">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="95da4-534">Regione fiscale (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-534">Tax region (required)</span></span>
- <span data-ttu-id="95da4-535">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-535">Country/Region (required)</span></span>
- <span data-ttu-id="95da4-536">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="95da4-536">State (required)</span></span>
- <span data-ttu-id="95da4-537">Regione</span><span class="sxs-lookup"><span data-stu-id="95da4-537">County</span></span> 
- <span data-ttu-id="95da4-538">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="95da4-538">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="95da4-539">Configurare i dati per generare le retribuzioni in Messico</span><span class="sxs-lookup"><span data-stu-id="95da4-539">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="95da4-540">Se si desidera generare la retribuzione per i dipendenti in Messico, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="95da4-540">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="95da4-541">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="95da4-541">Departments are required on positions.</span></span>
- <span data-ttu-id="95da4-542">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="95da4-542">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="95da4-543">Tipi di posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="95da4-543">Job types</span></span>

<span data-ttu-id="95da4-544">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="95da4-544">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="95da4-545">Tipi di mansione necessari per elaborare le retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="95da4-545">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="95da4-546">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="95da4-546">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="95da4-547">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="95da4-547">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="95da4-548">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="95da4-548">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="95da4-549">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="95da4-549">Job type</span></span>   | <span data-ttu-id="95da4-550">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95da4-550">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="95da4-551">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="95da4-551">Hourly</span></span>     | <span data-ttu-id="95da4-552">Su base oraria MX</span><span class="sxs-lookup"><span data-stu-id="95da4-552">MX Hourly</span></span>   |
| <span data-ttu-id="95da4-553">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="95da4-553">Salaried</span></span>   | <span data-ttu-id="95da4-554">Stipendiato MX</span><span class="sxs-lookup"><span data-stu-id="95da4-554">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="95da4-555">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="95da4-555">Position types</span></span> 

<span data-ttu-id="95da4-556">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="95da4-556">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="95da4-557">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="95da4-557">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="95da4-558">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="95da4-558">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="95da4-559">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="95da4-559">Position type</span></span>   | <span data-ttu-id="95da4-560">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95da4-560">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="95da4-561">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="95da4-561">Full-time</span></span>       | <span data-ttu-id="95da4-562">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="95da4-562">Full time employee</span></span> |
| <span data-ttu-id="95da4-563">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="95da4-563">Part-time</span></span>       | <span data-ttu-id="95da4-564">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="95da4-564">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="95da4-565">Codici causale</span><span class="sxs-lookup"><span data-stu-id="95da4-565">Reason codes</span></span>

<span data-ttu-id="95da4-566">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="95da4-566">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="95da4-567">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="95da4-567">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="95da4-568">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="95da4-568">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="95da4-569">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="95da4-569">Reason code</span></span>            | <span data-ttu-id="95da4-570">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95da4-570">Description</span></span>                    | <span data-ttu-id="95da4-571">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="95da4-571">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="95da4-572">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="95da4-572">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="95da4-573">Partenza prima della prima retribuzione</span><span class="sxs-lookup"><span data-stu-id="95da4-573">Departure before first payroll</span></span> | <span data-ttu-id="95da4-574">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-574">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-575">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="95da4-575">RESIGNATION</span></span>            | <span data-ttu-id="95da4-576">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="95da4-576">Resignation</span></span>                    | <span data-ttu-id="95da4-577">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-577">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-578">PENSION</span><span class="sxs-lookup"><span data-stu-id="95da4-578">PENSION</span></span>                | <span data-ttu-id="95da4-579">Pensionamento</span><span class="sxs-lookup"><span data-stu-id="95da4-579">Pension</span></span>                        | <span data-ttu-id="95da4-580">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-580">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-581">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="95da4-581">TERMINATION</span></span>            | <span data-ttu-id="95da4-582">Fine</span><span class="sxs-lookup"><span data-stu-id="95da4-582">Termination</span></span>                    | <span data-ttu-id="95da4-583">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-583">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-584">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="95da4-584">RETIREMENT</span></span>             | <span data-ttu-id="95da4-585">Pensione</span><span class="sxs-lookup"><span data-stu-id="95da4-585">Retirement</span></span>                     | <span data-ttu-id="95da4-586">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-586">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-587">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="95da4-587">ABSENTEE</span></span>               | <span data-ttu-id="95da4-588">Assente</span><span class="sxs-lookup"><span data-stu-id="95da4-588">Absentee</span></span>                       | <span data-ttu-id="95da4-589">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-589">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-590">OTHER</span><span class="sxs-lookup"><span data-stu-id="95da4-590">OTHER</span></span>                  | <span data-ttu-id="95da4-591">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="95da4-591">Other Reasons</span></span>                  | <span data-ttu-id="95da4-592">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-592">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-593">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="95da4-593">CLOSURE</span></span>                | <span data-ttu-id="95da4-594">Chiusura attività</span><span class="sxs-lookup"><span data-stu-id="95da4-594">Business Closure</span></span>               | <span data-ttu-id="95da4-595">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-595">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-596">DEATH</span><span class="sxs-lookup"><span data-stu-id="95da4-596">DEATH</span></span>                  | <span data-ttu-id="95da4-597">Decesso</span><span class="sxs-lookup"><span data-stu-id="95da4-597">Death</span></span>                          | <span data-ttu-id="95da4-598">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-598">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-599">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="95da4-599">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="95da4-600">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="95da4-600">Leave of Absence</span></span>               | <span data-ttu-id="95da4-601">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-601">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-602">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="95da4-602">CONTRACTEND</span></span>            | <span data-ttu-id="95da4-603">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="95da4-603">End of Contract</span></span>                | <span data-ttu-id="95da4-604">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="95da4-604">Terminate worker</span></span>     |
| <span data-ttu-id="95da4-605">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="95da4-605">SALARYCHANGE</span></span>           | <span data-ttu-id="95da4-606">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="95da4-606">Change of Salary</span></span>               | <span data-ttu-id="95da4-607">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="95da4-607">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="95da4-608">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="95da4-608">Terms of employment</span></span>

<span data-ttu-id="95da4-609">Le condizioni di impiego vengono utilizzate per creare categorie di termini di impiego.</span><span class="sxs-lookup"><span data-stu-id="95da4-609">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="95da4-610">I termini vengono mappati in Dayforce come valori degli indicatori di impiego.</span><span class="sxs-lookup"><span data-stu-id="95da4-610">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="95da4-611">I seguenti termini di impiego e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="95da4-611">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="95da4-612">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="95da4-612">Terms of employment</span></span>   | <span data-ttu-id="95da4-613">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95da4-613">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="95da4-614">Regolare</span><span class="sxs-lookup"><span data-stu-id="95da4-614">Regular</span></span>               | <span data-ttu-id="95da4-615">Regolare</span><span class="sxs-lookup"><span data-stu-id="95da4-615">Regular</span></span>     |
| <span data-ttu-id="95da4-616">Diretto</span><span class="sxs-lookup"><span data-stu-id="95da4-616">Direct</span></span>                | <span data-ttu-id="95da4-617">Diretto</span><span class="sxs-lookup"><span data-stu-id="95da4-617">Direct</span></span>      |
| <span data-ttu-id="95da4-618">Internato</span><span class="sxs-lookup"><span data-stu-id="95da4-618">Internship</span></span>            | <span data-ttu-id="95da4-619">Internato</span><span class="sxs-lookup"><span data-stu-id="95da4-619">Internship</span></span>  |
| <span data-ttu-id="95da4-620">Permanente</span><span class="sxs-lookup"><span data-stu-id="95da4-620">Permanent</span></span>             | <span data-ttu-id="95da4-621">Permanente</span><span class="sxs-lookup"><span data-stu-id="95da4-621">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="95da4-622">Stato civile</span><span class="sxs-lookup"><span data-stu-id="95da4-622">Marital status</span></span>

<span data-ttu-id="95da4-623">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="95da4-623">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="95da4-624">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95da4-624">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="95da4-625">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="95da4-625">Human Resources</span></span>                 | <span data-ttu-id="95da4-626">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95da4-626">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="95da4-627">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="95da4-627">Married</span></span>                | <span data-ttu-id="95da4-628">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="95da4-628">Married</span></span>                   |
| <span data-ttu-id="95da4-629">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="95da4-629">Single</span></span>                 | <span data-ttu-id="95da4-630">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="95da4-630">Single</span></span>                    |
| <span data-ttu-id="95da4-631">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="95da4-631">Widowed</span></span>                | <span data-ttu-id="95da4-632">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="95da4-632">Widowed</span></span>                   |
| <span data-ttu-id="95da4-633">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="95da4-633">Divorced</span></span>               | <span data-ttu-id="95da4-634">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="95da4-634">Divorced</span></span>                  |
| <span data-ttu-id="95da4-635">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="95da4-635">Registered Partnership</span></span> | <span data-ttu-id="95da4-636">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="95da4-636">Domestic Partnership</span></span>      |
| <span data-ttu-id="95da4-637">Nessuna</span><span class="sxs-lookup"><span data-stu-id="95da4-637">None</span></span>                   | <span data-ttu-id="95da4-638">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="95da4-638">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="95da4-639">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="95da4-639">Cohabiting</span></span>             | <span data-ttu-id="95da4-640">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="95da4-640">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="95da4-641">Genere</span><span class="sxs-lookup"><span data-stu-id="95da4-641">Gender</span></span>

<span data-ttu-id="95da4-642">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="95da4-642">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="95da4-643">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95da4-643">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="95da4-644">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="95da4-644">Human Resources</span></span>       | <span data-ttu-id="95da4-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95da4-645">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="95da4-646">Maschio</span><span class="sxs-lookup"><span data-stu-id="95da4-646">Male</span></span>         | <span data-ttu-id="95da4-647">Maschio</span><span class="sxs-lookup"><span data-stu-id="95da4-647">Male</span></span>                      |
| <span data-ttu-id="95da4-648">Femmina</span><span class="sxs-lookup"><span data-stu-id="95da4-648">Female</span></span>       | <span data-ttu-id="95da4-649">Femmina</span><span class="sxs-lookup"><span data-stu-id="95da4-649">Female</span></span>                    |
| <span data-ttu-id="95da4-650">Non specifico</span><span class="sxs-lookup"><span data-stu-id="95da4-650">Non-specific</span></span> | <span data-ttu-id="95da4-651">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="95da4-651">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="95da4-652">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="95da4-652">Payment method</span></span>

<span data-ttu-id="95da4-653">I metodi di pagamento offrono al dipendente e all'azienda un modo per descrivere la modalità di pagamento dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="95da4-653">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="95da4-654">I metodi di pagamento vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="95da4-654">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="95da4-655">Nella tabella seguente vengono illustrati in che modo i metodi di pagamento vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95da4-655">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="95da4-656">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="95da4-656">Human Resources</span></span>             | <span data-ttu-id="95da4-657">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95da4-657">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="95da4-658">Contanti</span><span class="sxs-lookup"><span data-stu-id="95da4-658">Cash</span></span>               | <span data-ttu-id="95da4-659">Contanti</span><span class="sxs-lookup"><span data-stu-id="95da4-659">Cash</span></span>                      |
| <span data-ttu-id="95da4-660">Pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="95da4-660">Electronic Payment</span></span> | <span data-ttu-id="95da4-661">Trasferimenti</span><span class="sxs-lookup"><span data-stu-id="95da4-661">Transfer</span></span>                  |
| <span data-ttu-id="95da4-662">Seleziona</span><span class="sxs-lookup"><span data-stu-id="95da4-662">Check</span></span>              | <span data-ttu-id="95da4-663">Assegno</span><span class="sxs-lookup"><span data-stu-id="95da4-663">Cheque</span></span>                    |
| <span data-ttu-id="95da4-664">Assegno circolare</span><span class="sxs-lookup"><span data-stu-id="95da4-664">Bank Draft</span></span>         | <span data-ttu-id="95da4-665">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="95da4-665">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="95da4-666">Altro</span><span class="sxs-lookup"><span data-stu-id="95da4-666">Other</span></span>              | <span data-ttu-id="95da4-667">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="95da4-667">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="95da4-668">Tipo di conto bancario</span><span class="sxs-lookup"><span data-stu-id="95da4-668">Bank account type</span></span>

<span data-ttu-id="95da4-669">I tipi di conto bancario vengono utilizzati per i pagamenti elettronici ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="95da4-669">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="95da4-670">I tipi di conto bancario vengono mappati in Dayforce come informazioni sul conto di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="95da4-670">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="95da4-671">I tipi di conto bancario vengono convertiti, come appropriato, nei valori accettati per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="95da4-671">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="95da4-672">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="95da4-672">Human Resources</span></span>            | <span data-ttu-id="95da4-673">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95da4-673">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="95da4-674">Conto corrente</span><span class="sxs-lookup"><span data-stu-id="95da4-674">Checking Account</span></span>  | <span data-ttu-id="95da4-675">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="95da4-675">CheckingAccount</span></span>           |
| <span data-ttu-id="95da4-676">Conto retribuzioni</span><span class="sxs-lookup"><span data-stu-id="95da4-676">Payroll Account</span></span>   | <span data-ttu-id="95da4-677">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="95da4-677">PayrollAccount</span></span>            |
| <span data-ttu-id="95da4-678">Conto di risparmio</span><span class="sxs-lookup"><span data-stu-id="95da4-678">Savings Account</span></span>   | <span data-ttu-id="95da4-679">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="95da4-679">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="95da4-680">Conto Bankgirot</span><span class="sxs-lookup"><span data-stu-id="95da4-680">BankGirot account</span></span> | <span data-ttu-id="95da4-681">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="95da4-681">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="95da4-682">Conto PlusGirot</span><span class="sxs-lookup"><span data-stu-id="95da4-682">PlusGirot account</span></span> | <span data-ttu-id="95da4-683">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="95da4-683">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="95da4-684">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="95da4-684">Earning codes</span></span>

<span data-ttu-id="95da4-685">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="95da4-685">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="95da4-686">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="95da4-686">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="95da4-687">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="95da4-687">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="95da4-688">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="95da4-688">Supported frequencies</span></span>

- <span data-ttu-id="95da4-689">Tutti</span><span class="sxs-lookup"><span data-stu-id="95da4-689">All</span></span>
- <span data-ttu-id="95da4-690">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="95da4-690">EVERYPAY</span></span>
- <span data-ttu-id="95da4-691">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="95da4-691">EACHPAYPERIOD</span></span>
- <span data-ttu-id="95da4-692">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="95da4-692">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="95da4-693">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="95da4-693">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="95da4-694">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-694">1OFMTH</span></span>
- <span data-ttu-id="95da4-695">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-695">LASTOFMTH</span></span>
- <span data-ttu-id="95da4-696">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-696">2OFMTH</span></span>
- <span data-ttu-id="95da4-697">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-697">3OFMTH</span></span>
- <span data-ttu-id="95da4-698">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-698">4OFMTH</span></span>
- <span data-ttu-id="95da4-699">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-699">5OFMTH</span></span>
- <span data-ttu-id="95da4-700">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-700">1N2OFMTH</span></span>
- <span data-ttu-id="95da4-701">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-701">3N4OFMTH</span></span>
- <span data-ttu-id="95da4-702">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-702">1N3OFMTH</span></span>
- <span data-ttu-id="95da4-703">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-703">1N4OFMTH</span></span>
- <span data-ttu-id="95da4-704">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-704">2N3OFMTH</span></span>
- <span data-ttu-id="95da4-705">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-705">2N4OFMTH</span></span>
- <span data-ttu-id="95da4-706">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-706">1N2N3OFMTH</span></span>
- <span data-ttu-id="95da4-707">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-707">1N2N4OFMTH</span></span>
- <span data-ttu-id="95da4-708">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-708">1N3N4OFMTH</span></span>
- <span data-ttu-id="95da4-709">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-709">2N3N4OFMTH</span></span>
- <span data-ttu-id="95da4-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95da4-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="95da4-711">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="95da4-711">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="95da4-712">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="95da4-712">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="95da4-713">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="95da4-713">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="95da4-714">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="95da4-714">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="95da4-715">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="95da4-715">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="95da4-716">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="95da4-716">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="95da4-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="95da4-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="95da4-718">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="95da4-718">Addresses</span></span>

<span data-ttu-id="95da4-719">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="95da4-719">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="95da4-720">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="95da4-720">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="95da4-721">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="95da4-721">Human Resources</span></span>              | <span data-ttu-id="95da4-722">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95da4-722">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="95da4-723">Paese/area geografica</span><span class="sxs-lookup"><span data-stu-id="95da4-723">Country/Region</span></span>      | <span data-ttu-id="95da4-724">Codice paese</span><span class="sxs-lookup"><span data-stu-id="95da4-724">Country Code</span></span>          |
| <span data-ttu-id="95da4-725">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="95da4-725">Zip/Postal Code</span></span>     | <span data-ttu-id="95da4-726">CAP</span><span class="sxs-lookup"><span data-stu-id="95da4-726">Postal Code</span></span>           |
| <span data-ttu-id="95da4-727">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="95da4-727">State</span></span>               | <span data-ttu-id="95da4-728">Codice stato</span><span class="sxs-lookup"><span data-stu-id="95da4-728">State Code</span></span>            |
| <span data-ttu-id="95da4-729">Città</span><span class="sxs-lookup"><span data-stu-id="95da4-729">City</span></span>                | <span data-ttu-id="95da4-730">Città</span><span class="sxs-lookup"><span data-stu-id="95da4-730">City</span></span>                  |
| <span data-ttu-id="95da4-731">Regione</span><span class="sxs-lookup"><span data-stu-id="95da4-731">County</span></span>              | <span data-ttu-id="95da4-732">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="95da4-732">County (Municipality)</span></span> |
| <span data-ttu-id="95da4-733">Via</span><span class="sxs-lookup"><span data-stu-id="95da4-733">Street</span></span>              | <span data-ttu-id="95da4-734">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="95da4-734">Address Line 1</span></span>        |
| <span data-ttu-id="95da4-735">Numero civico</span><span class="sxs-lookup"><span data-stu-id="95da4-735">Street Number</span></span>       | <span data-ttu-id="95da4-736">Riga indirizzo 2</span><span class="sxs-lookup"><span data-stu-id="95da4-736">Address Line 2</span></span>        |
| <span data-ttu-id="95da4-737">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="95da4-737">Building Complement</span></span> | <span data-ttu-id="95da4-738">Riga indirizzo 5</span><span class="sxs-lookup"><span data-stu-id="95da4-738">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="95da4-739">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="95da4-739">Passport number</span></span>

<span data-ttu-id="95da4-740">I dipendenti possono indicare le informazioni sul passaporto.</span><span class="sxs-lookup"><span data-stu-id="95da4-740">Employees can declare passport information.</span></span> <span data-ttu-id="95da4-741">Queste informazioni sono del tipo di identificazione **Passaporto** e vengono integrate in Dayforce come parte delle informazioni di un dipendente specifiche per il Messico.</span><span class="sxs-lookup"><span data-stu-id="95da4-741">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="95da4-742">Tipo di identificazione = "Passaporto"</span><span class="sxs-lookup"><span data-stu-id="95da4-742">Identification Type = "Passport"</span></span>
- <span data-ttu-id="95da4-743">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="95da4-743">Issued Date</span></span>
- <span data-ttu-id="95da4-744">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="95da4-744">Expiration Date</span></span>

<span data-ttu-id="95da4-745">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **Passaporto**.</span><span class="sxs-lookup"><span data-stu-id="95da4-745">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="95da4-746">Tuttavia, solo l'immissione del passaporto attivo corrente viene integrata in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95da4-746">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="95da4-747">Se tutte le immissioni di passaporto sono scadute, in Dayforce viene integrato il passaporto di emissione più recente.</span><span class="sxs-lookup"><span data-stu-id="95da4-747">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]