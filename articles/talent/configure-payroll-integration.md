---
title: Configurare l'integrazione delle retribuzioni tra Talent e Dayforce
description: In questo argomento viene descritto come configurare l'integrazione tra Microsoft Dynamics 365 for Talent e Ceridian Dayforce in modo da poter elaborare è un ciclo di pagamenti.
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
ms.openlocfilehash: c26dfed9909b0dbd05fc18c206e5adc947feaef5
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742916"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="7c27b-103">Configurare l'integrazione retribuzioni tra Talent e Dayforce</span><span class="sxs-lookup"><span data-stu-id="7c27b-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7c27b-104">L'integrazione tra Microsoft Dynamics 365 for Talent e Ceridian Dayforce si basa su vari passaggi di configurazione descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7c27b-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="7c27b-105">È necessario configurare l'integrazione sia in Talent che in Dayforce prima di poter elaborare un ciclo di pagamenti.</span><span class="sxs-lookup"><span data-stu-id="7c27b-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="7c27b-106">Quando si utilizza un servizio, ad esempio Dayforce, per completare i cicli di pagamenti, è necessario abilitare l'integrazione in Talent.</span><span class="sxs-lookup"><span data-stu-id="7c27b-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="7c27b-107">L'integrazione richiede dati specifici da Talent.</span><span class="sxs-lookup"><span data-stu-id="7c27b-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="7c27b-108">Di conseguenza, è necessario verificare che i dati che vengono mappati a Dayforce siano configurati in Talent in modo che supporti l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="7c27b-109">L'integrazione utilizza le seguenti categorie generiche di dati:</span><span class="sxs-lookup"><span data-stu-id="7c27b-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="7c27b-110">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="7c27b-110">Human resources data</span></span>
- <span data-ttu-id="7c27b-111">Dati di compensazione</span><span class="sxs-lookup"><span data-stu-id="7c27b-111">Compensation data</span></span>
- <span data-ttu-id="7c27b-112">Data di retribuzione, ad esempio i cicli di pagamenti, i periodi retributivi e i codici reddito</span><span class="sxs-lookup"><span data-stu-id="7c27b-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="7c27b-113">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-113">Worker data</span></span>

<span data-ttu-id="7c27b-114">In questo argomento vengono descritti i passaggi che è necessario completare per abilitare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="7c27b-115">E vengono descritti i tipi di dati e i dettagli di configurazione necessari all'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="7c27b-116">Abilitare l'integrazione</span><span class="sxs-lookup"><span data-stu-id="7c27b-116">Enable the integration</span></span>

<span data-ttu-id="7c27b-117">In Talent è necessario attivare l'integrazione e immettere le informazioni di configurazione per connettersi a Dayforce.</span><span class="sxs-lookup"><span data-stu-id="7c27b-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="7c27b-118">Se si desidera che la transazione contabile prodotta venga importata in Microsoft Dynamics 365 for Finance and Operations, è necessario impostare anche un conto di archiviazione di Microsoft Azure e immettere la stringa di connessione di Archiviazione di Azure in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7c27b-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="7c27b-119">Per attivare l'integrazione in Talent, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="7c27b-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="7c27b-120">Nella pagina **Amministrazione sistema** selezionare **Configurazione di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="7c27b-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="7c27b-121">Immettere l'endpoint FTP (File Transfer Protocol) e il percorso protetto della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="7c27b-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="7c27b-122">Immettere il nome utente e la password dell'utente che accederà al percorso protetto dell'endpoint e della cartella FTP.</span><span class="sxs-lookup"><span data-stu-id="7c27b-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="7c27b-123">Verificare la connessione, secondo le esigenze, e impostare l'opzione **Abilita integrazione retribuzioni** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="7c27b-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="7c27b-124">Quando l'integrazione viene attivata, vengono creati i file e il pacchetto di esportazione dei dati e viene impostata la frequenza.</span><span class="sxs-lookup"><span data-stu-id="7c27b-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="7c27b-125">È possibile cambiare la frequenza in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="7c27b-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="7c27b-126">Per altre informazioni sugli account di Archiviazione di Azure e sulle stringhe di connessione di Archiviazione di Azure, vedere gli argomenti di Azure seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c27b-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="7c27b-127">Account di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="7c27b-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="7c27b-128">Configurare le stringhe di connessione di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="7c27b-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="7c27b-129">Dettagli tecnici quando l'integrazione delle retribuzioni è attivata</span><span class="sxs-lookup"><span data-stu-id="7c27b-129">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="7c27b-130">L'attivazione dell'integrazione delle retribuzioni comporta due effetti primari:</span><span class="sxs-lookup"><span data-stu-id="7c27b-130">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="7c27b-131">Viene creato un progetto di esportazione di dati denominato "Esportazione integrazione delle retribuzioni".</span><span class="sxs-lookup"><span data-stu-id="7c27b-131">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="7c27b-132">Questo progetto contiene le entità e i campi necessari per l'integrazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="7c27b-132">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="7c27b-133">Per esaminare il progetto, andare a **Amministrazione sistema**, selezionare il riquadro **Gestione dati** e infine aprire il progetto dati dall'elenco di progetti.</span><span class="sxs-lookup"><span data-stu-id="7c27b-133">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="7c27b-134">Questo processo batch esegue il progetto di esportazione dei dati, codifica il pacchetto dati risultante e trasferisce il file del pacchetto dati all'endpoint SFTP configurato nella schermata **Configurazione di integrazione**.</span><span class="sxs-lookup"><span data-stu-id="7c27b-134">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="7c27b-135">Il pacchetto dati trasferito all'endpoint SFTP viene codificato utilizzando una chiave univoca per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7c27b-135">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="7c27b-136">La chiave è un Azure Key Vault accessibile solo da Ceridian.</span><span class="sxs-lookup"><span data-stu-id="7c27b-136">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="7c27b-137">Non è possibile decrittografare ed esaminare il contenuto del pacchetto dati.</span><span class="sxs-lookup"><span data-stu-id="7c27b-137">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="7c27b-138">Se è necessario esaminare il contenuto del pacchetto dati, esportare manualmente il progetto dati "Esportazione integrazione delle retribuzioni", scaricarlo e quindi aprirlo.</span><span class="sxs-lookup"><span data-stu-id="7c27b-138">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="7c27b-139">L'esportazione manuale non comporta la crittografia o il trasferimento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7c27b-139">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="7c27b-140">Configurare i dati</span><span class="sxs-lookup"><span data-stu-id="7c27b-140">Configure your data</span></span> 

<span data-ttu-id="7c27b-141">Per elaborare le retribuzioni, è necessario configurare i dati di Risorse umane in Talent.</span><span class="sxs-lookup"><span data-stu-id="7c27b-141">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="7c27b-142">È necessario impostare i dati dell'organizzazione, ad esempio mansioni e posizioni, insieme alle informazioni sui benefit e sulle compensazioni.</span><span class="sxs-lookup"><span data-stu-id="7c27b-142">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="7c27b-143">Queste informazioni includono informazioni sull'impiego, la retribuzione e le detrazioni che sono richieste per generare la retribuzione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="7c27b-143">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="7c27b-144">Dati di Risorse umane</span><span class="sxs-lookup"><span data-stu-id="7c27b-144">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="7c27b-145">Benefit</span><span class="sxs-lookup"><span data-stu-id="7c27b-145">Benefits</span></span> 

<span data-ttu-id="7c27b-146">Le risorse umane dispongono di strumenti per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori.</span><span class="sxs-lookup"><span data-stu-id="7c27b-146">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="7c27b-147">Quando si creano i benefit, tenere presenti i seguenti dati e configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="7c27b-147">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="7c27b-148">Piani di benefit</span><span class="sxs-lookup"><span data-stu-id="7c27b-148">Benefit plans</span></span>

- <span data-ttu-id="7c27b-149">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-149">Plan (required)</span></span>
- <span data-ttu-id="7c27b-150">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-150">Type (required)</span></span>
- <span data-ttu-id="7c27b-151">Impatto retribuzioni (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-151">Payroll impact (required)</span></span>
- <span data-ttu-id="7c27b-152">Recupera arretrati</span><span class="sxs-lookup"><span data-stu-id="7c27b-152">Recover arrears</span></span>
- <span data-ttu-id="7c27b-153">Metodo di detrazione</span><span class="sxs-lookup"><span data-stu-id="7c27b-153">Deduction method</span></span>
- <span data-ttu-id="7c27b-154">Priorità detrazione</span><span class="sxs-lookup"><span data-stu-id="7c27b-154">Deduction priority</span></span>
- <span data-ttu-id="7c27b-155">Periodo limite</span><span class="sxs-lookup"><span data-stu-id="7c27b-155">Limit period</span></span>
- <span data-ttu-id="7c27b-156">Importo limite</span><span class="sxs-lookup"><span data-stu-id="7c27b-156">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="7c27b-157">Benefit</span><span class="sxs-lookup"><span data-stu-id="7c27b-157">Benefits</span></span>

- <span data-ttu-id="7c27b-158">Piano (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-158">Plan (required)</span></span>
- <span data-ttu-id="7c27b-159">Tipo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-159">Type (required)</span></span>
- <span data-ttu-id="7c27b-160">Opzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-160">Option (required)</span></span>
- <span data-ttu-id="7c27b-161">ID benefit (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-161">Benefit ID (required)</span></span>
- <span data-ttu-id="7c27b-162">Frequenza</span><span class="sxs-lookup"><span data-stu-id="7c27b-162">Frequency</span></span>
- <span data-ttu-id="7c27b-163">Base</span><span class="sxs-lookup"><span data-stu-id="7c27b-163">Basis</span></span>
- <span data-ttu-id="7c27b-164">Importo o coefficiente</span><span class="sxs-lookup"><span data-stu-id="7c27b-164">Amount or rate</span></span>
- <span data-ttu-id="7c27b-165">Codice di reddito</span><span class="sxs-lookup"><span data-stu-id="7c27b-165">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="7c27b-166">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="7c27b-166">Supported frequencies</span></span> 

- <span data-ttu-id="7c27b-167">Ogni settimana</span><span class="sxs-lookup"><span data-stu-id="7c27b-167">Weekly</span></span>
- <span data-ttu-id="7c27b-168">Bisettimanale</span><span class="sxs-lookup"><span data-stu-id="7c27b-168">Bi-weekly</span></span>
- <span data-ttu-id="7c27b-169">Quindicinale</span><span class="sxs-lookup"><span data-stu-id="7c27b-169">Semi-monthly</span></span>
- <span data-ttu-id="7c27b-170">Ogni mese</span><span class="sxs-lookup"><span data-stu-id="7c27b-170">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="7c27b-171">Basi supportate</span><span class="sxs-lookup"><span data-stu-id="7c27b-171">Supported bases</span></span> 

- <span data-ttu-id="7c27b-172">Importo fisso</span><span class="sxs-lookup"><span data-stu-id="7c27b-172">Fixed amount</span></span>
- <span data-ttu-id="7c27b-173">Percentuale di redditi</span><span class="sxs-lookup"><span data-stu-id="7c27b-173">Percent of earnings</span></span>
- <span data-ttu-id="7c27b-174">Ore di produzione</span><span class="sxs-lookup"><span data-stu-id="7c27b-174">Productive hours</span></span>

<span data-ttu-id="7c27b-175">Dayforce crea le seguenti detrazioni, in base all'impatto delle retribuzioni definito nel piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="7c27b-175">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="7c27b-176">Selezione in Talent</span><span class="sxs-lookup"><span data-stu-id="7c27b-176">Selection in Talent</span></span>        | <span data-ttu-id="7c27b-177">Risultato in Dayforce</span><span class="sxs-lookup"><span data-stu-id="7c27b-177">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="7c27b-178">Nessuna</span><span class="sxs-lookup"><span data-stu-id="7c27b-178">None</span></span>                       | <span data-ttu-id="7c27b-179">Non viene creata alcuna detrazione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-179">No deduction is created.</span></span>                      |
| <span data-ttu-id="7c27b-180">Solo detrazione</span><span class="sxs-lookup"><span data-stu-id="7c27b-180">Deduction only</span></span>             | <span data-ttu-id="7c27b-181">Viene creata una detrazione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="7c27b-181">An employee deduction is created.</span></span>             |
| <span data-ttu-id="7c27b-182">Solo contribuzione</span><span class="sxs-lookup"><span data-stu-id="7c27b-182">Contribution only</span></span>          | <span data-ttu-id="7c27b-183">Viene creata una detrazione del datore di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7c27b-183">An employer deduction is created.</span></span>             |
| <span data-ttu-id="7c27b-184">Detrazione e contribuzione</span><span class="sxs-lookup"><span data-stu-id="7c27b-184">Deduction and contribution</span></span> | <span data-ttu-id="7c27b-185">Vengono create detrazioni del datore di lavoro e del dipendente.</span><span class="sxs-lookup"><span data-stu-id="7c27b-185">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="7c27b-186">Per altre informazioni su come definire e gestire un programma di benefit, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c27b-186">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="7c27b-187">Realizzare un programma di benefit per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="7c27b-187">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="7c27b-188">Creare un nuovo benefit</span><span class="sxs-lookup"><span data-stu-id="7c27b-188">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="7c27b-189">Definire regole e criteri di idoneità ai benefit</span><span class="sxs-lookup"><span data-stu-id="7c27b-189">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="7c27b-190">Iscrivere e rimuovere benefit da lavoratori</span><span class="sxs-lookup"><span data-stu-id="7c27b-190">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="7c27b-191">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="7c27b-191">Compensation</span></span> 

<span data-ttu-id="7c27b-192">La gestione delle retribuzioni consente di controllare la liquidazione dei premi e della retribuzione base.</span><span class="sxs-lookup"><span data-stu-id="7c27b-192">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="7c27b-193">La retribuzione di base fissa di un dipendente e gli aumenti per merito sono controllati mediante piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="7c27b-193">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="7c27b-194">È possibile controllare il pagamento degli incentivi, ad esempio il pagamento dei bonus, dei premi produttività, dei diritti di opzione, delle sovvenzioni, oltre che dei premi una tantum, tramite i piani di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="7c27b-194">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="7c27b-195">Dayforce utilizza le informazioni sulla compensazione per calcolare la retribuzione annuale o oraria di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="7c27b-195">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="7c27b-196">I piani di retribuzione fissa e conversioni della retribuzione sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="7c27b-196">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="7c27b-197">I dipendenti devono essere associati a un piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="7c27b-197">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="7c27b-198">Per ulteriori informazioni sui piani di retribuzione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c27b-198">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="7c27b-199">Creare i piani di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="7c27b-199">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="7c27b-200">Creare i piani di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="7c27b-200">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="7c27b-201">Sviluppare una struttura e piani di stipendi/retribuzioni</span><span class="sxs-lookup"><span data-stu-id="7c27b-201">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="7c27b-202">Processo retributivo</span><span class="sxs-lookup"><span data-stu-id="7c27b-202">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="7c27b-203">Definire il processo retributivo e calcolare i risultati</span><span class="sxs-lookup"><span data-stu-id="7c27b-203">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="7c27b-204">Iscrivere un dipendente a un piano di retribuzione fisso</span><span class="sxs-lookup"><span data-stu-id="7c27b-204">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="7c27b-205">Iscrivere un dipendente a un piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="7c27b-205">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="7c27b-206">Mansioni</span><span class="sxs-lookup"><span data-stu-id="7c27b-206">Jobs</span></span> 

<span data-ttu-id="7c27b-207">Una mansione è una raccolta delle attività e delle responsabilità proprie della persona assegnata a una mansione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-207">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="7c27b-208">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="7c27b-208">For more information, see the following topics:</span></span>

- [<span data-ttu-id="7c27b-209">Impostazione dei componenti di una mansione</span><span class="sxs-lookup"><span data-stu-id="7c27b-209">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="7c27b-210">Definire nuovi processi</span><span class="sxs-lookup"><span data-stu-id="7c27b-210">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="7c27b-211">Posizioni</span><span class="sxs-lookup"><span data-stu-id="7c27b-211">Positions</span></span>

<span data-ttu-id="7c27b-212">Una posizione è una singola istanza di un processo.</span><span class="sxs-lookup"><span data-stu-id="7c27b-212">A position is an individual instance of a job.</span></span> <span data-ttu-id="7c27b-213">Ad esempio, la posizione "Manager vendite (Est") è una delle posizioni associate alla mansione "Manager vendite".</span><span class="sxs-lookup"><span data-stu-id="7c27b-213">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="7c27b-214">Una posizione è presente in un reparto.</span><span class="sxs-lookup"><span data-stu-id="7c27b-214">A position exists in a department.</span></span> <span data-ttu-id="7c27b-215">È possibile associare un solo lavoratore a ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-215">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="7c27b-216">Tenere a mente i seguenti dati e la configurazione quando si impostano le posizioni:</span><span class="sxs-lookup"><span data-stu-id="7c27b-216">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="7c27b-217">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-217">Position (required)</span></span>
- <span data-ttu-id="7c27b-218">Descrizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-218">Description (required)</span></span>
- <span data-ttu-id="7c27b-219">Mansione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-219">Job (required)</span></span>
- <span data-ttu-id="7c27b-220">Reparto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-220">Department (required)</span></span>
- <span data-ttu-id="7c27b-221">Tipo di posizione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-221">Position type (required)</span></span>
- <span data-ttu-id="7c27b-222">Equivalente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="7c27b-222">Full-time equivalent</span></span>
- <span data-ttu-id="7c27b-223">Ore regolari annuali (obbligatorie)</span><span class="sxs-lookup"><span data-stu-id="7c27b-223">Annual regular hours (required)</span></span>
- <span data-ttu-id="7c27b-224">Pagamento in base alla persona giuridica (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-224">Paid by legal entity (required)</span></span>
- <span data-ttu-id="7c27b-225">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="7c27b-225">Pay cycle (required)</span></span>
- <span data-ttu-id="7c27b-226">Dimensione finanziaria predefinita - Centro di costo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-226">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="7c27b-227">Assegnazione del lavoratore - Lavoratore, inizio assegnazione, fine assegnazione, codice motivo</span><span class="sxs-lookup"><span data-stu-id="7c27b-227">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="7c27b-228">Se nello stesso reparto più posizioni sono associate alla stessa mansione, vengono consolidate in una singola posizione in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="7c27b-228">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="7c27b-229">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="7c27b-229">For more information, see the following topics:</span></span>

- [<span data-ttu-id="7c27b-230">Organizzare la forza lavoro utilizzando i reparti, le mansioni e le posizioni</span><span class="sxs-lookup"><span data-stu-id="7c27b-230">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="7c27b-231">Impostare le posizioni</span><span class="sxs-lookup"><span data-stu-id="7c27b-231">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="7c27b-232">Reparti</span><span class="sxs-lookup"><span data-stu-id="7c27b-232">Departments</span></span>

<span data-ttu-id="7c27b-233">Un reparto è un'unità operativa che rappresenta una categoria o un'area operativa di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-233">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="7c27b-234">Un reparto è responsabile di una specifica area dell'organizzazione, ad esempio la vendita, la contabilità o le risorse umane.</span><span class="sxs-lookup"><span data-stu-id="7c27b-234">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="7c27b-235">È possibile utilizzare i reparti per creare report sulle aree operative.</span><span class="sxs-lookup"><span data-stu-id="7c27b-235">You can use departments to report on functional areas.</span></span> <span data-ttu-id="7c27b-236">I reparti possono essere responsabili di profitti e perdite.</span><span class="sxs-lookup"><span data-stu-id="7c27b-236">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="7c27b-237">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="7c27b-237">For more information, see the following topics:</span></span>

- [<span data-ttu-id="7c27b-238">Creare un reparto e associarlo alla gerarchia reparti</span><span class="sxs-lookup"><span data-stu-id="7c27b-238">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="7c27b-239">Definire nuovi reparti</span><span class="sxs-lookup"><span data-stu-id="7c27b-239">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="7c27b-240">Cicli e periodi retributivi</span><span class="sxs-lookup"><span data-stu-id="7c27b-240">Pay cycles and pay periods</span></span>

<span data-ttu-id="7c27b-241">Un ciclo retributivo determina la frequenza di elaborazione delle retribuzioni e i giorni specifici in cui i lavoratori vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="7c27b-241">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="7c27b-242">Un ciclo retributivo può essere ad esempio mensile e i dipendenti possono essere pagati l'ultimo giorno del mese.</span><span class="sxs-lookup"><span data-stu-id="7c27b-242">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="7c27b-243">Un ciclo retributivo può in alternativa essere settimanale e i dipendenti possono essere pagati il giovedì successivo alla fine del periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="7c27b-243">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="7c27b-244">I cicli retributivi vengono assegnati alle posizioni per controllare quando i lavoratori in tali posizioni vengono pagati.</span><span class="sxs-lookup"><span data-stu-id="7c27b-244">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="7c27b-245">Dopo aver creato i cicli retributivi, è possibile generare periodi retributivi per ogni ciclo.</span><span class="sxs-lookup"><span data-stu-id="7c27b-245">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="7c27b-246">Ogni periodo retributivo include una data di pagamento predefinita in base alle informazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="7c27b-246">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="7c27b-247">Tuttavia, è possibile modificare la data di pagamento predefinita in un periodo retributivo per consentire eccezioni, ad esempio quando la data di pagamento cade in un giorno festivo.</span><span class="sxs-lookup"><span data-stu-id="7c27b-247">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="7c27b-248">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="7c27b-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="7c27b-249">Ciclo retributivo (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="7c27b-249">Pay cycle (required)</span></span>
- <span data-ttu-id="7c27b-250">Frequenza ciclo retributivo (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-250">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="7c27b-251">Data di inizio del periodo (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-251">Period start date (first pay period required)</span></span>
- <span data-ttu-id="7c27b-252">Data di pagamento predefinita (primo periodo retributivo obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-252">Default payment date (first pay period required)</span></span>

<span data-ttu-id="7c27b-253">Queste informazioni sono integrate con Dayforce come gruppi retributivi e sono separata in base al paese o alla regione per ogni ciclo retributivo.</span><span class="sxs-lookup"><span data-stu-id="7c27b-253">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="7c27b-254">Prima dell'integrazione è necessario generare almeno un periodo retributivo.</span><span class="sxs-lookup"><span data-stu-id="7c27b-254">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="7c27b-255">Dayforce genera calendari di gruppi retributivi e date di pagamento, in base alla data di inizio del primo periodo retributivo e alla data di pagamento predefinita che viene impostata in Talent.</span><span class="sxs-lookup"><span data-stu-id="7c27b-255">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="7c27b-256">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="7c27b-256">Earning codes</span></span>

<span data-ttu-id="7c27b-257">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="7c27b-257">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="7c27b-258">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="7c27b-258">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="7c27b-259">Le informazioni seguenti vengono utilizzate in Dayforce:</span><span class="sxs-lookup"><span data-stu-id="7c27b-259">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="7c27b-260">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-260">Earning Code (required)</span></span>
- <span data-ttu-id="7c27b-261">descrizione</span><span class="sxs-lookup"><span data-stu-id="7c27b-261">Description</span></span>
- <span data-ttu-id="7c27b-262">Unità di misura</span><span class="sxs-lookup"><span data-stu-id="7c27b-262">Unit of measure</span></span>
- <span data-ttu-id="7c27b-263">Produttivo</span><span class="sxs-lookup"><span data-stu-id="7c27b-263">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="7c27b-264">Dati del lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-264">Worker data</span></span>

<span data-ttu-id="7c27b-265">I record per i diversi tipi di lavoratori a disposizione sono importanti per i sistemi di gestione delle risorse umane e delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="7c27b-265">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="7c27b-266">Le informazioni immesse possono essere utilizzate per tenere traccia di informazioni personali e sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="7c27b-266">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="7c27b-267">È possibile gestire le seguenti informazioni per i lavoratori:</span><span class="sxs-lookup"><span data-stu-id="7c27b-267">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="7c27b-268">**Base** - Gestire le informazioni di base su un lavoratore, ad esempio le informazioni sui contatti, le informazioni demografiche, le informazioni di identificazione, le informazioni sulla famiglia, lo stato di servizio militare, le informazioni sull'espatrio, e i contatti personali e di emergenza.</span><span class="sxs-lookup"><span data-stu-id="7c27b-268">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="7c27b-269">**Impiego** - Consente di gestire le informazioni sull'impiego di un lavoratore, ad esempio rapporto con l'organizzazione o la società, assegnazione della posizione, date di inizio e fine, idoneità al lavoro, condizioni di impiego, pensionamento, ferie e trasferimento.</span><span class="sxs-lookup"><span data-stu-id="7c27b-269">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="7c27b-270">**Congedo e assenza** - Consente di gestire le informazioni sulle assenze di un lavoratore, ad esempio calendari di lavoro, transazioni assenze e impostazione assenze.</span><span class="sxs-lookup"><span data-stu-id="7c27b-270">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="7c27b-271">**Retribuzioni** - Consente di gestire le informazioni sui piani di retribuzione di un lavoratore, ad esempio registrazione del piano, premi, prestazioni, provvigione, dati fiscali, pensionamento e detrazioni sullo stipendio.</span><span class="sxs-lookup"><span data-stu-id="7c27b-271">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="7c27b-272">Quando si immettono le informazioni su un lavoratore, tenere presenti i seguenti dati e le configurazioni utilizzati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="7c27b-272">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="7c27b-273">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="7c27b-273">General information</span></span>

- <span data-ttu-id="7c27b-274">Numero dipendente (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-274">Personnel number (required)</span></span>
- <span data-ttu-id="7c27b-275">Nome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-275">First name (required)</span></span>
- <span data-ttu-id="7c27b-276">Cognome (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-276">Last name (required)</span></span>
- <span data-ttu-id="7c27b-277">Secondo nome</span><span class="sxs-lookup"><span data-stu-id="7c27b-277">Middle name</span></span>
- <span data-ttu-id="7c27b-278">Data di anzianità</span><span class="sxs-lookup"><span data-stu-id="7c27b-278">Seniority date</span></span>
- <span data-ttu-id="7c27b-279">Nome noto</span><span class="sxs-lookup"><span data-stu-id="7c27b-279">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="7c27b-280">Informazioni personali</span><span class="sxs-lookup"><span data-stu-id="7c27b-280">Personal information</span></span>

- <span data-ttu-id="7c27b-281">Stato civile (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-281">Marital status (required)</span></span>
- <span data-ttu-id="7c27b-282">Data di nascita (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-282">Birth date (required)</span></span>
- <span data-ttu-id="7c27b-283">Sesso (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-283">Gender (required)</span></span>
- <span data-ttu-id="7c27b-284">Persona disabile</span><span class="sxs-lookup"><span data-stu-id="7c27b-284">Person with disabilities</span></span>
- <span data-ttu-id="7c27b-285">Nazionalità paese regione (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="7c27b-285">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="7c27b-286">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="7c27b-286">Address information</span></span>

- <span data-ttu-id="7c27b-287">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-287">Primary (required)</span></span>
- <span data-ttu-id="7c27b-288">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-288">Country/region (required)</span></span>
- <span data-ttu-id="7c27b-289">Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-289">Postal code (required)</span></span>
- <span data-ttu-id="7c27b-290">Numero civico (obbligatorio) (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="7c27b-290">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="7c27b-291">Informazioni aggiuntive sull'indirizzo (solo per il Messico)</span><span class="sxs-lookup"><span data-stu-id="7c27b-291">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="7c27b-292">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-292">City (required)</span></span>
- <span data-ttu-id="7c27b-293">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-293">State (required)</span></span>
- <span data-ttu-id="7c27b-294">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-294">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="7c27b-295">Informazioni contatto</span><span class="sxs-lookup"><span data-stu-id="7c27b-295">Contact information</span></span> 

- <span data-ttu-id="7c27b-296">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-296">Primary (required)</span></span>
- <span data-ttu-id="7c27b-297">Numero contatto (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-297">Contact number (required)</span></span>
- <span data-ttu-id="7c27b-298">Interno</span><span class="sxs-lookup"><span data-stu-id="7c27b-298">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="7c27b-299">Informazioni sulle retribuzioni e codici di reddito</span><span class="sxs-lookup"><span data-stu-id="7c27b-299">Payroll information and earning codes</span></span>

<span data-ttu-id="7c27b-300">Ai dipendenti possono essere assegnati redditi specifici a una determinata frequenza di pagamento e un metodo di pagamento preferito.</span><span class="sxs-lookup"><span data-stu-id="7c27b-300">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="7c27b-301">I campi seguenti vengono utilizzati in Dayforce per garantire che le preferenze e le impostazioni vengano utilizzate.</span><span class="sxs-lookup"><span data-stu-id="7c27b-301">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="7c27b-302">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="7c27b-302">Earning codes</span></span>

- <span data-ttu-id="7c27b-303">Posizione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-303">Position (required)</span></span>
- <span data-ttu-id="7c27b-304">Codice di reddito (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-304">Earning Code (required)</span></span>
- <span data-ttu-id="7c27b-305">Frequenza (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-305">Frequency (required)</span></span>
- <span data-ttu-id="7c27b-306">Importo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-306">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="7c27b-307">Informazioni retribuzioni</span><span class="sxs-lookup"><span data-stu-id="7c27b-307">Payroll information</span></span>

- <span data-ttu-id="7c27b-308">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="7c27b-308">Payment Method</span></span>
- <span data-ttu-id="7c27b-309">Area economica (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-309">Economic Region (required)</span></span>
- <span data-ttu-id="7c27b-310">ID benefit dipendente</span><span class="sxs-lookup"><span data-stu-id="7c27b-310">Employee Benefits ID</span></span>
- <span data-ttu-id="7c27b-311">Numero documento identità (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-311">National ID Number (required)</span></span>
- <span data-ttu-id="7c27b-312">Numero servizio militare</span><span class="sxs-lookup"><span data-stu-id="7c27b-312">Military Service Number</span></span>
- <span data-ttu-id="7c27b-313">ID turno (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-313">Shift ID (required)</span></span>
- <span data-ttu-id="7c27b-314">Numero imposta (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-314">Tax Number (required)</span></span>
- <span data-ttu-id="7c27b-315">ID sindacato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-315">Union ID (required)</span></span>
- <span data-ttu-id="7c27b-316">ID giorno lavorativo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-316">Work Day ID (required)</span></span>
- <span data-ttu-id="7c27b-317">Numero permesso di lavoro</span><span class="sxs-lookup"><span data-stu-id="7c27b-317">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="7c27b-318">Per il metodo di pagamento, il Messico supporta **Contante**, **Assegno** (l'assegno fisico della società) e **Pagamento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="7c27b-318">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="7c27b-319">Se non viene specificato alcun metodo di pagamento, **Assegno** è 'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7c27b-319">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="7c27b-320">Dettagli impiego</span><span class="sxs-lookup"><span data-stu-id="7c27b-320">Employment details</span></span>

<span data-ttu-id="7c27b-321">Lo storico dei dettagli impiego viene utilizzato come informazioni chiave da cui derivare gli stati di assunzione, termine e riassunzione di un dipendente Dayforce.</span><span class="sxs-lookup"><span data-stu-id="7c27b-321">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="7c27b-322">Dayforce supporta solo un record di impiego attivo alla volta.</span><span class="sxs-lookup"><span data-stu-id="7c27b-322">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="7c27b-323">Data di inizio impiego (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-323">Employment start date (required)</span></span>
- <span data-ttu-id="7c27b-324">Data di fine impiego</span><span class="sxs-lookup"><span data-stu-id="7c27b-324">Employment end date</span></span>
- <span data-ttu-id="7c27b-325">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="7c27b-325">Start date</span></span>
- <span data-ttu-id="7c27b-326">Data di inizio rettificata</span><span class="sxs-lookup"><span data-stu-id="7c27b-326">Adjusted start date</span></span>
- <span data-ttu-id="7c27b-327">Data fine rapporto (obbligatoria con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="7c27b-327">Termination date (required upon termination)</span></span>
- <span data-ttu-id="7c27b-328">Motivo fine rapporto (obbligatorio con il fine rapporto)</span><span class="sxs-lookup"><span data-stu-id="7c27b-328">Termination reason (required upon termination)</span></span>

<span data-ttu-id="7c27b-329">Le date chiave del dipendente sono derivate utilizzando le informazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="7c27b-329">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="7c27b-330">Talent</span><span class="sxs-lookup"><span data-stu-id="7c27b-330">Talent</span></span>                | <span data-ttu-id="7c27b-331">Dayforce</span><span class="sxs-lookup"><span data-stu-id="7c27b-331">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7c27b-332">Data di assunzione più recente</span><span class="sxs-lookup"><span data-stu-id="7c27b-332">Most recent hire date</span></span> | <span data-ttu-id="7c27b-333">Inizio dell'impiego del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="7c27b-333">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="7c27b-334">Data fine rapporto</span><span class="sxs-lookup"><span data-stu-id="7c27b-334">Termination date</span></span>      | <span data-ttu-id="7c27b-335">Data di fine rapporto del record corrente dello storico di impiego non concluso</span><span class="sxs-lookup"><span data-stu-id="7c27b-335">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="7c27b-336">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="7c27b-336">Start date</span></span>            | <span data-ttu-id="7c27b-337">Data di inizio rettificata, data di inizio o inizio dell'impiego del record corrente dello storico di impiego non attivo</span><span class="sxs-lookup"><span data-stu-id="7c27b-337">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="7c27b-338">Data di assunzione originale</span><span class="sxs-lookup"><span data-stu-id="7c27b-338">Original hire date</span></span>    | <span data-ttu-id="7c27b-339">Inizio dell'impiego del record dello storico di impiego meno recente</span><span class="sxs-lookup"><span data-stu-id="7c27b-339">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="7c27b-340">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="7c27b-340">Compensation</span></span>

<span data-ttu-id="7c27b-341">Un piano di retribuzione fissa deve essere associato alla posizione primaria di ogni dipendente durante un periodo di impiego.</span><span class="sxs-lookup"><span data-stu-id="7c27b-341">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="7c27b-342">Questo periodo inizia alla data in cui il dipendente è stato assunto (o la data di inizio dell'impiego) e continua fino alla fine del rapporto.</span><span class="sxs-lookup"><span data-stu-id="7c27b-342">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="7c27b-343">Data di validità (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-343">Effective Date (required)</span></span>
- <span data-ttu-id="7c27b-344">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="7c27b-344">Expiration date</span></span>
- <span data-ttu-id="7c27b-345">Retribuzione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-345">Pay Rate (required)</span></span>
- <span data-ttu-id="7c27b-346">Conversioni retribuzione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-346">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="7c27b-347">Equivalente annuale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-347">Annual equivalent (required)</span></span>
- <span data-ttu-id="7c27b-348">Equivalente orario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-348">Hourly equivalent (required)</span></span>

<span data-ttu-id="7c27b-349">Se un dipendente a ore ha più posizioni, la retribuzione fissa della posizione primaria viene importata in Dayforce come il tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="7c27b-349">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="7c27b-350">Per le posizioni non principali, la tariffa oraria viene salvata nella posizione corrispondente in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="7c27b-350">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="7c27b-351">Se un dipendente stipendiato ha più posizioni, la tariffa oraria cumulativa e lo stipendio annuale di tutte le posizioni attive vengono calcolati e utilizzati come tariffa/stipendio di base del dipendente.</span><span class="sxs-lookup"><span data-stu-id="7c27b-351">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="7c27b-352">Numeri di identificazione</span><span class="sxs-lookup"><span data-stu-id="7c27b-352">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="7c27b-353">Numero di Previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="7c27b-353">Social Security identifier</span></span> 

<span data-ttu-id="7c27b-354">Ogni dipendente deve avere un identificatore primario.</span><span class="sxs-lookup"><span data-stu-id="7c27b-354">Every employee must have one primary identifier.</span></span> <span data-ttu-id="7c27b-355">Questo identificatore deve essere di tipo identificatore **SSN**.</span><span class="sxs-lookup"><span data-stu-id="7c27b-355">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="7c27b-356">In Dayforce, viene ricavato automaticamente come identificatore di previdenza sociale del dipendente per l'assunzione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-356">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="7c27b-357">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-357">Primary (required)</span></span>
- <span data-ttu-id="7c27b-358">Tipo di identificazione = "SSN"</span><span class="sxs-lookup"><span data-stu-id="7c27b-358">Identification Type = "SSN"</span></span>
- <span data-ttu-id="7c27b-359">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="7c27b-359">Issued Date</span></span>
- <span data-ttu-id="7c27b-360">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="7c27b-360">Expiration Date</span></span>

<span data-ttu-id="7c27b-361">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **SSN**.</span><span class="sxs-lookup"><span data-stu-id="7c27b-361">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="7c27b-362">Tuttavia, solo il record che è contrassegnato come **Primario** viene integrato in Dayforce, a prescindere che il numero sia attivo o scaduto.</span><span class="sxs-lookup"><span data-stu-id="7c27b-362">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="7c27b-363">Esborsi e conti bancari</span><span class="sxs-lookup"><span data-stu-id="7c27b-363">Bank accounts and disbursements</span></span>

<span data-ttu-id="7c27b-364">È necessario immettere informazioni sul conto bancario valide per un dipendente che scelga di essere pagato tramite trasferimenti di conto bancario.</span><span class="sxs-lookup"><span data-stu-id="7c27b-364">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="7c27b-365">Talent</span><span class="sxs-lookup"><span data-stu-id="7c27b-365">Talent</span></span>                         | <span data-ttu-id="7c27b-366">Dayforce</span><span class="sxs-lookup"><span data-stu-id="7c27b-366">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7c27b-367">Numero conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-367">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="7c27b-368">Codice SWIFT (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-368">SWIFT code (required)</span></span>          | <span data-ttu-id="7c27b-369">Campo **ID banca** utilizzato durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="7c27b-369">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="7c27b-370">Codice filiale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-370">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="7c27b-371">Tipo di conto bancario (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-371">Bank account type (required)</span></span>   | <span data-ttu-id="7c27b-372">Campo **Tipo di conto** utilizzando durante l'elaborazione delle retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="7c27b-372">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="7c27b-373">I valori supportati includono **Controllo** e **Retribuzioni**.</span><span class="sxs-lookup"><span data-stu-id="7c27b-373">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="7c27b-374">I dipendenti che scelgono di essere pagati tramite trasferimenti di conto bancario devono fornire un collegamento a un conto rimanente che è sotto la persona giuridica che ha l'indirizzo primario in Messico ed è associato a un conto bancario valido presso una banca messicana.</span><span class="sxs-lookup"><span data-stu-id="7c27b-374">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="7c27b-375">Tutti gli altri account non di rimanenze verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="7c27b-375">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="7c27b-376">Informazioni indirizzo</span><span class="sxs-lookup"><span data-stu-id="7c27b-376">Address information</span></span>

<span data-ttu-id="7c27b-377">Ogni dipendente deve avere un'ubicazione primaria.</span><span class="sxs-lookup"><span data-stu-id="7c27b-377">Every employee must have one primary location.</span></span> <span data-ttu-id="7c27b-378">In Dayforce, questa ubicazione viene utilizzata per determinare la principale residenza del dipendente a scopo fiscale.</span><span class="sxs-lookup"><span data-stu-id="7c27b-378">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="7c27b-379">Principale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-379">Primary (required)</span></span>
- <span data-ttu-id="7c27b-380">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-380">Country/region (required)</span></span>
- <span data-ttu-id="7c27b-381">CAP/Codice postale (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-381">Zip/postal code (required)</span></span>
- <span data-ttu-id="7c27b-382">Via (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-382">Street (required)</span></span>
- <span data-ttu-id="7c27b-383">Numero civico (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-383">Street Number (required)</span></span>
- <span data-ttu-id="7c27b-384">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="7c27b-384">Building Complement</span></span>
- <span data-ttu-id="7c27b-385">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-385">City (required)</span></span>
- <span data-ttu-id="7c27b-386">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-386">State (required)</span></span>
- <span data-ttu-id="7c27b-387">Regione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-387">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="7c27b-388">Configurare i dati per generare le retribuzioni negli Stati Uniti e in Canada</span><span class="sxs-lookup"><span data-stu-id="7c27b-388">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="7c27b-389">Se si desidera generare la retribuzione per i dipendenti negli Stati Uniti e in Canada, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="7c27b-389">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="7c27b-390">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="7c27b-390">Departments are required on positions.</span></span>
- <span data-ttu-id="7c27b-391">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="7c27b-391">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="7c27b-392">È possibile configurare Talent per far sì che Posizioni specifichi un reparto.</span><span class="sxs-lookup"><span data-stu-id="7c27b-392">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="7c27b-393">A tale scopo, andare a **Posizioni condivise Risorse umane > Posizioni > Richiedi reparti su posizioni**.</span><span class="sxs-lookup"><span data-stu-id="7c27b-393">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="7c27b-394">Si consiglia di applicare questa impostazione per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-394">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="7c27b-395">Tipi di lavoro</span><span class="sxs-lookup"><span data-stu-id="7c27b-395">Job types</span></span>

<span data-ttu-id="7c27b-396">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="7c27b-396">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="7c27b-397">I tipi di mansione sono necessari per elaborare le retribuzioni negli Stati Uniti e in Canada.</span><span class="sxs-lookup"><span data-stu-id="7c27b-397">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="7c27b-398">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="7c27b-398">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="7c27b-399">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="7c27b-399">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="7c27b-400">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="7c27b-400">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="7c27b-401">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="7c27b-401">Job type</span></span>   | <span data-ttu-id="7c27b-402">descrizione</span><span class="sxs-lookup"><span data-stu-id="7c27b-402">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="7c27b-403">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="7c27b-403">Hourly</span></span>     | <span data-ttu-id="7c27b-404">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="7c27b-404">Hourly</span></span>      |
| <span data-ttu-id="7c27b-405">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="7c27b-405">Salaried</span></span>   | <span data-ttu-id="7c27b-406">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="7c27b-406">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="7c27b-407">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="7c27b-407">Position types</span></span> 

<span data-ttu-id="7c27b-408">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="7c27b-408">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="7c27b-409">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="7c27b-409">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="7c27b-410">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="7c27b-410">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="7c27b-411">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="7c27b-411">Position type</span></span>   | <span data-ttu-id="7c27b-412">descrizione</span><span class="sxs-lookup"><span data-stu-id="7c27b-412">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="7c27b-413">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="7c27b-413">Full-time</span></span>       | <span data-ttu-id="7c27b-414">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="7c27b-414">Full time employee</span></span> |
| <span data-ttu-id="7c27b-415">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="7c27b-415">Part-time</span></span>       | <span data-ttu-id="7c27b-416">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="7c27b-416">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="7c27b-417">Codici causale</span><span class="sxs-lookup"><span data-stu-id="7c27b-417">Reason codes</span></span>

<span data-ttu-id="7c27b-418">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="7c27b-418">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="7c27b-419">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="7c27b-419">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="7c27b-420">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="7c27b-420">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="7c27b-421">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="7c27b-421">Reason code</span></span>    | <span data-ttu-id="7c27b-422">descrizione</span><span class="sxs-lookup"><span data-stu-id="7c27b-422">Description</span></span>      | <span data-ttu-id="7c27b-423">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="7c27b-423">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="7c27b-424">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="7c27b-424">RESIGNATION</span></span>    | <span data-ttu-id="7c27b-425">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="7c27b-425">Resignation</span></span>      | <span data-ttu-id="7c27b-426">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-426">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-427">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="7c27b-427">TERMINATION</span></span>    | <span data-ttu-id="7c27b-428">Fine</span><span class="sxs-lookup"><span data-stu-id="7c27b-428">Termination</span></span>      | <span data-ttu-id="7c27b-429">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-429">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-430">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="7c27b-430">RETIREMENT</span></span>     | <span data-ttu-id="7c27b-431">Pensione</span><span class="sxs-lookup"><span data-stu-id="7c27b-431">Retirement</span></span>       | <span data-ttu-id="7c27b-432">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-432">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-433">OTHER</span><span class="sxs-lookup"><span data-stu-id="7c27b-433">OTHER</span></span>          | <span data-ttu-id="7c27b-434">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="7c27b-434">Other Reasons</span></span>    | <span data-ttu-id="7c27b-435">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-435">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-436">DEATH</span><span class="sxs-lookup"><span data-stu-id="7c27b-436">DEATH</span></span>          | <span data-ttu-id="7c27b-437">Decesso</span><span class="sxs-lookup"><span data-stu-id="7c27b-437">Death</span></span>            | <span data-ttu-id="7c27b-438">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-438">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-439">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="7c27b-439">LEAVEOFABSENCE</span></span> | <span data-ttu-id="7c27b-440">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="7c27b-440">Leave of Absence</span></span> | <span data-ttu-id="7c27b-441">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-441">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-442">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="7c27b-442">CONTRACTEND</span></span>    | <span data-ttu-id="7c27b-443">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="7c27b-443">End of Contract</span></span>  | <span data-ttu-id="7c27b-444">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-444">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-445">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="7c27b-445">SALARYCHANGE</span></span>   | <span data-ttu-id="7c27b-446">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="7c27b-446">Change of Salary</span></span> | <span data-ttu-id="7c27b-447">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="7c27b-447">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="7c27b-448">Stato civile</span><span class="sxs-lookup"><span data-stu-id="7c27b-448">Marital status</span></span>

<span data-ttu-id="7c27b-449">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-449">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="7c27b-450">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="7c27b-450">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="7c27b-451">Talent</span><span class="sxs-lookup"><span data-stu-id="7c27b-451">Talent</span></span>                 | <span data-ttu-id="7c27b-452">Dayforce</span><span class="sxs-lookup"><span data-stu-id="7c27b-452">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="7c27b-453">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="7c27b-453">Married</span></span>                | <span data-ttu-id="7c27b-454">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="7c27b-454">Married</span></span>              |
| <span data-ttu-id="7c27b-455">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="7c27b-455">Single</span></span>                 | <span data-ttu-id="7c27b-456">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="7c27b-456">Single</span></span>               |
| <span data-ttu-id="7c27b-457">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="7c27b-457">Widowed</span></span>                | <span data-ttu-id="7c27b-458">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="7c27b-458">Widowed</span></span>              |
| <span data-ttu-id="7c27b-459">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="7c27b-459">Divorced</span></span>               | <span data-ttu-id="7c27b-460">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="7c27b-460">Divorced</span></span>             |
| <span data-ttu-id="7c27b-461">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="7c27b-461">Registered Partnership</span></span> | <span data-ttu-id="7c27b-462">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="7c27b-462">Domestic Partnership</span></span> |
| <span data-ttu-id="7c27b-463">Nessuna</span><span class="sxs-lookup"><span data-stu-id="7c27b-463">None</span></span>                   | <span data-ttu-id="7c27b-464">Nessuna</span><span class="sxs-lookup"><span data-stu-id="7c27b-464">None</span></span>                 |
| <span data-ttu-id="7c27b-465">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="7c27b-465">Cohabiting</span></span>             | <span data-ttu-id="7c27b-466">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="7c27b-466">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="7c27b-467">Genere</span><span class="sxs-lookup"><span data-stu-id="7c27b-467">Gender</span></span>

<span data-ttu-id="7c27b-468">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-468">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="7c27b-469">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="7c27b-469">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="7c27b-470">Talent</span><span class="sxs-lookup"><span data-stu-id="7c27b-470">Talent</span></span>       | <span data-ttu-id="7c27b-471">Dayforce</span><span class="sxs-lookup"><span data-stu-id="7c27b-471">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="7c27b-472">Maschio</span><span class="sxs-lookup"><span data-stu-id="7c27b-472">Male</span></span>         | <span data-ttu-id="7c27b-473">Maschio</span><span class="sxs-lookup"><span data-stu-id="7c27b-473">Male</span></span>            |
| <span data-ttu-id="7c27b-474">Femmina</span><span class="sxs-lookup"><span data-stu-id="7c27b-474">Female</span></span>       | <span data-ttu-id="7c27b-475">Femmina</span><span class="sxs-lookup"><span data-stu-id="7c27b-475">Female</span></span>          |
| <span data-ttu-id="7c27b-476">Non specifico</span><span class="sxs-lookup"><span data-stu-id="7c27b-476">Non-specific</span></span> | <span data-ttu-id="7c27b-477">*Non supportato*</span><span class="sxs-lookup"><span data-stu-id="7c27b-477">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="7c27b-478">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="7c27b-478">Earning codes</span></span>

<span data-ttu-id="7c27b-479">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="7c27b-479">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="7c27b-480">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="7c27b-480">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="7c27b-481">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="7c27b-481">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="7c27b-482">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="7c27b-482">Supported frequencies</span></span>

- <span data-ttu-id="7c27b-483">Tutti</span><span class="sxs-lookup"><span data-stu-id="7c27b-483">All</span></span>
- <span data-ttu-id="7c27b-484">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="7c27b-484">EVERYPAY</span></span>
- <span data-ttu-id="7c27b-485">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="7c27b-485">EACHPAYPERIOD</span></span>
- <span data-ttu-id="7c27b-486">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="7c27b-486">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="7c27b-487">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="7c27b-487">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="7c27b-488">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-488">1OFMTH</span></span>
- <span data-ttu-id="7c27b-489">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-489">LASTOFMTH</span></span>
- <span data-ttu-id="7c27b-490">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-490">2OFMTH</span></span>
- <span data-ttu-id="7c27b-491">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-491">3OFMTH</span></span>
- <span data-ttu-id="7c27b-492">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-492">4OFMTH</span></span>
- <span data-ttu-id="7c27b-493">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-493">5OFMTH</span></span>
- <span data-ttu-id="7c27b-494">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-494">1N2OFMTH</span></span>
- <span data-ttu-id="7c27b-495">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-495">3N4OFMTH</span></span>
- <span data-ttu-id="7c27b-496">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-496">1N3OFMTH</span></span>
- <span data-ttu-id="7c27b-497">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-497">1N4OFMTH</span></span>
- <span data-ttu-id="7c27b-498">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-498">2N3OFMTH</span></span>
- <span data-ttu-id="7c27b-499">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-499">2N4OFMTH</span></span>
- <span data-ttu-id="7c27b-500">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-500">1N2N3OFMTH</span></span>
- <span data-ttu-id="7c27b-501">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-501">1N2N4OFMTH</span></span>
- <span data-ttu-id="7c27b-502">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-502">1N3N4OFMTH</span></span>
- <span data-ttu-id="7c27b-503">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-503">2N3N4OFMTH</span></span>
- <span data-ttu-id="7c27b-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="7c27b-505">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="7c27b-505">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="7c27b-506">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="7c27b-506">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="7c27b-507">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="7c27b-507">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="7c27b-508">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="7c27b-508">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="7c27b-509">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="7c27b-509">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="7c27b-510">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="7c27b-510">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="7c27b-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="7c27b-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="7c27b-512">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="7c27b-512">Addresses</span></span>

<span data-ttu-id="7c27b-513">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="7c27b-513">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="7c27b-514">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="7c27b-514">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="7c27b-515">Talent</span><span class="sxs-lookup"><span data-stu-id="7c27b-515">Talent</span></span>          | <span data-ttu-id="7c27b-516">Dayforce</span><span class="sxs-lookup"><span data-stu-id="7c27b-516">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="7c27b-517">Paese</span><span class="sxs-lookup"><span data-stu-id="7c27b-517">Country/Region</span></span>  | <span data-ttu-id="7c27b-518">Codice paese</span><span class="sxs-lookup"><span data-stu-id="7c27b-518">Country Code</span></span>          |
| <span data-ttu-id="7c27b-519">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="7c27b-519">Zip/Postal Code</span></span> | <span data-ttu-id="7c27b-520">CAP</span><span class="sxs-lookup"><span data-stu-id="7c27b-520">Postal Code</span></span>           |
| <span data-ttu-id="7c27b-521">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="7c27b-521">State</span></span>           | <span data-ttu-id="7c27b-522">Codice stato</span><span class="sxs-lookup"><span data-stu-id="7c27b-522">State Code</span></span>            |
| <span data-ttu-id="7c27b-523">Città</span><span class="sxs-lookup"><span data-stu-id="7c27b-523">City</span></span>            | <span data-ttu-id="7c27b-524">Città</span><span class="sxs-lookup"><span data-stu-id="7c27b-524">City</span></span>                  |
| <span data-ttu-id="7c27b-525">Regione</span><span class="sxs-lookup"><span data-stu-id="7c27b-525">County</span></span>          | <span data-ttu-id="7c27b-526">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="7c27b-526">County (Municipality)</span></span> |
| <span data-ttu-id="7c27b-527">Via</span><span class="sxs-lookup"><span data-stu-id="7c27b-527">Street</span></span>          | <span data-ttu-id="7c27b-528">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="7c27b-528">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="7c27b-529">Regioni fiscali</span><span class="sxs-lookup"><span data-stu-id="7c27b-529">Tax regions</span></span>

<span data-ttu-id="7c27b-530">Le regioni fiscali vengono utilizzate per determinare l'imposta appropriata che deve essere applicata durante la generazione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="7c27b-530">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="7c27b-531">Le regioni fiscali vengono mappate in Dayforce come indirizzi di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-531">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="7c27b-532">La regione fiscale predefinita deve essere associata alla posizione attiva del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="7c27b-532">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="7c27b-533">Regione fiscale (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-533">Tax region (required)</span></span>
- <span data-ttu-id="7c27b-534">Paese/regione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-534">Country/Region (required)</span></span>
- <span data-ttu-id="7c27b-535">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="7c27b-535">State (required)</span></span>
- <span data-ttu-id="7c27b-536">Regione</span><span class="sxs-lookup"><span data-stu-id="7c27b-536">County</span></span> 
- <span data-ttu-id="7c27b-537">Città (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="7c27b-537">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="7c27b-538">Configurare i dati per generare le retribuzioni in Messico</span><span class="sxs-lookup"><span data-stu-id="7c27b-538">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="7c27b-539">Se si desidera generare la retribuzione per i dipendenti in Messico, i seguenti elementi devono essere configurati:</span><span class="sxs-lookup"><span data-stu-id="7c27b-539">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="7c27b-540">I reparti sono necessari nelle posizioni.</span><span class="sxs-lookup"><span data-stu-id="7c27b-540">Departments are required on positions.</span></span>
- <span data-ttu-id="7c27b-541">I centri di costo devono essere impostati come dimensioni finanziarie ed essere il primo elemento nella stringa della dimensione finanziaria predefinita.</span><span class="sxs-lookup"><span data-stu-id="7c27b-541">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="7c27b-542">Tipi di posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="7c27b-542">Job types</span></span>

<span data-ttu-id="7c27b-543">I tipi di mansione vengono utilizzati per raggruppare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="7c27b-543">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="7c27b-544">Tipi di mansione necessari per elaborare le retribuzioni in Messico.</span><span class="sxs-lookup"><span data-stu-id="7c27b-544">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="7c27b-545">Alcuni esempi di tipi di mansione includono il tempo pieno e il part-time o stipendio e retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="7c27b-545">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="7c27b-546">I tipi di mansioni vengono mappati in Dayforce come tipi di retribuzione che indicano se un dipendente viene pagato a ore o è stipendiato.</span><span class="sxs-lookup"><span data-stu-id="7c27b-546">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="7c27b-547">I seguenti tipi di mansione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="7c27b-547">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="7c27b-548">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="7c27b-548">Job type</span></span>   | <span data-ttu-id="7c27b-549">descrizione</span><span class="sxs-lookup"><span data-stu-id="7c27b-549">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="7c27b-550">Su base oraria</span><span class="sxs-lookup"><span data-stu-id="7c27b-550">Hourly</span></span>     | <span data-ttu-id="7c27b-551">Su base oraria MX</span><span class="sxs-lookup"><span data-stu-id="7c27b-551">MX Hourly</span></span>   |
| <span data-ttu-id="7c27b-552">Stipendiato</span><span class="sxs-lookup"><span data-stu-id="7c27b-552">Salaried</span></span>   | <span data-ttu-id="7c27b-553">Stipendiato MX</span><span class="sxs-lookup"><span data-stu-id="7c27b-553">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="7c27b-554">Tipi di posizione</span><span class="sxs-lookup"><span data-stu-id="7c27b-554">Position types</span></span> 

<span data-ttu-id="7c27b-555">Si utilizzano i tipi di posizione per descrivere se è la posizione è a tempo pieno, part-time o altro.</span><span class="sxs-lookup"><span data-stu-id="7c27b-555">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="7c27b-556">I tipi di posizione vengono mappati in Dayforce come classi di retribuzione che indicano se un dipendente viene pagato a tempo pieno o part-time.</span><span class="sxs-lookup"><span data-stu-id="7c27b-556">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="7c27b-557">I seguenti tipi di posizione e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="7c27b-557">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="7c27b-558">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="7c27b-558">Position type</span></span>   | <span data-ttu-id="7c27b-559">descrizione</span><span class="sxs-lookup"><span data-stu-id="7c27b-559">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="7c27b-560">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="7c27b-560">Full-time</span></span>       | <span data-ttu-id="7c27b-561">Dipendente a tempo pieno</span><span class="sxs-lookup"><span data-stu-id="7c27b-561">Full time employee</span></span> |
| <span data-ttu-id="7c27b-562">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="7c27b-562">Part-time</span></span>       | <span data-ttu-id="7c27b-563">Dipendente a tempo parziale</span><span class="sxs-lookup"><span data-stu-id="7c27b-563">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="7c27b-564">Codici causale</span><span class="sxs-lookup"><span data-stu-id="7c27b-564">Reason codes</span></span>

<span data-ttu-id="7c27b-565">I codici motivo forniscono informazioni sullo stato di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="7c27b-565">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="7c27b-566">I codici motivo vengono mappati in Dayforce come motivi di stato che indicano il motivo dei cambiamenti nella posizione del dipendente o nello stato di impiego.</span><span class="sxs-lookup"><span data-stu-id="7c27b-566">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="7c27b-567">I seguenti codici motivo e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="7c27b-567">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="7c27b-568">Codice motivo</span><span class="sxs-lookup"><span data-stu-id="7c27b-568">Reason code</span></span>            | <span data-ttu-id="7c27b-569">descrizione</span><span class="sxs-lookup"><span data-stu-id="7c27b-569">Description</span></span>                    | <span data-ttu-id="7c27b-570">Scenari applicabili</span><span class="sxs-lookup"><span data-stu-id="7c27b-570">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="7c27b-571">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="7c27b-571">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="7c27b-572">Partenza prima della prima retribuzione</span><span class="sxs-lookup"><span data-stu-id="7c27b-572">Departure before first payroll</span></span> | <span data-ttu-id="7c27b-573">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-573">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-574">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="7c27b-574">RESIGNATION</span></span>            | <span data-ttu-id="7c27b-575">Dimissioni</span><span class="sxs-lookup"><span data-stu-id="7c27b-575">Resignation</span></span>                    | <span data-ttu-id="7c27b-576">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-576">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-577">PENSION</span><span class="sxs-lookup"><span data-stu-id="7c27b-577">PENSION</span></span>                | <span data-ttu-id="7c27b-578">Pensionamento</span><span class="sxs-lookup"><span data-stu-id="7c27b-578">Pension</span></span>                        | <span data-ttu-id="7c27b-579">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-579">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-580">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="7c27b-580">TERMINATION</span></span>            | <span data-ttu-id="7c27b-581">Fine</span><span class="sxs-lookup"><span data-stu-id="7c27b-581">Termination</span></span>                    | <span data-ttu-id="7c27b-582">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-582">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-583">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="7c27b-583">RETIREMENT</span></span>             | <span data-ttu-id="7c27b-584">Pensione</span><span class="sxs-lookup"><span data-stu-id="7c27b-584">Retirement</span></span>                     | <span data-ttu-id="7c27b-585">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-585">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-586">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="7c27b-586">ABSENTEE</span></span>               | <span data-ttu-id="7c27b-587">Assente</span><span class="sxs-lookup"><span data-stu-id="7c27b-587">Absentee</span></span>                       | <span data-ttu-id="7c27b-588">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-588">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-589">OTHER</span><span class="sxs-lookup"><span data-stu-id="7c27b-589">OTHER</span></span>                  | <span data-ttu-id="7c27b-590">Altri motivi</span><span class="sxs-lookup"><span data-stu-id="7c27b-590">Other Reasons</span></span>                  | <span data-ttu-id="7c27b-591">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-591">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-592">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="7c27b-592">CLOSURE</span></span>                | <span data-ttu-id="7c27b-593">Chiusura attività</span><span class="sxs-lookup"><span data-stu-id="7c27b-593">Business Closure</span></span>               | <span data-ttu-id="7c27b-594">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-594">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-595">DEATH</span><span class="sxs-lookup"><span data-stu-id="7c27b-595">DEATH</span></span>                  | <span data-ttu-id="7c27b-596">Decesso</span><span class="sxs-lookup"><span data-stu-id="7c27b-596">Death</span></span>                          | <span data-ttu-id="7c27b-597">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-597">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-598">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="7c27b-598">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="7c27b-599">Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="7c27b-599">Leave of Absence</span></span>               | <span data-ttu-id="7c27b-600">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-600">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-601">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="7c27b-601">CONTRACTEND</span></span>            | <span data-ttu-id="7c27b-602">Fine di contratto</span><span class="sxs-lookup"><span data-stu-id="7c27b-602">End of Contract</span></span>                | <span data-ttu-id="7c27b-603">Termina rapporto con lavoratore</span><span class="sxs-lookup"><span data-stu-id="7c27b-603">Terminate worker</span></span>     |
| <span data-ttu-id="7c27b-604">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="7c27b-604">SALARYCHANGE</span></span>           | <span data-ttu-id="7c27b-605">Modifica dello stipendio</span><span class="sxs-lookup"><span data-stu-id="7c27b-605">Change of Salary</span></span>               | <span data-ttu-id="7c27b-606">Retribuzione</span><span class="sxs-lookup"><span data-stu-id="7c27b-606">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="7c27b-607">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="7c27b-607">Terms of employment</span></span>

<span data-ttu-id="7c27b-608">Le condizioni di impiego vengono utilizzate per creare categorie di termini di impiego.</span><span class="sxs-lookup"><span data-stu-id="7c27b-608">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="7c27b-609">I termini vengono mappati in Dayforce come valori degli indicatori di impiego.</span><span class="sxs-lookup"><span data-stu-id="7c27b-609">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="7c27b-610">I seguenti termini di impiego e le descrizioni sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="7c27b-610">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="7c27b-611">Condizioni di impiego</span><span class="sxs-lookup"><span data-stu-id="7c27b-611">Terms of employment</span></span>   | <span data-ttu-id="7c27b-612">descrizione</span><span class="sxs-lookup"><span data-stu-id="7c27b-612">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="7c27b-613">Regolare</span><span class="sxs-lookup"><span data-stu-id="7c27b-613">Regular</span></span>               | <span data-ttu-id="7c27b-614">Regolare</span><span class="sxs-lookup"><span data-stu-id="7c27b-614">Regular</span></span>     |
| <span data-ttu-id="7c27b-615">Diretto</span><span class="sxs-lookup"><span data-stu-id="7c27b-615">Direct</span></span>                | <span data-ttu-id="7c27b-616">Diretto</span><span class="sxs-lookup"><span data-stu-id="7c27b-616">Direct</span></span>      |
| <span data-ttu-id="7c27b-617">Internato</span><span class="sxs-lookup"><span data-stu-id="7c27b-617">Internship</span></span>            | <span data-ttu-id="7c27b-618">Internato</span><span class="sxs-lookup"><span data-stu-id="7c27b-618">Internship</span></span>  |
| <span data-ttu-id="7c27b-619">Permanente</span><span class="sxs-lookup"><span data-stu-id="7c27b-619">Permanent</span></span>             | <span data-ttu-id="7c27b-620">Permanente</span><span class="sxs-lookup"><span data-stu-id="7c27b-620">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="7c27b-621">Stato civile</span><span class="sxs-lookup"><span data-stu-id="7c27b-621">Marital status</span></span>

<span data-ttu-id="7c27b-622">I valori dello stato civile vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-622">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="7c27b-623">Nella tabella seguente vengono illustrati in che modo i valori dello stato civile vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="7c27b-623">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="7c27b-624">Talent</span><span class="sxs-lookup"><span data-stu-id="7c27b-624">Talent</span></span>                 | <span data-ttu-id="7c27b-625">Dayforce</span><span class="sxs-lookup"><span data-stu-id="7c27b-625">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="7c27b-626">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="7c27b-626">Married</span></span>                | <span data-ttu-id="7c27b-627">Sposato/a</span><span class="sxs-lookup"><span data-stu-id="7c27b-627">Married</span></span>                   |
| <span data-ttu-id="7c27b-628">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="7c27b-628">Single</span></span>                 | <span data-ttu-id="7c27b-629">Celibe/nubile</span><span class="sxs-lookup"><span data-stu-id="7c27b-629">Single</span></span>                    |
| <span data-ttu-id="7c27b-630">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="7c27b-630">Widowed</span></span>                | <span data-ttu-id="7c27b-631">Vedovo/a</span><span class="sxs-lookup"><span data-stu-id="7c27b-631">Widowed</span></span>                   |
| <span data-ttu-id="7c27b-632">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="7c27b-632">Divorced</span></span>               | <span data-ttu-id="7c27b-633">Divorziato/a</span><span class="sxs-lookup"><span data-stu-id="7c27b-633">Divorced</span></span>                  |
| <span data-ttu-id="7c27b-634">Relazione registrata</span><span class="sxs-lookup"><span data-stu-id="7c27b-634">Registered Partnership</span></span> | <span data-ttu-id="7c27b-635">Relazione nazionale</span><span class="sxs-lookup"><span data-stu-id="7c27b-635">Domestic Partnership</span></span>      |
| <span data-ttu-id="7c27b-636">Nessuna</span><span class="sxs-lookup"><span data-stu-id="7c27b-636">None</span></span>                   | <span data-ttu-id="7c27b-637">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="7c27b-637">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="7c27b-638">Coabitazione</span><span class="sxs-lookup"><span data-stu-id="7c27b-638">Cohabiting</span></span>             | <span data-ttu-id="7c27b-639">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="7c27b-639">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="7c27b-640">Genere</span><span class="sxs-lookup"><span data-stu-id="7c27b-640">Gender</span></span>

<span data-ttu-id="7c27b-641">Le designazioni di sesso vengono mappate in Dayforce e tradotte, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-641">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="7c27b-642">Nella tabella seguente vengono illustrati in che modo le designazioni di sesso vengono mappate in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="7c27b-642">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="7c27b-643">Talent</span><span class="sxs-lookup"><span data-stu-id="7c27b-643">Talent</span></span>       | <span data-ttu-id="7c27b-644">Dayforce</span><span class="sxs-lookup"><span data-stu-id="7c27b-644">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="7c27b-645">Maschio</span><span class="sxs-lookup"><span data-stu-id="7c27b-645">Male</span></span>         | <span data-ttu-id="7c27b-646">Maschio</span><span class="sxs-lookup"><span data-stu-id="7c27b-646">Male</span></span>                      |
| <span data-ttu-id="7c27b-647">Femmina</span><span class="sxs-lookup"><span data-stu-id="7c27b-647">Female</span></span>       | <span data-ttu-id="7c27b-648">Femmina</span><span class="sxs-lookup"><span data-stu-id="7c27b-648">Female</span></span>                    |
| <span data-ttu-id="7c27b-649">Non specifico</span><span class="sxs-lookup"><span data-stu-id="7c27b-649">Non-specific</span></span> | <span data-ttu-id="7c27b-650">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="7c27b-650">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="7c27b-651">Metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="7c27b-651">Payment method</span></span>

<span data-ttu-id="7c27b-652">I metodi di pagamento offrono al dipendente e all'azienda un modo per descrivere la modalità di pagamento dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="7c27b-652">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="7c27b-653">I metodi di pagamento vengono mappati in Dayforce e tradotti, come appropriato, nei valori accettati con l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-653">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="7c27b-654">Nella tabella seguente vengono illustrati in che modo i metodi di pagamento vengono mappati in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="7c27b-654">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="7c27b-655">Talent</span><span class="sxs-lookup"><span data-stu-id="7c27b-655">Talent</span></span>             | <span data-ttu-id="7c27b-656">Dayforce</span><span class="sxs-lookup"><span data-stu-id="7c27b-656">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="7c27b-657">In contanti</span><span class="sxs-lookup"><span data-stu-id="7c27b-657">Cash</span></span>               | <span data-ttu-id="7c27b-658">In contanti</span><span class="sxs-lookup"><span data-stu-id="7c27b-658">Cash</span></span>                      |
| <span data-ttu-id="7c27b-659">Pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="7c27b-659">Electronic Payment</span></span> | <span data-ttu-id="7c27b-660">Trasferimenti</span><span class="sxs-lookup"><span data-stu-id="7c27b-660">Transfer</span></span>                  |
| <span data-ttu-id="7c27b-661">Verifica</span><span class="sxs-lookup"><span data-stu-id="7c27b-661">Check</span></span>              | <span data-ttu-id="7c27b-662">Assegno</span><span class="sxs-lookup"><span data-stu-id="7c27b-662">Cheque</span></span>                    |
| <span data-ttu-id="7c27b-663">Assegno circolare</span><span class="sxs-lookup"><span data-stu-id="7c27b-663">Bank Draft</span></span>         | <span data-ttu-id="7c27b-664">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="7c27b-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="7c27b-665">Altro</span><span class="sxs-lookup"><span data-stu-id="7c27b-665">Other</span></span>              | <span data-ttu-id="7c27b-666">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="7c27b-666">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="7c27b-667">Tipo di conto bancario</span><span class="sxs-lookup"><span data-stu-id="7c27b-667">Bank account type</span></span>

<span data-ttu-id="7c27b-668">I tipi di conto bancario vengono utilizzati per i pagamenti elettronici ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="7c27b-668">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="7c27b-669">I tipi di conto bancario vengono mappati in Dayforce come informazioni sul conto di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="7c27b-669">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="7c27b-670">I tipi di conto bancario vengono convertiti, come appropriato, nei valori accettati per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="7c27b-670">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="7c27b-671">Talent</span><span class="sxs-lookup"><span data-stu-id="7c27b-671">Talent</span></span>            | <span data-ttu-id="7c27b-672">Dayforce</span><span class="sxs-lookup"><span data-stu-id="7c27b-672">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="7c27b-673">Conto corrente</span><span class="sxs-lookup"><span data-stu-id="7c27b-673">Checking Account</span></span>  | <span data-ttu-id="7c27b-674">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="7c27b-674">CheckingAccount</span></span>           |
| <span data-ttu-id="7c27b-675">Conto retribuzioni</span><span class="sxs-lookup"><span data-stu-id="7c27b-675">Payroll Account</span></span>   | <span data-ttu-id="7c27b-676">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="7c27b-676">PayrollAccount</span></span>            |
| <span data-ttu-id="7c27b-677">Conto di risparmio</span><span class="sxs-lookup"><span data-stu-id="7c27b-677">Savings Account</span></span>   | <span data-ttu-id="7c27b-678">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="7c27b-678">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="7c27b-679">Conto Bankgirot</span><span class="sxs-lookup"><span data-stu-id="7c27b-679">BankGirot account</span></span> | <span data-ttu-id="7c27b-680">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="7c27b-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="7c27b-681">Conto PlusGirot</span><span class="sxs-lookup"><span data-stu-id="7c27b-681">PlusGirot account</span></span> | <span data-ttu-id="7c27b-682">*Non supportato in Messico*</span><span class="sxs-lookup"><span data-stu-id="7c27b-682">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="7c27b-683">Codici di reddito</span><span class="sxs-lookup"><span data-stu-id="7c27b-683">Earning codes</span></span>

<span data-ttu-id="7c27b-684">I codici di reddito identificano in modo univoco ogni tipo di reddito che i lavoratori ricevono.</span><span class="sxs-lookup"><span data-stu-id="7c27b-684">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="7c27b-685">I codici contengono vari parametri correlati ai ricavi, ad esempio regole contabili, leggi fiscali, requisiti di reporting e capacità di calcolo lordo.</span><span class="sxs-lookup"><span data-stu-id="7c27b-685">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="7c27b-686">Se una frequenza non supportata viene utilizzata, la frequenza **Ogni retribuzione** viene utilizzata per impostazione predefinita per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="7c27b-686">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="7c27b-687">Frequenze supportate</span><span class="sxs-lookup"><span data-stu-id="7c27b-687">Supported frequencies</span></span>

- <span data-ttu-id="7c27b-688">Tutti</span><span class="sxs-lookup"><span data-stu-id="7c27b-688">All</span></span>
- <span data-ttu-id="7c27b-689">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="7c27b-689">EVERYPAY</span></span>
- <span data-ttu-id="7c27b-690">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="7c27b-690">EACHPAYPERIOD</span></span>
- <span data-ttu-id="7c27b-691">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="7c27b-691">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="7c27b-692">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="7c27b-692">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="7c27b-693">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-693">1OFMTH</span></span>
- <span data-ttu-id="7c27b-694">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-694">LASTOFMTH</span></span>
- <span data-ttu-id="7c27b-695">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-695">2OFMTH</span></span>
- <span data-ttu-id="7c27b-696">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-696">3OFMTH</span></span>
- <span data-ttu-id="7c27b-697">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-697">4OFMTH</span></span>
- <span data-ttu-id="7c27b-698">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-698">5OFMTH</span></span>
- <span data-ttu-id="7c27b-699">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-699">1N2OFMTH</span></span>
- <span data-ttu-id="7c27b-700">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-700">3N4OFMTH</span></span>
- <span data-ttu-id="7c27b-701">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-701">1N3OFMTH</span></span>
- <span data-ttu-id="7c27b-702">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-702">1N4OFMTH</span></span>
- <span data-ttu-id="7c27b-703">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-703">2N3OFMTH</span></span>
- <span data-ttu-id="7c27b-704">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-704">2N4OFMTH</span></span>
- <span data-ttu-id="7c27b-705">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-705">1N2N3OFMTH</span></span>
- <span data-ttu-id="7c27b-706">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-706">1N2N4OFMTH</span></span>
- <span data-ttu-id="7c27b-707">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-707">1N3N4OFMTH</span></span>
- <span data-ttu-id="7c27b-708">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-708">2N3N4OFMTH</span></span>
- <span data-ttu-id="7c27b-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="7c27b-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="7c27b-710">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="7c27b-710">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="7c27b-711">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="7c27b-711">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="7c27b-712">LASTOFQTR - LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="7c27b-712">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="7c27b-713">LASTMTHOFQTR - LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="7c27b-713">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="7c27b-714">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="7c27b-714">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="7c27b-715">LASTOFYEAR - LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="7c27b-715">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="7c27b-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="7c27b-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="7c27b-717">Indirizzi</span><span class="sxs-lookup"><span data-stu-id="7c27b-717">Addresses</span></span>

<span data-ttu-id="7c27b-718">L'identificazione del paese specifico o dei codici di paese, stato e provincia (municipalità) richiede formati specifici che i fornitori di Dayforce e nazionali/regionali possono riconoscere.</span><span class="sxs-lookup"><span data-stu-id="7c27b-718">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="7c27b-719">Sebbene il formato per le città sia flessibile, ogni città deve essere associata a uno stato.</span><span class="sxs-lookup"><span data-stu-id="7c27b-719">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="7c27b-720">Talent</span><span class="sxs-lookup"><span data-stu-id="7c27b-720">Talent</span></span>              | <span data-ttu-id="7c27b-721">Dayforce</span><span class="sxs-lookup"><span data-stu-id="7c27b-721">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="7c27b-722">Paese</span><span class="sxs-lookup"><span data-stu-id="7c27b-722">Country/Region</span></span>      | <span data-ttu-id="7c27b-723">Codice paese</span><span class="sxs-lookup"><span data-stu-id="7c27b-723">Country Code</span></span>          |
| <span data-ttu-id="7c27b-724">CAP/Codice postale</span><span class="sxs-lookup"><span data-stu-id="7c27b-724">Zip/Postal Code</span></span>     | <span data-ttu-id="7c27b-725">CAP</span><span class="sxs-lookup"><span data-stu-id="7c27b-725">Postal Code</span></span>           |
| <span data-ttu-id="7c27b-726">Stato/regione</span><span class="sxs-lookup"><span data-stu-id="7c27b-726">State</span></span>               | <span data-ttu-id="7c27b-727">Codice stato</span><span class="sxs-lookup"><span data-stu-id="7c27b-727">State Code</span></span>            |
| <span data-ttu-id="7c27b-728">Città</span><span class="sxs-lookup"><span data-stu-id="7c27b-728">City</span></span>                | <span data-ttu-id="7c27b-729">Città</span><span class="sxs-lookup"><span data-stu-id="7c27b-729">City</span></span>                  |
| <span data-ttu-id="7c27b-730">Regione</span><span class="sxs-lookup"><span data-stu-id="7c27b-730">County</span></span>              | <span data-ttu-id="7c27b-731">Provincia (municipalità)</span><span class="sxs-lookup"><span data-stu-id="7c27b-731">County (Municipality)</span></span> |
| <span data-ttu-id="7c27b-732">Via</span><span class="sxs-lookup"><span data-stu-id="7c27b-732">Street</span></span>              | <span data-ttu-id="7c27b-733">Riga indirizzo 1</span><span class="sxs-lookup"><span data-stu-id="7c27b-733">Address Line 1</span></span>        |
| <span data-ttu-id="7c27b-734">Numero civico</span><span class="sxs-lookup"><span data-stu-id="7c27b-734">Street Number</span></span>       | <span data-ttu-id="7c27b-735">Riga indirizzo 2</span><span class="sxs-lookup"><span data-stu-id="7c27b-735">Address Line 2</span></span>        |
| <span data-ttu-id="7c27b-736">Informazioni aggiuntive sull'indirizzo</span><span class="sxs-lookup"><span data-stu-id="7c27b-736">Building Complement</span></span> | <span data-ttu-id="7c27b-737">Riga indirizzo 5</span><span class="sxs-lookup"><span data-stu-id="7c27b-737">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="7c27b-738">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="7c27b-738">Passport number</span></span>

<span data-ttu-id="7c27b-739">I dipendenti possono indicare le informazioni sul passaporto.</span><span class="sxs-lookup"><span data-stu-id="7c27b-739">Employees can declare passport information.</span></span> <span data-ttu-id="7c27b-740">Queste informazioni sono del tipo di identificazione **Passaporto** e vengono integrate in Dayforce come parte delle informazioni di un dipendente specifiche per il Messico.</span><span class="sxs-lookup"><span data-stu-id="7c27b-740">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="7c27b-741">Tipo di identificazione = "Passaporto"</span><span class="sxs-lookup"><span data-stu-id="7c27b-741">Identification Type = "Passport"</span></span>
- <span data-ttu-id="7c27b-742">Data di emissione</span><span class="sxs-lookup"><span data-stu-id="7c27b-742">Issued Date</span></span>
- <span data-ttu-id="7c27b-743">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="7c27b-743">Expiration Date</span></span>

<span data-ttu-id="7c27b-744">I dipendenti possono dichiarare più numeri di identificazione più del tipo di identificazione **Passaporto**.</span><span class="sxs-lookup"><span data-stu-id="7c27b-744">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="7c27b-745">Tuttavia, solo l'immissione del passaporto attivo corrente viene integrata in Dayforce.</span><span class="sxs-lookup"><span data-stu-id="7c27b-745">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="7c27b-746">Se tutte le immissioni di passaporto sono scadute, in Dayforce viene integrato il passaporto di emissione più recente.</span><span class="sxs-lookup"><span data-stu-id="7c27b-746">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
