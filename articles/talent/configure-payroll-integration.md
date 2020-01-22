---
title: Configurare l'integrazione delle retribuzioni tra Talent e Dayforce
description: In questo argomento viene descritto come configurare l'integrazione tra Microsoft Dynamics 365 Talent e Ceridian Dayforce in modo da poter elaborare è un ciclo di pagamenti.
author: andreabichsel
manager: AnnBe
ms.date: 06/24/2019
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
ms.openlocfilehash: 075b2bdfa08bb190f66b6d60074e1263feedcf70
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898537"
---
# <a name="configure-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="03e0f-103">Configurare l'integrazione retribuzioni tra Talent e Dayforce</span><span class="sxs-lookup"><span data-stu-id="03e0f-103">Configure payroll integration between Talent and Dayforce</span></span>

<span data-ttu-id="03e0f-104">L'integrazione tra Microsoft Dynamics 365 Talent e Ceridian Dayforce si basa su vari passaggi di configurazione descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="03e0f-104">The integration between Microsoft Dynamics 365 Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="03e0f-105">È necessario configurare l'integrazione sia in Talent che in Dayforce prima di poter elaborare un ciclo di pagamenti.</span><span class="sxs-lookup"><span data-stu-id="03e0f-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="03e0f-106">Quando si utilizza un servizio, ad esempio Dayforce, per completare i cicli di pagamenti, è necessario abilitare l'integrazione in Talent.</span><span class="sxs-lookup"><span data-stu-id="03e0f-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="03e0f-107">L'integrazione richiede dati specifici da Talent.</span><span class="sxs-lookup"><span data-stu-id="03e0f-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="03e0f-108">Di conseguenza, è necessario verificare che i dati che vengono mappati a Dayforce siano configurati in Talent in modo che supporti l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="03e0f-109">L'integrazione utilizza le seguenti categorie generiche di dati:</span><span class="sxs-lookup"><span data-stu-id="03e0f-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="03e0f-110">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="03e0f-110">Human resources data</span></span>
- <span data-ttu-id="03e0f-111">Dati di compensazione</span><span class="sxs-lookup"><span data-stu-id="03e0f-111">Compensation data</span></span>
- <span data-ttu-id="03e0f-112">Data di retribuzione, ad esempio i cicli di pagamenti, i periodi retributivi e i codici reddito</span><span class="sxs-lookup"><span data-stu-id="03e0f-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="03e0f-113">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-113">Worker data</span></span>

<span data-ttu-id="03e0f-114">In questo argomento vengono descritti i passaggi che è necessario completare per abilitare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="03e0f-115">E vengono descritti i tipi di dati e i dettagli di configurazione necessari all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="03e0f-116">Abilitare l'integrazione</span><span class="sxs-lookup"><span data-stu-id="03e0f-116">Enable the integration</span></span>

<span data-ttu-id="03e0f-117">In Talent è necessario attivare l'integrazione e immettere le informazioni di configurazione per connettersi a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="03e0f-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="03e0f-118">Se si desidera che la transazione contabile prodotta venga importata in Microsoft Dynamics 365 Finance, è necessario impostare anche un conto di archiviazione di Microsoft Azure e immettere la stringa di connessione di Archiviazione di Azure in Finance.</span><span class="sxs-lookup"><span data-stu-id="03e0f-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="03e0f-119">Per attivare l'integrazione in Talent, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="03e0f-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="03e0f-120">Nella pagina **Amministrazione sistema** selezionare **Configurazione di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="03e0f-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="03e0f-121">Immettere l'endpoint FTP (File Transfer Protocol) e il percorso protetto della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="03e0f-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="03e0f-122">Immettere il nome utente e la password dell'utente che accederà al percorso protetto dell'endpoint e della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="03e0f-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="03e0f-123">Verificare la connessione, secondo le esigenze, e impostare l'opzione **Abilita integrazione retribuzioni** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="03e0f-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="03e0f-124">Quando l'integrazione viene attivata, vengono creati i file e il pacchetto di esportazione dei dati e viene impostata la frequenza.</span><span class="sxs-lookup"><span data-stu-id="03e0f-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="03e0f-125">È possibile cambiare la frequenza in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="03e0f-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="03e0f-126">Per altre informazioni sugli account di Archiviazione di Azure e sulle stringhe di connessione di Archiviazione di Azure, vedere gli argomenti di Azure seguenti:</span><span class="sxs-lookup"><span data-stu-id="03e0f-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="03e0f-127">Account di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="03e0f-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="03e0f-128">Configurare le stringhe di connessione di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="03e0f-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="03e0f-129">Dettagli tecnici quando l'integrazione delle retribuzioni è attivata</span><span class="sxs-lookup"><span data-stu-id="03e0f-129">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="03e0f-130">L'attivazione dell'integrazione delle retribuzioni comporta due effetti primari:</span><span class="sxs-lookup"><span data-stu-id="03e0f-130">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="03e0f-131">Viene creato un progetto di esportazione di dati denominato "Esportazione integrazione delle retribuzioni".</span><span class="sxs-lookup"><span data-stu-id="03e0f-131">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="03e0f-132">Questo progetto contiene le entità e i campi necessari per l'integrazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="03e0f-132">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="03e0f-133">Per esaminare il progetto, andare a **Amministrazione sistema**, selezionare il riquadro **Gestione dati** e infine aprire il progetto dati dall'elenco di progetti.</span><span class="sxs-lookup"><span data-stu-id="03e0f-133">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="03e0f-134">Questo processo batch esegue il progetto di esportazione dei dati, codifica il pacchetto dati risultante e trasferisce il file del pacchetto dati all'endpoint SFTP configurato nella schermata **Configurazione di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="03e0f-134">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="03e0f-135">Il pacchetto dati trasferito all'endpoint SFTP viene codificato utilizzando una chiave univoca per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="03e0f-135">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="03e0f-136">La chiave è un Azure Key Vault accessibile solo da Ceridian.</span><span class="sxs-lookup"><span data-stu-id="03e0f-136">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="03e0f-137">Non è possibile decrittografare ed esaminare il contenuto del pacchetto dati.</span><span class="sxs-lookup"><span data-stu-id="03e0f-137">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="03e0f-138">Se è necessario esaminare il contenuto del pacchetto dati, esportare manualmente il progetto dati "Esportazione integrazione delle retribuzioni", scaricarlo e quindi aprirlo.</span><span class="sxs-lookup"><span data-stu-id="03e0f-138">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="03e0f-139">L'esportazione manuale non comporta la crittografia o il trasferimento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="03e0f-139">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="03e0f-140">Configurare i dati</span><span class="sxs-lookup"><span data-stu-id="03e0f-140">Configure your data</span></span> 

<span data-ttu-id="03e0f-141">Per elaborare le retribuzioni, è necessario configurare i dati di Risorse umane in Talent.</span><span class="sxs-lookup"><span data-stu-id="03e0f-141">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="03e0f-142">È necessario impostare i dati dell'organizzazione, ad esempio mansioni e posizioni, insieme alle informazioni sui benefit e sulle compensazioni.</span><span class="sxs-lookup"><span data-stu-id="03e0f-142">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="03e0f-143">Queste informazioni includono informazioni sull'impiego, la retribuzione e le detrazioni che sono richieste per generare la retribuzione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="03e0f-143">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="03e0f-144">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="03e0f-144">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="03e0f-145">Benefit</span><span class="sxs-lookup"><span data-stu-id="03e0f-145">Benefits</span></span> 

<span data-ttu-id="03e0f-146">Le risorse umane dispongono di strumenti per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori.</span><span class="sxs-lookup"><span data-stu-id="03e0f-146">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="03e0f-147">Quando si creano i benefit, tenere presenti i seguenti dati e configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="03e0f-147">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="03e0f-148">Piani di benefit</span><span class="sxs-lookup"><span data-stu-id="03e0f-148">Benefit plans</span></span>

- <span data-ttu-id="03e0f-149">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-149">Plan (required)</span></span>
- <span data-ttu-id="03e0f-150">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-150">Type (required)</span></span>
- <span data-ttu-id="03e0f-151">Impatto retribuzioni (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-151">Payroll impact (required)</span></span>
- <span data-ttu-id="03e0f-152">Recupera arretrati</span><span class="sxs-lookup"><span data-stu-id="03e0f-152">Recover arrears</span></span>
- <span data-ttu-id="03e0f-153">Metodo di detrazione</span><span class="sxs-lookup"><span data-stu-id="03e0f-153">Deduction method</span></span>
- <span data-ttu-id="03e0f-154">Priorità detrazione</span><span class="sxs-lookup"><span data-stu-id="03e0f-154">Deduction priority</span></span>
- <span data-ttu-id="03e0f-155">Periodo limite</span><span class="sxs-lookup"><span data-stu-id="03e0f-155">Limit period</span></span>
- <span data-ttu-id="03e0f-156">Importo limite</span><span class="sxs-lookup"><span data-stu-id="03e0f-156">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="03e0f-157">Benefit</span><span class="sxs-lookup"><span data-stu-id="03e0f-157">Benefits</span></span>

- <span data-ttu-id="03e0f-158">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-158">Plan (required)</span></span>
- <span data-ttu-id="03e0f-159">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-159">Type (required)</span></span>
- <span data-ttu-id="03e0f-160">Opzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-160">Option (required)</span></span>
- <span data-ttu-id="03e0f-161">ID benefit (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-161">Benefit ID (required)</span></span>
- <span data-ttu-id="03e0f-162">Frequenza</span><span class="sxs-lookup"><span data-stu-id="03e0f-162">Frequency</span></span>
- <span data-ttu-id="03e0f-163">Base</span><span class="sxs-lookup"><span data-stu-id="03e0f-163">Basis</span></span>
- <span data-ttu-id="03e0f-164">Importo o coefficiente</span><span class="sxs-lookup"><span data-stu-id="03e0f-164">Amount or rate</span></span>
- <span data-ttu-id="03e0f-165">Codice di reddito</span><span class="sxs-lookup"><span data-stu-id="03e0f-165">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="03e0f-166">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="03e0f-166">Supported frequencies</span></span> 

- <span data-ttu-id="03e0f-167">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="03e0f-167">Weekly</span></span>
- <span data-ttu-id="03e0f-168">Bisettimanale</span><span class="sxs-lookup"><span data-stu-id="03e0f-168">Bi-weekly</span></span>
- <span data-ttu-id="03e0f-169">Quindicinale</span><span class="sxs-lookup"><span data-stu-id="03e0f-169">Semi-monthly</span></span>
- <span data-ttu-id="03e0f-170">Ogni mese</span><span class="sxs-lookup"><span data-stu-id="03e0f-170">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="03e0f-171">Basi supportate</span><span class="sxs-lookup"><span data-stu-id="03e0f-171">Supported bases</span></span> 

- <span data-ttu-id="03e0f-172">Importo fisso</span><span class="sxs-lookup"><span data-stu-id="03e0f-172">Fixed amount</span></span>
- <span data-ttu-id="03e0f-173">Percentuale di redditi</span><span class="sxs-lookup"><span data-stu-id="03e0f-173">Percent of earnings</span></span>
- <span data-ttu-id="03e0f-174">Ore di produzione</span><span class="sxs-lookup"><span data-stu-id="03e0f-174">Productive hours</span></span>

<span data-ttu-id="03e0f-175">Dayforce crea le seguenti detrazioni, in base all'impatto delle retribuzioni definito nel piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="03e0f-175">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="03e0f-176">Selezione in Talent</span><span class="sxs-lookup"><span data-stu-id="03e0f-176">Selection in Talent</span></span>        | <span data-ttu-id="03e0f-177">Risultato in Dayforce</span><span class="sxs-lookup"><span data-stu-id="03e0f-177">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="03e0f-178">Nessuna</span><span class="sxs-lookup"><span data-stu-id="03e0f-178">None</span></span>                       | <span data-ttu-id="03e0f-179">Non viene creata alcuna detrazione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-179">No deduction is created.</span></span>                      |
| <span data-ttu-id="03e0f-180">Solo detrazione</span><span class="sxs-lookup"><span data-stu-id="03e0f-180">Deduction only</span></span>             | <span data-ttu-id="03e0f-181">Viene creata una detrazione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="03e0f-181">An employee deduction is created.</span></span>             |
| <span data-ttu-id="03e0f-182">Solo contribuzione</span><span class="sxs-lookup"><span data-stu-id="03e0f-182">Contribution only</span></span>          | <span data-ttu-id="03e0f-183">Viene creata una detrazione del datore di lavoro.</span><span class="sxs-lookup"><span data-stu-id="03e0f-183">An employer deduction is created.</span></span>             |
| <span data-ttu-id="03e0f-184">Detrazione e contribuzione</span><span class="sxs-lookup"><span data-stu-id="03e0f-184">Deduction and contribution</span></span> | <span data-ttu-id="03e0f-185">Vengono create detrazioni del datore di lavoro e del dipendente.</span><span class="sxs-lookup"><span data-stu-id="03e0f-185">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="03e0f-186">Per altre informazioni su come definire e gestire un programma di benefit, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="03e0f-186">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="03e0f-187">Realizzare un programma di benefit per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="03e0f-187">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="03e0f-188">Creare un nuovo benefit</span><span class="sxs-lookup"><span data-stu-id="03e0f-188">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="03e0f-189">Definire regole e criteri di idoneità ai benefit</span><span class="sxs-lookup"><span data-stu-id="03e0f-189">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="03e0f-190">Iscrivere e rimuovere benefit da lavoratori</span><span class="sxs-lookup"><span data-stu-id="03e0f-190">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="03e0f-191">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="03e0f-191">Compensation</span></span> 

<span data-ttu-id="03e0f-192">La gestione delle retribuzioni consente di controllare la liquidazione dei premi e della retribuzione base.</span><span class="sxs-lookup"><span data-stu-id="03e0f-192">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="03e0f-193">La retribuzione di base fissa di un dipendente e gli aumenti per merito sono controllati mediante piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="03e0f-193">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="03e0f-194">È possibile controllare il pagamento degli incentivi, ad esempio il pagamento dei bonus, dei premi produttività, dei diritti di opzione, delle sovvenzioni, oltre che dei premi una tantum, tramite i piani di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="03e0f-194">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="03e0f-195">Dayforce utilizza le informazioni sulla compensazione per calcolare la retribuzione annuale o oraria di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="03e0f-195">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="03e0f-196">I piani di retribuzione fissa e conversioni della retribuzione sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="03e0f-196">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="03e0f-197">I dipendenti devono essere associati a un piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="03e0f-197">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="03e0f-198">Per ulteriori informazioni sui piani di retribuzione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="03e0f-198">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="03e0f-199">Creare i piani di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="03e0f-199">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="03e0f-200">Creare i piani di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="03e0f-200">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="03e0f-201">Sviluppare una struttura e piani di stipendi/retribuzioni</span><span class="sxs-lookup"><span data-stu-id="03e0f-201">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="03e0f-202">Processo retributivo</span><span class="sxs-lookup"><span data-stu-id="03e0f-202">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="03e0f-203">Definire il processo retributivo e calcolare i risultati</span><span class="sxs-lookup"><span data-stu-id="03e0f-203">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="03e0f-204">Iscrivere un dipendente a un piano di retribuzione fisso</span><span class="sxs-lookup"><span data-stu-id="03e0f-204">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="03e0f-205">Iscrivere un dipendente a un piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="03e0f-205">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="03e0f-206">Mansioni</span><span class="sxs-lookup"><span data-stu-id="03e0f-206">Jobs</span></span> 

<span data-ttu-id="03e0f-207">Una mansione è una raccolta delle attività e delle responsabilità proprie della persona assegnata a una mansione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-207">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="03e0f-208">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="03e0f-208">For more information, see the following topics:</span></span>

- [<span data-ttu-id="03e0f-209">Impostazione dei componenti di una mansione</span><span class="sxs-lookup"><span data-stu-id="03e0f-209">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="03e0f-210">Definire nuovi processi</span><span class="sxs-lookup"><span data-stu-id="03e0f-210">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="03e0f-211">Posizioni</span><span class="sxs-lookup"><span data-stu-id="03e0f-211">Positions</span></span>

<span data-ttu-id="03e0f-212">Una posizione è una singola istanza di un processo.</span><span class="sxs-lookup"><span data-stu-id="03e0f-212">A position is an individual instance of a job.</span></span> <span data-ttu-id="03e0f-213">Ad esempio, la posizione "Manager vendite (Est") è una delle posizioni associate alla mansione "Manager vendite".</span><span class="sxs-lookup"><span data-stu-id="03e0f-213">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="03e0f-214">Una posizione è presente in un reparto.</span><span class="sxs-lookup"><span data-stu-id="03e0f-214">A position exists in a department.</span></span> <span data-ttu-id="03e0f-215">È possibile associare un solo lavoratore a ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-215">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="03e0f-216">Tenere a mente i seguenti dati e la configurazione quando si impostano le posizioni:</span><span class="sxs-lookup"><span data-stu-id="03e0f-216">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="03e0f-217">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-217">Position (required)</span></span>
- <span data-ttu-id="03e0f-218">Descrizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-218">Description (required)</span></span>
- <span data-ttu-id="03e0f-219">Mansione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-219">Job (required)</span></span>
- <span data-ttu-id="03e0f-220">Reparto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-220">Department (required)</span></span>
- <span data-ttu-id="03e0f-221">Tipo di posizione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-221">Position type (required)</span></span>
- <span data-ttu-id="03e0f-222">Equivalente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="03e0f-222">Full-time equivalent</span></span>
- <span data-ttu-id="03e0f-223">Ore regolari annuali (obbligatorie)</span><span class="sxs-lookup"><span data-stu-id="03e0f-223">Annual regular hours (required)</span></span>
- <span data-ttu-id="03e0f-224">Pagamento in base alla persona giuridica (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-224">Paid by legal entity (required)</span></span>
- <span data-ttu-id="03e0f-225">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="03e0f-225">Pay cycle (required)</span></span>
- <span data-ttu-id="03e0f-226">Dimensione finanziaria predefinita - Centro di costo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-226">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="03e0f-227">Assegnazione del lavoratore - Lavoratore, inizio assegnazione, fine assegnazione, codice motivo</span><span class="sxs-lookup"><span data-stu-id="03e0f-227">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="03e0f-228">Se nello stesso reparto più posizioni sono associate alla stessa mansione, vengono consolidate in una singola posizione in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="03e0f-228">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="03e0f-229">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="03e0f-229">For more information, see the following topics:</span></span>

- [<span data-ttu-id="03e0f-230">Organizzare la forza lavoro utilizzando i reparti, le mansioni e le posizioni</span><span class="sxs-lookup"><span data-stu-id="03e0f-230">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="03e0f-231">Impostare le posizioni</span><span class="sxs-lookup"><span data-stu-id="03e0f-231">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="03e0f-232">Reparti</span><span class="sxs-lookup"><span data-stu-id="03e0f-232">Departments</span></span>

<span data-ttu-id="03e0f-233">Un reparto è un'unità operativa che rappresenta una categoria o un'area operativa di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-233">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="03e0f-234">Un reparto è responsabile di una specifica area dell'organizzazione, ad esempio la vendita, la contabilità o le risorse umane.</span><span class="sxs-lookup"><span data-stu-id="03e0f-234">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="03e0f-235">È possibile utilizzare i reparti per creare report sulle aree operative.</span><span class="sxs-lookup"><span data-stu-id="03e0f-235">You can use departments to report on functional areas.</span></span> <span data-ttu-id="03e0f-236">I reparti possono essere responsabili di profitti e perdite.</span><span class="sxs-lookup"><span data-stu-id="03e0f-236">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="03e0f-237">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="03e0f-237">For more information, see the following topics:</span></span>

- [<span data-ttu-id="03e0f-238">Creare un reparto e associarlo alla gerarchia reparti</span><span class="sxs-lookup"><span data-stu-id="03e0f-238">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="03e0f-239">Definire nuovi reparti</span><span class="sxs-lookup"><span data-stu-id="03e0f-239">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="03e0f-240">Cicli e periodi retributivi</span><span class="sxs-lookup"><span data-stu-id="03e0f-240">Pay cycles and pay periods</span></span>

<span data-ttu-id="03e0f-241">Un ciclo retributivo determina la frequenza di elaborazione delle retribuzioni e i giorni specifici in cui i lavoratori vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="03e0f-241">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="03e0f-242">Un ciclo retributivo può essere ad esempio mensile e i dipendenti possono essere pagati l'ultimo giorno del mese.</span><span class="sxs-lookup"><span data-stu-id="03e0f-242">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="03e0f-243">Un ciclo retributivo può in alternativa essere settimanale e i dipendenti possono essere pagati il giovedì successivo alla fine del periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="03e0f-243">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="03e0f-244">I cicli retributivi vengono assegnati alle posizioni per controllare quando i lavoratori in tali posizioni vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="03e0f-244">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="03e0f-245">Dopo aver creato i cicli retributivi, è possibile generare periodi retributivi per ogni ciclo.</span><span class="sxs-lookup"><span data-stu-id="03e0f-245">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="03e0f-246">Ogni periodo retributivo include una data di pagamento predefinita in base alle informazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="03e0f-246">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="03e0f-247">Tuttavia, è possibile modificare la data di pagamento predefinita in un periodo retributivo per consentire eccezioni, ad esempio quando la data di pagamento cade in un giorno festivo.</span><span class="sxs-lookup"><span data-stu-id="03e0f-247">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="03e0f-248">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="03e0f-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="03e0f-249">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="03e0f-249">Pay cycle (required)</span></span>
- <span data-ttu-id="03e0f-250">Frequenza ciclo retributivo (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-250">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="03e0f-251">Data di inizio del periodo (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-251">Period start date (first pay period required)</span></span>
- <span data-ttu-id="03e0f-252">Data di pagamento predefinita (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-252">Default payment date (first pay period required)</span></span>

<span data-ttu-id="03e0f-253">Queste informazioni sono integrate con Dayforce come gruppi retributivi e sono separata in base al paese o alla regione per ogni ciclo retributivo.</span><span class="sxs-lookup"><span data-stu-id="03e0f-253">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="03e0f-254">Prima dell'integrazione è necessario generare almeno un periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="03e0f-254">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="03e0f-255">Dayforce genera calendari di gruppi retributivi e date di pagamento, in base alla data di inizio del primo periodo retributivo e alla data di pagamento predefinita che viene impostata in Talent.</span><span class="sxs-lookup"><span data-stu-id="03e0f-255">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="03e0f-256">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="03e0f-256">Earning codes</span></span>

<span data-ttu-id="03e0f-257">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="03e0f-257">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="03e0f-258">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="03e0f-258">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="03e0f-259">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="03e0f-259">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="03e0f-260">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-260">Earning Code (required)</span></span>
- <span data-ttu-id="03e0f-261">descrizione</span><span class="sxs-lookup"><span data-stu-id="03e0f-261">Description</span></span>
- <span data-ttu-id="03e0f-262">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="03e0f-262">Unit of measure</span></span>
- <span data-ttu-id="03e0f-263">Produttivo</span><span class="sxs-lookup"><span data-stu-id="03e0f-263">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="03e0f-264">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-264">Worker data</span></span>

<span data-ttu-id="03e0f-265">I record per i diversi tipi di lavoratori a disposizione sono importanti per i sistemi di gestione delle risorse umane e delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="03e0f-265">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="03e0f-266">Le informazioni immesse possono essere utilizzate per tenere traccia di informazioni personali e sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="03e0f-266">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="03e0f-267">È possibile gestire le seguenti informazioni per i lavoratori:</span><span class="sxs-lookup"><span data-stu-id="03e0f-267">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="03e0f-268">**Base** - Gestire le informazioni di base su un lavoratore, ad esempio le informazioni sui contatti, le informazioni demografiche, le informazioni di identificazione, le informazioni sulla famiglia, lo stato di servizio militare, le informazioni sull'espatrio, e i contatti personali e di emergenza.</span><span class="sxs-lookup"><span data-stu-id="03e0f-268">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="03e0f-269">**Impiego** - Consente di gestire le informazioni sull'impiego di un lavoratore, ad esempio rapporto con l'organizzazione o la società, assegnazione della posizione, date di inizio e fine, idoneità al lavoro, condizioni di impiego, pensionamento, ferie e trasferimento.</span><span class="sxs-lookup"><span data-stu-id="03e0f-269">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="03e0f-270">**Congedo e assenza** - Consente di gestire le informazioni sulle assenze di un lavoratore, ad esempio calendari di lavoro, transazioni assenze e impostazione assenze.</span><span class="sxs-lookup"><span data-stu-id="03e0f-270">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="03e0f-271">**Retribuzioni** - Consente di gestire le informazioni sui piani di retribuzione di un lavoratore, ad esempio registrazione del piano, premi, prestazioni, provvigione, dati fiscali, pensionamento e detrazioni sullo stipendio.</span><span class="sxs-lookup"><span data-stu-id="03e0f-271">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="03e0f-272">Quando si immettono le informazioni su un lavoratore, tenere presenti i seguenti dati e le configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="03e0f-272">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="03e0f-273">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="03e0f-273">General information</span></span>

- <span data-ttu-id="03e0f-274">Numero dipendente (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-274">Personnel number (required)</span></span>
- <span data-ttu-id="03e0f-275">Nome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-275">First name (required)</span></span>
- <span data-ttu-id="03e0f-276">Cognome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-276">Last name (required)</span></span>
- <span data-ttu-id="03e0f-277">Secondo nome</span><span class="sxs-lookup"><span data-stu-id="03e0f-277">Middle name</span></span>
- <span data-ttu-id="03e0f-278">Data di anzianità</span><span class="sxs-lookup"><span data-stu-id="03e0f-278">Seniority date</span></span>
- <span data-ttu-id="03e0f-279">Nome noto</span><span class="sxs-lookup"><span data-stu-id="03e0f-279">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="03e0f-280">Informazioni personali</span><span class="sxs-lookup"><span data-stu-id="03e0f-280">Personal information</span></span>

- <span data-ttu-id="03e0f-281">Stato civile (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-281">Marital status (required)</span></span>
- <span data-ttu-id="03e0f-282">Data di nascita (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-282">Birth date (required)</span></span>
- <span data-ttu-id="03e0f-283">Sesso (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-283">Gender (required)</span></span>
- <span data-ttu-id="03e0f-284">Persona disabile</span><span class="sxs-lookup"><span data-stu-id="03e0f-284">Person with disabilities</span></span>
- <span data-ttu-id="03e0f-285">Nazionalità paese regione (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="03e0f-285">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="03e0f-286">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="03e0f-286">Address information</span></span>

- <span data-ttu-id="03e0f-287">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-287">Primary (required)</span></span>
- <span data-ttu-id="03e0f-288">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-288">Country/region (required)</span></span>
- <span data-ttu-id="03e0f-289">Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-289">Postal code (required)</span></span>
- <span data-ttu-id="03e0f-290">Numero civico (obbligatorio) (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="03e0f-290">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="03e0f-291">Informazioni aggiuntive sull'indirizzo (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="03e0f-291">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="03e0f-292">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-292">City (required)</span></span>
- <span data-ttu-id="03e0f-293">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-293">State (required)</span></span>
- <span data-ttu-id="03e0f-294">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-294">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="03e0f-295">Informazioni contatto</span><span class="sxs-lookup"><span data-stu-id="03e0f-295">Contact information</span></span> 

- <span data-ttu-id="03e0f-296">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-296">Primary (required)</span></span>
- <span data-ttu-id="03e0f-297">Numero contatto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-297">Contact number (required)</span></span>
- <span data-ttu-id="03e0f-298">Interno</span><span class="sxs-lookup"><span data-stu-id="03e0f-298">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="03e0f-299">Informazioni sulle retribuzioni e codici di reddito</span><span class="sxs-lookup"><span data-stu-id="03e0f-299">Payroll information and earning codes</span></span>

<span data-ttu-id="03e0f-300">Ai dipendenti possono essere assegnati redditi specifici a una determinata frequenza di pagamento e un metodo di pagamento preferito.</span><span class="sxs-lookup"><span data-stu-id="03e0f-300">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="03e0f-301">I campi seguenti vengono utilizzati in Dayforce per garantire che le preferenze e le impostazioni vengano utilizzate.</span><span class="sxs-lookup"><span data-stu-id="03e0f-301">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="03e0f-302">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="03e0f-302">Earning codes</span></span>

- <span data-ttu-id="03e0f-303">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-303">Position (required)</span></span>
- <span data-ttu-id="03e0f-304">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-304">Earning Code (required)</span></span>
- <span data-ttu-id="03e0f-305">Frequenza (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-305">Frequency (required)</span></span>
- <span data-ttu-id="03e0f-306">Importo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-306">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="03e0f-307">Informazioni retribuzioni</span><span class="sxs-lookup"><span data-stu-id="03e0f-307">Payroll information</span></span>

- <span data-ttu-id="03e0f-308">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="03e0f-308">Payment Method</span></span>
- <span data-ttu-id="03e0f-309">Area economica (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-309">Economic Region (required)</span></span>
- <span data-ttu-id="03e0f-310">ID benefit dipendente</span><span class="sxs-lookup"><span data-stu-id="03e0f-310">Employee Benefits ID</span></span>
- <span data-ttu-id="03e0f-311">Numero documento identità (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-311">National ID Number (required)</span></span>
- <span data-ttu-id="03e0f-312">Numero servizio militare</span><span class="sxs-lookup"><span data-stu-id="03e0f-312">Military Service Number</span></span>
- <span data-ttu-id="03e0f-313">ID turno (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-313">Shift ID (required)</span></span>
- <span data-ttu-id="03e0f-314">Numero imposta (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-314">Tax Number (required)</span></span>
- <span data-ttu-id="03e0f-315">ID sindacato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-315">Union ID (required)</span></span>
- <span data-ttu-id="03e0f-316">ID giorno lavorativo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-316">Work Day ID (required)</span></span>
- <span data-ttu-id="03e0f-317">Numero permesso di lavoro</span><span class="sxs-lookup"><span data-stu-id="03e0f-317">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="03e0f-318">Per il metodo di pagamento, il Messico supporta **Contante**, **Assegno** (l'assegno fisico della società) e **Pagamento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="03e0f-318">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="03e0f-319">Se non viene specificato alcun metodo di pagamento, **Assegno** è 'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="03e0f-319">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="03e0f-320">Dettagli impiego</span><span class="sxs-lookup"><span data-stu-id="03e0f-320">Employment details</span></span>

<span data-ttu-id="03e0f-321">Lo storico dei dettagli impiego viene utilizzato come informazioni chiave da cui derivare gli stati di assunzione, termine e riassunzione di un dipendente Dayforce.</span><span class="sxs-lookup"><span data-stu-id="03e0f-321">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="03e0f-322">Dayforce supporta solo un record di impiego attivo alla volta.</span><span class="sxs-lookup"><span data-stu-id="03e0f-322">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="03e0f-323">Data di inizio impiego (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-323">Employment start date (required)</span></span>
- <span data-ttu-id="03e0f-324">Data di fine impiego</span><span class="sxs-lookup"><span data-stu-id="03e0f-324">Employment end date</span></span>
- <span data-ttu-id="03e0f-325">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="03e0f-325">Start date</span></span>
- <span data-ttu-id="03e0f-326">Data di inizio rettificata</span><span class="sxs-lookup"><span data-stu-id="03e0f-326">Adjusted start date</span></span>
- <span data-ttu-id="03e0f-327">Data fine rapporto (obbligatoria con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="03e0f-327">Termination date (required upon termination)</span></span>
- <span data-ttu-id="03e0f-328">Motivo fine rapporto (obbligatorio con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="03e0f-328">Termination reason (required upon termination)</span></span>

<span data-ttu-id="03e0f-329">Le date chiave del dipendente sono derivate utilizzando le informazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="03e0f-329">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="03e0f-330">Talent</span><span class="sxs-lookup"><span data-stu-id="03e0f-330">Talent</span></span>                | <span data-ttu-id="03e0f-331">Dayforce</span><span class="sxs-lookup"><span data-stu-id="03e0f-331">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="03e0f-332">Data di assunzione più recente</span><span class="sxs-lookup"><span data-stu-id="03e0f-332">Most recent hire date</span></span> | <span data-ttu-id="03e0f-333">Inizio dell'impiego del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="03e0f-333">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="03e0f-334">Data fine rapporto</span><span class="sxs-lookup"><span data-stu-id="03e0f-334">Termination date</span></span>      | <span data-ttu-id="03e0f-335">Data di fine rapporto del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="03e0f-335">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="03e0f-336">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="03e0f-336">Start date</span></span>            | <span data-ttu-id="03e0f-337">Data di inizio rettificata, data di inizio o inizio dell'impiego del record corrente dello storico di impiego non attivo</span><span class="sxs-lookup"><span data-stu-id="03e0f-337">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="03e0f-338">Data di assunzione originale</span><span class="sxs-lookup"><span data-stu-id="03e0f-338">Original hire date</span></span>    | <span data-ttu-id="03e0f-339">Inizio dell'impiego del record dello storico di impiego meno recente</span><span class="sxs-lookup"><span data-stu-id="03e0f-339">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="03e0f-340">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="03e0f-340">Compensation</span></span>

<span data-ttu-id="03e0f-341">Un piano di retribuzione fissa deve essere associato alla posizione primaria di ogni dipendente durante un periodo di impiego.</span><span class="sxs-lookup"><span data-stu-id="03e0f-341">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="03e0f-342">Questo periodo inizia alla data in cui il dipendente è stato assunto (o la data di inizio dell'impiego) e continua fino alla fine del rapporto.</span><span class="sxs-lookup"><span data-stu-id="03e0f-342">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="03e0f-343">Data di validità (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-343">Effective Date (required)</span></span>
- <span data-ttu-id="03e0f-344">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="03e0f-344">Expiration date</span></span>
- <span data-ttu-id="03e0f-345">Retribuzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-345">Pay Rate (required)</span></span>
- <span data-ttu-id="03e0f-346">Conversioni retribuzione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-346">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="03e0f-347">Equivalente annuale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-347">Annual equivalent (required)</span></span>
- <span data-ttu-id="03e0f-348">Equivalente orario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-348">Hourly equivalent (required)</span></span>

<span data-ttu-id="03e0f-349">Se un dipendente a ore ha più posizioni, la retribuzione fissa della posizione primaria viene importata in Dayforce come il tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="03e0f-349">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="03e0f-350">Per le posizioni non principali, la tariffa oraria viene salvata nella posizione corrispondente in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="03e0f-350">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="03e0f-351">Se un dipendente stipendiato ha più posizioni, la tariffa oraria cumulativa e lo stipendio annuale di tutte le posizioni attive vengono calcolati e utilizzati come tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="03e0f-351">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="03e0f-352">Numeri di identificazione</span><span class="sxs-lookup"><span data-stu-id="03e0f-352">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="03e0f-353">Numero di Previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="03e0f-353">Social Security identifier</span></span> 

<span data-ttu-id="03e0f-354">Ogni dipendente deve avere un identificatore primario.</span><span class="sxs-lookup"><span data-stu-id="03e0f-354">Every employee must have one primary identifier.</span></span> <span data-ttu-id="03e0f-355">Questo identificatore deve essere di tipo identificatore **SSN**.</span><span class="sxs-lookup"><span data-stu-id="03e0f-355">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="03e0f-356">In Dayforce, viene ricavato automaticamente come identificatore di previdenza sociale del dipendente per l'assunzione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-356">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="03e0f-357">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-357">Primary (required)</span></span>
- <span data-ttu-id="03e0f-358">Tipo di identificazione = "SSN"</span><span class="sxs-lookup"><span data-stu-id="03e0f-358">Identification Type = "SSN"</span></span>
- <span data-ttu-id="03e0f-359">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="03e0f-359">Issued Date</span></span>
- <span data-ttu-id="03e0f-360">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="03e0f-360">Expiration Date</span></span>

<span data-ttu-id="03e0f-361">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **SSN**.</span><span class="sxs-lookup"><span data-stu-id="03e0f-361">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="03e0f-362">Tuttavia, solo il record che è contrassegnato come **Primario** viene integrato in Dayforce, a prescindere che il numero sia attivo o scaduto.</span><span class="sxs-lookup"><span data-stu-id="03e0f-362">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="03e0f-363">Esborsi e conti bancari</span><span class="sxs-lookup"><span data-stu-id="03e0f-363">Bank accounts and disbursements</span></span>

<span data-ttu-id="03e0f-364">È necessario immettere informazioni sul conto bancario valide per un dipendente che scelga di essere pagato tramite trasferimenti di conto bancario.</span><span class="sxs-lookup"><span data-stu-id="03e0f-364">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="03e0f-365">Talent</span><span class="sxs-lookup"><span data-stu-id="03e0f-365">Talent</span></span>                         | <span data-ttu-id="03e0f-366">Dayforce</span><span class="sxs-lookup"><span data-stu-id="03e0f-366">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="03e0f-367">Numero conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-367">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="03e0f-368">Codice SWIFT (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-368">SWIFT code (required)</span></span>          | <span data-ttu-id="03e0f-369">Campo **ID banca** utilizzato durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="03e0f-369">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="03e0f-370">Codice filiale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-370">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="03e0f-371">Tipo di conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-371">Bank account type (required)</span></span>   | <span data-ttu-id="03e0f-372">Campo **Tipo di conto** utilizzando durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="03e0f-372">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="03e0f-373">I valori supportati includono **Controllo** e **Retribuzioni**.</span><span class="sxs-lookup"><span data-stu-id="03e0f-373">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="03e0f-374">I dipendenti che scelgono di essere pagati tramite trasferimenti di conto bancario devono fornire un collegamento a un conto rimanente che è sotto la persona giuridica che ha l'indirizzo primario in Messico ed è associato a un conto bancario valido presso una banca messicana.</span><span class="sxs-lookup"><span data-stu-id="03e0f-374">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="03e0f-375">Tutti gli altri account non di rimanenze verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="03e0f-375">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="03e0f-376">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="03e0f-376">Address information</span></span>

<span data-ttu-id="03e0f-377">Ogni dipendente deve avere un'ubicazione primaria.</span><span class="sxs-lookup"><span data-stu-id="03e0f-377">Every employee must have one primary location.</span></span> <span data-ttu-id="03e0f-378">In Dayforce, questa ubicazione viene utilizzata per determinare la principale residenza del dipendente a scopo fiscale.</span><span class="sxs-lookup"><span data-stu-id="03e0f-378">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="03e0f-379">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-379">Primary (required)</span></span>
- <span data-ttu-id="03e0f-380">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-380">Country/region (required)</span></span>
- <span data-ttu-id="03e0f-381">CAP/Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-381">Zip/postal code (required)</span></span>
- <span data-ttu-id="03e0f-382">Via (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-382">Street (required)</span></span>
- <span data-ttu-id="03e0f-383">Numero civico (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-383">Street Number (required)</span></span>
- <span data-ttu-id="03e0f-384">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="03e0f-384">Building Complement</span></span>
- <span data-ttu-id="03e0f-385">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-385">City (required)</span></span>
- <span data-ttu-id="03e0f-386">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-386">State (required)</span></span>
- <span data-ttu-id="03e0f-387">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-387">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="03e0f-388">Configurare i dati per generare le retribuzioni negli Stati Uniti e in Canada</span><span class="sxs-lookup"><span data-stu-id="03e0f-388">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="03e0f-389">Se si desidera generare la retribuzione per i dipendenti negli Stati Uniti e in Canada, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="03e0f-389">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="03e0f-390">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="03e0f-390">Departments are required on positions.</span></span>
- <span data-ttu-id="03e0f-391">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="03e0f-391">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="03e0f-392">È possibile configurare Talent per far sì che Posizioni specifichi un reparto.</span><span class="sxs-lookup"><span data-stu-id="03e0f-392">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="03e0f-393">A tale scopo, andare a **Posizioni condivise Risorse umane > Posizioni > Richiedi reparti su posizioni**.</span><span class="sxs-lookup"><span data-stu-id="03e0f-393">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="03e0f-394">Si consiglia di applicare questa impostazione per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-394">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="03e0f-395">Tipi di lavoro</span><span class="sxs-lookup"><span data-stu-id="03e0f-395">Job types</span></span>

<span data-ttu-id="03e0f-396">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="03e0f-396">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="03e0f-397">I tipi di mansione sono necessari per elaborare le retribuzioni negli Stati Uniti e in Canada.</span><span class="sxs-lookup"><span data-stu-id="03e0f-397">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="03e0f-398">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="03e0f-398">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="03e0f-399">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="03e0f-399">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="03e0f-400">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="03e0f-400">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="03e0f-401">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="03e0f-401">Job type</span></span>   | <span data-ttu-id="03e0f-402">descrizione</span><span class="sxs-lookup"><span data-stu-id="03e0f-402">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="03e0f-403">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="03e0f-403">Hourly</span></span>     | <span data-ttu-id="03e0f-404">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="03e0f-404">Hourly</span></span>      |
| <span data-ttu-id="03e0f-405">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="03e0f-405">Salaried</span></span>   | <span data-ttu-id="03e0f-406">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="03e0f-406">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="03e0f-407">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="03e0f-407">Position types</span></span> 

<span data-ttu-id="03e0f-408">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="03e0f-408">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="03e0f-409">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="03e0f-409">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="03e0f-410">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="03e0f-410">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="03e0f-411">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="03e0f-411">Position type</span></span>   | <span data-ttu-id="03e0f-412">descrizione</span><span class="sxs-lookup"><span data-stu-id="03e0f-412">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="03e0f-413">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="03e0f-413">Full-time</span></span>       | <span data-ttu-id="03e0f-414">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="03e0f-414">Full time employee</span></span> |
| <span data-ttu-id="03e0f-415">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="03e0f-415">Part-time</span></span>       | <span data-ttu-id="03e0f-416">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="03e0f-416">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="03e0f-417">Codici causale</span><span class="sxs-lookup"><span data-stu-id="03e0f-417">Reason codes</span></span>

<span data-ttu-id="03e0f-418">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="03e0f-418">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="03e0f-419">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="03e0f-419">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="03e0f-420">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="03e0f-420">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="03e0f-421">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="03e0f-421">Reason code</span></span>    | <span data-ttu-id="03e0f-422">descrizione</span><span class="sxs-lookup"><span data-stu-id="03e0f-422">Description</span></span>      | <span data-ttu-id="03e0f-423">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="03e0f-423">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="03e0f-424">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="03e0f-424">RESIGNATION</span></span>    | <span data-ttu-id="03e0f-425">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="03e0f-425">Resignation</span></span>      | <span data-ttu-id="03e0f-426">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-426">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-427">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="03e0f-427">TERMINATION</span></span>    | <span data-ttu-id="03e0f-428">Fine</span><span class="sxs-lookup"><span data-stu-id="03e0f-428">Termination</span></span>      | <span data-ttu-id="03e0f-429">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-429">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-430">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="03e0f-430">RETIREMENT</span></span>     | <span data-ttu-id="03e0f-431">Pensione</span><span class="sxs-lookup"><span data-stu-id="03e0f-431">Retirement</span></span>       | <span data-ttu-id="03e0f-432">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-432">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-433">OTHER</span><span class="sxs-lookup"><span data-stu-id="03e0f-433">OTHER</span></span>          | <span data-ttu-id="03e0f-434">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="03e0f-434">Other Reasons</span></span>    | <span data-ttu-id="03e0f-435">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-435">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-436">DEATH</span><span class="sxs-lookup"><span data-stu-id="03e0f-436">DEATH</span></span>          | <span data-ttu-id="03e0f-437">Decesso</span><span class="sxs-lookup"><span data-stu-id="03e0f-437">Death</span></span>            | <span data-ttu-id="03e0f-438">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-438">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-439">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="03e0f-439">LEAVEOFABSENCE</span></span> | <span data-ttu-id="03e0f-440">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="03e0f-440">Leave of Absence</span></span> | <span data-ttu-id="03e0f-441">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-441">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-442">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="03e0f-442">CONTRACTEND</span></span>    | <span data-ttu-id="03e0f-443">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="03e0f-443">End of Contract</span></span>  | <span data-ttu-id="03e0f-444">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-444">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-445">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="03e0f-445">SALARYCHANGE</span></span>   | <span data-ttu-id="03e0f-446">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="03e0f-446">Change of Salary</span></span> | <span data-ttu-id="03e0f-447">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="03e0f-447">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="03e0f-448">Stato civile</span><span class="sxs-lookup"><span data-stu-id="03e0f-448">Marital status</span></span>

<span data-ttu-id="03e0f-449">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-449">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="03e0f-450">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="03e0f-450">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="03e0f-451">Talent</span><span class="sxs-lookup"><span data-stu-id="03e0f-451">Talent</span></span>                 | <span data-ttu-id="03e0f-452">Dayforce</span><span class="sxs-lookup"><span data-stu-id="03e0f-452">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="03e0f-453">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="03e0f-453">Married</span></span>                | <span data-ttu-id="03e0f-454">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="03e0f-454">Married</span></span>              |
| <span data-ttu-id="03e0f-455">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="03e0f-455">Single</span></span>                 | <span data-ttu-id="03e0f-456">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="03e0f-456">Single</span></span>               |
| <span data-ttu-id="03e0f-457">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="03e0f-457">Widowed</span></span>                | <span data-ttu-id="03e0f-458">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="03e0f-458">Widowed</span></span>              |
| <span data-ttu-id="03e0f-459">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="03e0f-459">Divorced</span></span>               | <span data-ttu-id="03e0f-460">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="03e0f-460">Divorced</span></span>             |
| <span data-ttu-id="03e0f-461">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="03e0f-461">Registered Partnership</span></span> | <span data-ttu-id="03e0f-462">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="03e0f-462">Domestic Partnership</span></span> |
| <span data-ttu-id="03e0f-463">Nessuna</span><span class="sxs-lookup"><span data-stu-id="03e0f-463">None</span></span>                   | <span data-ttu-id="03e0f-464">Nessuna</span><span class="sxs-lookup"><span data-stu-id="03e0f-464">None</span></span>                 |
| <span data-ttu-id="03e0f-465">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="03e0f-465">Cohabiting</span></span>             | <span data-ttu-id="03e0f-466">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="03e0f-466">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="03e0f-467">Genere</span><span class="sxs-lookup"><span data-stu-id="03e0f-467">Gender</span></span>

<span data-ttu-id="03e0f-468">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-468">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="03e0f-469">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="03e0f-469">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="03e0f-470">Talent</span><span class="sxs-lookup"><span data-stu-id="03e0f-470">Talent</span></span>       | <span data-ttu-id="03e0f-471">Dayforce</span><span class="sxs-lookup"><span data-stu-id="03e0f-471">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="03e0f-472">Maschio</span><span class="sxs-lookup"><span data-stu-id="03e0f-472">Male</span></span>         | <span data-ttu-id="03e0f-473">Maschio</span><span class="sxs-lookup"><span data-stu-id="03e0f-473">Male</span></span>            |
| <span data-ttu-id="03e0f-474">Femmina</span><span class="sxs-lookup"><span data-stu-id="03e0f-474">Female</span></span>       | <span data-ttu-id="03e0f-475">Femmina</span><span class="sxs-lookup"><span data-stu-id="03e0f-475">Female</span></span>          |
| <span data-ttu-id="03e0f-476">Non specifico</span><span class="sxs-lookup"><span data-stu-id="03e0f-476">Non-specific</span></span> | <span data-ttu-id="03e0f-477">*Non supportato*</span><span class="sxs-lookup"><span data-stu-id="03e0f-477">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="03e0f-478">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="03e0f-478">Earning codes</span></span>

<span data-ttu-id="03e0f-479">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="03e0f-479">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="03e0f-480">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="03e0f-480">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="03e0f-481">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="03e0f-481">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="03e0f-482">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="03e0f-482">Supported frequencies</span></span>

- <span data-ttu-id="03e0f-483">Tutti</span><span class="sxs-lookup"><span data-stu-id="03e0f-483">All</span></span>
- <span data-ttu-id="03e0f-484">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="03e0f-484">EVERYPAY</span></span>
- <span data-ttu-id="03e0f-485">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="03e0f-485">EACHPAYPERIOD</span></span>
- <span data-ttu-id="03e0f-486">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="03e0f-486">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="03e0f-487">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="03e0f-487">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="03e0f-488">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-488">1OFMTH</span></span>
- <span data-ttu-id="03e0f-489">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-489">LASTOFMTH</span></span>
- <span data-ttu-id="03e0f-490">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-490">2OFMTH</span></span>
- <span data-ttu-id="03e0f-491">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-491">3OFMTH</span></span>
- <span data-ttu-id="03e0f-492">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-492">4OFMTH</span></span>
- <span data-ttu-id="03e0f-493">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-493">5OFMTH</span></span>
- <span data-ttu-id="03e0f-494">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-494">1N2OFMTH</span></span>
- <span data-ttu-id="03e0f-495">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-495">3N4OFMTH</span></span>
- <span data-ttu-id="03e0f-496">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-496">1N3OFMTH</span></span>
- <span data-ttu-id="03e0f-497">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-497">1N4OFMTH</span></span>
- <span data-ttu-id="03e0f-498">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-498">2N3OFMTH</span></span>
- <span data-ttu-id="03e0f-499">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-499">2N4OFMTH</span></span>
- <span data-ttu-id="03e0f-500">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-500">1N2N3OFMTH</span></span>
- <span data-ttu-id="03e0f-501">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-501">1N2N4OFMTH</span></span>
- <span data-ttu-id="03e0f-502">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-502">1N3N4OFMTH</span></span>
- <span data-ttu-id="03e0f-503">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-503">2N3N4OFMTH</span></span>
- <span data-ttu-id="03e0f-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="03e0f-505">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="03e0f-505">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="03e0f-506">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="03e0f-506">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="03e0f-507">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="03e0f-507">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="03e0f-508">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="03e0f-508">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="03e0f-509">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="03e0f-509">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="03e0f-510">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="03e0f-510">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="03e0f-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="03e0f-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="03e0f-512">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="03e0f-512">Addresses</span></span>

<span data-ttu-id="03e0f-513">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="03e0f-513">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="03e0f-514">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="03e0f-514">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="03e0f-515">Talent</span><span class="sxs-lookup"><span data-stu-id="03e0f-515">Talent</span></span>          | <span data-ttu-id="03e0f-516">Dayforce</span><span class="sxs-lookup"><span data-stu-id="03e0f-516">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="03e0f-517">Paese</span><span class="sxs-lookup"><span data-stu-id="03e0f-517">Country/Region</span></span>  | <span data-ttu-id="03e0f-518">Codice paese</span><span class="sxs-lookup"><span data-stu-id="03e0f-518">Country Code</span></span>          |
| <span data-ttu-id="03e0f-519">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="03e0f-519">Zip/Postal Code</span></span> | <span data-ttu-id="03e0f-520">CAP</span><span class="sxs-lookup"><span data-stu-id="03e0f-520">Postal Code</span></span>           |
| <span data-ttu-id="03e0f-521">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="03e0f-521">State</span></span>           | <span data-ttu-id="03e0f-522">Codice stato</span><span class="sxs-lookup"><span data-stu-id="03e0f-522">State Code</span></span>            |
| <span data-ttu-id="03e0f-523">Città</span><span class="sxs-lookup"><span data-stu-id="03e0f-523">City</span></span>            | <span data-ttu-id="03e0f-524">Città</span><span class="sxs-lookup"><span data-stu-id="03e0f-524">City</span></span>                  |
| <span data-ttu-id="03e0f-525">Regione</span><span class="sxs-lookup"><span data-stu-id="03e0f-525">County</span></span>          | <span data-ttu-id="03e0f-526">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="03e0f-526">County (Municipality)</span></span> |
| <span data-ttu-id="03e0f-527">Via</span><span class="sxs-lookup"><span data-stu-id="03e0f-527">Street</span></span>          | <span data-ttu-id="03e0f-528">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="03e0f-528">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="03e0f-529">Regioni fiscali</span><span class="sxs-lookup"><span data-stu-id="03e0f-529">Tax regions</span></span>

<span data-ttu-id="03e0f-530">Le regioni fiscali vengono utilizzate per determinare l'imposta appropriata che deve essere applicata durante la generazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="03e0f-530">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="03e0f-531">Le regioni fiscali vengono mappate in Dayforce come indirizzi di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-531">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="03e0f-532">La regione fiscale predefinita deve essere associata alla posizione attiva del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="03e0f-532">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="03e0f-533">Regione fiscale (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-533">Tax region (required)</span></span>
- <span data-ttu-id="03e0f-534">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-534">Country/Region (required)</span></span>
- <span data-ttu-id="03e0f-535">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="03e0f-535">State (required)</span></span>
- <span data-ttu-id="03e0f-536">Regione</span><span class="sxs-lookup"><span data-stu-id="03e0f-536">County</span></span> 
- <span data-ttu-id="03e0f-537">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="03e0f-537">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="03e0f-538">Configurare i dati per generare le retribuzioni in Messico</span><span class="sxs-lookup"><span data-stu-id="03e0f-538">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="03e0f-539">Se si desidera generare la retribuzione per i dipendenti in Messico, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="03e0f-539">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="03e0f-540">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="03e0f-540">Departments are required on positions.</span></span>
- <span data-ttu-id="03e0f-541">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="03e0f-541">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="03e0f-542">Tipi di posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="03e0f-542">Job types</span></span>

<span data-ttu-id="03e0f-543">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="03e0f-543">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="03e0f-544">Tipi di mansione necessari per elaborare le retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="03e0f-544">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="03e0f-545">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="03e0f-545">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="03e0f-546">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="03e0f-546">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="03e0f-547">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="03e0f-547">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="03e0f-548">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="03e0f-548">Job type</span></span>   | <span data-ttu-id="03e0f-549">descrizione</span><span class="sxs-lookup"><span data-stu-id="03e0f-549">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="03e0f-550">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="03e0f-550">Hourly</span></span>     | <span data-ttu-id="03e0f-551">Su base oraria MX</span><span class="sxs-lookup"><span data-stu-id="03e0f-551">MX Hourly</span></span>   |
| <span data-ttu-id="03e0f-552">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="03e0f-552">Salaried</span></span>   | <span data-ttu-id="03e0f-553">Stipendiato MX</span><span class="sxs-lookup"><span data-stu-id="03e0f-553">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="03e0f-554">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="03e0f-554">Position types</span></span> 

<span data-ttu-id="03e0f-555">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="03e0f-555">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="03e0f-556">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="03e0f-556">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="03e0f-557">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="03e0f-557">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="03e0f-558">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="03e0f-558">Position type</span></span>   | <span data-ttu-id="03e0f-559">descrizione</span><span class="sxs-lookup"><span data-stu-id="03e0f-559">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="03e0f-560">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="03e0f-560">Full-time</span></span>       | <span data-ttu-id="03e0f-561">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="03e0f-561">Full time employee</span></span> |
| <span data-ttu-id="03e0f-562">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="03e0f-562">Part-time</span></span>       | <span data-ttu-id="03e0f-563">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="03e0f-563">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="03e0f-564">Codici causale</span><span class="sxs-lookup"><span data-stu-id="03e0f-564">Reason codes</span></span>

<span data-ttu-id="03e0f-565">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="03e0f-565">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="03e0f-566">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="03e0f-566">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="03e0f-567">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="03e0f-567">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="03e0f-568">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="03e0f-568">Reason code</span></span>            | <span data-ttu-id="03e0f-569">descrizione</span><span class="sxs-lookup"><span data-stu-id="03e0f-569">Description</span></span>                    | <span data-ttu-id="03e0f-570">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="03e0f-570">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="03e0f-571">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="03e0f-571">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="03e0f-572">Partenza prima della prima retribuzione</span><span class="sxs-lookup"><span data-stu-id="03e0f-572">Departure before first payroll</span></span> | <span data-ttu-id="03e0f-573">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-573">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-574">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="03e0f-574">RESIGNATION</span></span>            | <span data-ttu-id="03e0f-575">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="03e0f-575">Resignation</span></span>                    | <span data-ttu-id="03e0f-576">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-576">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-577">PENSION</span><span class="sxs-lookup"><span data-stu-id="03e0f-577">PENSION</span></span>                | <span data-ttu-id="03e0f-578">Pensionamento</span><span class="sxs-lookup"><span data-stu-id="03e0f-578">Pension</span></span>                        | <span data-ttu-id="03e0f-579">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-579">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-580">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="03e0f-580">TERMINATION</span></span>            | <span data-ttu-id="03e0f-581">Fine</span><span class="sxs-lookup"><span data-stu-id="03e0f-581">Termination</span></span>                    | <span data-ttu-id="03e0f-582">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-582">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-583">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="03e0f-583">RETIREMENT</span></span>             | <span data-ttu-id="03e0f-584">Pensione</span><span class="sxs-lookup"><span data-stu-id="03e0f-584">Retirement</span></span>                     | <span data-ttu-id="03e0f-585">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-585">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-586">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="03e0f-586">ABSENTEE</span></span>               | <span data-ttu-id="03e0f-587">Assente</span><span class="sxs-lookup"><span data-stu-id="03e0f-587">Absentee</span></span>                       | <span data-ttu-id="03e0f-588">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-588">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-589">OTHER</span><span class="sxs-lookup"><span data-stu-id="03e0f-589">OTHER</span></span>                  | <span data-ttu-id="03e0f-590">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="03e0f-590">Other Reasons</span></span>                  | <span data-ttu-id="03e0f-591">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-591">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-592">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="03e0f-592">CLOSURE</span></span>                | <span data-ttu-id="03e0f-593">Chiusura attività</span><span class="sxs-lookup"><span data-stu-id="03e0f-593">Business Closure</span></span>               | <span data-ttu-id="03e0f-594">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-594">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-595">DEATH</span><span class="sxs-lookup"><span data-stu-id="03e0f-595">DEATH</span></span>                  | <span data-ttu-id="03e0f-596">Decesso</span><span class="sxs-lookup"><span data-stu-id="03e0f-596">Death</span></span>                          | <span data-ttu-id="03e0f-597">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-597">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-598">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="03e0f-598">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="03e0f-599">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="03e0f-599">Leave of Absence</span></span>               | <span data-ttu-id="03e0f-600">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-600">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-601">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="03e0f-601">CONTRACTEND</span></span>            | <span data-ttu-id="03e0f-602">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="03e0f-602">End of Contract</span></span>                | <span data-ttu-id="03e0f-603">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="03e0f-603">Terminate worker</span></span>     |
| <span data-ttu-id="03e0f-604">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="03e0f-604">SALARYCHANGE</span></span>           | <span data-ttu-id="03e0f-605">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="03e0f-605">Change of Salary</span></span>               | <span data-ttu-id="03e0f-606">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="03e0f-606">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="03e0f-607">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="03e0f-607">Terms of employment</span></span>

<span data-ttu-id="03e0f-608">Le condizioni di impiego vengono utilizzate per creare categorie di termini di impiego.</span><span class="sxs-lookup"><span data-stu-id="03e0f-608">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="03e0f-609">I termini vengono mappati in Dayforce come valori degli indicatori di impiego.</span><span class="sxs-lookup"><span data-stu-id="03e0f-609">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="03e0f-610">I seguenti termini di impiego e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="03e0f-610">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="03e0f-611">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="03e0f-611">Terms of employment</span></span>   | <span data-ttu-id="03e0f-612">descrizione</span><span class="sxs-lookup"><span data-stu-id="03e0f-612">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="03e0f-613">Regolare</span><span class="sxs-lookup"><span data-stu-id="03e0f-613">Regular</span></span>               | <span data-ttu-id="03e0f-614">Regolare</span><span class="sxs-lookup"><span data-stu-id="03e0f-614">Regular</span></span>     |
| <span data-ttu-id="03e0f-615">Diretto</span><span class="sxs-lookup"><span data-stu-id="03e0f-615">Direct</span></span>                | <span data-ttu-id="03e0f-616">Diretto</span><span class="sxs-lookup"><span data-stu-id="03e0f-616">Direct</span></span>      |
| <span data-ttu-id="03e0f-617">Internato</span><span class="sxs-lookup"><span data-stu-id="03e0f-617">Internship</span></span>            | <span data-ttu-id="03e0f-618">Internato</span><span class="sxs-lookup"><span data-stu-id="03e0f-618">Internship</span></span>  |
| <span data-ttu-id="03e0f-619">Permanente</span><span class="sxs-lookup"><span data-stu-id="03e0f-619">Permanent</span></span>             | <span data-ttu-id="03e0f-620">Permanente</span><span class="sxs-lookup"><span data-stu-id="03e0f-620">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="03e0f-621">Stato civile</span><span class="sxs-lookup"><span data-stu-id="03e0f-621">Marital status</span></span>

<span data-ttu-id="03e0f-622">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-622">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="03e0f-623">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="03e0f-623">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="03e0f-624">Talent</span><span class="sxs-lookup"><span data-stu-id="03e0f-624">Talent</span></span>                 | <span data-ttu-id="03e0f-625">Dayforce</span><span class="sxs-lookup"><span data-stu-id="03e0f-625">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="03e0f-626">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="03e0f-626">Married</span></span>                | <span data-ttu-id="03e0f-627">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="03e0f-627">Married</span></span>                   |
| <span data-ttu-id="03e0f-628">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="03e0f-628">Single</span></span>                 | <span data-ttu-id="03e0f-629">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="03e0f-629">Single</span></span>                    |
| <span data-ttu-id="03e0f-630">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="03e0f-630">Widowed</span></span>                | <span data-ttu-id="03e0f-631">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="03e0f-631">Widowed</span></span>                   |
| <span data-ttu-id="03e0f-632">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="03e0f-632">Divorced</span></span>               | <span data-ttu-id="03e0f-633">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="03e0f-633">Divorced</span></span>                  |
| <span data-ttu-id="03e0f-634">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="03e0f-634">Registered Partnership</span></span> | <span data-ttu-id="03e0f-635">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="03e0f-635">Domestic Partnership</span></span>      |
| <span data-ttu-id="03e0f-636">Nessuna</span><span class="sxs-lookup"><span data-stu-id="03e0f-636">None</span></span>                   | <span data-ttu-id="03e0f-637">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="03e0f-637">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="03e0f-638">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="03e0f-638">Cohabiting</span></span>             | <span data-ttu-id="03e0f-639">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="03e0f-639">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="03e0f-640">Genere</span><span class="sxs-lookup"><span data-stu-id="03e0f-640">Gender</span></span>

<span data-ttu-id="03e0f-641">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-641">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="03e0f-642">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="03e0f-642">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="03e0f-643">Talent</span><span class="sxs-lookup"><span data-stu-id="03e0f-643">Talent</span></span>       | <span data-ttu-id="03e0f-644">Dayforce</span><span class="sxs-lookup"><span data-stu-id="03e0f-644">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="03e0f-645">Maschio</span><span class="sxs-lookup"><span data-stu-id="03e0f-645">Male</span></span>         | <span data-ttu-id="03e0f-646">Maschio</span><span class="sxs-lookup"><span data-stu-id="03e0f-646">Male</span></span>                      |
| <span data-ttu-id="03e0f-647">Femmina</span><span class="sxs-lookup"><span data-stu-id="03e0f-647">Female</span></span>       | <span data-ttu-id="03e0f-648">Femmina</span><span class="sxs-lookup"><span data-stu-id="03e0f-648">Female</span></span>                    |
| <span data-ttu-id="03e0f-649">Non specifico</span><span class="sxs-lookup"><span data-stu-id="03e0f-649">Non-specific</span></span> | <span data-ttu-id="03e0f-650">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="03e0f-650">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="03e0f-651">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="03e0f-651">Payment method</span></span>

<span data-ttu-id="03e0f-652">I metodi di pagamento offrono al dipendente e all'azienda un modo per descrivere la modalità di pagamento dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="03e0f-652">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="03e0f-653">I metodi di pagamento vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-653">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="03e0f-654">Nella tabella seguente vengono illustrati in che modo i metodi di pagamento vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="03e0f-654">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="03e0f-655">Talent</span><span class="sxs-lookup"><span data-stu-id="03e0f-655">Talent</span></span>             | <span data-ttu-id="03e0f-656">Dayforce</span><span class="sxs-lookup"><span data-stu-id="03e0f-656">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="03e0f-657">In contanti</span><span class="sxs-lookup"><span data-stu-id="03e0f-657">Cash</span></span>               | <span data-ttu-id="03e0f-658">In contanti</span><span class="sxs-lookup"><span data-stu-id="03e0f-658">Cash</span></span>                      |
| <span data-ttu-id="03e0f-659">Pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="03e0f-659">Electronic Payment</span></span> | <span data-ttu-id="03e0f-660">Trasferimenti</span><span class="sxs-lookup"><span data-stu-id="03e0f-660">Transfer</span></span>                  |
| <span data-ttu-id="03e0f-661">Verifica</span><span class="sxs-lookup"><span data-stu-id="03e0f-661">Check</span></span>              | <span data-ttu-id="03e0f-662">Assegno</span><span class="sxs-lookup"><span data-stu-id="03e0f-662">Cheque</span></span>                    |
| <span data-ttu-id="03e0f-663">Assegno circolare</span><span class="sxs-lookup"><span data-stu-id="03e0f-663">Bank Draft</span></span>         | <span data-ttu-id="03e0f-664">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="03e0f-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="03e0f-665">Altro</span><span class="sxs-lookup"><span data-stu-id="03e0f-665">Other</span></span>              | <span data-ttu-id="03e0f-666">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="03e0f-666">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="03e0f-667">Tipo di conto bancario</span><span class="sxs-lookup"><span data-stu-id="03e0f-667">Bank account type</span></span>

<span data-ttu-id="03e0f-668">I tipi di conto bancario vengono utilizzati per i pagamenti elettronici ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="03e0f-668">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="03e0f-669">I tipi di conto bancario vengono mappati in Dayforce come informazioni sul conto di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="03e0f-669">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="03e0f-670">I tipi di conto bancario vengono convertiti, come appropriato, nei valori accettati per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="03e0f-670">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="03e0f-671">Talent</span><span class="sxs-lookup"><span data-stu-id="03e0f-671">Talent</span></span>            | <span data-ttu-id="03e0f-672">Dayforce</span><span class="sxs-lookup"><span data-stu-id="03e0f-672">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="03e0f-673">Conto corrente</span><span class="sxs-lookup"><span data-stu-id="03e0f-673">Checking Account</span></span>  | <span data-ttu-id="03e0f-674">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="03e0f-674">CheckingAccount</span></span>           |
| <span data-ttu-id="03e0f-675">Conto retribuzioni</span><span class="sxs-lookup"><span data-stu-id="03e0f-675">Payroll Account</span></span>   | <span data-ttu-id="03e0f-676">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="03e0f-676">PayrollAccount</span></span>            |
| <span data-ttu-id="03e0f-677">Conto di risparmio</span><span class="sxs-lookup"><span data-stu-id="03e0f-677">Savings Account</span></span>   | <span data-ttu-id="03e0f-678">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="03e0f-678">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="03e0f-679">Conto Bankgirot</span><span class="sxs-lookup"><span data-stu-id="03e0f-679">BankGirot account</span></span> | <span data-ttu-id="03e0f-680">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="03e0f-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="03e0f-681">Conto PlusGirot</span><span class="sxs-lookup"><span data-stu-id="03e0f-681">PlusGirot account</span></span> | <span data-ttu-id="03e0f-682">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="03e0f-682">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="03e0f-683">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="03e0f-683">Earning codes</span></span>

<span data-ttu-id="03e0f-684">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="03e0f-684">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="03e0f-685">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="03e0f-685">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="03e0f-686">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="03e0f-686">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="03e0f-687">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="03e0f-687">Supported frequencies</span></span>

- <span data-ttu-id="03e0f-688">Tutti</span><span class="sxs-lookup"><span data-stu-id="03e0f-688">All</span></span>
- <span data-ttu-id="03e0f-689">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="03e0f-689">EVERYPAY</span></span>
- <span data-ttu-id="03e0f-690">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="03e0f-690">EACHPAYPERIOD</span></span>
- <span data-ttu-id="03e0f-691">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="03e0f-691">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="03e0f-692">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="03e0f-692">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="03e0f-693">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-693">1OFMTH</span></span>
- <span data-ttu-id="03e0f-694">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-694">LASTOFMTH</span></span>
- <span data-ttu-id="03e0f-695">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-695">2OFMTH</span></span>
- <span data-ttu-id="03e0f-696">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-696">3OFMTH</span></span>
- <span data-ttu-id="03e0f-697">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-697">4OFMTH</span></span>
- <span data-ttu-id="03e0f-698">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-698">5OFMTH</span></span>
- <span data-ttu-id="03e0f-699">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-699">1N2OFMTH</span></span>
- <span data-ttu-id="03e0f-700">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-700">3N4OFMTH</span></span>
- <span data-ttu-id="03e0f-701">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-701">1N3OFMTH</span></span>
- <span data-ttu-id="03e0f-702">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-702">1N4OFMTH</span></span>
- <span data-ttu-id="03e0f-703">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-703">2N3OFMTH</span></span>
- <span data-ttu-id="03e0f-704">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-704">2N4OFMTH</span></span>
- <span data-ttu-id="03e0f-705">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-705">1N2N3OFMTH</span></span>
- <span data-ttu-id="03e0f-706">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-706">1N2N4OFMTH</span></span>
- <span data-ttu-id="03e0f-707">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-707">1N3N4OFMTH</span></span>
- <span data-ttu-id="03e0f-708">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-708">2N3N4OFMTH</span></span>
- <span data-ttu-id="03e0f-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="03e0f-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="03e0f-710">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="03e0f-710">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="03e0f-711">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="03e0f-711">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="03e0f-712">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="03e0f-712">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="03e0f-713">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="03e0f-713">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="03e0f-714">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="03e0f-714">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="03e0f-715">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="03e0f-715">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="03e0f-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="03e0f-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="03e0f-717">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="03e0f-717">Addresses</span></span>

<span data-ttu-id="03e0f-718">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="03e0f-718">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="03e0f-719">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="03e0f-719">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="03e0f-720">Talent</span><span class="sxs-lookup"><span data-stu-id="03e0f-720">Talent</span></span>              | <span data-ttu-id="03e0f-721">Dayforce</span><span class="sxs-lookup"><span data-stu-id="03e0f-721">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="03e0f-722">Paese</span><span class="sxs-lookup"><span data-stu-id="03e0f-722">Country/Region</span></span>      | <span data-ttu-id="03e0f-723">Codice paese</span><span class="sxs-lookup"><span data-stu-id="03e0f-723">Country Code</span></span>          |
| <span data-ttu-id="03e0f-724">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="03e0f-724">Zip/Postal Code</span></span>     | <span data-ttu-id="03e0f-725">CAP</span><span class="sxs-lookup"><span data-stu-id="03e0f-725">Postal Code</span></span>           |
| <span data-ttu-id="03e0f-726">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="03e0f-726">State</span></span>               | <span data-ttu-id="03e0f-727">Codice stato</span><span class="sxs-lookup"><span data-stu-id="03e0f-727">State Code</span></span>            |
| <span data-ttu-id="03e0f-728">Città</span><span class="sxs-lookup"><span data-stu-id="03e0f-728">City</span></span>                | <span data-ttu-id="03e0f-729">Città</span><span class="sxs-lookup"><span data-stu-id="03e0f-729">City</span></span>                  |
| <span data-ttu-id="03e0f-730">Regione</span><span class="sxs-lookup"><span data-stu-id="03e0f-730">County</span></span>              | <span data-ttu-id="03e0f-731">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="03e0f-731">County (Municipality)</span></span> |
| <span data-ttu-id="03e0f-732">Via</span><span class="sxs-lookup"><span data-stu-id="03e0f-732">Street</span></span>              | <span data-ttu-id="03e0f-733">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="03e0f-733">Address Line 1</span></span>        |
| <span data-ttu-id="03e0f-734">Numero civico</span><span class="sxs-lookup"><span data-stu-id="03e0f-734">Street Number</span></span>       | <span data-ttu-id="03e0f-735">Riga indirizzo 2</span><span class="sxs-lookup"><span data-stu-id="03e0f-735">Address Line 2</span></span>        |
| <span data-ttu-id="03e0f-736">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="03e0f-736">Building Complement</span></span> | <span data-ttu-id="03e0f-737">Riga indirizzo 5</span><span class="sxs-lookup"><span data-stu-id="03e0f-737">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="03e0f-738">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="03e0f-738">Passport number</span></span>

<span data-ttu-id="03e0f-739">I dipendenti possono indicare le informazioni sul passaporto.</span><span class="sxs-lookup"><span data-stu-id="03e0f-739">Employees can declare passport information.</span></span> <span data-ttu-id="03e0f-740">Queste informazioni sono del tipo di identificazione **Passaporto** e vengono integrate in Dayforce come parte delle informazioni di un dipendente specifiche per il Messico.</span><span class="sxs-lookup"><span data-stu-id="03e0f-740">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="03e0f-741">Tipo di identificazione = "Passaporto"</span><span class="sxs-lookup"><span data-stu-id="03e0f-741">Identification Type = "Passport"</span></span>
- <span data-ttu-id="03e0f-742">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="03e0f-742">Issued Date</span></span>
- <span data-ttu-id="03e0f-743">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="03e0f-743">Expiration Date</span></span>

<span data-ttu-id="03e0f-744">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **Passaporto**.</span><span class="sxs-lookup"><span data-stu-id="03e0f-744">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="03e0f-745">Tuttavia, solo l'immissione del passaporto attivo corrente viene integrata in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="03e0f-745">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="03e0f-746">Se tutte le immissioni di passaporto sono scadute, in Dayforce viene integrato il passaporto di emissione più recente.</span><span class="sxs-lookup"><span data-stu-id="03e0f-746">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
