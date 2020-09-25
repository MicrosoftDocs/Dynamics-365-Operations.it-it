---
title: Tipo di destinazione posta elettronica ER
description: In questo argomento vengono fornite informazioni su come configurare una destinazione posta elettronica per ogni componente CARTELLA o FILE di un formato ER configurato per generare documenti in uscita.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 72f67ad915ba2acc90ecb52bdb97e42504450a03
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745563"
---
# <a name="email-destination"></a><span data-ttu-id="39ab4-103">Destinazione posta elettronica</span><span class="sxs-lookup"><span data-stu-id="39ab4-103">Email destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39ab4-104">È possibile configurare una destinazione posta elettronica per ogni componente CARTELLA o FILE di un formato ER configurato per generare documenti in uscita.</span><span class="sxs-lookup"><span data-stu-id="39ab4-104">You can configure an email destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="39ab4-105">In base all'impostazione di destinazione, un documento generato viene fornito come allegato di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="39ab4-105">Based on the destination setting, a generated document is delivered as an attachment of an electronic mail.</span></span>

<span data-ttu-id="39ab4-106">Impostare **Abilitato** su **Sì** per inviare un file di output tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="39ab4-106">Set **Enabled** to **Yes** to send an output file by email.</span></span> <span data-ttu-id="39ab4-107">Dopo aver abilitato questa opzione, è possibile specificare i destinatari del messaggio di posta elettronica e modificare l'oggetto e il corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="39ab4-107">After this option is enabled, you can specify the email recipients and edit the subject and body of the email message.</span></span> <span data-ttu-id="39ab4-108">È possibile impostare testi costanti per l'oggetto e il corpo del messaggio di posta elettronica oppure utilizzare le [formule](er-formula-language.md) ER per creare in modo dinamico i testi del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="39ab4-108">You can set up constant texts for the email subject and body, or you can use ER [formulas](er-formula-language.md) to dynamically create email texts.</span></span> 

<span data-ttu-id="39ab4-109">È possibile configurare gli indirizzi di posta elettronica per ER in due modi.</span><span class="sxs-lookup"><span data-stu-id="39ab4-109">You can configure email addresses for ER in two ways.</span></span> <span data-ttu-id="39ab4-110">La configurazione può essere completata come avviene con la funzionalità Gestione stampa oppure è possibile risolvere un indirizzo di posta elettronica utilizzando un riferimento diretto alla configurazione ER mediante una formula.</span><span class="sxs-lookup"><span data-stu-id="39ab4-110">The configuration can be completed in the same way that the Print management feature completes it, or you can resolve an email address by using a direct reference to the ER configuration through a formula.</span></span>

<span data-ttu-id="39ab4-111">[![Abilitare la destinazione posta elettronica](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span><span class="sxs-lookup"><span data-stu-id="39ab4-111">[![Enable email destination](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span></span>

## <a name="email-address-types"></a><span data-ttu-id="39ab4-112">Tipi di indirizzo di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="39ab4-112">Email address types</span></span>

<span data-ttu-id="39ab4-113">Quando si seleziona **Modifica** nel campo **A** o **Cc**, viene visualizzata la finestra di dialogo **Destinatario messaggio di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="39ab4-113">When you select **Edit** in the **To** or **Cc** fields, the **Email to** dialog box appears.</span></span> <span data-ttu-id="39ab4-114">È quindi possibile selezionare il tipo di indirizzo di posta elettronica da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="39ab4-114">You can then select the type of email address to use.</span></span> <span data-ttu-id="39ab4-115">I tipi di posta elettronica **Posta elettronica configurazione** e **Gestione stampa** sono attualmente supportati.</span><span class="sxs-lookup"><span data-stu-id="39ab4-115">The **Configuration email** and **Print Management** email types are currently supported.</span></span>

<span data-ttu-id="39ab4-116">[![Selezionare il tipo di posta elettronica](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span><span class="sxs-lookup"><span data-stu-id="39ab4-116">[![Select email type](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span></span>

### <a name="print-management"></a><span data-ttu-id="39ab4-117">Gestione stampa</span><span class="sxs-lookup"><span data-stu-id="39ab4-117">Print management</span></span>

<span data-ttu-id="39ab4-118">Se si seleziona il tipo di posta elettronica **Gestione stampa**, è possibile immettere indirizzi di posta elettronica fissi nel campo **A**.</span><span class="sxs-lookup"><span data-stu-id="39ab4-118">If you select the **Print Management** email type, you can enter fixed email addresses in the **To** field.</span></span> 

<span data-ttu-id="39ab4-119">[![Configurare indirizzi di posta elettronica fissi](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span><span class="sxs-lookup"><span data-stu-id="39ab4-119">[![Configure fixed email addresses](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span></span>

<span data-ttu-id="39ab4-120">Per utilizzare indirizzi di posta elettronica non fissi, è necessario selezionare il tipo di origine di posta elettronica per una destinazione file.</span><span class="sxs-lookup"><span data-stu-id="39ab4-120">To use email addresses that aren't fixed, you must select the email source type for a file destination.</span></span> <span data-ttu-id="39ab4-121">I valori seguenti sono supportati: **Cliente**, **Fornitore**, **Prospect**, **Contatto**, **Concorrente**, **Lavoratore**, **Candidato**, **Fornitore potenziale** e **Fornitore non autorizzato**.</span><span class="sxs-lookup"><span data-stu-id="39ab4-121">The following values are supported: **Customer**, **Vendor**, **Prospect**, **Contact**, **Competitor**, **Worker**, **Applicant**, **Prospective vendor**, and **Disallowed vendor**.</span></span> <span data-ttu-id="39ab4-122">Dopo avere selezionato un tipo di origine di posta elettronica, utilizzare il pulsante accanto al campo **Conto di origine posta elettronica** per aprire il modulo **Designer formula**.</span><span class="sxs-lookup"><span data-stu-id="39ab4-122">After you select an email source type, use the button next to the **Email source account** field to open the **Formula designer** form.</span></span> <span data-ttu-id="39ab4-123">È possibile utilizzare questo modulo per allegare una formula che restituisce in fase di esecuzione il '**conto parte** del tipo di origine selezionato nel documento elaborato per la destinazione posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="39ab4-123">You can use this form to attach a formula that returns at runtime, the **party account** of the selected source type from the processed document to the email destination.</span></span>

<span data-ttu-id="39ab4-124">[![Configurare un conto di origine di posta elettronica](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span><span class="sxs-lookup"><span data-stu-id="39ab4-124">[![Configure email source account](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span></span>

<span data-ttu-id="39ab4-125">Le formule sono specifiche alla configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="39ab4-125">Formulas are specific to the ER configuration.</span></span> <span data-ttu-id="39ab4-126">Nel campo **Formula** immettere un riferimento specifico per il documento a un tipo di parte del cliente o del fornitore.</span><span class="sxs-lookup"><span data-stu-id="39ab4-126">In the **Formula** field, enter a document-specific reference to a customer or vendor party type.</span></span> <span data-ttu-id="39ab4-127">Anziché digitare, è possibile cercare il nodo di origine dati che rappresenti il conto cliente o fornitore e selezionare **Aggiungi origine dati** per aggiornare la formula.</span><span class="sxs-lookup"><span data-stu-id="39ab4-127">Instead of typing, you can find the data source node that represents the customer or vendor account, and then select **Add data source** to update the formula.</span></span> <span data-ttu-id="39ab4-128">Ad esempio, se si utilizza la configurazione **bonifico ISO 20022**, il nodo che rappresenta un conto fornitore è `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`</span><span class="sxs-lookup"><span data-stu-id="39ab4-128">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents a vendor account is `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.</span></span>

<span data-ttu-id="39ab4-129">Se si immette un valore stringa, ad esempio `"DE-001"` e si salva una formula, verrà inviato un messaggio e-mail alla persona di contatto del fornitore, ovvero **DE-001**.</span><span class="sxs-lookup"><span data-stu-id="39ab4-129">If you enter a string value, such as `"DE-001"`, and save a formula, an email will be sent to the contact person of the vendor, **DE-001**.</span></span>


<span data-ttu-id="39ab4-130">[![Pagina Designer formula ER](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span><span class="sxs-lookup"><span data-stu-id="39ab4-130">[![ER formula designer page](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span></span>

<span data-ttu-id="39ab4-131">[![Configurare il conto con attributi di origine posta elettronica](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span><span class="sxs-lookup"><span data-stu-id="39ab4-131">[![Configure email source attributes account](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span></span>



### <a name="configuration-email"></a><span data-ttu-id="39ab4-132">Posta elettronica configurazione</span><span class="sxs-lookup"><span data-stu-id="39ab4-132">Configuration email</span></span>

<span data-ttu-id="39ab4-133">Utilizzare questo tipo di messaggio di posta elettronica se la configurazione utilizzata include un nodo nelle origini dati che restituisce un **indirizzo di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="39ab4-133">Use this email type if the configuration that you use has a node in the data sources that returns an **email address**.</span></span> <span data-ttu-id="39ab4-134">È possibile utilizzare le origini dati e le funzioni in Designer formula per ottenere un indirizzo di posta elettronica formattato correttamente.</span><span class="sxs-lookup"><span data-stu-id="39ab4-134">You can use data sources and functions in the formula designer to get a correctly formatted email address.</span></span> <span data-ttu-id="39ab4-135">Ad esempio, se si utilizza la configurazione **bonifico ISO 20022**, il nodo che rappresenta un indirizzo di posta elettronica di una persona di contatto di un fornitore è `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span><span class="sxs-lookup"><span data-stu-id="39ab4-135">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents an email address of a vendor's contact person is `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span></span>

<span data-ttu-id="39ab4-136">[![Configurare l'origine di un indirizzo di posta elettronica](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span><span class="sxs-lookup"><span data-stu-id="39ab4-136">[![Configure email address source](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="39ab4-137">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="39ab4-137">Additional resources</span></span>

- [<span data-ttu-id="39ab4-138">Panoramica dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="39ab4-138">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="39ab4-139">Destinazioni dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="39ab4-139">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="39ab4-140">Designer formula nella creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="39ab4-140">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)
