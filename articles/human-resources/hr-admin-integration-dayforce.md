---
title: Configurare l'integrazione con Dayforce
description: L'integrazione tra Microsoft Dynamics 365 Human Resources e Ceridian Dayforce si basa su vari passaggi di configurazione descritti in questo articolo. È necessario configurare l'integrazione sia in Human Resources che in Dayforce prima di poter elaborare un ciclo di pagamenti.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 1647b7fbf84a78051e745e918954df32a2e7e1dd
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890006"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="6f511-104">Configurare l'integrazione con Dayforce</span><span class="sxs-lookup"><span data-stu-id="6f511-104">Configure integration with Dayforce</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="6f511-105">L'integrazione tra Microsoft Dynamics 365 Human Resources e Ceridian Dayforce si basa su vari passaggi di configurazione descritti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="6f511-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="6f511-106">È necessario configurare l'integrazione sia in Human Resources che in Dayforce prima di poter elaborare un ciclo di pagamenti.</span><span class="sxs-lookup"><span data-stu-id="6f511-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="6f511-107">Quando si utilizza un servizio, ad esempio Dayforce, per completare i cicli di pagamenti, è necessario abilitare l'integrazione in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6f511-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="6f511-108">L'integrazione richiede dati specifici da Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6f511-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="6f511-109">Di conseguenza, è necessario verificare che i dati che vengono mappati a Dayforce siano configurati in Human Resources in modo che supporti l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="6f511-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="6f511-110">L'integrazione utilizza le seguenti categorie generiche di dati:</span><span class="sxs-lookup"><span data-stu-id="6f511-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="6f511-111">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6f511-111">Human resources data</span></span>
- <span data-ttu-id="6f511-112">Dati di compensazione</span><span class="sxs-lookup"><span data-stu-id="6f511-112">Compensation data</span></span>
- <span data-ttu-id="6f511-113">Data di retribuzione, ad esempio i cicli di pagamenti, i periodi retributivi e i codici reddito</span><span class="sxs-lookup"><span data-stu-id="6f511-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="6f511-114">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-114">Worker data</span></span>

<span data-ttu-id="6f511-115">In questo articolo vengono descritti i passaggi che è necessario completare per abilitare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="6f511-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="6f511-116">E vengono descritti i tipi di dati e i dettagli di configurazione necessari all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="6f511-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="6f511-117">Abilitare l'integrazione</span><span class="sxs-lookup"><span data-stu-id="6f511-117">Enable the integration</span></span>

<span data-ttu-id="6f511-118">In Human Resources è necessario attivare l'integrazione e immettere le informazioni di configurazione per connettersi a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6f511-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="6f511-119">Se si desidera che la transazione contabile prodotta venga importata in Microsoft Dynamics 365 Finance, è necessario impostare anche un conto di archiviazione di Microsoft Azure e immettere la stringa di connessione di Archiviazione di Azure in Finance.</span><span class="sxs-lookup"><span data-stu-id="6f511-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="6f511-120">Per attivare l'integrazione in Human Resources, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6f511-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="6f511-121">Nella pagina **Amministrazione sistema** selezionare **Configurazione di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="6f511-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="6f511-122">Immettere l'endpoint FTP (File Transfer Protocol) e il percorso protetto della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="6f511-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="6f511-123">Immettere il nome utente e la password dell'utente che accederà al percorso protetto dell'endpoint e della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="6f511-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="6f511-124">Verificare la connessione, secondo le esigenze, e impostare l'opzione **Abilita integrazione retribuzioni** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6f511-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="6f511-125">Quando l'integrazione viene attivata, vengono creati i file e il pacchetto di esportazione dei dati e viene impostata la frequenza.</span><span class="sxs-lookup"><span data-stu-id="6f511-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="6f511-126">È possibile cambiare la frequenza in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="6f511-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="6f511-127">Per altre informazioni sugli account di Archiviazione di Azure e sulle stringhe di connessione di Archiviazione di Azure, vedere gli articoli di Azure seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f511-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="6f511-128">Account di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="6f511-128">About Azure storage accounts</span></span>](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="6f511-129">Configurare le stringhe di connessione di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="6f511-129">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="6f511-130">Dettagli tecnici quando l'integrazione delle retribuzioni è attivata</span><span class="sxs-lookup"><span data-stu-id="6f511-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="6f511-131">L'attivazione dell'integrazione delle retribuzioni comporta due effetti primari:</span><span class="sxs-lookup"><span data-stu-id="6f511-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="6f511-132">Viene creato un progetto di esportazione di dati denominato "Esportazione integrazione delle retribuzioni".</span><span class="sxs-lookup"><span data-stu-id="6f511-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="6f511-133">Questo progetto contiene le entità e i campi necessari per l'integrazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="6f511-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="6f511-134">Per esaminare il progetto, andare a **Amministrazione sistema**, selezionare il riquadro **Gestione dati** e infine aprire il progetto dati dall'elenco di progetti.</span><span class="sxs-lookup"><span data-stu-id="6f511-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="6f511-135">Questo processo batch esegue il progetto di esportazione dei dati, codifica il pacchetto dati risultante e trasferisce il file del pacchetto dati all'endpoint SFTP configurato nella schermata **Configurazione di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="6f511-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="6f511-136">Il pacchetto dati trasferito all'endpoint SFTP viene codificato utilizzando una chiave univoca per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6f511-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="6f511-137">La chiave è un Azure Key Vault accessibile solo da Ceridian.</span><span class="sxs-lookup"><span data-stu-id="6f511-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="6f511-138">Non è possibile decrittografare ed esaminare il contenuto del pacchetto dati.</span><span class="sxs-lookup"><span data-stu-id="6f511-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="6f511-139">Se è necessario esaminare il contenuto del pacchetto dati, esportare manualmente il progetto dati "Esportazione integrazione delle retribuzioni", scaricarlo e quindi aprirlo.</span><span class="sxs-lookup"><span data-stu-id="6f511-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="6f511-140">L'esportazione manuale non comporta la crittografia o il trasferimento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6f511-140">Manual export will not apply encryption or transfer the package.</span></span>
> <span data-ttu-id="6f511-141">Per le istanze in cui i file di integrazione vengono inviati da un ambiente Sandbox o UAT di Dynamics 365 Human Resources a un ambiente Ceridian Dayforce Test, è possibile utilizzare il seguente URL dell'insieme di credenziali delle chiavi: https://payrollintegrationprod.vault.azure.net.</span><span class="sxs-lookup"><span data-stu-id="6f511-141">For instances where the integration files are sent from a Dynamics 365 Human Resources UAT or Sandbox environment to a Ceridian Dayforce Test environment, you can use the following key vault URL: https://payrollintegrationprod.vault.azure.net.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="6f511-142">Configurare i dati</span><span class="sxs-lookup"><span data-stu-id="6f511-142">Configure your data</span></span> 

<span data-ttu-id="6f511-143">Per elaborare le retribuzioni, è necessario configurare i dati di Risorse umane in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6f511-143">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="6f511-144">È necessario impostare i dati dell'organizzazione, ad esempio mansioni e posizioni, insieme alle informazioni sui benefit e sulle compensazioni.</span><span class="sxs-lookup"><span data-stu-id="6f511-144">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="6f511-145">Queste informazioni includono informazioni sull'impiego, la retribuzione e le detrazioni che sono richieste per generare la retribuzione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="6f511-145">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="6f511-146">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6f511-146">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="6f511-147">Benefit</span><span class="sxs-lookup"><span data-stu-id="6f511-147">Benefits</span></span> 

<span data-ttu-id="6f511-148">Le risorse umane dispongono di strumenti per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori.</span><span class="sxs-lookup"><span data-stu-id="6f511-148">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="6f511-149">Quando si creano i benefit, tenere presenti i seguenti dati e configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6f511-149">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="6f511-150">Piani di benefit</span><span class="sxs-lookup"><span data-stu-id="6f511-150">Benefit plans</span></span>

- <span data-ttu-id="6f511-151">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-151">Plan (required)</span></span>
- <span data-ttu-id="6f511-152">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-152">Type (required)</span></span>
- <span data-ttu-id="6f511-153">Impatto retribuzioni (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-153">Payroll impact (required)</span></span>
- <span data-ttu-id="6f511-154">Recupera arretrati</span><span class="sxs-lookup"><span data-stu-id="6f511-154">Recover arrears</span></span>
- <span data-ttu-id="6f511-155">Metodo di detrazione</span><span class="sxs-lookup"><span data-stu-id="6f511-155">Deduction method</span></span>
- <span data-ttu-id="6f511-156">Priorità detrazione</span><span class="sxs-lookup"><span data-stu-id="6f511-156">Deduction priority</span></span>
- <span data-ttu-id="6f511-157">Periodo limite</span><span class="sxs-lookup"><span data-stu-id="6f511-157">Limit period</span></span>
- <span data-ttu-id="6f511-158">Importo limite</span><span class="sxs-lookup"><span data-stu-id="6f511-158">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="6f511-159">Benefit</span><span class="sxs-lookup"><span data-stu-id="6f511-159">Benefits</span></span>

- <span data-ttu-id="6f511-160">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-160">Plan (required)</span></span>
- <span data-ttu-id="6f511-161">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-161">Type (required)</span></span>
- <span data-ttu-id="6f511-162">Opzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-162">Option (required)</span></span>
- <span data-ttu-id="6f511-163">ID benefit (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-163">Benefit ID (required)</span></span>
- <span data-ttu-id="6f511-164">Frequenza</span><span class="sxs-lookup"><span data-stu-id="6f511-164">Frequency</span></span>
- <span data-ttu-id="6f511-165">Base</span><span class="sxs-lookup"><span data-stu-id="6f511-165">Basis</span></span>
- <span data-ttu-id="6f511-166">Importo o coefficiente</span><span class="sxs-lookup"><span data-stu-id="6f511-166">Amount or rate</span></span>
- <span data-ttu-id="6f511-167">Codice di reddito</span><span class="sxs-lookup"><span data-stu-id="6f511-167">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="6f511-168">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="6f511-168">Supported frequencies</span></span> 

- <span data-ttu-id="6f511-169">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="6f511-169">Weekly</span></span>
- <span data-ttu-id="6f511-170">Bisettimanale</span><span class="sxs-lookup"><span data-stu-id="6f511-170">Bi-weekly</span></span>
- <span data-ttu-id="6f511-171">Quindicinale</span><span class="sxs-lookup"><span data-stu-id="6f511-171">Semi-monthly</span></span>
- <span data-ttu-id="6f511-172">Ogni mese</span><span class="sxs-lookup"><span data-stu-id="6f511-172">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="6f511-173">Basi supportate</span><span class="sxs-lookup"><span data-stu-id="6f511-173">Supported bases</span></span> 

- <span data-ttu-id="6f511-174">Importo fisso</span><span class="sxs-lookup"><span data-stu-id="6f511-174">Fixed amount</span></span>
- <span data-ttu-id="6f511-175">Percentuale di redditi</span><span class="sxs-lookup"><span data-stu-id="6f511-175">Percent of earnings</span></span>
- <span data-ttu-id="6f511-176">Ore di produzione</span><span class="sxs-lookup"><span data-stu-id="6f511-176">Productive hours</span></span>

<span data-ttu-id="6f511-177">Dayforce crea le seguenti detrazioni, in base all'impatto delle retribuzioni definito nel piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="6f511-177">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="6f511-178">Selezione in Human Resources</span><span class="sxs-lookup"><span data-stu-id="6f511-178">Selection in Human Resources</span></span>        | <span data-ttu-id="6f511-179">Risultato in Dayforce</span><span class="sxs-lookup"><span data-stu-id="6f511-179">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="6f511-180">Nessuna</span><span class="sxs-lookup"><span data-stu-id="6f511-180">None</span></span>                       | <span data-ttu-id="6f511-181">Non viene creata alcuna detrazione.</span><span class="sxs-lookup"><span data-stu-id="6f511-181">No deduction is created.</span></span>                      |
| <span data-ttu-id="6f511-182">Solo detrazione</span><span class="sxs-lookup"><span data-stu-id="6f511-182">Deduction only</span></span>             | <span data-ttu-id="6f511-183">Viene creata una detrazione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="6f511-183">An employee deduction is created.</span></span>             |
| <span data-ttu-id="6f511-184">Solo contribuzione</span><span class="sxs-lookup"><span data-stu-id="6f511-184">Contribution only</span></span>          | <span data-ttu-id="6f511-185">Viene creata una detrazione del datore di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6f511-185">An employer deduction is created.</span></span>             |
| <span data-ttu-id="6f511-186">Detrazione e contribuzione</span><span class="sxs-lookup"><span data-stu-id="6f511-186">Deduction and contribution</span></span> | <span data-ttu-id="6f511-187">Vengono create detrazioni del datore di lavoro e del dipendente.</span><span class="sxs-lookup"><span data-stu-id="6f511-187">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="6f511-188">Per altre informazioni su come definire e gestire un programma di benefit, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f511-188">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="6f511-189">Realizzare un programma di benefit per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="6f511-189">Deliver an employee benefits program</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="6f511-190">Crea un nuovo benefit</span><span class="sxs-lookup"><span data-stu-id="6f511-190">Create a new benefit</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="6f511-191">Definire regole e criteri di idoneità ai benefit</span><span class="sxs-lookup"><span data-stu-id="6f511-191">Define benefit eligibility rules and policies</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="6f511-192">Iscrivere e rimuovere benefit da lavoratori</span><span class="sxs-lookup"><span data-stu-id="6f511-192">Enroll and remove benefits from workers</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="6f511-193">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="6f511-193">Compensation</span></span> 

<span data-ttu-id="6f511-194">La gestione delle retribuzioni consente di controllare la liquidazione dei premi e della retribuzione base.</span><span class="sxs-lookup"><span data-stu-id="6f511-194">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="6f511-195">La retribuzione di base fissa di un dipendente e gli aumenti per merito sono controllati mediante piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="6f511-195">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="6f511-196">È possibile controllare il pagamento degli incentivi, ad esempio il pagamento dei bonus, dei premi produttività, dei diritti di opzione, delle sovvenzioni, oltre che dei premi una tantum, tramite i piani di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="6f511-196">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="6f511-197">Dayforce utilizza le informazioni sulla compensazione per calcolare la retribuzione annuale o oraria di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="6f511-197">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="6f511-198">I piani di retribuzione fissa e conversioni della retribuzione sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="6f511-198">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="6f511-199">I dipendenti devono essere associati a un piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="6f511-199">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="6f511-200">Per ulteriori informazioni sui piani di retribuzione, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f511-200">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="6f511-201">Creare piani di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="6f511-201">Create fixed compensation plans</span></span>](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="6f511-202">Creare piani di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="6f511-202">Create variable compensation plans</span></span>](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="6f511-203">Sviluppare una struttura e piani di stipendi/retribuzioni</span><span class="sxs-lookup"><span data-stu-id="6f511-203">Develop salary/compensation structure and plans</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="6f511-204">Processo retributivo</span><span class="sxs-lookup"><span data-stu-id="6f511-204">Process compensation</span></span>](/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="6f511-205">Definire il processo retributivo e calcolare i risultati</span><span class="sxs-lookup"><span data-stu-id="6f511-205">Define compensation process and calculate results</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="6f511-206">Iscrivere un dipendente a un piano di retribuzione fisso</span><span class="sxs-lookup"><span data-stu-id="6f511-206">Enroll an employee in a fixed compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="6f511-207">Iscrivere un dipendente a un piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="6f511-207">Enroll an employee in a variable compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="6f511-208">Mansioni</span><span class="sxs-lookup"><span data-stu-id="6f511-208">Jobs</span></span> 

<span data-ttu-id="6f511-209">Una mansione è una raccolta delle attività e delle responsabilità proprie della persona assegnata a una mansione.</span><span class="sxs-lookup"><span data-stu-id="6f511-209">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="6f511-210">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f511-210">For more information, see the following articles:</span></span>

- [<span data-ttu-id="6f511-211">Impostazione dei componenti di una mansione</span><span class="sxs-lookup"><span data-stu-id="6f511-211">Setting up the components of a job</span></span>](/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="6f511-212">Definire nuovi processi</span><span class="sxs-lookup"><span data-stu-id="6f511-212">Define new jobs</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="6f511-213">Posizioni</span><span class="sxs-lookup"><span data-stu-id="6f511-213">Positions</span></span>

<span data-ttu-id="6f511-214">Una posizione è una singola istanza di un processo.</span><span class="sxs-lookup"><span data-stu-id="6f511-214">A position is an individual instance of a job.</span></span> <span data-ttu-id="6f511-215">Ad esempio, la posizione "Manager vendite (Est") è una delle posizioni associate alla mansione "Manager vendite".</span><span class="sxs-lookup"><span data-stu-id="6f511-215">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="6f511-216">Una posizione è presente in un reparto.</span><span class="sxs-lookup"><span data-stu-id="6f511-216">A position exists in a department.</span></span> <span data-ttu-id="6f511-217">È possibile associare un solo lavoratore a ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="6f511-217">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="6f511-218">Tenere a mente i seguenti dati e la configurazione quando si impostano le posizioni:</span><span class="sxs-lookup"><span data-stu-id="6f511-218">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="6f511-219">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-219">Position (required)</span></span>
- <span data-ttu-id="6f511-220">Descrizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-220">Description (required)</span></span>
- <span data-ttu-id="6f511-221">Mansione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-221">Job (required)</span></span>
- <span data-ttu-id="6f511-222">Reparto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-222">Department (required)</span></span>
- <span data-ttu-id="6f511-223">Tipo di posizione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-223">Position type (required)</span></span>
- <span data-ttu-id="6f511-224">Equivalente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="6f511-224">Full-time equivalent</span></span>
- <span data-ttu-id="6f511-225">Ore regolari annuali (obbligatorie)</span><span class="sxs-lookup"><span data-stu-id="6f511-225">Annual regular hours (required)</span></span>
- <span data-ttu-id="6f511-226">Pagamento in base alla persona giuridica (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-226">Paid by legal entity (required)</span></span>
- <span data-ttu-id="6f511-227">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="6f511-227">Pay cycle (required)</span></span>
- <span data-ttu-id="6f511-228">Dimensione finanziaria predefinita - Centro di costo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-228">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="6f511-229">Assegnazione del lavoratore - Lavoratore, inizio assegnazione, fine assegnazione, codice motivo</span><span class="sxs-lookup"><span data-stu-id="6f511-229">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="6f511-230">Se nello stesso reparto più posizioni sono associate alla stessa mansione, vengono consolidate in una singola posizione in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6f511-230">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="6f511-231">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f511-231">For more information, see the following articles:</span></span>

- [<span data-ttu-id="6f511-232">Organizzare la forza lavoro utilizzando i reparti, le mansioni e le posizioni</span><span class="sxs-lookup"><span data-stu-id="6f511-232">Organize your workforce using departments, jobs, and positions</span></span>](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="6f511-233">Impostare le posizioni</span><span class="sxs-lookup"><span data-stu-id="6f511-233">Set up positions</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="6f511-234">Reparti</span><span class="sxs-lookup"><span data-stu-id="6f511-234">Departments</span></span>

<span data-ttu-id="6f511-235">Un reparto è un'unità operativa che rappresenta una categoria o un'area operativa di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6f511-235">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="6f511-236">Un reparto è responsabile di una specifica area dell'organizzazione, ad esempio la vendita, la contabilità o le risorse umane.</span><span class="sxs-lookup"><span data-stu-id="6f511-236">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="6f511-237">È possibile utilizzare i reparti per creare report sulle aree operative.</span><span class="sxs-lookup"><span data-stu-id="6f511-237">You can use departments to report on functional areas.</span></span> <span data-ttu-id="6f511-238">I reparti possono essere responsabili di profitti e perdite.</span><span class="sxs-lookup"><span data-stu-id="6f511-238">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="6f511-239">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f511-239">For more information, see the following articles:</span></span>

- [<span data-ttu-id="6f511-240">Creare un reparto e associarlo alla gerarchia reparti</span><span class="sxs-lookup"><span data-stu-id="6f511-240">Create a department and associate it with the department hierarchy</span></span>](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="6f511-241">Definire nuovi reparti</span><span class="sxs-lookup"><span data-stu-id="6f511-241">Define new departments</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="6f511-242">Cicli e periodi retributivi</span><span class="sxs-lookup"><span data-stu-id="6f511-242">Pay cycles and pay periods</span></span>

<span data-ttu-id="6f511-243">Un ciclo retributivo determina la frequenza di elaborazione delle retribuzioni e i giorni specifici in cui i lavoratori vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="6f511-243">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="6f511-244">Un ciclo retributivo può essere ad esempio mensile e i dipendenti possono essere pagati l'ultimo giorno del mese.</span><span class="sxs-lookup"><span data-stu-id="6f511-244">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="6f511-245">Un ciclo retributivo può in alternativa essere settimanale e i dipendenti possono essere pagati il giovedì successivo alla fine del periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="6f511-245">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="6f511-246">I cicli retributivi vengono assegnati alle posizioni per controllare quando i lavoratori in tali posizioni vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="6f511-246">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="6f511-247">Dopo aver creato i cicli retributivi, è possibile generare periodi retributivi per ogni ciclo.</span><span class="sxs-lookup"><span data-stu-id="6f511-247">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="6f511-248">Ogni periodo retributivo include una data di pagamento predefinita in base alle informazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="6f511-248">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="6f511-249">Tuttavia, è possibile modificare la data di pagamento predefinita in un periodo retributivo per consentire eccezioni, ad esempio quando la data di pagamento cade in un giorno festivo.</span><span class="sxs-lookup"><span data-stu-id="6f511-249">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="6f511-250">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="6f511-250">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="6f511-251">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="6f511-251">Pay cycle (required)</span></span>
- <span data-ttu-id="6f511-252">Frequenza ciclo retributivo (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-252">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="6f511-253">Data di inizio del periodo (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-253">Period start date (first pay period required)</span></span>
- <span data-ttu-id="6f511-254">Data di pagamento predefinita (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-254">Default payment date (first pay period required)</span></span>

<span data-ttu-id="6f511-255">Queste informazioni sono integrate con Dayforce come gruppi retributivi e sono separata in base al paese o alla regione per ogni ciclo retributivo.</span><span class="sxs-lookup"><span data-stu-id="6f511-255">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="6f511-256">Prima dell'integrazione è necessario generare almeno un periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="6f511-256">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="6f511-257">Dayforce genera calendari di gruppi retributivi e date di pagamento, in base alla data di inizio del primo periodo retributivo e alla data di pagamento predefinita che viene impostata in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6f511-257">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="6f511-258">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="6f511-258">Earning codes</span></span>

<span data-ttu-id="6f511-259">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="6f511-259">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="6f511-260">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="6f511-260">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="6f511-261">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="6f511-261">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="6f511-262">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-262">Earning Code (required)</span></span>
- <span data-ttu-id="6f511-263">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f511-263">Description</span></span>
- <span data-ttu-id="6f511-264">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="6f511-264">Unit of measure</span></span>
- <span data-ttu-id="6f511-265">Produttivo</span><span class="sxs-lookup"><span data-stu-id="6f511-265">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="6f511-266">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-266">Worker data</span></span>

<span data-ttu-id="6f511-267">I record per i diversi tipi di lavoratori a disposizione sono importanti per i sistemi di gestione delle risorse umane e delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="6f511-267">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="6f511-268">Le informazioni immesse possono essere utilizzate per tenere traccia di informazioni personali e sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="6f511-268">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="6f511-269">È possibile gestire le seguenti informazioni per i lavoratori:</span><span class="sxs-lookup"><span data-stu-id="6f511-269">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="6f511-270">**Base** - Gestire le informazioni di base su un lavoratore, ad esempio le informazioni sui contatti, le informazioni demografiche, le informazioni di identificazione, le informazioni sulla famiglia, lo stato di servizio militare, le informazioni sull'espatrio, e i contatti personali e di emergenza.</span><span class="sxs-lookup"><span data-stu-id="6f511-270">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="6f511-271">**Impiego** - Consente di gestire le informazioni sull'impiego di un lavoratore, ad esempio rapporto con l'organizzazione o la società, assegnazione della posizione, date di inizio e fine, idoneità al lavoro, condizioni di impiego, pensionamento, ferie e trasferimento.</span><span class="sxs-lookup"><span data-stu-id="6f511-271">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="6f511-272">**Congedo e assenza** - Consente di gestire le informazioni sulle assenze di un lavoratore, ad esempio calendari di lavoro, transazioni assenze e impostazione assenze.</span><span class="sxs-lookup"><span data-stu-id="6f511-272">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="6f511-273">**Retribuzioni** - Consente di gestire le informazioni sui piani di retribuzione di un lavoratore, ad esempio registrazione del piano, premi, prestazioni, provvigione, dati fiscali, pensionamento e detrazioni sullo stipendio.</span><span class="sxs-lookup"><span data-stu-id="6f511-273">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="6f511-274">Quando si immettono le informazioni su un lavoratore, tenere presenti i seguenti dati e le configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6f511-274">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="6f511-275">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="6f511-275">General information</span></span>

- <span data-ttu-id="6f511-276">Numero dipendente (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-276">Personnel number (required)</span></span>
- <span data-ttu-id="6f511-277">Nome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-277">First name (required)</span></span>
- <span data-ttu-id="6f511-278">Cognome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-278">Last name (required)</span></span>
- <span data-ttu-id="6f511-279">Secondo nome</span><span class="sxs-lookup"><span data-stu-id="6f511-279">Middle name</span></span>
- <span data-ttu-id="6f511-280">Data di anzianità</span><span class="sxs-lookup"><span data-stu-id="6f511-280">Seniority date</span></span>
- <span data-ttu-id="6f511-281">Nome noto</span><span class="sxs-lookup"><span data-stu-id="6f511-281">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="6f511-282">Informazioni personali</span><span class="sxs-lookup"><span data-stu-id="6f511-282">Personal information</span></span>

- <span data-ttu-id="6f511-283">Stato civile (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-283">Marital status (required)</span></span>
- <span data-ttu-id="6f511-284">Data di nascita (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-284">Birth date (required)</span></span>
- <span data-ttu-id="6f511-285">Sesso (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-285">Gender (required)</span></span>
- <span data-ttu-id="6f511-286">Persona disabile</span><span class="sxs-lookup"><span data-stu-id="6f511-286">Person with disabilities</span></span>
- <span data-ttu-id="6f511-287">Nazionalità paese regione (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="6f511-287">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="6f511-288">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="6f511-288">Address information</span></span>

- <span data-ttu-id="6f511-289">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-289">Primary (required)</span></span>
- <span data-ttu-id="6f511-290">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-290">Country/region (required)</span></span>
- <span data-ttu-id="6f511-291">Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-291">Postal code (required)</span></span>
- <span data-ttu-id="6f511-292">Numero civico (obbligatorio) (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="6f511-292">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="6f511-293">Informazioni aggiuntive sull'indirizzo (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="6f511-293">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="6f511-294">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-294">City (required)</span></span>
- <span data-ttu-id="6f511-295">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-295">State (required)</span></span>
- <span data-ttu-id="6f511-296">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-296">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="6f511-297">Informazioni contatto</span><span class="sxs-lookup"><span data-stu-id="6f511-297">Contact information</span></span> 

- <span data-ttu-id="6f511-298">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-298">Primary (required)</span></span>
- <span data-ttu-id="6f511-299">Numero contatto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-299">Contact number (required)</span></span>
- <span data-ttu-id="6f511-300">Interno</span><span class="sxs-lookup"><span data-stu-id="6f511-300">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="6f511-301">Informazioni sulle retribuzioni e codici di reddito</span><span class="sxs-lookup"><span data-stu-id="6f511-301">Payroll information and earning codes</span></span>

<span data-ttu-id="6f511-302">Ai dipendenti possono essere assegnati redditi specifici a una determinata frequenza di pagamento e un metodo di pagamento preferito.</span><span class="sxs-lookup"><span data-stu-id="6f511-302">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="6f511-303">I campi seguenti vengono utilizzati in Dayforce per garantire che le preferenze e le impostazioni vengano utilizzate.</span><span class="sxs-lookup"><span data-stu-id="6f511-303">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="6f511-304">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="6f511-304">Earning codes</span></span>

- <span data-ttu-id="6f511-305">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-305">Position (required)</span></span>
- <span data-ttu-id="6f511-306">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-306">Earning Code (required)</span></span>
- <span data-ttu-id="6f511-307">Frequenza (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-307">Frequency (required)</span></span>
- <span data-ttu-id="6f511-308">Importo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-308">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="6f511-309">Informazioni retribuzioni</span><span class="sxs-lookup"><span data-stu-id="6f511-309">Payroll information</span></span>

- <span data-ttu-id="6f511-310">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="6f511-310">Payment Method</span></span>
- <span data-ttu-id="6f511-311">Area economica (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-311">Economic Region (required)</span></span>
- <span data-ttu-id="6f511-312">ID benefit dipendente</span><span class="sxs-lookup"><span data-stu-id="6f511-312">Employee Benefits ID</span></span>
- <span data-ttu-id="6f511-313">Numero documento identità (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-313">National ID Number (required)</span></span>
- <span data-ttu-id="6f511-314">Numero servizio militare</span><span class="sxs-lookup"><span data-stu-id="6f511-314">Military Service Number</span></span>
- <span data-ttu-id="6f511-315">ID turno (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-315">Shift ID (required)</span></span>
- <span data-ttu-id="6f511-316">Numero imposta (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-316">Tax Number (required)</span></span>
- <span data-ttu-id="6f511-317">ID sindacato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-317">Union ID (required)</span></span>
- <span data-ttu-id="6f511-318">ID giorno lavorativo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-318">Work Day ID (required)</span></span>
- <span data-ttu-id="6f511-319">Numero permesso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6f511-319">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="6f511-320">Per il metodo di pagamento, il Messico supporta **Contante**, **Assegno** (l'assegno fisico della società) e **Pagamento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="6f511-320">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="6f511-321">Se non viene specificato alcun metodo di pagamento, **Assegno** è 'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6f511-321">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="6f511-322">Dettagli impiego</span><span class="sxs-lookup"><span data-stu-id="6f511-322">Employment details</span></span>

<span data-ttu-id="6f511-323">Lo storico dei dettagli impiego viene utilizzato come informazioni chiave da cui derivare gli stati di assunzione, termine e riassunzione di un dipendente Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6f511-323">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="6f511-324">Dayforce supporta solo un record di impiego attivo alla volta.</span><span class="sxs-lookup"><span data-stu-id="6f511-324">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="6f511-325">Data di inizio impiego (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-325">Employment start date (required)</span></span>
- <span data-ttu-id="6f511-326">Data di fine impiego</span><span class="sxs-lookup"><span data-stu-id="6f511-326">Employment end date</span></span>
- <span data-ttu-id="6f511-327">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="6f511-327">Start date</span></span>
- <span data-ttu-id="6f511-328">Data di inizio rettificata</span><span class="sxs-lookup"><span data-stu-id="6f511-328">Adjusted start date</span></span>
- <span data-ttu-id="6f511-329">Data fine rapporto (obbligatoria con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="6f511-329">Termination date (required upon termination)</span></span>
- <span data-ttu-id="6f511-330">Motivo fine rapporto (obbligatorio con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="6f511-330">Termination reason (required upon termination)</span></span>

<span data-ttu-id="6f511-331">Le date chiave del dipendente sono derivate utilizzando le informazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="6f511-331">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="6f511-332">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6f511-332">Human Resources</span></span>                | <span data-ttu-id="6f511-333">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6f511-333">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="6f511-334">Data di assunzione più recente</span><span class="sxs-lookup"><span data-stu-id="6f511-334">Most recent hire date</span></span> | <span data-ttu-id="6f511-335">Inizio dell'impiego del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="6f511-335">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="6f511-336">Data fine rapporto</span><span class="sxs-lookup"><span data-stu-id="6f511-336">Termination date</span></span>      | <span data-ttu-id="6f511-337">Data di fine rapporto del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="6f511-337">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="6f511-338">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="6f511-338">Start date</span></span>            | <span data-ttu-id="6f511-339">Data di inizio rettificata, data di inizio o inizio dell'impiego del record corrente dello storico di impiego non attivo</span><span class="sxs-lookup"><span data-stu-id="6f511-339">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="6f511-340">Data di assunzione originale</span><span class="sxs-lookup"><span data-stu-id="6f511-340">Original hire date</span></span>    | <span data-ttu-id="6f511-341">Inizio dell'impiego del record dello storico di impiego meno recente</span><span class="sxs-lookup"><span data-stu-id="6f511-341">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="6f511-342">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="6f511-342">Compensation</span></span>

<span data-ttu-id="6f511-343">Un piano di retribuzione fissa deve essere associato alla posizione primaria di ogni dipendente durante un periodo di impiego.</span><span class="sxs-lookup"><span data-stu-id="6f511-343">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="6f511-344">Questo periodo inizia alla data in cui il dipendente è stato assunto (o la data di inizio dell'impiego) e continua fino alla fine del rapporto.</span><span class="sxs-lookup"><span data-stu-id="6f511-344">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="6f511-345">Data di validità (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-345">Effective Date (required)</span></span>
- <span data-ttu-id="6f511-346">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="6f511-346">Expiration date</span></span>
- <span data-ttu-id="6f511-347">Retribuzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-347">Pay Rate (required)</span></span>
- <span data-ttu-id="6f511-348">Conversioni retribuzione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-348">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="6f511-349">Equivalente annuale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-349">Annual equivalent (required)</span></span>
- <span data-ttu-id="6f511-350">Equivalente orario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-350">Hourly equivalent (required)</span></span>

<span data-ttu-id="6f511-351">Se un dipendente a ore ha più posizioni, la retribuzione fissa della posizione primaria viene importata in Dayforce come il tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="6f511-351">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="6f511-352">Per le posizioni non principali, la tariffa oraria viene salvata nella posizione corrispondente in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6f511-352">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="6f511-353">Se un dipendente stipendiato ha più posizioni, la tariffa oraria cumulativa e lo stipendio annuale di tutte le posizioni attive vengono calcolati e utilizzati come tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="6f511-353">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="6f511-354">Numeri di identificazione</span><span class="sxs-lookup"><span data-stu-id="6f511-354">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="6f511-355">Numero di Previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="6f511-355">Social Security identifier</span></span> 

<span data-ttu-id="6f511-356">Ogni dipendente deve avere un identificatore primario.</span><span class="sxs-lookup"><span data-stu-id="6f511-356">Every employee must have one primary identifier.</span></span> <span data-ttu-id="6f511-357">Questo identificatore deve essere di tipo identificatore **SSN**.</span><span class="sxs-lookup"><span data-stu-id="6f511-357">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="6f511-358">In Dayforce, viene ricavato automaticamente come identificatore di previdenza sociale del dipendente per l'assunzione.</span><span class="sxs-lookup"><span data-stu-id="6f511-358">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="6f511-359">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-359">Primary (required)</span></span>
- <span data-ttu-id="6f511-360">Tipo di identificazione = "SSN"</span><span class="sxs-lookup"><span data-stu-id="6f511-360">Identification Type = "SSN"</span></span>
- <span data-ttu-id="6f511-361">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="6f511-361">Issued Date</span></span>
- <span data-ttu-id="6f511-362">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="6f511-362">Expiration Date</span></span>

<span data-ttu-id="6f511-363">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **SSN**.</span><span class="sxs-lookup"><span data-stu-id="6f511-363">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="6f511-364">Tuttavia, solo il record che è contrassegnato come **Primario** viene integrato in Dayforce, a prescindere che il numero sia attivo o scaduto.</span><span class="sxs-lookup"><span data-stu-id="6f511-364">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="6f511-365">Esborsi e conti bancari</span><span class="sxs-lookup"><span data-stu-id="6f511-365">Bank accounts and disbursements</span></span>

<span data-ttu-id="6f511-366">È necessario immettere informazioni sul conto bancario valide per un dipendente che scelga di essere pagato tramite trasferimenti di conto bancario.</span><span class="sxs-lookup"><span data-stu-id="6f511-366">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="6f511-367">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6f511-367">Human Resources</span></span>                         | <span data-ttu-id="6f511-368">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6f511-368">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="6f511-369">Numero conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-369">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="6f511-370">Codice SWIFT (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-370">SWIFT code (required)</span></span>          | <span data-ttu-id="6f511-371">Campo **ID banca** utilizzato durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="6f511-371">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="6f511-372">Codice filiale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-372">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="6f511-373">Tipo di conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-373">Bank account type (required)</span></span>   | <span data-ttu-id="6f511-374">Campo **Tipo di conto** utilizzando durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="6f511-374">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="6f511-375">I valori supportati includono **Controllo** e **Retribuzioni**.</span><span class="sxs-lookup"><span data-stu-id="6f511-375">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="6f511-376">I dipendenti che scelgono di essere pagati tramite trasferimenti di conto bancario devono fornire un collegamento a un conto rimanente che è sotto la persona giuridica che ha l'indirizzo primario in Messico ed è associato a un conto bancario valido presso una banca messicana.</span><span class="sxs-lookup"><span data-stu-id="6f511-376">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="6f511-377">Tutti gli altri account non di rimanenze verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="6f511-377">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="6f511-378">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="6f511-378">Address information</span></span>

<span data-ttu-id="6f511-379">Ogni dipendente deve avere un'ubicazione primaria.</span><span class="sxs-lookup"><span data-stu-id="6f511-379">Every employee must have one primary location.</span></span> <span data-ttu-id="6f511-380">In Dayforce, questa ubicazione viene utilizzata per determinare la principale residenza del dipendente a scopo fiscale.</span><span class="sxs-lookup"><span data-stu-id="6f511-380">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="6f511-381">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-381">Primary (required)</span></span>
- <span data-ttu-id="6f511-382">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-382">Country/region (required)</span></span>
- <span data-ttu-id="6f511-383">CAP/Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-383">Zip/postal code (required)</span></span>
- <span data-ttu-id="6f511-384">Via (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-384">Street (required)</span></span>
- <span data-ttu-id="6f511-385">Numero civico (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-385">Street Number (required)</span></span>
- <span data-ttu-id="6f511-386">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="6f511-386">Building Complement</span></span>
- <span data-ttu-id="6f511-387">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-387">City (required)</span></span>
- <span data-ttu-id="6f511-388">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-388">State (required)</span></span>
- <span data-ttu-id="6f511-389">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-389">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="6f511-390">Configurare i dati per generare le retribuzioni negli Stati Uniti e in Canada</span><span class="sxs-lookup"><span data-stu-id="6f511-390">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="6f511-391">Se si desidera generare la retribuzione per i dipendenti negli Stati Uniti e in Canada, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="6f511-391">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="6f511-392">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="6f511-392">Departments are required on positions.</span></span>
- <span data-ttu-id="6f511-393">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="6f511-393">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="6f511-394">È possibile configurare Human Resources per far sì che Posizioni specifichi un reparto.</span><span class="sxs-lookup"><span data-stu-id="6f511-394">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="6f511-395">A tale scopo, andare a **Posizioni condivise Risorse umane > Posizioni > Richiedi reparti su posizioni**.</span><span class="sxs-lookup"><span data-stu-id="6f511-395">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="6f511-396">Si consiglia di applicare questa impostazione per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="6f511-396">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="6f511-397">Tipi di lavoro</span><span class="sxs-lookup"><span data-stu-id="6f511-397">Job types</span></span>

<span data-ttu-id="6f511-398">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="6f511-398">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="6f511-399">I tipi di mansione sono necessari per elaborare le retribuzioni negli Stati Uniti e in Canada.</span><span class="sxs-lookup"><span data-stu-id="6f511-399">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="6f511-400">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="6f511-400">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="6f511-401">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="6f511-401">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="6f511-402">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="6f511-402">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="6f511-403">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="6f511-403">Job type</span></span>   | <span data-ttu-id="6f511-404">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f511-404">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="6f511-405">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="6f511-405">Hourly</span></span>     | <span data-ttu-id="6f511-406">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="6f511-406">Hourly</span></span>      |
| <span data-ttu-id="6f511-407">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="6f511-407">Salaried</span></span>   | <span data-ttu-id="6f511-408">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="6f511-408">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="6f511-409">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="6f511-409">Position types</span></span> 

<span data-ttu-id="6f511-410">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="6f511-410">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="6f511-411">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="6f511-411">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="6f511-412">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="6f511-412">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="6f511-413">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="6f511-413">Position type</span></span>   | <span data-ttu-id="6f511-414">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f511-414">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="6f511-415">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="6f511-415">Full-time</span></span>       | <span data-ttu-id="6f511-416">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="6f511-416">Full time employee</span></span> |
| <span data-ttu-id="6f511-417">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="6f511-417">Part-time</span></span>       | <span data-ttu-id="6f511-418">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="6f511-418">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="6f511-419">Codici causale</span><span class="sxs-lookup"><span data-stu-id="6f511-419">Reason codes</span></span>

<span data-ttu-id="6f511-420">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="6f511-420">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="6f511-421">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="6f511-421">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="6f511-422">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="6f511-422">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="6f511-423">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="6f511-423">Reason code</span></span>    | <span data-ttu-id="6f511-424">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f511-424">Description</span></span>      | <span data-ttu-id="6f511-425">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="6f511-425">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="6f511-426">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="6f511-426">RESIGNATION</span></span>    | <span data-ttu-id="6f511-427">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="6f511-427">Resignation</span></span>      | <span data-ttu-id="6f511-428">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-428">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-429">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="6f511-429">TERMINATION</span></span>    | <span data-ttu-id="6f511-430">Fine</span><span class="sxs-lookup"><span data-stu-id="6f511-430">Termination</span></span>      | <span data-ttu-id="6f511-431">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-431">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-432">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="6f511-432">RETIREMENT</span></span>     | <span data-ttu-id="6f511-433">Pensione</span><span class="sxs-lookup"><span data-stu-id="6f511-433">Retirement</span></span>       | <span data-ttu-id="6f511-434">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-434">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-435">OTHER</span><span class="sxs-lookup"><span data-stu-id="6f511-435">OTHER</span></span>          | <span data-ttu-id="6f511-436">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="6f511-436">Other Reasons</span></span>    | <span data-ttu-id="6f511-437">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-437">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-438">DEATH</span><span class="sxs-lookup"><span data-stu-id="6f511-438">DEATH</span></span>          | <span data-ttu-id="6f511-439">Decesso</span><span class="sxs-lookup"><span data-stu-id="6f511-439">Death</span></span>            | <span data-ttu-id="6f511-440">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-440">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-441">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="6f511-441">LEAVEOFABSENCE</span></span> | <span data-ttu-id="6f511-442">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="6f511-442">Leave of Absence</span></span> | <span data-ttu-id="6f511-443">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-443">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-444">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="6f511-444">CONTRACTEND</span></span>    | <span data-ttu-id="6f511-445">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="6f511-445">End of Contract</span></span>  | <span data-ttu-id="6f511-446">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-446">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-447">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="6f511-447">SALARYCHANGE</span></span>   | <span data-ttu-id="6f511-448">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="6f511-448">Change of Salary</span></span> | <span data-ttu-id="6f511-449">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="6f511-449">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="6f511-450">Stato civile</span><span class="sxs-lookup"><span data-stu-id="6f511-450">Marital status</span></span>

<span data-ttu-id="6f511-451">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="6f511-451">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6f511-452">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6f511-452">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="6f511-453">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6f511-453">Human Resources</span></span>                 | <span data-ttu-id="6f511-454">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6f511-454">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="6f511-455">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="6f511-455">Married</span></span>                | <span data-ttu-id="6f511-456">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="6f511-456">Married</span></span>              |
| <span data-ttu-id="6f511-457">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="6f511-457">Single</span></span>                 | <span data-ttu-id="6f511-458">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="6f511-458">Single</span></span>               |
| <span data-ttu-id="6f511-459">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="6f511-459">Widowed</span></span>                | <span data-ttu-id="6f511-460">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="6f511-460">Widowed</span></span>              |
| <span data-ttu-id="6f511-461">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="6f511-461">Divorced</span></span>               | <span data-ttu-id="6f511-462">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="6f511-462">Divorced</span></span>             |
| <span data-ttu-id="6f511-463">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="6f511-463">Registered Partnership</span></span> | <span data-ttu-id="6f511-464">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="6f511-464">Domestic Partnership</span></span> |
| <span data-ttu-id="6f511-465">Nessuna</span><span class="sxs-lookup"><span data-stu-id="6f511-465">None</span></span>                   | <span data-ttu-id="6f511-466">Nessuna</span><span class="sxs-lookup"><span data-stu-id="6f511-466">None</span></span>                 |
| <span data-ttu-id="6f511-467">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="6f511-467">Cohabiting</span></span>             | <span data-ttu-id="6f511-468">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="6f511-468">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="6f511-469">Genere</span><span class="sxs-lookup"><span data-stu-id="6f511-469">Gender</span></span>

<span data-ttu-id="6f511-470">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="6f511-470">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6f511-471">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6f511-471">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="6f511-472">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6f511-472">Human Resources</span></span>       | <span data-ttu-id="6f511-473">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6f511-473">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="6f511-474">Maschio</span><span class="sxs-lookup"><span data-stu-id="6f511-474">Male</span></span>         | <span data-ttu-id="6f511-475">Maschio</span><span class="sxs-lookup"><span data-stu-id="6f511-475">Male</span></span>            |
| <span data-ttu-id="6f511-476">Femmina</span><span class="sxs-lookup"><span data-stu-id="6f511-476">Female</span></span>       | <span data-ttu-id="6f511-477">Femmina</span><span class="sxs-lookup"><span data-stu-id="6f511-477">Female</span></span>          |
| <span data-ttu-id="6f511-478">Non specifico</span><span class="sxs-lookup"><span data-stu-id="6f511-478">Non-specific</span></span> | <span data-ttu-id="6f511-479">*Non supportato*</span><span class="sxs-lookup"><span data-stu-id="6f511-479">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="6f511-480">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="6f511-480">Earning codes</span></span>

<span data-ttu-id="6f511-481">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="6f511-481">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="6f511-482">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="6f511-482">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="6f511-483">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="6f511-483">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="6f511-484">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="6f511-484">Supported frequencies</span></span>

- <span data-ttu-id="6f511-485">Tutti</span><span class="sxs-lookup"><span data-stu-id="6f511-485">All</span></span>
- <span data-ttu-id="6f511-486">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="6f511-486">EVERYPAY</span></span>
- <span data-ttu-id="6f511-487">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="6f511-487">EACHPAYPERIOD</span></span>
- <span data-ttu-id="6f511-488">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="6f511-488">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="6f511-489">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="6f511-489">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="6f511-490">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-490">1OFMTH</span></span>
- <span data-ttu-id="6f511-491">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-491">LASTOFMTH</span></span>
- <span data-ttu-id="6f511-492">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-492">2OFMTH</span></span>
- <span data-ttu-id="6f511-493">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-493">3OFMTH</span></span>
- <span data-ttu-id="6f511-494">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-494">4OFMTH</span></span>
- <span data-ttu-id="6f511-495">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-495">5OFMTH</span></span>
- <span data-ttu-id="6f511-496">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-496">1N2OFMTH</span></span>
- <span data-ttu-id="6f511-497">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-497">3N4OFMTH</span></span>
- <span data-ttu-id="6f511-498">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-498">1N3OFMTH</span></span>
- <span data-ttu-id="6f511-499">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-499">1N4OFMTH</span></span>
- <span data-ttu-id="6f511-500">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-500">2N3OFMTH</span></span>
- <span data-ttu-id="6f511-501">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-501">2N4OFMTH</span></span>
- <span data-ttu-id="6f511-502">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-502">1N2N3OFMTH</span></span>
- <span data-ttu-id="6f511-503">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-503">1N2N4OFMTH</span></span>
- <span data-ttu-id="6f511-504">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-504">1N3N4OFMTH</span></span>
- <span data-ttu-id="6f511-505">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-505">2N3N4OFMTH</span></span>
- <span data-ttu-id="6f511-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="6f511-507">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="6f511-507">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="6f511-508">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="6f511-508">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="6f511-509">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="6f511-509">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="6f511-510">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="6f511-510">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="6f511-511">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="6f511-511">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="6f511-512">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="6f511-512">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="6f511-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="6f511-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="6f511-514">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="6f511-514">Addresses</span></span>

<span data-ttu-id="6f511-515">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="6f511-515">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="6f511-516">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="6f511-516">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="6f511-517">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6f511-517">Human Resources</span></span>          | <span data-ttu-id="6f511-518">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6f511-518">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="6f511-519">Paese/area geografica</span><span class="sxs-lookup"><span data-stu-id="6f511-519">Country/Region</span></span>  | <span data-ttu-id="6f511-520">Codice paese</span><span class="sxs-lookup"><span data-stu-id="6f511-520">Country Code</span></span>          |
| <span data-ttu-id="6f511-521">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="6f511-521">Zip/Postal Code</span></span> | <span data-ttu-id="6f511-522">CAP</span><span class="sxs-lookup"><span data-stu-id="6f511-522">Postal Code</span></span>           |
| <span data-ttu-id="6f511-523">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="6f511-523">State</span></span>           | <span data-ttu-id="6f511-524">Codice stato</span><span class="sxs-lookup"><span data-stu-id="6f511-524">State Code</span></span>            |
| <span data-ttu-id="6f511-525">Città</span><span class="sxs-lookup"><span data-stu-id="6f511-525">City</span></span>            | <span data-ttu-id="6f511-526">Città</span><span class="sxs-lookup"><span data-stu-id="6f511-526">City</span></span>                  |
| <span data-ttu-id="6f511-527">Regione</span><span class="sxs-lookup"><span data-stu-id="6f511-527">County</span></span>          | <span data-ttu-id="6f511-528">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="6f511-528">County (Municipality)</span></span> |
| <span data-ttu-id="6f511-529">Via</span><span class="sxs-lookup"><span data-stu-id="6f511-529">Street</span></span>          | <span data-ttu-id="6f511-530">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="6f511-530">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="6f511-531">Regioni fiscali</span><span class="sxs-lookup"><span data-stu-id="6f511-531">Tax regions</span></span>

<span data-ttu-id="6f511-532">Le regioni fiscali vengono utilizzate per determinare l'imposta appropriata che deve essere applicata durante la generazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="6f511-532">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="6f511-533">Le regioni fiscali vengono mappate in Dayforce come indirizzi di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="6f511-533">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="6f511-534">La regione fiscale predefinita deve essere associata alla posizione attiva del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="6f511-534">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="6f511-535">Regione fiscale (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-535">Tax region (required)</span></span>
- <span data-ttu-id="6f511-536">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-536">Country/Region (required)</span></span>
- <span data-ttu-id="6f511-537">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6f511-537">State (required)</span></span>
- <span data-ttu-id="6f511-538">Regione</span><span class="sxs-lookup"><span data-stu-id="6f511-538">County</span></span> 
- <span data-ttu-id="6f511-539">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="6f511-539">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="6f511-540">Configurare i dati per generare le retribuzioni in Messico</span><span class="sxs-lookup"><span data-stu-id="6f511-540">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="6f511-541">Se si desidera generare la retribuzione per i dipendenti in Messico, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="6f511-541">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="6f511-542">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="6f511-542">Departments are required on positions.</span></span>
- <span data-ttu-id="6f511-543">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="6f511-543">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="6f511-544">Tipi di posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="6f511-544">Job types</span></span>

<span data-ttu-id="6f511-545">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="6f511-545">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="6f511-546">Tipi di mansione necessari per elaborare le retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="6f511-546">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="6f511-547">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="6f511-547">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="6f511-548">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="6f511-548">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="6f511-549">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="6f511-549">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="6f511-550">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="6f511-550">Job type</span></span>   | <span data-ttu-id="6f511-551">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f511-551">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="6f511-552">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="6f511-552">Hourly</span></span>     | <span data-ttu-id="6f511-553">Su base oraria MX</span><span class="sxs-lookup"><span data-stu-id="6f511-553">MX Hourly</span></span>   |
| <span data-ttu-id="6f511-554">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="6f511-554">Salaried</span></span>   | <span data-ttu-id="6f511-555">Stipendiato MX</span><span class="sxs-lookup"><span data-stu-id="6f511-555">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="6f511-556">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="6f511-556">Position types</span></span> 

<span data-ttu-id="6f511-557">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="6f511-557">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="6f511-558">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="6f511-558">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="6f511-559">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="6f511-559">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="6f511-560">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="6f511-560">Position type</span></span>   | <span data-ttu-id="6f511-561">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f511-561">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="6f511-562">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="6f511-562">Full-time</span></span>       | <span data-ttu-id="6f511-563">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="6f511-563">Full time employee</span></span> |
| <span data-ttu-id="6f511-564">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="6f511-564">Part-time</span></span>       | <span data-ttu-id="6f511-565">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="6f511-565">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="6f511-566">Codici causale</span><span class="sxs-lookup"><span data-stu-id="6f511-566">Reason codes</span></span>

<span data-ttu-id="6f511-567">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="6f511-567">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="6f511-568">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="6f511-568">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="6f511-569">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="6f511-569">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="6f511-570">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="6f511-570">Reason code</span></span>            | <span data-ttu-id="6f511-571">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f511-571">Description</span></span>                    | <span data-ttu-id="6f511-572">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="6f511-572">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="6f511-573">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="6f511-573">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="6f511-574">Partenza prima della prima retribuzione</span><span class="sxs-lookup"><span data-stu-id="6f511-574">Departure before first payroll</span></span> | <span data-ttu-id="6f511-575">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-575">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-576">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="6f511-576">RESIGNATION</span></span>            | <span data-ttu-id="6f511-577">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="6f511-577">Resignation</span></span>                    | <span data-ttu-id="6f511-578">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-578">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-579">PENSION</span><span class="sxs-lookup"><span data-stu-id="6f511-579">PENSION</span></span>                | <span data-ttu-id="6f511-580">Pensionamento</span><span class="sxs-lookup"><span data-stu-id="6f511-580">Pension</span></span>                        | <span data-ttu-id="6f511-581">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-581">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-582">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="6f511-582">TERMINATION</span></span>            | <span data-ttu-id="6f511-583">Fine</span><span class="sxs-lookup"><span data-stu-id="6f511-583">Termination</span></span>                    | <span data-ttu-id="6f511-584">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-584">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-585">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="6f511-585">RETIREMENT</span></span>             | <span data-ttu-id="6f511-586">Pensione</span><span class="sxs-lookup"><span data-stu-id="6f511-586">Retirement</span></span>                     | <span data-ttu-id="6f511-587">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-587">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-588">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="6f511-588">ABSENTEE</span></span>               | <span data-ttu-id="6f511-589">Assente</span><span class="sxs-lookup"><span data-stu-id="6f511-589">Absentee</span></span>                       | <span data-ttu-id="6f511-590">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-590">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-591">OTHER</span><span class="sxs-lookup"><span data-stu-id="6f511-591">OTHER</span></span>                  | <span data-ttu-id="6f511-592">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="6f511-592">Other Reasons</span></span>                  | <span data-ttu-id="6f511-593">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-593">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-594">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="6f511-594">CLOSURE</span></span>                | <span data-ttu-id="6f511-595">Chiusura attività</span><span class="sxs-lookup"><span data-stu-id="6f511-595">Business Closure</span></span>               | <span data-ttu-id="6f511-596">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-596">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-597">DEATH</span><span class="sxs-lookup"><span data-stu-id="6f511-597">DEATH</span></span>                  | <span data-ttu-id="6f511-598">Decesso</span><span class="sxs-lookup"><span data-stu-id="6f511-598">Death</span></span>                          | <span data-ttu-id="6f511-599">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-599">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-600">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="6f511-600">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="6f511-601">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="6f511-601">Leave of Absence</span></span>               | <span data-ttu-id="6f511-602">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-602">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-603">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="6f511-603">CONTRACTEND</span></span>            | <span data-ttu-id="6f511-604">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="6f511-604">End of Contract</span></span>                | <span data-ttu-id="6f511-605">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="6f511-605">Terminate worker</span></span>     |
| <span data-ttu-id="6f511-606">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="6f511-606">SALARYCHANGE</span></span>           | <span data-ttu-id="6f511-607">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="6f511-607">Change of Salary</span></span>               | <span data-ttu-id="6f511-608">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="6f511-608">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="6f511-609">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="6f511-609">Terms of employment</span></span>

<span data-ttu-id="6f511-610">Le condizioni di impiego vengono utilizzate per creare categorie di termini di impiego.</span><span class="sxs-lookup"><span data-stu-id="6f511-610">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="6f511-611">I termini vengono mappati in Dayforce come valori degli indicatori di impiego.</span><span class="sxs-lookup"><span data-stu-id="6f511-611">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="6f511-612">I seguenti termini di impiego e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="6f511-612">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="6f511-613">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="6f511-613">Terms of employment</span></span>   | <span data-ttu-id="6f511-614">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f511-614">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="6f511-615">Regolare</span><span class="sxs-lookup"><span data-stu-id="6f511-615">Regular</span></span>               | <span data-ttu-id="6f511-616">Regolare</span><span class="sxs-lookup"><span data-stu-id="6f511-616">Regular</span></span>     |
| <span data-ttu-id="6f511-617">Diretto</span><span class="sxs-lookup"><span data-stu-id="6f511-617">Direct</span></span>                | <span data-ttu-id="6f511-618">Diretto</span><span class="sxs-lookup"><span data-stu-id="6f511-618">Direct</span></span>      |
| <span data-ttu-id="6f511-619">Internato</span><span class="sxs-lookup"><span data-stu-id="6f511-619">Internship</span></span>            | <span data-ttu-id="6f511-620">Internato</span><span class="sxs-lookup"><span data-stu-id="6f511-620">Internship</span></span>  |
| <span data-ttu-id="6f511-621">Permanente</span><span class="sxs-lookup"><span data-stu-id="6f511-621">Permanent</span></span>             | <span data-ttu-id="6f511-622">Permanente</span><span class="sxs-lookup"><span data-stu-id="6f511-622">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="6f511-623">Stato civile</span><span class="sxs-lookup"><span data-stu-id="6f511-623">Marital status</span></span>

<span data-ttu-id="6f511-624">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="6f511-624">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6f511-625">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6f511-625">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="6f511-626">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6f511-626">Human Resources</span></span>                 | <span data-ttu-id="6f511-627">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6f511-627">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="6f511-628">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="6f511-628">Married</span></span>                | <span data-ttu-id="6f511-629">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="6f511-629">Married</span></span>                   |
| <span data-ttu-id="6f511-630">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="6f511-630">Single</span></span>                 | <span data-ttu-id="6f511-631">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="6f511-631">Single</span></span>                    |
| <span data-ttu-id="6f511-632">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="6f511-632">Widowed</span></span>                | <span data-ttu-id="6f511-633">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="6f511-633">Widowed</span></span>                   |
| <span data-ttu-id="6f511-634">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="6f511-634">Divorced</span></span>               | <span data-ttu-id="6f511-635">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="6f511-635">Divorced</span></span>                  |
| <span data-ttu-id="6f511-636">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="6f511-636">Registered Partnership</span></span> | <span data-ttu-id="6f511-637">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="6f511-637">Domestic Partnership</span></span>      |
| <span data-ttu-id="6f511-638">Nessuna</span><span class="sxs-lookup"><span data-stu-id="6f511-638">None</span></span>                   | <span data-ttu-id="6f511-639">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="6f511-639">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="6f511-640">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="6f511-640">Cohabiting</span></span>             | <span data-ttu-id="6f511-641">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="6f511-641">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="6f511-642">Genere</span><span class="sxs-lookup"><span data-stu-id="6f511-642">Gender</span></span>

<span data-ttu-id="6f511-643">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="6f511-643">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6f511-644">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6f511-644">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="6f511-645">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6f511-645">Human Resources</span></span>       | <span data-ttu-id="6f511-646">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6f511-646">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="6f511-647">Maschio</span><span class="sxs-lookup"><span data-stu-id="6f511-647">Male</span></span>         | <span data-ttu-id="6f511-648">Maschio</span><span class="sxs-lookup"><span data-stu-id="6f511-648">Male</span></span>                      |
| <span data-ttu-id="6f511-649">Femmina</span><span class="sxs-lookup"><span data-stu-id="6f511-649">Female</span></span>       | <span data-ttu-id="6f511-650">Femmina</span><span class="sxs-lookup"><span data-stu-id="6f511-650">Female</span></span>                    |
| <span data-ttu-id="6f511-651">Non specifico</span><span class="sxs-lookup"><span data-stu-id="6f511-651">Non-specific</span></span> | <span data-ttu-id="6f511-652">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="6f511-652">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="6f511-653">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="6f511-653">Payment method</span></span>

<span data-ttu-id="6f511-654">I metodi di pagamento offrono al dipendente e all'azienda un modo per descrivere la modalità di pagamento dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="6f511-654">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="6f511-655">I metodi di pagamento vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="6f511-655">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="6f511-656">Nella tabella seguente vengono illustrati in che modo i metodi di pagamento vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6f511-656">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="6f511-657">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6f511-657">Human Resources</span></span>             | <span data-ttu-id="6f511-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6f511-658">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="6f511-659">Contanti</span><span class="sxs-lookup"><span data-stu-id="6f511-659">Cash</span></span>               | <span data-ttu-id="6f511-660">Contanti</span><span class="sxs-lookup"><span data-stu-id="6f511-660">Cash</span></span>                      |
| <span data-ttu-id="6f511-661">Pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="6f511-661">Electronic Payment</span></span> | <span data-ttu-id="6f511-662">Trasferimenti</span><span class="sxs-lookup"><span data-stu-id="6f511-662">Transfer</span></span>                  |
| <span data-ttu-id="6f511-663">Seleziona</span><span class="sxs-lookup"><span data-stu-id="6f511-663">Check</span></span>              | <span data-ttu-id="6f511-664">Assegno</span><span class="sxs-lookup"><span data-stu-id="6f511-664">Cheque</span></span>                    |
| <span data-ttu-id="6f511-665">Assegno circolare</span><span class="sxs-lookup"><span data-stu-id="6f511-665">Bank Draft</span></span>         | <span data-ttu-id="6f511-666">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="6f511-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="6f511-667">Altro</span><span class="sxs-lookup"><span data-stu-id="6f511-667">Other</span></span>              | <span data-ttu-id="6f511-668">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="6f511-668">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="6f511-669">Tipo di conto bancario</span><span class="sxs-lookup"><span data-stu-id="6f511-669">Bank account type</span></span>

<span data-ttu-id="6f511-670">I tipi di conto bancario vengono utilizzati per i pagamenti elettronici ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="6f511-670">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="6f511-671">I tipi di conto bancario vengono mappati in Dayforce come informazioni sul conto di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="6f511-671">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="6f511-672">I tipi di conto bancario vengono convertiti, come appropriato, nei valori accettati per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="6f511-672">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="6f511-673">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6f511-673">Human Resources</span></span>            | <span data-ttu-id="6f511-674">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6f511-674">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="6f511-675">Conto corrente</span><span class="sxs-lookup"><span data-stu-id="6f511-675">Checking Account</span></span>  | <span data-ttu-id="6f511-676">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="6f511-676">CheckingAccount</span></span>           |
| <span data-ttu-id="6f511-677">Conto retribuzioni</span><span class="sxs-lookup"><span data-stu-id="6f511-677">Payroll Account</span></span>   | <span data-ttu-id="6f511-678">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="6f511-678">PayrollAccount</span></span>            |
| <span data-ttu-id="6f511-679">Conto di risparmio</span><span class="sxs-lookup"><span data-stu-id="6f511-679">Savings Account</span></span>   | <span data-ttu-id="6f511-680">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="6f511-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="6f511-681">Conto Bankgirot</span><span class="sxs-lookup"><span data-stu-id="6f511-681">BankGirot account</span></span> | <span data-ttu-id="6f511-682">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="6f511-682">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="6f511-683">Conto PlusGirot</span><span class="sxs-lookup"><span data-stu-id="6f511-683">PlusGirot account</span></span> | <span data-ttu-id="6f511-684">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="6f511-684">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="6f511-685">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="6f511-685">Earning codes</span></span>

<span data-ttu-id="6f511-686">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="6f511-686">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="6f511-687">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="6f511-687">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="6f511-688">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="6f511-688">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="6f511-689">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="6f511-689">Supported frequencies</span></span>

- <span data-ttu-id="6f511-690">Tutti</span><span class="sxs-lookup"><span data-stu-id="6f511-690">All</span></span>
- <span data-ttu-id="6f511-691">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="6f511-691">EVERYPAY</span></span>
- <span data-ttu-id="6f511-692">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="6f511-692">EACHPAYPERIOD</span></span>
- <span data-ttu-id="6f511-693">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="6f511-693">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="6f511-694">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="6f511-694">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="6f511-695">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-695">1OFMTH</span></span>
- <span data-ttu-id="6f511-696">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-696">LASTOFMTH</span></span>
- <span data-ttu-id="6f511-697">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-697">2OFMTH</span></span>
- <span data-ttu-id="6f511-698">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-698">3OFMTH</span></span>
- <span data-ttu-id="6f511-699">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-699">4OFMTH</span></span>
- <span data-ttu-id="6f511-700">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-700">5OFMTH</span></span>
- <span data-ttu-id="6f511-701">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-701">1N2OFMTH</span></span>
- <span data-ttu-id="6f511-702">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-702">3N4OFMTH</span></span>
- <span data-ttu-id="6f511-703">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-703">1N3OFMTH</span></span>
- <span data-ttu-id="6f511-704">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-704">1N4OFMTH</span></span>
- <span data-ttu-id="6f511-705">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-705">2N3OFMTH</span></span>
- <span data-ttu-id="6f511-706">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-706">2N4OFMTH</span></span>
- <span data-ttu-id="6f511-707">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-707">1N2N3OFMTH</span></span>
- <span data-ttu-id="6f511-708">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-708">1N2N4OFMTH</span></span>
- <span data-ttu-id="6f511-709">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-709">1N3N4OFMTH</span></span>
- <span data-ttu-id="6f511-710">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-710">2N3N4OFMTH</span></span>
- <span data-ttu-id="6f511-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="6f511-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="6f511-712">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="6f511-712">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="6f511-713">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="6f511-713">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="6f511-714">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="6f511-714">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="6f511-715">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="6f511-715">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="6f511-716">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="6f511-716">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="6f511-717">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="6f511-717">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="6f511-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="6f511-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="6f511-719">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="6f511-719">Addresses</span></span>

<span data-ttu-id="6f511-720">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="6f511-720">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="6f511-721">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="6f511-721">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="6f511-722">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="6f511-722">Human Resources</span></span>              | <span data-ttu-id="6f511-723">Dayforce</span><span class="sxs-lookup"><span data-stu-id="6f511-723">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="6f511-724">Paese/area geografica</span><span class="sxs-lookup"><span data-stu-id="6f511-724">Country/Region</span></span>      | <span data-ttu-id="6f511-725">Codice paese</span><span class="sxs-lookup"><span data-stu-id="6f511-725">Country Code</span></span>          |
| <span data-ttu-id="6f511-726">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="6f511-726">Zip/Postal Code</span></span>     | <span data-ttu-id="6f511-727">CAP</span><span class="sxs-lookup"><span data-stu-id="6f511-727">Postal Code</span></span>           |
| <span data-ttu-id="6f511-728">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="6f511-728">State</span></span>               | <span data-ttu-id="6f511-729">Codice stato</span><span class="sxs-lookup"><span data-stu-id="6f511-729">State Code</span></span>            |
| <span data-ttu-id="6f511-730">Città</span><span class="sxs-lookup"><span data-stu-id="6f511-730">City</span></span>                | <span data-ttu-id="6f511-731">Città</span><span class="sxs-lookup"><span data-stu-id="6f511-731">City</span></span>                  |
| <span data-ttu-id="6f511-732">Regione</span><span class="sxs-lookup"><span data-stu-id="6f511-732">County</span></span>              | <span data-ttu-id="6f511-733">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="6f511-733">County (Municipality)</span></span> |
| <span data-ttu-id="6f511-734">Via</span><span class="sxs-lookup"><span data-stu-id="6f511-734">Street</span></span>              | <span data-ttu-id="6f511-735">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="6f511-735">Address Line 1</span></span>        |
| <span data-ttu-id="6f511-736">Numero civico</span><span class="sxs-lookup"><span data-stu-id="6f511-736">Street Number</span></span>       | <span data-ttu-id="6f511-737">Riga indirizzo 2</span><span class="sxs-lookup"><span data-stu-id="6f511-737">Address Line 2</span></span>        |
| <span data-ttu-id="6f511-738">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="6f511-738">Building Complement</span></span> | <span data-ttu-id="6f511-739">Riga indirizzo 5</span><span class="sxs-lookup"><span data-stu-id="6f511-739">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="6f511-740">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="6f511-740">Passport number</span></span>

<span data-ttu-id="6f511-741">I dipendenti possono indicare le informazioni sul passaporto.</span><span class="sxs-lookup"><span data-stu-id="6f511-741">Employees can declare passport information.</span></span> <span data-ttu-id="6f511-742">Queste informazioni sono del tipo di identificazione **Passaporto** e vengono integrate in Dayforce come parte delle informazioni di un dipendente specifiche per il Messico.</span><span class="sxs-lookup"><span data-stu-id="6f511-742">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="6f511-743">Tipo di identificazione = "Passaporto"</span><span class="sxs-lookup"><span data-stu-id="6f511-743">Identification Type = "Passport"</span></span>
- <span data-ttu-id="6f511-744">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="6f511-744">Issued Date</span></span>
- <span data-ttu-id="6f511-745">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="6f511-745">Expiration Date</span></span>

<span data-ttu-id="6f511-746">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **Passaporto**.</span><span class="sxs-lookup"><span data-stu-id="6f511-746">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="6f511-747">Tuttavia, solo l'immissione del passaporto attivo corrente viene integrata in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="6f511-747">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="6f511-748">Se tutte le immissioni di passaporto sono scadute, in Dayforce viene integrato il passaporto di emissione più recente.</span><span class="sxs-lookup"><span data-stu-id="6f511-748">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]