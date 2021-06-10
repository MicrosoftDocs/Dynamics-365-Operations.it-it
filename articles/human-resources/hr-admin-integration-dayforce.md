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
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d150daa92fe79cf6620ce5ddf1a01f369c64053
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051499"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="8f8a3-104">Configurare l'integrazione con Dayforce</span><span class="sxs-lookup"><span data-stu-id="8f8a3-104">Configure integration with Dayforce</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8f8a3-105">L'integrazione tra Microsoft Dynamics 365 Human Resources e Ceridian Dayforce si basa su vari passaggi di configurazione descritti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="8f8a3-106">È necessario configurare l'integrazione sia in Human Resources che in Dayforce prima di poter elaborare un ciclo di pagamenti.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="8f8a3-107">Quando si utilizza un servizio, ad esempio Dayforce, per completare i cicli di pagamenti, è necessario abilitare l'integrazione in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="8f8a3-108">L'integrazione richiede dati specifici da Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="8f8a3-109">Di conseguenza, è necessario verificare che i dati che vengono mappati a Dayforce siano configurati in Human Resources in modo che supporti l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="8f8a3-110">L'integrazione utilizza le seguenti categorie generiche di dati:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="8f8a3-111">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="8f8a3-111">Human resources data</span></span>
- <span data-ttu-id="8f8a3-112">Dati di compensazione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-112">Compensation data</span></span>
- <span data-ttu-id="8f8a3-113">Data di retribuzione, ad esempio i cicli di pagamenti, i periodi retributivi e i codici reddito</span><span class="sxs-lookup"><span data-stu-id="8f8a3-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="8f8a3-114">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-114">Worker data</span></span>

<span data-ttu-id="8f8a3-115">In questo articolo vengono descritti i passaggi che è necessario completare per abilitare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="8f8a3-116">E vengono descritti i tipi di dati e i dettagli di configurazione necessari all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="8f8a3-117">Abilitare l'integrazione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-117">Enable the integration</span></span>

<span data-ttu-id="8f8a3-118">In Human Resources è necessario attivare l'integrazione e immettere le informazioni di configurazione per connettersi a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="8f8a3-119">Se si desidera che la transazione contabile prodotta venga importata in Microsoft Dynamics 365 Finance, è necessario impostare anche un conto di archiviazione di Microsoft Azure e immettere la stringa di connessione di Archiviazione di Azure in Finance.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="8f8a3-120">Per attivare l'integrazione in Human Resources, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="8f8a3-121">Nella pagina **Amministrazione sistema** selezionare **Configurazione di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="8f8a3-122">Immettere l'endpoint FTP (File Transfer Protocol) e il percorso protetto della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="8f8a3-123">Immettere il nome utente e la password dell'utente che accederà al percorso protetto dell'endpoint e della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="8f8a3-124">Verificare la connessione, secondo le esigenze, e impostare l'opzione **Abilita integrazione retribuzioni** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="8f8a3-125">Quando l'integrazione viene attivata, vengono creati i file e il pacchetto di esportazione dei dati e viene impostata la frequenza.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="8f8a3-126">È possibile cambiare la frequenza in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="8f8a3-127">Per altre informazioni sugli account di Archiviazione di Azure e sulle stringhe di connessione di Archiviazione di Azure, vedere gli articoli di Azure seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="8f8a3-128">Account di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="8f8a3-128">About Azure storage accounts</span></span>](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="8f8a3-129">Configurare le stringhe di connessione di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="8f8a3-129">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="8f8a3-130">Dettagli tecnici quando l'integrazione delle retribuzioni è attivata</span><span class="sxs-lookup"><span data-stu-id="8f8a3-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="8f8a3-131">L'attivazione dell'integrazione delle retribuzioni comporta due effetti primari:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="8f8a3-132">Viene creato un progetto di esportazione di dati denominato "Esportazione integrazione delle retribuzioni".</span><span class="sxs-lookup"><span data-stu-id="8f8a3-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="8f8a3-133">Questo progetto contiene le entità e i campi necessari per l'integrazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="8f8a3-134">Per esaminare il progetto, andare a **Amministrazione sistema**, selezionare il riquadro **Gestione dati** e infine aprire il progetto dati dall'elenco di progetti.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="8f8a3-135">Questo processo batch esegue il progetto di esportazione dei dati, codifica il pacchetto dati risultante e trasferisce il file del pacchetto dati all'endpoint SFTP configurato nella schermata **Configurazione di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="8f8a3-136">Il pacchetto dati trasferito all'endpoint SFTP viene codificato utilizzando una chiave univoca per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="8f8a3-137">La chiave è un Azure Key Vault accessibile solo da Ceridian.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="8f8a3-138">Non è possibile decrittografare ed esaminare il contenuto del pacchetto dati.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="8f8a3-139">Se è necessario esaminare il contenuto del pacchetto dati, esportare manualmente il progetto dati "Esportazione integrazione delle retribuzioni", scaricarlo e quindi aprirlo.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="8f8a3-140">L'esportazione manuale non comporta la crittografia o il trasferimento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-140">Manual export will not apply encryption or transfer the package.</span></span>
> <span data-ttu-id="8f8a3-141">Per le istanze in cui i file di integrazione vengono inviati da un ambiente Sandbox o UAT di Dynamics 365 Human Resources a un ambiente Ceridian Dayforce Test, è possibile utilizzare il seguente URL dell'insieme di credenziali delle chiavi: https://payrollintegrationprod.vault.azure.net.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-141">For instances where the integration files are sent from a Dynamics 365 Human Resources UAT or Sandbox environment to a Ceridian Dayforce Test environment, you can use the following key vault URL: https://payrollintegrationprod.vault.azure.net.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="8f8a3-142">Configurare i dati</span><span class="sxs-lookup"><span data-stu-id="8f8a3-142">Configure your data</span></span> 

<span data-ttu-id="8f8a3-143">Per elaborare le retribuzioni, è necessario configurare i dati di Risorse umane in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-143">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="8f8a3-144">È necessario impostare i dati dell'organizzazione, ad esempio mansioni e posizioni, insieme alle informazioni sui benefit e sulle compensazioni.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-144">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="8f8a3-145">Queste informazioni includono informazioni sull'impiego, la retribuzione e le detrazioni che sono richieste per generare la retribuzione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-145">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="8f8a3-146">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="8f8a3-146">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="8f8a3-147">Benefit</span><span class="sxs-lookup"><span data-stu-id="8f8a3-147">Benefits</span></span> 

<span data-ttu-id="8f8a3-148">Le risorse umane dispongono di strumenti per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-148">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="8f8a3-149">Quando si creano i benefit, tenere presenti i seguenti dati e configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-149">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="8f8a3-150">Piani di benefit</span><span class="sxs-lookup"><span data-stu-id="8f8a3-150">Benefit plans</span></span>

- <span data-ttu-id="8f8a3-151">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-151">Plan (required)</span></span>
- <span data-ttu-id="8f8a3-152">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-152">Type (required)</span></span>
- <span data-ttu-id="8f8a3-153">Impatto retribuzioni (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-153">Payroll impact (required)</span></span>
- <span data-ttu-id="8f8a3-154">Recupera arretrati</span><span class="sxs-lookup"><span data-stu-id="8f8a3-154">Recover arrears</span></span>
- <span data-ttu-id="8f8a3-155">Metodo di detrazione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-155">Deduction method</span></span>
- <span data-ttu-id="8f8a3-156">Priorità detrazione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-156">Deduction priority</span></span>
- <span data-ttu-id="8f8a3-157">Periodo limite</span><span class="sxs-lookup"><span data-stu-id="8f8a3-157">Limit period</span></span>
- <span data-ttu-id="8f8a3-158">Importo limite</span><span class="sxs-lookup"><span data-stu-id="8f8a3-158">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="8f8a3-159">Benefit</span><span class="sxs-lookup"><span data-stu-id="8f8a3-159">Benefits</span></span>

- <span data-ttu-id="8f8a3-160">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-160">Plan (required)</span></span>
- <span data-ttu-id="8f8a3-161">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-161">Type (required)</span></span>
- <span data-ttu-id="8f8a3-162">Opzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-162">Option (required)</span></span>
- <span data-ttu-id="8f8a3-163">ID benefit (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-163">Benefit ID (required)</span></span>
- <span data-ttu-id="8f8a3-164">Frequenza</span><span class="sxs-lookup"><span data-stu-id="8f8a3-164">Frequency</span></span>
- <span data-ttu-id="8f8a3-165">Base</span><span class="sxs-lookup"><span data-stu-id="8f8a3-165">Basis</span></span>
- <span data-ttu-id="8f8a3-166">Importo o coefficiente</span><span class="sxs-lookup"><span data-stu-id="8f8a3-166">Amount or rate</span></span>
- <span data-ttu-id="8f8a3-167">Codice di reddito</span><span class="sxs-lookup"><span data-stu-id="8f8a3-167">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="8f8a3-168">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="8f8a3-168">Supported frequencies</span></span> 

- <span data-ttu-id="8f8a3-169">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="8f8a3-169">Weekly</span></span>
- <span data-ttu-id="8f8a3-170">Bisettimanale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-170">Bi-weekly</span></span>
- <span data-ttu-id="8f8a3-171">Quindicinale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-171">Semi-monthly</span></span>
- <span data-ttu-id="8f8a3-172">Ogni mese</span><span class="sxs-lookup"><span data-stu-id="8f8a3-172">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="8f8a3-173">Basi supportate</span><span class="sxs-lookup"><span data-stu-id="8f8a3-173">Supported bases</span></span> 

- <span data-ttu-id="8f8a3-174">Importo fisso</span><span class="sxs-lookup"><span data-stu-id="8f8a3-174">Fixed amount</span></span>
- <span data-ttu-id="8f8a3-175">Percentuale di redditi</span><span class="sxs-lookup"><span data-stu-id="8f8a3-175">Percent of earnings</span></span>
- <span data-ttu-id="8f8a3-176">Ore di produzione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-176">Productive hours</span></span>

<span data-ttu-id="8f8a3-177">Dayforce crea le seguenti detrazioni, in base all'impatto delle retribuzioni definito nel piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-177">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="8f8a3-178">Selezione in Human Resources</span><span class="sxs-lookup"><span data-stu-id="8f8a3-178">Selection in Human Resources</span></span>        | <span data-ttu-id="8f8a3-179">Risultato in Dayforce</span><span class="sxs-lookup"><span data-stu-id="8f8a3-179">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="8f8a3-180">Nessuna</span><span class="sxs-lookup"><span data-stu-id="8f8a3-180">None</span></span>                       | <span data-ttu-id="8f8a3-181">Non viene creata alcuna detrazione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-181">No deduction is created.</span></span>                      |
| <span data-ttu-id="8f8a3-182">Solo detrazione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-182">Deduction only</span></span>             | <span data-ttu-id="8f8a3-183">Viene creata una detrazione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-183">An employee deduction is created.</span></span>             |
| <span data-ttu-id="8f8a3-184">Solo contribuzione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-184">Contribution only</span></span>          | <span data-ttu-id="8f8a3-185">Viene creata una detrazione del datore di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-185">An employer deduction is created.</span></span>             |
| <span data-ttu-id="8f8a3-186">Detrazione e contribuzione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-186">Deduction and contribution</span></span> | <span data-ttu-id="8f8a3-187">Vengono create detrazioni del datore di lavoro e del dipendente.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-187">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="8f8a3-188">Per altre informazioni su come definire e gestire un programma di benefit, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-188">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="8f8a3-189">Realizzare un programma di benefit per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="8f8a3-189">Deliver an employee benefits program</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="8f8a3-190">Crea un nuovo benefit</span><span class="sxs-lookup"><span data-stu-id="8f8a3-190">Create a new benefit</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="8f8a3-191">Definire regole e criteri di idoneità ai benefit</span><span class="sxs-lookup"><span data-stu-id="8f8a3-191">Define benefit eligibility rules and policies</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="8f8a3-192">Iscrivere e rimuovere benefit da lavoratori</span><span class="sxs-lookup"><span data-stu-id="8f8a3-192">Enroll and remove benefits from workers</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="8f8a3-193">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-193">Compensation</span></span> 

<span data-ttu-id="8f8a3-194">La gestione delle retribuzioni consente di controllare la liquidazione dei premi e della retribuzione base.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-194">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="8f8a3-195">La retribuzione di base fissa di un dipendente e gli aumenti per merito sono controllati mediante piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-195">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="8f8a3-196">È possibile controllare il pagamento degli incentivi, ad esempio il pagamento dei bonus, dei premi produttività, dei diritti di opzione, delle sovvenzioni, oltre che dei premi una tantum, tramite i piani di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-196">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="8f8a3-197">Dayforce utilizza le informazioni sulla compensazione per calcolare la retribuzione annuale o oraria di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-197">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="8f8a3-198">I piani di retribuzione fissa e conversioni della retribuzione sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-198">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="8f8a3-199">I dipendenti devono essere associati a un piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-199">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="8f8a3-200">Per ulteriori informazioni sui piani di retribuzione, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-200">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="8f8a3-201">Creare piani di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="8f8a3-201">Create fixed compensation plans</span></span>](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="8f8a3-202">Creare piani di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="8f8a3-202">Create variable compensation plans</span></span>](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="8f8a3-203">Sviluppare una struttura e piani di stipendi/retribuzioni</span><span class="sxs-lookup"><span data-stu-id="8f8a3-203">Develop salary/compensation structure and plans</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="8f8a3-204">Processo retributivo</span><span class="sxs-lookup"><span data-stu-id="8f8a3-204">Process compensation</span></span>](/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="8f8a3-205">Definire il processo retributivo e calcolare i risultati</span><span class="sxs-lookup"><span data-stu-id="8f8a3-205">Define compensation process and calculate results</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="8f8a3-206">Iscrivere un dipendente a un piano di retribuzione fisso</span><span class="sxs-lookup"><span data-stu-id="8f8a3-206">Enroll an employee in a fixed compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="8f8a3-207">Iscrivere un dipendente a un piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="8f8a3-207">Enroll an employee in a variable compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="8f8a3-208">Mansioni</span><span class="sxs-lookup"><span data-stu-id="8f8a3-208">Jobs</span></span> 

<span data-ttu-id="8f8a3-209">Una mansione è una raccolta delle attività e delle responsabilità proprie della persona assegnata a una mansione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-209">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="8f8a3-210">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-210">For more information, see the following articles:</span></span>

- [<span data-ttu-id="8f8a3-211">Impostazione dei componenti di una mansione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-211">Setting up the components of a job</span></span>](/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="8f8a3-212">Definire nuovi processi</span><span class="sxs-lookup"><span data-stu-id="8f8a3-212">Define new jobs</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="8f8a3-213">Posizioni</span><span class="sxs-lookup"><span data-stu-id="8f8a3-213">Positions</span></span>

<span data-ttu-id="8f8a3-214">Una posizione è una singola istanza di un processo.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-214">A position is an individual instance of a job.</span></span> <span data-ttu-id="8f8a3-215">Ad esempio, la posizione "Manager vendite (Est") è una delle posizioni associate alla mansione "Manager vendite".</span><span class="sxs-lookup"><span data-stu-id="8f8a3-215">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="8f8a3-216">Una posizione è presente in un reparto.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-216">A position exists in a department.</span></span> <span data-ttu-id="8f8a3-217">È possibile associare un solo lavoratore a ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-217">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="8f8a3-218">Tenere a mente i seguenti dati e la configurazione quando si impostano le posizioni:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-218">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="8f8a3-219">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-219">Position (required)</span></span>
- <span data-ttu-id="8f8a3-220">Descrizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-220">Description (required)</span></span>
- <span data-ttu-id="8f8a3-221">Mansione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-221">Job (required)</span></span>
- <span data-ttu-id="8f8a3-222">Reparto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-222">Department (required)</span></span>
- <span data-ttu-id="8f8a3-223">Tipo di posizione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-223">Position type (required)</span></span>
- <span data-ttu-id="8f8a3-224">Equivalente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="8f8a3-224">Full-time equivalent</span></span>
- <span data-ttu-id="8f8a3-225">Ore regolari annuali (obbligatorie)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-225">Annual regular hours (required)</span></span>
- <span data-ttu-id="8f8a3-226">Pagamento in base alla persona giuridica (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-226">Paid by legal entity (required)</span></span>
- <span data-ttu-id="8f8a3-227">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="8f8a3-227">Pay cycle (required)</span></span>
- <span data-ttu-id="8f8a3-228">Dimensione finanziaria predefinita - Centro di costo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-228">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="8f8a3-229">Assegnazione del lavoratore - Lavoratore, inizio assegnazione, fine assegnazione, codice motivo</span><span class="sxs-lookup"><span data-stu-id="8f8a3-229">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="8f8a3-230">Se nello stesso reparto più posizioni sono associate alla stessa mansione, vengono consolidate in una singola posizione in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-230">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="8f8a3-231">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-231">For more information, see the following articles:</span></span>

- [<span data-ttu-id="8f8a3-232">Organizzare la forza lavoro utilizzando i reparti, le mansioni e le posizioni</span><span class="sxs-lookup"><span data-stu-id="8f8a3-232">Organize your workforce using departments, jobs, and positions</span></span>](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="8f8a3-233">Impostare le posizioni</span><span class="sxs-lookup"><span data-stu-id="8f8a3-233">Set up positions</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="8f8a3-234">Reparti</span><span class="sxs-lookup"><span data-stu-id="8f8a3-234">Departments</span></span>

<span data-ttu-id="8f8a3-235">Un reparto è un'unità operativa che rappresenta una categoria o un'area operativa di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-235">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="8f8a3-236">Un reparto è responsabile di una specifica area dell'organizzazione, ad esempio la vendita, la contabilità o le risorse umane.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-236">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="8f8a3-237">È possibile utilizzare i reparti per creare report sulle aree operative.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-237">You can use departments to report on functional areas.</span></span> <span data-ttu-id="8f8a3-238">I reparti possono essere responsabili di profitti e perdite.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-238">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="8f8a3-239">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-239">For more information, see the following articles:</span></span>

- [<span data-ttu-id="8f8a3-240">Creare un reparto e associarlo alla gerarchia reparti</span><span class="sxs-lookup"><span data-stu-id="8f8a3-240">Create a department and associate it with the department hierarchy</span></span>](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="8f8a3-241">Definire nuovi reparti</span><span class="sxs-lookup"><span data-stu-id="8f8a3-241">Define new departments</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="8f8a3-242">Cicli e periodi retributivi</span><span class="sxs-lookup"><span data-stu-id="8f8a3-242">Pay cycles and pay periods</span></span>

<span data-ttu-id="8f8a3-243">Un ciclo retributivo determina la frequenza di elaborazione delle retribuzioni e i giorni specifici in cui i lavoratori vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-243">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="8f8a3-244">Un ciclo retributivo può essere ad esempio mensile e i dipendenti possono essere pagati l'ultimo giorno del mese.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-244">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="8f8a3-245">Un ciclo retributivo può in alternativa essere settimanale e i dipendenti possono essere pagati il giovedì successivo alla fine del periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-245">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="8f8a3-246">I cicli retributivi vengono assegnati alle posizioni per controllare quando i lavoratori in tali posizioni vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-246">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="8f8a3-247">Dopo aver creato i cicli retributivi, è possibile generare periodi retributivi per ogni ciclo.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-247">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="8f8a3-248">Ogni periodo retributivo include una data di pagamento predefinita in base alle informazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-248">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="8f8a3-249">Tuttavia, è possibile modificare la data di pagamento predefinita in un periodo retributivo per consentire eccezioni, ad esempio quando la data di pagamento cade in un giorno festivo.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-249">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="8f8a3-250">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-250">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="8f8a3-251">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="8f8a3-251">Pay cycle (required)</span></span>
- <span data-ttu-id="8f8a3-252">Frequenza ciclo retributivo (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-252">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="8f8a3-253">Data di inizio del periodo (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-253">Period start date (first pay period required)</span></span>
- <span data-ttu-id="8f8a3-254">Data di pagamento predefinita (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-254">Default payment date (first pay period required)</span></span>

<span data-ttu-id="8f8a3-255">Queste informazioni sono integrate con Dayforce come gruppi retributivi e sono separata in base al paese o alla regione per ogni ciclo retributivo.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-255">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="8f8a3-256">Prima dell'integrazione è necessario generare almeno un periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-256">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="8f8a3-257">Dayforce genera calendari di gruppi retributivi e date di pagamento, in base alla data di inizio del primo periodo retributivo e alla data di pagamento predefinita che viene impostata in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-257">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="8f8a3-258">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="8f8a3-258">Earning codes</span></span>

<span data-ttu-id="8f8a3-259">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-259">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="8f8a3-260">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-260">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="8f8a3-261">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-261">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="8f8a3-262">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-262">Earning Code (required)</span></span>
- <span data-ttu-id="8f8a3-263">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-263">Description</span></span>
- <span data-ttu-id="8f8a3-264">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="8f8a3-264">Unit of measure</span></span>
- <span data-ttu-id="8f8a3-265">Produttivo</span><span class="sxs-lookup"><span data-stu-id="8f8a3-265">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="8f8a3-266">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-266">Worker data</span></span>

<span data-ttu-id="8f8a3-267">I record per i diversi tipi di lavoratori a disposizione sono importanti per i sistemi di gestione delle risorse umane e delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-267">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="8f8a3-268">Le informazioni immesse possono essere utilizzate per tenere traccia di informazioni personali e sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-268">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="8f8a3-269">È possibile gestire le seguenti informazioni per i lavoratori:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-269">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="8f8a3-270">**Base** - Gestire le informazioni di base su un lavoratore, ad esempio le informazioni sui contatti, le informazioni demografiche, le informazioni di identificazione, le informazioni sulla famiglia, lo stato di servizio militare, le informazioni sull'espatrio, e i contatti personali e di emergenza.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-270">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="8f8a3-271">**Impiego** - Consente di gestire le informazioni sull'impiego di un lavoratore, ad esempio rapporto con l'organizzazione o la società, assegnazione della posizione, date di inizio e fine, idoneità al lavoro, condizioni di impiego, pensionamento, ferie e trasferimento.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-271">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="8f8a3-272">**Congedo e assenza** - Consente di gestire le informazioni sulle assenze di un lavoratore, ad esempio calendari di lavoro, transazioni assenze e impostazione assenze.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-272">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="8f8a3-273">**Retribuzioni** - Consente di gestire le informazioni sui piani di retribuzione di un lavoratore, ad esempio registrazione del piano, premi, prestazioni, provvigione, dati fiscali, pensionamento e detrazioni sullo stipendio.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-273">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="8f8a3-274">Quando si immettono le informazioni su un lavoratore, tenere presenti i seguenti dati e le configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-274">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="8f8a3-275">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="8f8a3-275">General information</span></span>

- <span data-ttu-id="8f8a3-276">Numero dipendente (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-276">Personnel number (required)</span></span>
- <span data-ttu-id="8f8a3-277">Nome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-277">First name (required)</span></span>
- <span data-ttu-id="8f8a3-278">Cognome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-278">Last name (required)</span></span>
- <span data-ttu-id="8f8a3-279">Secondo nome</span><span class="sxs-lookup"><span data-stu-id="8f8a3-279">Middle name</span></span>
- <span data-ttu-id="8f8a3-280">Data di anzianità</span><span class="sxs-lookup"><span data-stu-id="8f8a3-280">Seniority date</span></span>
- <span data-ttu-id="8f8a3-281">Nome noto</span><span class="sxs-lookup"><span data-stu-id="8f8a3-281">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="8f8a3-282">Informazioni personali</span><span class="sxs-lookup"><span data-stu-id="8f8a3-282">Personal information</span></span>

- <span data-ttu-id="8f8a3-283">Stato civile (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-283">Marital status (required)</span></span>
- <span data-ttu-id="8f8a3-284">Data di nascita (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-284">Birth date (required)</span></span>
- <span data-ttu-id="8f8a3-285">Sesso (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-285">Gender (required)</span></span>
- <span data-ttu-id="8f8a3-286">Persona disabile</span><span class="sxs-lookup"><span data-stu-id="8f8a3-286">Person with disabilities</span></span>
- <span data-ttu-id="8f8a3-287">Nazionalità paese regione (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-287">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="8f8a3-288">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="8f8a3-288">Address information</span></span>

- <span data-ttu-id="8f8a3-289">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-289">Primary (required)</span></span>
- <span data-ttu-id="8f8a3-290">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-290">Country/region (required)</span></span>
- <span data-ttu-id="8f8a3-291">Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-291">Postal code (required)</span></span>
- <span data-ttu-id="8f8a3-292">Numero civico (obbligatorio) (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-292">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="8f8a3-293">Informazioni aggiuntive sull'indirizzo (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-293">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="8f8a3-294">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-294">City (required)</span></span>
- <span data-ttu-id="8f8a3-295">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-295">State (required)</span></span>
- <span data-ttu-id="8f8a3-296">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-296">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="8f8a3-297">Informazioni contatto</span><span class="sxs-lookup"><span data-stu-id="8f8a3-297">Contact information</span></span> 

- <span data-ttu-id="8f8a3-298">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-298">Primary (required)</span></span>
- <span data-ttu-id="8f8a3-299">Numero contatto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-299">Contact number (required)</span></span>
- <span data-ttu-id="8f8a3-300">Interno</span><span class="sxs-lookup"><span data-stu-id="8f8a3-300">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="8f8a3-301">Informazioni sulle retribuzioni e codici di reddito</span><span class="sxs-lookup"><span data-stu-id="8f8a3-301">Payroll information and earning codes</span></span>

<span data-ttu-id="8f8a3-302">Ai dipendenti possono essere assegnati redditi specifici a una determinata frequenza di pagamento e un metodo di pagamento preferito.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-302">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="8f8a3-303">I campi seguenti vengono utilizzati in Dayforce per garantire che le preferenze e le impostazioni vengano utilizzate.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-303">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="8f8a3-304">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="8f8a3-304">Earning codes</span></span>

- <span data-ttu-id="8f8a3-305">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-305">Position (required)</span></span>
- <span data-ttu-id="8f8a3-306">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-306">Earning Code (required)</span></span>
- <span data-ttu-id="8f8a3-307">Frequenza (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-307">Frequency (required)</span></span>
- <span data-ttu-id="8f8a3-308">Importo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-308">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="8f8a3-309">Informazioni retribuzioni</span><span class="sxs-lookup"><span data-stu-id="8f8a3-309">Payroll information</span></span>

- <span data-ttu-id="8f8a3-310">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="8f8a3-310">Payment Method</span></span>
- <span data-ttu-id="8f8a3-311">Area economica (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-311">Economic Region (required)</span></span>
- <span data-ttu-id="8f8a3-312">ID benefit dipendente</span><span class="sxs-lookup"><span data-stu-id="8f8a3-312">Employee Benefits ID</span></span>
- <span data-ttu-id="8f8a3-313">Numero documento identità (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-313">National ID Number (required)</span></span>
- <span data-ttu-id="8f8a3-314">Numero servizio militare</span><span class="sxs-lookup"><span data-stu-id="8f8a3-314">Military Service Number</span></span>
- <span data-ttu-id="8f8a3-315">ID turno (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-315">Shift ID (required)</span></span>
- <span data-ttu-id="8f8a3-316">Numero imposta (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-316">Tax Number (required)</span></span>
- <span data-ttu-id="8f8a3-317">ID sindacato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-317">Union ID (required)</span></span>
- <span data-ttu-id="8f8a3-318">ID giorno lavorativo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-318">Work Day ID (required)</span></span>
- <span data-ttu-id="8f8a3-319">Numero permesso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8f8a3-319">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="8f8a3-320">Per il metodo di pagamento, il Messico supporta **Contante**, **Assegno** (l'assegno fisico della società) e **Pagamento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-320">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="8f8a3-321">Se non viene specificato alcun metodo di pagamento, **Assegno** è 'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-321">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="8f8a3-322">Dettagli impiego</span><span class="sxs-lookup"><span data-stu-id="8f8a3-322">Employment details</span></span>

<span data-ttu-id="8f8a3-323">Lo storico dei dettagli impiego viene utilizzato come informazioni chiave da cui derivare gli stati di assunzione, termine e riassunzione di un dipendente Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-323">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="8f8a3-324">Dayforce supporta solo un record di impiego attivo alla volta.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-324">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="8f8a3-325">Data di inizio impiego (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-325">Employment start date (required)</span></span>
- <span data-ttu-id="8f8a3-326">Data di fine impiego</span><span class="sxs-lookup"><span data-stu-id="8f8a3-326">Employment end date</span></span>
- <span data-ttu-id="8f8a3-327">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="8f8a3-327">Start date</span></span>
- <span data-ttu-id="8f8a3-328">Data di inizio rettificata</span><span class="sxs-lookup"><span data-stu-id="8f8a3-328">Adjusted start date</span></span>
- <span data-ttu-id="8f8a3-329">Data fine rapporto (obbligatoria con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-329">Termination date (required upon termination)</span></span>
- <span data-ttu-id="8f8a3-330">Motivo fine rapporto (obbligatorio con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-330">Termination reason (required upon termination)</span></span>

<span data-ttu-id="8f8a3-331">Le date chiave del dipendente sono derivate utilizzando le informazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-331">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="8f8a3-332">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="8f8a3-332">Human Resources</span></span>                | <span data-ttu-id="8f8a3-333">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8f8a3-333">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8f8a3-334">Data di assunzione più recente</span><span class="sxs-lookup"><span data-stu-id="8f8a3-334">Most recent hire date</span></span> | <span data-ttu-id="8f8a3-335">Inizio dell'impiego del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="8f8a3-335">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="8f8a3-336">Data fine rapporto</span><span class="sxs-lookup"><span data-stu-id="8f8a3-336">Termination date</span></span>      | <span data-ttu-id="8f8a3-337">Data di fine rapporto del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="8f8a3-337">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="8f8a3-338">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="8f8a3-338">Start date</span></span>            | <span data-ttu-id="8f8a3-339">Data di inizio rettificata, data di inizio o inizio dell'impiego del record corrente dello storico di impiego non attivo</span><span class="sxs-lookup"><span data-stu-id="8f8a3-339">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="8f8a3-340">Data di assunzione originale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-340">Original hire date</span></span>    | <span data-ttu-id="8f8a3-341">Inizio dell'impiego del record dello storico di impiego meno recente</span><span class="sxs-lookup"><span data-stu-id="8f8a3-341">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="8f8a3-342">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-342">Compensation</span></span>

<span data-ttu-id="8f8a3-343">Un piano di retribuzione fissa deve essere associato alla posizione primaria di ogni dipendente durante un periodo di impiego.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-343">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="8f8a3-344">Questo periodo inizia alla data in cui il dipendente è stato assunto (o la data di inizio dell'impiego) e continua fino alla fine del rapporto.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-344">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="8f8a3-345">Data di validità (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-345">Effective Date (required)</span></span>
- <span data-ttu-id="8f8a3-346">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="8f8a3-346">Expiration date</span></span>
- <span data-ttu-id="8f8a3-347">Retribuzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-347">Pay Rate (required)</span></span>
- <span data-ttu-id="8f8a3-348">Conversioni retribuzione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-348">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="8f8a3-349">Equivalente annuale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-349">Annual equivalent (required)</span></span>
- <span data-ttu-id="8f8a3-350">Equivalente orario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-350">Hourly equivalent (required)</span></span>

<span data-ttu-id="8f8a3-351">Se un dipendente a ore ha più posizioni, la retribuzione fissa della posizione primaria viene importata in Dayforce come il tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-351">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="8f8a3-352">Per le posizioni non principali, la tariffa oraria viene salvata nella posizione corrispondente in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-352">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="8f8a3-353">Se un dipendente stipendiato ha più posizioni, la tariffa oraria cumulativa e lo stipendio annuale di tutte le posizioni attive vengono calcolati e utilizzati come tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-353">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="8f8a3-354">Numeri di identificazione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-354">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="8f8a3-355">Numero di Previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-355">Social Security identifier</span></span> 

<span data-ttu-id="8f8a3-356">Ogni dipendente deve avere un identificatore primario.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-356">Every employee must have one primary identifier.</span></span> <span data-ttu-id="8f8a3-357">Questo identificatore deve essere di tipo identificatore **SSN**.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-357">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="8f8a3-358">In Dayforce, viene ricavato automaticamente come identificatore di previdenza sociale del dipendente per l'assunzione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-358">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="8f8a3-359">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-359">Primary (required)</span></span>
- <span data-ttu-id="8f8a3-360">Tipo di identificazione = "SSN"</span><span class="sxs-lookup"><span data-stu-id="8f8a3-360">Identification Type = "SSN"</span></span>
- <span data-ttu-id="8f8a3-361">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-361">Issued Date</span></span>
- <span data-ttu-id="8f8a3-362">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="8f8a3-362">Expiration Date</span></span>

<span data-ttu-id="8f8a3-363">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **SSN**.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-363">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="8f8a3-364">Tuttavia, solo il record che è contrassegnato come **Primario** viene integrato in Dayforce, a prescindere che il numero sia attivo o scaduto.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-364">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="8f8a3-365">Esborsi e conti bancari</span><span class="sxs-lookup"><span data-stu-id="8f8a3-365">Bank accounts and disbursements</span></span>

<span data-ttu-id="8f8a3-366">È necessario immettere informazioni sul conto bancario valide per un dipendente che scelga di essere pagato tramite trasferimenti di conto bancario.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-366">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="8f8a3-367">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="8f8a3-367">Human Resources</span></span>                         | <span data-ttu-id="8f8a3-368">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8f8a3-368">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8f8a3-369">Numero conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-369">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="8f8a3-370">Codice SWIFT (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-370">SWIFT code (required)</span></span>          | <span data-ttu-id="8f8a3-371">Campo **ID banca** utilizzato durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-371">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="8f8a3-372">Codice filiale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-372">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="8f8a3-373">Tipo di conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-373">Bank account type (required)</span></span>   | <span data-ttu-id="8f8a3-374">Campo **Tipo di conto** utilizzando durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-374">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="8f8a3-375">I valori supportati includono **Controllo** e **Retribuzioni**.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-375">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="8f8a3-376">I dipendenti che scelgono di essere pagati tramite trasferimenti di conto bancario devono fornire un collegamento a un conto rimanente che è sotto la persona giuridica che ha l'indirizzo primario in Messico ed è associato a un conto bancario valido presso una banca messicana.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-376">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="8f8a3-377">Tutti gli altri account non di rimanenze verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-377">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="8f8a3-378">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="8f8a3-378">Address information</span></span>

<span data-ttu-id="8f8a3-379">Ogni dipendente deve avere un'ubicazione primaria.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-379">Every employee must have one primary location.</span></span> <span data-ttu-id="8f8a3-380">In Dayforce, questa ubicazione viene utilizzata per determinare la principale residenza del dipendente a scopo fiscale.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-380">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="8f8a3-381">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-381">Primary (required)</span></span>
- <span data-ttu-id="8f8a3-382">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-382">Country/region (required)</span></span>
- <span data-ttu-id="8f8a3-383">CAP/Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-383">Zip/postal code (required)</span></span>
- <span data-ttu-id="8f8a3-384">Via (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-384">Street (required)</span></span>
- <span data-ttu-id="8f8a3-385">Numero civico (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-385">Street Number (required)</span></span>
- <span data-ttu-id="8f8a3-386">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="8f8a3-386">Building Complement</span></span>
- <span data-ttu-id="8f8a3-387">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-387">City (required)</span></span>
- <span data-ttu-id="8f8a3-388">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-388">State (required)</span></span>
- <span data-ttu-id="8f8a3-389">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-389">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="8f8a3-390">Configurare i dati per generare le retribuzioni negli Stati Uniti e in Canada</span><span class="sxs-lookup"><span data-stu-id="8f8a3-390">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="8f8a3-391">Se si desidera generare la retribuzione per i dipendenti negli Stati Uniti e in Canada, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-391">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="8f8a3-392">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-392">Departments are required on positions.</span></span>
- <span data-ttu-id="8f8a3-393">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-393">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="8f8a3-394">È possibile configurare Human Resources per far sì che Posizioni specifichi un reparto.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-394">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="8f8a3-395">A tale scopo, andare a **Posizioni condivise Risorse umane > Posizioni > Richiedi reparti su posizioni**.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-395">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="8f8a3-396">Si consiglia di applicare questa impostazione per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-396">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="8f8a3-397">Tipi di lavoro</span><span class="sxs-lookup"><span data-stu-id="8f8a3-397">Job types</span></span>

<span data-ttu-id="8f8a3-398">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-398">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="8f8a3-399">I tipi di mansione sono necessari per elaborare le retribuzioni negli Stati Uniti e in Canada.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-399">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="8f8a3-400">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-400">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="8f8a3-401">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-401">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="8f8a3-402">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-402">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="8f8a3-403">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="8f8a3-403">Job type</span></span>   | <span data-ttu-id="8f8a3-404">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-404">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="8f8a3-405">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="8f8a3-405">Hourly</span></span>     | <span data-ttu-id="8f8a3-406">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="8f8a3-406">Hourly</span></span>      |
| <span data-ttu-id="8f8a3-407">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="8f8a3-407">Salaried</span></span>   | <span data-ttu-id="8f8a3-408">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="8f8a3-408">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="8f8a3-409">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-409">Position types</span></span> 

<span data-ttu-id="8f8a3-410">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-410">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="8f8a3-411">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-411">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="8f8a3-412">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-412">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="8f8a3-413">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-413">Position type</span></span>   | <span data-ttu-id="8f8a3-414">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-414">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="8f8a3-415">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="8f8a3-415">Full-time</span></span>       | <span data-ttu-id="8f8a3-416">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="8f8a3-416">Full time employee</span></span> |
| <span data-ttu-id="8f8a3-417">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-417">Part-time</span></span>       | <span data-ttu-id="8f8a3-418">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-418">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="8f8a3-419">Codici causale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-419">Reason codes</span></span>

<span data-ttu-id="8f8a3-420">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-420">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="8f8a3-421">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-421">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="8f8a3-422">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-422">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="8f8a3-423">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="8f8a3-423">Reason code</span></span>    | <span data-ttu-id="8f8a3-424">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-424">Description</span></span>      | <span data-ttu-id="8f8a3-425">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="8f8a3-425">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="8f8a3-426">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="8f8a3-426">RESIGNATION</span></span>    | <span data-ttu-id="8f8a3-427">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="8f8a3-427">Resignation</span></span>      | <span data-ttu-id="8f8a3-428">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-428">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-429">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="8f8a3-429">TERMINATION</span></span>    | <span data-ttu-id="8f8a3-430">Fine</span><span class="sxs-lookup"><span data-stu-id="8f8a3-430">Termination</span></span>      | <span data-ttu-id="8f8a3-431">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-431">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-432">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="8f8a3-432">RETIREMENT</span></span>     | <span data-ttu-id="8f8a3-433">Pensione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-433">Retirement</span></span>       | <span data-ttu-id="8f8a3-434">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-434">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-435">OTHER</span><span class="sxs-lookup"><span data-stu-id="8f8a3-435">OTHER</span></span>          | <span data-ttu-id="8f8a3-436">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="8f8a3-436">Other Reasons</span></span>    | <span data-ttu-id="8f8a3-437">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-437">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-438">DEATH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-438">DEATH</span></span>          | <span data-ttu-id="8f8a3-439">Decesso</span><span class="sxs-lookup"><span data-stu-id="8f8a3-439">Death</span></span>            | <span data-ttu-id="8f8a3-440">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-440">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-441">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="8f8a3-441">LEAVEOFABSENCE</span></span> | <span data-ttu-id="8f8a3-442">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="8f8a3-442">Leave of Absence</span></span> | <span data-ttu-id="8f8a3-443">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-443">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-444">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="8f8a3-444">CONTRACTEND</span></span>    | <span data-ttu-id="8f8a3-445">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="8f8a3-445">End of Contract</span></span>  | <span data-ttu-id="8f8a3-446">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-446">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-447">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="8f8a3-447">SALARYCHANGE</span></span>   | <span data-ttu-id="8f8a3-448">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="8f8a3-448">Change of Salary</span></span> | <span data-ttu-id="8f8a3-449">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-449">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="8f8a3-450">Stato civile</span><span class="sxs-lookup"><span data-stu-id="8f8a3-450">Marital status</span></span>

<span data-ttu-id="8f8a3-451">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-451">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="8f8a3-452">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-452">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="8f8a3-453">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="8f8a3-453">Human Resources</span></span>                 | <span data-ttu-id="8f8a3-454">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8f8a3-454">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="8f8a3-455">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="8f8a3-455">Married</span></span>                | <span data-ttu-id="8f8a3-456">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="8f8a3-456">Married</span></span>              |
| <span data-ttu-id="8f8a3-457">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="8f8a3-457">Single</span></span>                 | <span data-ttu-id="8f8a3-458">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="8f8a3-458">Single</span></span>               |
| <span data-ttu-id="8f8a3-459">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="8f8a3-459">Widowed</span></span>                | <span data-ttu-id="8f8a3-460">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="8f8a3-460">Widowed</span></span>              |
| <span data-ttu-id="8f8a3-461">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="8f8a3-461">Divorced</span></span>               | <span data-ttu-id="8f8a3-462">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="8f8a3-462">Divorced</span></span>             |
| <span data-ttu-id="8f8a3-463">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="8f8a3-463">Registered Partnership</span></span> | <span data-ttu-id="8f8a3-464">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-464">Domestic Partnership</span></span> |
| <span data-ttu-id="8f8a3-465">Nessuna</span><span class="sxs-lookup"><span data-stu-id="8f8a3-465">None</span></span>                   | <span data-ttu-id="8f8a3-466">Nessuna</span><span class="sxs-lookup"><span data-stu-id="8f8a3-466">None</span></span>                 |
| <span data-ttu-id="8f8a3-467">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-467">Cohabiting</span></span>             | <span data-ttu-id="8f8a3-468">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-468">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="8f8a3-469">Genere</span><span class="sxs-lookup"><span data-stu-id="8f8a3-469">Gender</span></span>

<span data-ttu-id="8f8a3-470">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-470">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="8f8a3-471">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-471">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="8f8a3-472">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="8f8a3-472">Human Resources</span></span>       | <span data-ttu-id="8f8a3-473">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8f8a3-473">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="8f8a3-474">Maschio</span><span class="sxs-lookup"><span data-stu-id="8f8a3-474">Male</span></span>         | <span data-ttu-id="8f8a3-475">Maschio</span><span class="sxs-lookup"><span data-stu-id="8f8a3-475">Male</span></span>            |
| <span data-ttu-id="8f8a3-476">Femmina</span><span class="sxs-lookup"><span data-stu-id="8f8a3-476">Female</span></span>       | <span data-ttu-id="8f8a3-477">Femmina</span><span class="sxs-lookup"><span data-stu-id="8f8a3-477">Female</span></span>          |
| <span data-ttu-id="8f8a3-478">Non specifico</span><span class="sxs-lookup"><span data-stu-id="8f8a3-478">Non-specific</span></span> | <span data-ttu-id="8f8a3-479">*Non supportato*</span><span class="sxs-lookup"><span data-stu-id="8f8a3-479">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="8f8a3-480">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="8f8a3-480">Earning codes</span></span>

<span data-ttu-id="8f8a3-481">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-481">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="8f8a3-482">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-482">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="8f8a3-483">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-483">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="8f8a3-484">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="8f8a3-484">Supported frequencies</span></span>

- <span data-ttu-id="8f8a3-485">Tutti</span><span class="sxs-lookup"><span data-stu-id="8f8a3-485">All</span></span>
- <span data-ttu-id="8f8a3-486">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="8f8a3-486">EVERYPAY</span></span>
- <span data-ttu-id="8f8a3-487">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="8f8a3-487">EACHPAYPERIOD</span></span>
- <span data-ttu-id="8f8a3-488">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="8f8a3-488">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="8f8a3-489">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="8f8a3-489">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="8f8a3-490">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-490">1OFMTH</span></span>
- <span data-ttu-id="8f8a3-491">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-491">LASTOFMTH</span></span>
- <span data-ttu-id="8f8a3-492">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-492">2OFMTH</span></span>
- <span data-ttu-id="8f8a3-493">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-493">3OFMTH</span></span>
- <span data-ttu-id="8f8a3-494">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-494">4OFMTH</span></span>
- <span data-ttu-id="8f8a3-495">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-495">5OFMTH</span></span>
- <span data-ttu-id="8f8a3-496">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-496">1N2OFMTH</span></span>
- <span data-ttu-id="8f8a3-497">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-497">3N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-498">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-498">1N3OFMTH</span></span>
- <span data-ttu-id="8f8a3-499">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-499">1N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-500">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-500">2N3OFMTH</span></span>
- <span data-ttu-id="8f8a3-501">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-501">2N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-502">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-502">1N2N3OFMTH</span></span>
- <span data-ttu-id="8f8a3-503">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-503">1N2N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-504">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-504">1N3N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-505">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-505">2N3N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-507">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="8f8a3-507">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="8f8a3-508">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="8f8a3-508">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="8f8a3-509">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="8f8a3-509">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="8f8a3-510">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="8f8a3-510">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="8f8a3-511">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="8f8a3-511">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="8f8a3-512">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="8f8a3-512">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="8f8a3-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="8f8a3-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="8f8a3-514">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="8f8a3-514">Addresses</span></span>

<span data-ttu-id="8f8a3-515">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-515">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="8f8a3-516">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-516">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="8f8a3-517">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="8f8a3-517">Human Resources</span></span>          | <span data-ttu-id="8f8a3-518">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8f8a3-518">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="8f8a3-519">Paese/area geografica</span><span class="sxs-lookup"><span data-stu-id="8f8a3-519">Country/Region</span></span>  | <span data-ttu-id="8f8a3-520">Codice paese</span><span class="sxs-lookup"><span data-stu-id="8f8a3-520">Country Code</span></span>          |
| <span data-ttu-id="8f8a3-521">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-521">Zip/Postal Code</span></span> | <span data-ttu-id="8f8a3-522">CAP</span><span class="sxs-lookup"><span data-stu-id="8f8a3-522">Postal Code</span></span>           |
| <span data-ttu-id="8f8a3-523">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-523">State</span></span>           | <span data-ttu-id="8f8a3-524">Codice stato</span><span class="sxs-lookup"><span data-stu-id="8f8a3-524">State Code</span></span>            |
| <span data-ttu-id="8f8a3-525">Città</span><span class="sxs-lookup"><span data-stu-id="8f8a3-525">City</span></span>            | <span data-ttu-id="8f8a3-526">Città</span><span class="sxs-lookup"><span data-stu-id="8f8a3-526">City</span></span>                  |
| <span data-ttu-id="8f8a3-527">Regione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-527">County</span></span>          | <span data-ttu-id="8f8a3-528">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-528">County (Municipality)</span></span> |
| <span data-ttu-id="8f8a3-529">Via</span><span class="sxs-lookup"><span data-stu-id="8f8a3-529">Street</span></span>          | <span data-ttu-id="8f8a3-530">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="8f8a3-530">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="8f8a3-531">Regioni fiscali</span><span class="sxs-lookup"><span data-stu-id="8f8a3-531">Tax regions</span></span>

<span data-ttu-id="8f8a3-532">Le regioni fiscali vengono utilizzate per determinare l'imposta appropriata che deve essere applicata durante la generazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-532">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="8f8a3-533">Le regioni fiscali vengono mappate in Dayforce come indirizzi di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-533">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="8f8a3-534">La regione fiscale predefinita deve essere associata alla posizione attiva del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-534">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="8f8a3-535">Regione fiscale (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-535">Tax region (required)</span></span>
- <span data-ttu-id="8f8a3-536">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-536">Country/Region (required)</span></span>
- <span data-ttu-id="8f8a3-537">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-537">State (required)</span></span>
- <span data-ttu-id="8f8a3-538">Regione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-538">County</span></span> 
- <span data-ttu-id="8f8a3-539">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-539">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="8f8a3-540">Configurare i dati per generare le retribuzioni in Messico</span><span class="sxs-lookup"><span data-stu-id="8f8a3-540">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="8f8a3-541">Se si desidera generare la retribuzione per i dipendenti in Messico, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="8f8a3-541">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="8f8a3-542">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-542">Departments are required on positions.</span></span>
- <span data-ttu-id="8f8a3-543">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-543">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="8f8a3-544">Tipi di posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="8f8a3-544">Job types</span></span>

<span data-ttu-id="8f8a3-545">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-545">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="8f8a3-546">Tipi di mansione necessari per elaborare le retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-546">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="8f8a3-547">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-547">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="8f8a3-548">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-548">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="8f8a3-549">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-549">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="8f8a3-550">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="8f8a3-550">Job type</span></span>   | <span data-ttu-id="8f8a3-551">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-551">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="8f8a3-552">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="8f8a3-552">Hourly</span></span>     | <span data-ttu-id="8f8a3-553">Su base oraria MX</span><span class="sxs-lookup"><span data-stu-id="8f8a3-553">MX Hourly</span></span>   |
| <span data-ttu-id="8f8a3-554">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="8f8a3-554">Salaried</span></span>   | <span data-ttu-id="8f8a3-555">Stipendiato MX</span><span class="sxs-lookup"><span data-stu-id="8f8a3-555">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="8f8a3-556">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-556">Position types</span></span> 

<span data-ttu-id="8f8a3-557">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-557">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="8f8a3-558">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-558">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="8f8a3-559">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-559">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="8f8a3-560">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-560">Position type</span></span>   | <span data-ttu-id="8f8a3-561">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-561">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="8f8a3-562">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="8f8a3-562">Full-time</span></span>       | <span data-ttu-id="8f8a3-563">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="8f8a3-563">Full time employee</span></span> |
| <span data-ttu-id="8f8a3-564">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-564">Part-time</span></span>       | <span data-ttu-id="8f8a3-565">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-565">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="8f8a3-566">Codici causale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-566">Reason codes</span></span>

<span data-ttu-id="8f8a3-567">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-567">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="8f8a3-568">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-568">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="8f8a3-569">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-569">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="8f8a3-570">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="8f8a3-570">Reason code</span></span>            | <span data-ttu-id="8f8a3-571">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-571">Description</span></span>                    | <span data-ttu-id="8f8a3-572">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="8f8a3-572">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="8f8a3-573">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="8f8a3-573">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="8f8a3-574">Partenza prima della prima retribuzione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-574">Departure before first payroll</span></span> | <span data-ttu-id="8f8a3-575">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-575">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-576">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="8f8a3-576">RESIGNATION</span></span>            | <span data-ttu-id="8f8a3-577">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="8f8a3-577">Resignation</span></span>                    | <span data-ttu-id="8f8a3-578">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-578">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-579">PENSION</span><span class="sxs-lookup"><span data-stu-id="8f8a3-579">PENSION</span></span>                | <span data-ttu-id="8f8a3-580">Pensionamento</span><span class="sxs-lookup"><span data-stu-id="8f8a3-580">Pension</span></span>                        | <span data-ttu-id="8f8a3-581">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-581">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-582">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="8f8a3-582">TERMINATION</span></span>            | <span data-ttu-id="8f8a3-583">Fine</span><span class="sxs-lookup"><span data-stu-id="8f8a3-583">Termination</span></span>                    | <span data-ttu-id="8f8a3-584">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-584">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-585">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="8f8a3-585">RETIREMENT</span></span>             | <span data-ttu-id="8f8a3-586">Pensione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-586">Retirement</span></span>                     | <span data-ttu-id="8f8a3-587">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-587">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-588">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="8f8a3-588">ABSENTEE</span></span>               | <span data-ttu-id="8f8a3-589">Assente</span><span class="sxs-lookup"><span data-stu-id="8f8a3-589">Absentee</span></span>                       | <span data-ttu-id="8f8a3-590">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-590">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-591">OTHER</span><span class="sxs-lookup"><span data-stu-id="8f8a3-591">OTHER</span></span>                  | <span data-ttu-id="8f8a3-592">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="8f8a3-592">Other Reasons</span></span>                  | <span data-ttu-id="8f8a3-593">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-593">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-594">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="8f8a3-594">CLOSURE</span></span>                | <span data-ttu-id="8f8a3-595">Chiusura attività</span><span class="sxs-lookup"><span data-stu-id="8f8a3-595">Business Closure</span></span>               | <span data-ttu-id="8f8a3-596">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-596">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-597">DEATH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-597">DEATH</span></span>                  | <span data-ttu-id="8f8a3-598">Decesso</span><span class="sxs-lookup"><span data-stu-id="8f8a3-598">Death</span></span>                          | <span data-ttu-id="8f8a3-599">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-599">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-600">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="8f8a3-600">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="8f8a3-601">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="8f8a3-601">Leave of Absence</span></span>               | <span data-ttu-id="8f8a3-602">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-602">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-603">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="8f8a3-603">CONTRACTEND</span></span>            | <span data-ttu-id="8f8a3-604">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="8f8a3-604">End of Contract</span></span>                | <span data-ttu-id="8f8a3-605">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="8f8a3-605">Terminate worker</span></span>     |
| <span data-ttu-id="8f8a3-606">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="8f8a3-606">SALARYCHANGE</span></span>           | <span data-ttu-id="8f8a3-607">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="8f8a3-607">Change of Salary</span></span>               | <span data-ttu-id="8f8a3-608">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-608">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="8f8a3-609">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="8f8a3-609">Terms of employment</span></span>

<span data-ttu-id="8f8a3-610">Le condizioni di impiego vengono utilizzate per creare categorie di termini di impiego.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-610">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="8f8a3-611">I termini vengono mappati in Dayforce come valori degli indicatori di impiego.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-611">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="8f8a3-612">I seguenti termini di impiego e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-612">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="8f8a3-613">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="8f8a3-613">Terms of employment</span></span>   | <span data-ttu-id="8f8a3-614">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-614">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="8f8a3-615">Regolare</span><span class="sxs-lookup"><span data-stu-id="8f8a3-615">Regular</span></span>               | <span data-ttu-id="8f8a3-616">Regolare</span><span class="sxs-lookup"><span data-stu-id="8f8a3-616">Regular</span></span>     |
| <span data-ttu-id="8f8a3-617">Diretto</span><span class="sxs-lookup"><span data-stu-id="8f8a3-617">Direct</span></span>                | <span data-ttu-id="8f8a3-618">Diretto</span><span class="sxs-lookup"><span data-stu-id="8f8a3-618">Direct</span></span>      |
| <span data-ttu-id="8f8a3-619">Internato</span><span class="sxs-lookup"><span data-stu-id="8f8a3-619">Internship</span></span>            | <span data-ttu-id="8f8a3-620">Internato</span><span class="sxs-lookup"><span data-stu-id="8f8a3-620">Internship</span></span>  |
| <span data-ttu-id="8f8a3-621">Permanente</span><span class="sxs-lookup"><span data-stu-id="8f8a3-621">Permanent</span></span>             | <span data-ttu-id="8f8a3-622">Permanente</span><span class="sxs-lookup"><span data-stu-id="8f8a3-622">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="8f8a3-623">Stato civile</span><span class="sxs-lookup"><span data-stu-id="8f8a3-623">Marital status</span></span>

<span data-ttu-id="8f8a3-624">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-624">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="8f8a3-625">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-625">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="8f8a3-626">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="8f8a3-626">Human Resources</span></span>                 | <span data-ttu-id="8f8a3-627">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8f8a3-627">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="8f8a3-628">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="8f8a3-628">Married</span></span>                | <span data-ttu-id="8f8a3-629">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="8f8a3-629">Married</span></span>                   |
| <span data-ttu-id="8f8a3-630">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="8f8a3-630">Single</span></span>                 | <span data-ttu-id="8f8a3-631">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="8f8a3-631">Single</span></span>                    |
| <span data-ttu-id="8f8a3-632">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="8f8a3-632">Widowed</span></span>                | <span data-ttu-id="8f8a3-633">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="8f8a3-633">Widowed</span></span>                   |
| <span data-ttu-id="8f8a3-634">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="8f8a3-634">Divorced</span></span>               | <span data-ttu-id="8f8a3-635">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="8f8a3-635">Divorced</span></span>                  |
| <span data-ttu-id="8f8a3-636">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="8f8a3-636">Registered Partnership</span></span> | <span data-ttu-id="8f8a3-637">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-637">Domestic Partnership</span></span>      |
| <span data-ttu-id="8f8a3-638">Nessuna</span><span class="sxs-lookup"><span data-stu-id="8f8a3-638">None</span></span>                   | <span data-ttu-id="8f8a3-639">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="8f8a3-639">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="8f8a3-640">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-640">Cohabiting</span></span>             | <span data-ttu-id="8f8a3-641">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="8f8a3-641">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="8f8a3-642">Genere</span><span class="sxs-lookup"><span data-stu-id="8f8a3-642">Gender</span></span>

<span data-ttu-id="8f8a3-643">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-643">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="8f8a3-644">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-644">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="8f8a3-645">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="8f8a3-645">Human Resources</span></span>       | <span data-ttu-id="8f8a3-646">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8f8a3-646">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="8f8a3-647">Maschio</span><span class="sxs-lookup"><span data-stu-id="8f8a3-647">Male</span></span>         | <span data-ttu-id="8f8a3-648">Maschio</span><span class="sxs-lookup"><span data-stu-id="8f8a3-648">Male</span></span>                      |
| <span data-ttu-id="8f8a3-649">Femmina</span><span class="sxs-lookup"><span data-stu-id="8f8a3-649">Female</span></span>       | <span data-ttu-id="8f8a3-650">Femmina</span><span class="sxs-lookup"><span data-stu-id="8f8a3-650">Female</span></span>                    |
| <span data-ttu-id="8f8a3-651">Non specifico</span><span class="sxs-lookup"><span data-stu-id="8f8a3-651">Non-specific</span></span> | <span data-ttu-id="8f8a3-652">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="8f8a3-652">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="8f8a3-653">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="8f8a3-653">Payment method</span></span>

<span data-ttu-id="8f8a3-654">I metodi di pagamento offrono al dipendente e all'azienda un modo per descrivere la modalità di pagamento dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-654">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="8f8a3-655">I metodi di pagamento vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-655">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="8f8a3-656">Nella tabella seguente vengono illustrati in che modo i metodi di pagamento vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-656">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="8f8a3-657">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="8f8a3-657">Human Resources</span></span>             | <span data-ttu-id="8f8a3-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8f8a3-658">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="8f8a3-659">Contanti</span><span class="sxs-lookup"><span data-stu-id="8f8a3-659">Cash</span></span>               | <span data-ttu-id="8f8a3-660">Contanti</span><span class="sxs-lookup"><span data-stu-id="8f8a3-660">Cash</span></span>                      |
| <span data-ttu-id="8f8a3-661">Pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="8f8a3-661">Electronic Payment</span></span> | <span data-ttu-id="8f8a3-662">Trasferimenti</span><span class="sxs-lookup"><span data-stu-id="8f8a3-662">Transfer</span></span>                  |
| <span data-ttu-id="8f8a3-663">Seleziona</span><span class="sxs-lookup"><span data-stu-id="8f8a3-663">Check</span></span>              | <span data-ttu-id="8f8a3-664">Assegno</span><span class="sxs-lookup"><span data-stu-id="8f8a3-664">Cheque</span></span>                    |
| <span data-ttu-id="8f8a3-665">Assegno circolare</span><span class="sxs-lookup"><span data-stu-id="8f8a3-665">Bank Draft</span></span>         | <span data-ttu-id="8f8a3-666">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="8f8a3-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="8f8a3-667">Altro</span><span class="sxs-lookup"><span data-stu-id="8f8a3-667">Other</span></span>              | <span data-ttu-id="8f8a3-668">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="8f8a3-668">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="8f8a3-669">Tipo di conto bancario</span><span class="sxs-lookup"><span data-stu-id="8f8a3-669">Bank account type</span></span>

<span data-ttu-id="8f8a3-670">I tipi di conto bancario vengono utilizzati per i pagamenti elettronici ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-670">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="8f8a3-671">I tipi di conto bancario vengono mappati in Dayforce come informazioni sul conto di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-671">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="8f8a3-672">I tipi di conto bancario vengono convertiti, come appropriato, nei valori accettati per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-672">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="8f8a3-673">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="8f8a3-673">Human Resources</span></span>            | <span data-ttu-id="8f8a3-674">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8f8a3-674">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="8f8a3-675">Conto corrente</span><span class="sxs-lookup"><span data-stu-id="8f8a3-675">Checking Account</span></span>  | <span data-ttu-id="8f8a3-676">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="8f8a3-676">CheckingAccount</span></span>           |
| <span data-ttu-id="8f8a3-677">Conto retribuzioni</span><span class="sxs-lookup"><span data-stu-id="8f8a3-677">Payroll Account</span></span>   | <span data-ttu-id="8f8a3-678">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="8f8a3-678">PayrollAccount</span></span>            |
| <span data-ttu-id="8f8a3-679">Conto di risparmio</span><span class="sxs-lookup"><span data-stu-id="8f8a3-679">Savings Account</span></span>   | <span data-ttu-id="8f8a3-680">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="8f8a3-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="8f8a3-681">Conto Bankgirot</span><span class="sxs-lookup"><span data-stu-id="8f8a3-681">BankGirot account</span></span> | <span data-ttu-id="8f8a3-682">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="8f8a3-682">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="8f8a3-683">Conto PlusGirot</span><span class="sxs-lookup"><span data-stu-id="8f8a3-683">PlusGirot account</span></span> | <span data-ttu-id="8f8a3-684">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="8f8a3-684">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="8f8a3-685">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="8f8a3-685">Earning codes</span></span>

<span data-ttu-id="8f8a3-686">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-686">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="8f8a3-687">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-687">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="8f8a3-688">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-688">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="8f8a3-689">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="8f8a3-689">Supported frequencies</span></span>

- <span data-ttu-id="8f8a3-690">Tutti</span><span class="sxs-lookup"><span data-stu-id="8f8a3-690">All</span></span>
- <span data-ttu-id="8f8a3-691">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="8f8a3-691">EVERYPAY</span></span>
- <span data-ttu-id="8f8a3-692">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="8f8a3-692">EACHPAYPERIOD</span></span>
- <span data-ttu-id="8f8a3-693">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="8f8a3-693">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="8f8a3-694">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="8f8a3-694">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="8f8a3-695">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-695">1OFMTH</span></span>
- <span data-ttu-id="8f8a3-696">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-696">LASTOFMTH</span></span>
- <span data-ttu-id="8f8a3-697">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-697">2OFMTH</span></span>
- <span data-ttu-id="8f8a3-698">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-698">3OFMTH</span></span>
- <span data-ttu-id="8f8a3-699">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-699">4OFMTH</span></span>
- <span data-ttu-id="8f8a3-700">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-700">5OFMTH</span></span>
- <span data-ttu-id="8f8a3-701">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-701">1N2OFMTH</span></span>
- <span data-ttu-id="8f8a3-702">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-702">3N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-703">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-703">1N3OFMTH</span></span>
- <span data-ttu-id="8f8a3-704">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-704">1N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-705">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-705">2N3OFMTH</span></span>
- <span data-ttu-id="8f8a3-706">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-706">2N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-707">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-707">1N2N3OFMTH</span></span>
- <span data-ttu-id="8f8a3-708">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-708">1N2N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-709">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-709">1N3N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-710">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-710">2N3N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="8f8a3-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="8f8a3-712">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="8f8a3-712">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="8f8a3-713">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="8f8a3-713">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="8f8a3-714">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="8f8a3-714">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="8f8a3-715">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="8f8a3-715">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="8f8a3-716">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="8f8a3-716">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="8f8a3-717">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="8f8a3-717">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="8f8a3-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="8f8a3-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="8f8a3-719">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="8f8a3-719">Addresses</span></span>

<span data-ttu-id="8f8a3-720">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-720">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="8f8a3-721">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-721">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="8f8a3-722">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="8f8a3-722">Human Resources</span></span>              | <span data-ttu-id="8f8a3-723">Dayforce</span><span class="sxs-lookup"><span data-stu-id="8f8a3-723">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="8f8a3-724">Paese/area geografica</span><span class="sxs-lookup"><span data-stu-id="8f8a3-724">Country/Region</span></span>      | <span data-ttu-id="8f8a3-725">Codice paese</span><span class="sxs-lookup"><span data-stu-id="8f8a3-725">Country Code</span></span>          |
| <span data-ttu-id="8f8a3-726">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="8f8a3-726">Zip/Postal Code</span></span>     | <span data-ttu-id="8f8a3-727">CAP</span><span class="sxs-lookup"><span data-stu-id="8f8a3-727">Postal Code</span></span>           |
| <span data-ttu-id="8f8a3-728">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-728">State</span></span>               | <span data-ttu-id="8f8a3-729">Codice stato</span><span class="sxs-lookup"><span data-stu-id="8f8a3-729">State Code</span></span>            |
| <span data-ttu-id="8f8a3-730">Città</span><span class="sxs-lookup"><span data-stu-id="8f8a3-730">City</span></span>                | <span data-ttu-id="8f8a3-731">Città</span><span class="sxs-lookup"><span data-stu-id="8f8a3-731">City</span></span>                  |
| <span data-ttu-id="8f8a3-732">Regione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-732">County</span></span>              | <span data-ttu-id="8f8a3-733">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="8f8a3-733">County (Municipality)</span></span> |
| <span data-ttu-id="8f8a3-734">Via</span><span class="sxs-lookup"><span data-stu-id="8f8a3-734">Street</span></span>              | <span data-ttu-id="8f8a3-735">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="8f8a3-735">Address Line 1</span></span>        |
| <span data-ttu-id="8f8a3-736">Numero civico</span><span class="sxs-lookup"><span data-stu-id="8f8a3-736">Street Number</span></span>       | <span data-ttu-id="8f8a3-737">Riga indirizzo 2</span><span class="sxs-lookup"><span data-stu-id="8f8a3-737">Address Line 2</span></span>        |
| <span data-ttu-id="8f8a3-738">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="8f8a3-738">Building Complement</span></span> | <span data-ttu-id="8f8a3-739">Riga indirizzo 5</span><span class="sxs-lookup"><span data-stu-id="8f8a3-739">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="8f8a3-740">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="8f8a3-740">Passport number</span></span>

<span data-ttu-id="8f8a3-741">I dipendenti possono indicare le informazioni sul passaporto.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-741">Employees can declare passport information.</span></span> <span data-ttu-id="8f8a3-742">Queste informazioni sono del tipo di identificazione **Passaporto** e vengono integrate in Dayforce come parte delle informazioni di un dipendente specifiche per il Messico.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-742">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="8f8a3-743">Tipo di identificazione = "Passaporto"</span><span class="sxs-lookup"><span data-stu-id="8f8a3-743">Identification Type = "Passport"</span></span>
- <span data-ttu-id="8f8a3-744">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="8f8a3-744">Issued Date</span></span>
- <span data-ttu-id="8f8a3-745">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="8f8a3-745">Expiration Date</span></span>

<span data-ttu-id="8f8a3-746">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **Passaporto**.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-746">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="8f8a3-747">Tuttavia, solo l'immissione del passaporto attivo corrente viene integrata in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-747">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="8f8a3-748">Se tutte le immissioni di passaporto sono scadute, in Dayforce viene integrato il passaporto di emissione più recente.</span><span class="sxs-lookup"><span data-stu-id="8f8a3-748">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]