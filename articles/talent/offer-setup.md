---
title: Impostare la gestione offerta in Attract
description: In questo argomento viene descritto come impostare le offerte in Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc91a83afd5ce1627376685bcf612d6998ddbc02
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461628"
---
# <a name="set-up-offer-management-in-attract"></a><span data-ttu-id="433ca-103">Impostare la gestione offerta in Attract</span><span class="sxs-lookup"><span data-stu-id="433ca-103">Set up offer management in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="433ca-104">Quando un candidato viene passato nella fase offerta in Dynamics 365 Talent: Attract, è necessario assicurarsi che le offerte possano essere create rapidamente per il candidato, essere approvate secondo le esigenze e essere inviate al candidato.</span><span class="sxs-lookup"><span data-stu-id="433ca-104">When a candidate is moved to the offer stage in Dynamics 365 Talent: Attract, you need to ensure that the offers can be quickly created for the candidate, approved as necessary, and sent out to the candidate.</span></span> <span data-ttu-id="433ca-105">Poiché la maggior parte delle offerte sono standard, è possibile crearle da modelli riutilizzabili.</span><span class="sxs-lookup"><span data-stu-id="433ca-105">Because most offers are standard, they can be created from reusable templates.</span></span> <span data-ttu-id="433ca-106">In Attract, tutte le offerte vengono presentate in un pacchetto di offerta, cioè una raccolta di uno o più documenti di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-106">In Attract, all offers are rolled into an offer package, which is a collection of one or more offer documents.</span></span> 

<span data-ttu-id="433ca-107">Di seguito sono elencati tutti i passaggi che un amministratore di Attract deve seguire per impostare diversi modelli di pacchetti di offerta nell'ambito della funzionalità di gestione delle offerta in Attract.</span><span class="sxs-lookup"><span data-stu-id="433ca-107">This topic lists all the steps that an Attract administrator would follow to set up different offer package templates as part of the offer management capability in Attract.</span></span> <span data-ttu-id="433ca-108">Gli utenti senza ruoli di amministratore non avranno accesso a tali funzionalità.</span><span class="sxs-lookup"><span data-stu-id="433ca-108">Users with non-administrator roles will not have access to these capabilities.</span></span>

>[!NOTE]
> <span data-ttu-id="433ca-109">Le funzionalità di gestione delle offerte sono disponibili come parte del componente aggiuntivo per l'assunzione a livello globale.</span><span class="sxs-lookup"><span data-stu-id="433ca-109">Offer management capabilities are available as part of the Comprehensive Hiring Add-On.</span></span>

## <a name="offer-data"></a><span data-ttu-id="433ca-110">Dati dell'offerta</span><span class="sxs-lookup"><span data-stu-id="433ca-110">Offer data</span></span> 

<span data-ttu-id="433ca-111">I dati dell'offerta sono la più piccola unità nel modello di pacchetto di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-111">Offer data is the smallest unit inside the offer package template.</span></span> <span data-ttu-id="433ca-112">Un'offerta tipica è costituita da un testo standard e un insieme di valori.</span><span class="sxs-lookup"><span data-stu-id="433ca-112">A typical offer consists of standard text and a set of values.</span></span> <span data-ttu-id="433ca-113">I set di valori sono le singole parti che potrebbero variare tra le offerte.</span><span class="sxs-lookup"><span data-stu-id="433ca-113">The sets of values are the only pieces that could change between offers.</span></span> <span data-ttu-id="433ca-114">Durante la creazione dell'offerta, l'aspetto più importante su cui il creatore di offerta può focalizzarsi è l'elenco dei segnaposto di dati dell'offerta presenti in un modello di pacchetto di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-114">During the offer creation, the most important aspect that the offer creator can focus on is the list of offer data placeholders present in an offer package template.</span></span> <span data-ttu-id="433ca-115">Per impostare i dati di offerta, effettuare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="433ca-115">To set up offer data, do the following.</span></span>

1.  <span data-ttu-id="433ca-116">Andare a **Gestione offerte**.</span><span class="sxs-lookup"><span data-stu-id="433ca-116">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="433ca-117">Espandere la sezione **Raccolta** nel pannello di navigazione sinistro, quindi passare a **Dati dell'offerta**.</span><span class="sxs-lookup"><span data-stu-id="433ca-117">Expand the **Library** section in the left navigation pane, then go to **Offer data**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="433ca-118">Nella pagina **Dati dell'offerta** si trovano le sezioni **Dettagli candidato** e **Dettagli mansione**.</span><span class="sxs-lookup"><span data-stu-id="433ca-118">On the **Offer data** page are the **Candidate details** and **Job details** sections.</span></span> <span data-ttu-id="433ca-119">Attract fornisce alcuni segnaposto predefiniti per i dati di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-119">Attract provides a few offer data placeholders out-of-the-box.</span></span>
    > 
    > <span data-ttu-id="433ca-120">Sono disponibili sezioni nella pagina per organizzare i diversi segnaposto di dati di offerta in gruppi logici.</span><span class="sxs-lookup"><span data-stu-id="433ca-120">There are sections on the page to organize different offer data placeholders together in logical groups.</span></span> <span data-ttu-id="433ca-121">Queste sezioni possono facilitare la manutenzione dei dati di offerta e l'inserimento dei dati durante il processo di creazione di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-121">These sections can help with maintenance of offer data and population of data during the offer creation process.</span></span>
    > 
    > <span data-ttu-id="433ca-122">Per creare un elenco di valori per un segnaposto, caricare un foglio di calcolo Excel con una colonna con il segnaposto come titolo della colonna e l'elenco delle opzioni nelle righe sottostanti.</span><span class="sxs-lookup"><span data-stu-id="433ca-122">To create a list of values for a placeholder, upload an Excel spreadsheet that has one column with the placeholder as the column title and the list of choices in the rows underneath.</span></span> <span data-ttu-id="433ca-123">Se si fa riferimento allo stesso segnaposto in un altro set di regole dei dati, assicurarsi che abbiano un set comune di valori.</span><span class="sxs-lookup"><span data-stu-id="433ca-123">If the same placeholder is referenced in another data rule set, ensure they have a common set of values.</span></span>
    
1.  <span data-ttu-id="433ca-124">Per creare una nuova sezione di dati dell'offerta, fare clic su **Aggiungere una sezione** e immettere un nome univoco per la sezione.</span><span class="sxs-lookup"><span data-stu-id="433ca-124">To create a new offer data section, click **Add a section** and enter a unique name for the section.</span></span>

1.  <span data-ttu-id="433ca-125">Per aggiungere segnaposto di dati di offerta in una sezione, fare clic su **Aggiungi dati dell'offerta** e immettere un nome univoco per il segnaposto.</span><span class="sxs-lookup"><span data-stu-id="433ca-125">To add offer data placeholders to any section, click **Add offer data** and enter a unique name for the placeholder.</span></span>

1.  <span data-ttu-id="433ca-126">Per modificare il nome della sezione, passare il mouse sul nome della sezione e aggiornare il nome.</span><span class="sxs-lookup"><span data-stu-id="433ca-126">To edit the name of any section, hover over the section name and update the name.</span></span>

1.  <span data-ttu-id="433ca-127">Per modificare il nome di un segnaposto di dati di offerta esistente, è innanzitutto necessario assicurarsi che il segnaposto non sia già parte di alcun modello.</span><span class="sxs-lookup"><span data-stu-id="433ca-127">To edit the name of any existing offer data placeholder, first make sure that the placeholder is not already part of any template.</span></span> <span data-ttu-id="433ca-128">Quindi, passare il mouse sul nome del segnaposto di dati di oggerta e aggiornare il nome in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="433ca-128">Then, hover over the name of the offer data placeholder and update the name as needed.</span></span>

1. <span data-ttu-id="433ca-129">Per eliminare un segnaposto di dati di offerta esistente, è innanzitutto necessario assicurarsi che il segnaposto non sia già parte di un altro modello.</span><span class="sxs-lookup"><span data-stu-id="433ca-129">To delete an existing offer data placeholder, first make sure that the placeholder is not part of any other template.</span></span> <span data-ttu-id="433ca-130">Quindi, passare con il mouse sul segnaposto e quando appare l'icona del cestino fare clic su tale icona per eliminare il segnaposto di dati di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-130">Then, hover over the placeholder and when the trash can icon appears, click the trash can to delete the offer data placeholder.</span></span>
    >[!NOTE]
    > <span data-ttu-id="433ca-131">È possibile vedere di quanti modelli un segnaposto di dati di offerta fa parte in dall'indicatore numerico accanto a ogni dato di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-131">You can see how many templates an offer data placeholder is part of by the number indicator next to each offer data.</span></span> 

1. <span data-ttu-id="433ca-132">Per eliminare una sezione, passare con il mouse sul suo nome.</span><span class="sxs-lookup"><span data-stu-id="433ca-132">To delete any section, hover over the name.</span></span> <span data-ttu-id="433ca-133">Se nessuno dei segnaposto di dati di offerta nella sezione appare in qualsiasi modello, è possibile fare clic sull'icona del cestino per eliminarla.</span><span class="sxs-lookup"><span data-stu-id="433ca-133">If none of the offer data placeholders inside the section appear in any template, you can click the trash can icon to delete it.</span></span> 
    >[!NOTE]
    > <span data-ttu-id="433ca-134">L'eliminazione di una sezione implica anche l'eliminazione dei segnaposto di dati di offerta all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="433ca-134">Deleting the section will also delete all the offer data placeholders inside that section.</span></span>

<span data-ttu-id="433ca-135">Dopo aver impostato i segnaposto di dati di offerta, è possibile utilizzarli in qualsiasi modello di documento.</span><span class="sxs-lookup"><span data-stu-id="433ca-135">After the offer data placeholders have been set up, you can use them across any document template.</span></span> <span data-ttu-id="433ca-136">I segnaposto di dati di offerta non sono limitati a un modello specifico: lo stesso set può essere utilizzato in tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="433ca-136">Offer data placeholders are not restricted to a specific template -- the same set can be used across all templates.</span></span>

## <a name="offer-data-rules"></a><span data-ttu-id="433ca-137">Regole dati offerta</span><span class="sxs-lookup"><span data-stu-id="433ca-137">Offer data rules</span></span>

<span data-ttu-id="433ca-138">La maggior parte delle organizzazioni hanno regole per la creazione delle offerte.</span><span class="sxs-lookup"><span data-stu-id="433ca-138">Most organization have rules for how offers must be created.</span></span> <span data-ttu-id="433ca-139">Ad esempio, un'organizzazione può richiedere che la massima retribuzione annuale offerta per una combinazione specifica di sede e livello di anzianità deve essere compresa in un determinato intervallo o che ci siano solo pochi valori possibili per il livello di offerta per il nuovo assunto.</span><span class="sxs-lookup"><span data-stu-id="433ca-139">For example, an organization may want to require that the maximum annual salary offer for a specific location and seniority level combination has to be within a certain range, or that there are only a few specific values possible for the offer level for the new hire.</span></span> <span data-ttu-id="433ca-140">Attract attualmente supporta tutti questi tipi di regole di dati utilizzando un file CSV.</span><span class="sxs-lookup"><span data-stu-id="433ca-140">Attract currently supports all such data rules using a CSV file.</span></span>

<span data-ttu-id="433ca-141">Per preparare il file CSV di regole dei dati, effettuare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="433ca-141">To prepare the data rules CSV file, do the following.</span></span>

1.  <span data-ttu-id="433ca-142">Determinare il segnaposto di dati di offerta per il set di regole.</span><span class="sxs-lookup"><span data-stu-id="433ca-142">Determine the offer data placeholder for the rule set.</span></span> <span data-ttu-id="433ca-143">Ad esempio, **Salario annuale**.</span><span class="sxs-lookup"><span data-stu-id="433ca-143">For example, **Annual Salary**.</span></span>

1.  <span data-ttu-id="433ca-144">Identificare i valori dei segnaposto di dati di offerta dipendenti.</span><span class="sxs-lookup"><span data-stu-id="433ca-144">Identify the dependent offer data placeholder values.</span></span> <span data-ttu-id="433ca-145">Ad esempio, **Ubicazione mansione** e **Livello**.</span><span class="sxs-lookup"><span data-stu-id="433ca-145">For example, **Job Location** and **Level**.</span></span>

1.  <span data-ttu-id="433ca-146">Specificare le colonne 1 e 2 come **Ubicazione mansione** e **Livello**.</span><span class="sxs-lookup"><span data-stu-id="433ca-146">Specify columns 1 and 2 as **Job Location** and **Level**.</span></span>

1.  <span data-ttu-id="433ca-147">Per caricare un valore di intervallo, creare le colonne 3 e 4 **Salario annuale**.</span><span class="sxs-lookup"><span data-stu-id="433ca-147">To upload a range value, make columns 3 and 4 **Annual Salary**.</span></span> <span data-ttu-id="433ca-148">Per caricare un valore specifico anziché un intervallo, creare solo la colonna 3 **Salario annuale**.</span><span class="sxs-lookup"><span data-stu-id="433ca-148">To upload a specific value instead of a range, only make column 3 **Annual Salary**.</span></span>

1.  <span data-ttu-id="433ca-149">Popolare il file di Microsoft Excel in base ai ruoli richiesti.</span><span class="sxs-lookup"><span data-stu-id="433ca-149">Populate the Microsoft Excel file based on your required roles.</span></span>

1.  <span data-ttu-id="433ca-150">Assicurarsi che ogni riga sia una combinazione univoca di tutti i valori messi insieme.</span><span class="sxs-lookup"><span data-stu-id="433ca-150">Ensure that each row is a unique combination of all the values put together.</span></span>

1.  <span data-ttu-id="433ca-151">Salvare il file in formato CSV.</span><span class="sxs-lookup"><span data-stu-id="433ca-151">Save the file as a CSV format.</span></span>

<span data-ttu-id="433ca-152">Per caricare il file di regole dei dati di offerta, effettuare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="433ca-152">To upload the offer data rules file, do the following.</span></span>

1.  <span data-ttu-id="433ca-153">Andare a **Gestione offerte**.</span><span class="sxs-lookup"><span data-stu-id="433ca-153">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="433ca-154">Espandere la sezione **Raccolta** nel pannello di navigazione sinistro, quindi passare a **Regole dati offerta**.</span><span class="sxs-lookup"><span data-stu-id="433ca-154">Expand the **Library** section in the left navigation panel, then go to **Offer data rules**.</span></span>

1.  <span data-ttu-id="433ca-155">Fare clic su **Nuovo set di dati** per visualizzare la finestra di dialogo **Carica**.</span><span class="sxs-lookup"><span data-stu-id="433ca-155">Click **New data set** to display the **Upload** dialog box.</span></span>

1.  <span data-ttu-id="433ca-156">Specificare un nome univoco per il set di regole quindi caricare il file salvato CSV.</span><span class="sxs-lookup"><span data-stu-id="433ca-156">Specify a unique name for the rule set and then upload the saved CSV file.</span></span>

1.  <span data-ttu-id="433ca-157">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="433ca-157">Click **Add**.</span></span>
    <span data-ttu-id="433ca-158">Il set di regole verrà elaborato in background e si riceverà una notifica nell'app e tramite posta elettronica una volta completata.</span><span class="sxs-lookup"><span data-stu-id="433ca-158">The rule set will be processed in the background and you will be notified in-app and via email once it completes.</span></span>

    <span data-ttu-id="433ca-159">Verrà notificato se sono presenti errori durante l'elaborazione del caricamento.</span><span class="sxs-lookup"><span data-stu-id="433ca-159">You will be notified if there are errors while processing the upload.</span></span> <span data-ttu-id="433ca-160">È possibile scaricare il registro errori, correggere il file e caricarlo ancora.</span><span class="sxs-lookup"><span data-stu-id="433ca-160">You can then download the error log, fix the file, and upload it again.</span></span>

1.  <span data-ttu-id="433ca-161">Utilizzare l'opzione del pulsante con i puntini di sospensione (**…**) se si desidera scaricare il set di regole e aggiornare il set di valori.</span><span class="sxs-lookup"><span data-stu-id="433ca-161">Use the ellipses button (**…**) option if you want to download the rule set and update the set of values.</span></span> <span data-ttu-id="433ca-162">Dopo l'aggiornamento, è possibile caricare di nuovo il file.</span><span class="sxs-lookup"><span data-stu-id="433ca-162">After updating, you can upload the file again.</span></span>

1.  <span data-ttu-id="433ca-163">È possibile eliminare un set di regole caricato corrente se il segnaposto definito non è utilizzato in un altro modello di documento.</span><span class="sxs-lookup"><span data-stu-id="433ca-163">You can delete an existing rule set upload if the placeholder being defined is not being used in another document template.</span></span>

>[!NOTE]
> - <span data-ttu-id="433ca-164">Ogni segnaposto può essere associato a un solo insieme univoco di colonne da cui dipende.</span><span class="sxs-lookup"><span data-stu-id="433ca-164">Each placeholder can only have one unique set of columns that it is dependent on.</span></span> <span data-ttu-id="433ca-165">Ad esempio, se **Salario annuale** dipende da **Ubicazione mansione** e **Livello**, non è possibile caricare un altro set di regole in cui **Salario annuale** dipende da un diverso set di colonne.</span><span class="sxs-lookup"><span data-stu-id="433ca-165">For example, if **Annual Salary** is dependent on **Job Location** and **Level**, you can't upload another rule set where **Annual Salary** is dependent on a different set of columns.</span></span>

> - <span data-ttu-id="433ca-166">È possibile scaricare set di regole dei dati di offerta di esempio nella scheda **Esempi** della pagina **Regole dati offerta**.</span><span class="sxs-lookup"><span data-stu-id="433ca-166">You can download sample offer data rule sets on the **Samples** tab on the **Offer data rules** page.</span></span>

> - <span data-ttu-id="433ca-167">Quando un creatore di offerte ignora i valori suggeriti dalle regole dei dati di offerta, l'offerta viene contrassegnata come non standard e il flusso di lavoro di approvazione di offerta sarà obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="433ca-167">When an offer creator overrides the values that are recommended by the offer data rules, the offer is flagged as non-standard and offer approval workflow will be mandated.</span></span>

## <a name="document-templates"></a><span data-ttu-id="433ca-168">Modelli di documento</span><span class="sxs-lookup"><span data-stu-id="433ca-168">Document templates</span></span>

<span data-ttu-id="433ca-169">Un modello di documento di offerta può agevolare agli amministratori nella creazione delle lettere di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-169">An offer document template can help administrators create offer letters.</span></span> <span data-ttu-id="433ca-170">Il modello di documento di offerta è una combinazione di testo che fa parte dell'offerta nonché i segnaposto definiti dei dati di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-170">The offer document template is a combination of the text that will be part of the offer as well as the defined offer data placeholders.</span></span> 

<span data-ttu-id="433ca-171">Per creare un modello di documento di offerta, effettuare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="433ca-171">To create an offer document template, do the following.</span></span>

1.  <span data-ttu-id="433ca-172">Andare a **Gestione offerte**.</span><span class="sxs-lookup"><span data-stu-id="433ca-172">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="433ca-173">Espandere la sezione **Raccolta** nel pannello di navigazione sinistro, quindi passare a **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="433ca-173">Expand the **Library** section in the left navigation pane and go to **Templates**.</span></span>

    <span data-ttu-id="433ca-174">Nella pagina **Modelli** viene visualizzato un elenco dei modelli di documento già definiti.</span><span class="sxs-lookup"><span data-stu-id="433ca-174">The **Templates** page will display a list of document templates that have already been defined.</span></span>

1.  <span data-ttu-id="433ca-175">Per creare un nuovo modello di documento, fare clic su **Nuovo modello**.</span><span class="sxs-lookup"><span data-stu-id="433ca-175">To create a new document template, click **New Template**.</span></span>

1.  <span data-ttu-id="433ca-176">Immettere un nome univoco per il modello e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="433ca-176">Enter a unique name for the template and click **Create**.</span></span>

1.  <span data-ttu-id="433ca-177">Utilizzare l'editor di testo avanzato per inserire o modificare il contenuto del documento di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-177">Use the rich text editor to insert or edit the offer document content.</span></span> <span data-ttu-id="433ca-178">È possibile inserire tabelle, immagini e collegamenti ipertestuali utilizzando le opzioni disponibili nella parte superiore dell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="433ca-178">You can insert tables, images, and hyperlinks using the options available at the top of the text editor.</span></span>

1.  <span data-ttu-id="433ca-179">È possibile inserire segnaposto di dati di offerta nel documento di modello di offerta in questo modi:</span><span class="sxs-lookup"><span data-stu-id="433ca-179">You can insert offer data placeholders in the offer template document by:</span></span>

    - <span data-ttu-id="433ca-180">Trascinando la selezione dal riquadro a destra.</span><span class="sxs-lookup"><span data-stu-id="433ca-180">Dragging and dropping from the right pane.</span></span>

    - <span data-ttu-id="433ca-181">Posizionando direttamente l'hashtag del segnaposto di dati di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-181">Hashtag the offer data placeholder directly into position.</span></span> <span data-ttu-id="433ca-182">Digitando **\#** quindi iniziare a immettere il nome del segnaposto di dati di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-182">Type **\#** and then start typing the name of the offer data placeholder.</span></span> <span data-ttu-id="433ca-183">Le opzioni appariranno nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="433ca-183">Options will appear in the drop-down list.</span></span> <span data-ttu-id="433ca-184">Fare clic o premere **INVIO** per inserire il segnaposto di dati di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-184">Click or press **Enter** to insert the offer data placeholder.</span></span>

    >[!NOTE]
    > - <span data-ttu-id="433ca-185">Per associare un segnaposto al modello di documento di offerta senza esporre il relativo valore al candidato, passare il mouse sul segnaposto di dati di offerta e fare clic sull'icona **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="433ca-185">To associate a placeholder to the offer document template without exposing its value to the candidate, hover over the offer data placeholder and click the **Pin** icon.</span></span> <span data-ttu-id="433ca-186">Questo sposterà il segnaposto nella sezione **Dati dell'offerta aggiunti** del modello di documento di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-186">This will push the placeholder to the **Pinned offer data** section of the offer document template.</span></span> <span data-ttu-id="433ca-187">Per sbloccare, seguire la stessa procedura ma fare clic su **Sblocca** nell'elenco dei segnaposto di dati di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-187">To unpin, follow the same steps but click **Unpin** in the list of offer data placeholders.</span></span>

    > - <span data-ttu-id="433ca-188">Per visualizzare l'elenco dei segnaposto di dati di offerta attivi, passare alla scheda **Attivo** del riquadro a destra.</span><span class="sxs-lookup"><span data-stu-id="433ca-188">To view the list of active offer data placeholders, switch to the **Active** tab in the right pane.</span></span>

    > - <span data-ttu-id="433ca-189">Se si inserisce un segnaposto basato su un set di regole dei dati di offerta, è possibile visualizzare la dipendenza di tale segnaposto da altri valori.</span><span class="sxs-lookup"><span data-stu-id="433ca-189">If you insert a placeholder that is driven by an offer data rule set, you can see the dependency of that offer data placeholder on other values.</span></span>

    > - <span data-ttu-id="433ca-190">In alternativa, è possibile **Importare** il contenuto da un file .docx nel computer locale e modificarlo in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="433ca-190">Alternatively, you can **Import** the content from a .docx file on your local machine and edit as required.</span></span> <span data-ttu-id="433ca-191">In tal modo non sarà necessario digitare tutto il contenuto nell'editor.</span><span class="sxs-lookup"><span data-stu-id="433ca-191">That way, you don’t have to type in all the content in the editor.</span></span>

1. <span data-ttu-id="433ca-192">Per visualizzare l'anteprima del documento di offerta, utilizzare l'opzione **Anteprima** nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="433ca-192">To preview the offer document, use the **Preview** option at the top of the page.</span></span>

1. <span data-ttu-id="433ca-193">Per determinare se un creatore di offerte può modificare il contenuto del documento di offerta, utilizzare l'opzione **Gestisci autorizzazione** nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="433ca-193">To control whether an offer creator can edit the offer document content, use the **Manage permission** option at the top of the page.</span></span> <span data-ttu-id="433ca-194">Se si desidera che il creatore di offerta possa solo inserire i valori dei segnaposto e non modificare il testo, impostare il valore dell'autorizzazione su **No**.</span><span class="sxs-lookup"><span data-stu-id="433ca-194">If you want the offer creator to only insert placeholder values and not edit text, set the permission value to **No**.</span></span>

1. <span data-ttu-id="433ca-195">Scegliere **Salva** per salvare l'avanzamento.</span><span class="sxs-lookup"><span data-stu-id="433ca-195">Click **Save** to save your progress.</span></span> <span data-ttu-id="433ca-196">Il modello verrà salvato con stato di bozza.</span><span class="sxs-lookup"><span data-stu-id="433ca-196">The template will be saved in a draft state.</span></span>

1. <span data-ttu-id="433ca-197">Per finalizzare e contrassegnare il documento come pubblicato, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="433ca-197">To finalize and mark the document as published, click **Finish**.</span></span>

1. <span data-ttu-id="433ca-198">È possibile visualizzare quali modelli di documento sono attualmente attivi, in modalità bozza e archiviati e non più in uso nell'esperienza di destinazione della raccolta dei modelli di documento.</span><span class="sxs-lookup"><span data-stu-id="433ca-198">You can see which document templates are currently active, in draft mode, and have been archived and are no longer in use on the document templates library landing experience.</span></span>

>[!NOTE]
> <span data-ttu-id="433ca-199">È possibile eliminare qualsiasi modello di documento di offerta che non fa parte di un modello di pacchetto di offerta esistente.</span><span class="sxs-lookup"><span data-stu-id="433ca-199">You can delete any offer document template that is not part of an existing offer package template.</span></span>


## <a name="offer-package-templates"></a><span data-ttu-id="433ca-200">Modelli di pacchetti di offerta</span><span class="sxs-lookup"><span data-stu-id="433ca-200">Offer package templates</span></span>

<span data-ttu-id="433ca-201">I pacchetti di offerta sono gli elementi di offerta condivisi con il candidato e sono costituiti da una combinazione di uno o più modelli di documento di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-201">Offer packages are the offer artifacts that are shared with the candidate and consist of a combination of one or more offer document templates.</span></span> <span data-ttu-id="433ca-202">Per creare un pacchetto di offerta, effettuare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="433ca-202">To create an offer package, do the following.</span></span>

1.  <span data-ttu-id="433ca-203">Andare a **Gestione offerte**.</span><span class="sxs-lookup"><span data-stu-id="433ca-203">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="433ca-204">Passare a **Pacchetti** dal pannello di navigazione sinistro.</span><span class="sxs-lookup"><span data-stu-id="433ca-204">Go to **Packages** from the left navigation pane.</span></span>

    <span data-ttu-id="433ca-205">Un elenco dei modelli di pacchetto attivi disponibili per i creatori di offerta viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="433ca-205">A list of active package templates that are available for offer creators to use is displayed.</span></span>

1.  <span data-ttu-id="433ca-206">Per creare un nuovo pacchetto di offerta, scegliere **Nuovo pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="433ca-206">To create a new offer package, click **New Package**.</span></span>

1.  <span data-ttu-id="433ca-207">Immettere un nome univoco e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="433ca-207">Enter a unique name and click **Create**.</span></span>

1.  <span data-ttu-id="433ca-208">Fare clic su **Aggiungi modello**.</span><span class="sxs-lookup"><span data-stu-id="433ca-208">Click **Add template**.</span></span>

    >[!NOTE]
    > - <span data-ttu-id="433ca-209">È possibile creare un nuovo modello o sceglierne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="433ca-209">You can choose to create a new template or choose from an existing one.</span></span>

    > - <span data-ttu-id="433ca-210">Se si sceglie di aggiungere un modello esistente, verificare che il modello di documento di offerta sia stato salvato, finalizzato e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="433ca-210">If you choose to add an existing template, you need to make sure that the   offer document template was saved, finalized, and marked as   active.</span></span>
    
    > - <span data-ttu-id="433ca-211">È possibile scegliere tutti i modelli di documento desiderati.</span><span class="sxs-lookup"><span data-stu-id="433ca-211">You can choose as many document templates as you want.</span></span> 
    
1.  <span data-ttu-id="433ca-212">Fare clic su **Fatto** per tornare **Gestione pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="433ca-212">Click **Done** to return to **Package management**.</span></span>

    <span data-ttu-id="433ca-213">È possibile configurare la sequenza dei documenti e anche contrassegnare se il documento di offerta specifico viene richiesto durante la creazione di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-213">You can configure the sequence of the documents and also mark whether the specific offer document is required during offer creation.</span></span> <span data-ttu-id="433ca-214">Il creatore di offerta avrà una opzione per eliminare i documenti contrassegnati **Non obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="433ca-214">The offer creator will have an option to delete the documents marked as **Not required**.</span></span>

1. <span data-ttu-id="433ca-215">Per salvare il modello di pacchetto di offerta in modo che sia utilizzabile da tutti i creatori di offerta, clic su **Salva e pubblica**.</span><span class="sxs-lookup"><span data-stu-id="433ca-215">To save the offer package template so that it's usable by all offer creators, click **Save and publish**.</span></span>

   <span data-ttu-id="433ca-216">Per visualizzare le bozze di modelli di pacchetto dell'offerta, passare alla scheda **Bozze**. Se si apportano modifiche al modello di pacchetto di offerta, deve essere salvato e ripubblicato.</span><span class="sxs-lookup"><span data-stu-id="433ca-216">To view draft offer package templates, go to the **Drafts** tab. If a change is made to the offer package template, it must be  saved and republished.</span></span>

## <a name="configure-an-offer-process"></a><span data-ttu-id="433ca-217">Configurare un processo di offerta</span><span class="sxs-lookup"><span data-stu-id="433ca-217">Configure an offer process</span></span>

<span data-ttu-id="433ca-218">Diverse parti del processo di creazione dell'offerta possono essere configurate da un amministratore di Attract.</span><span class="sxs-lookup"><span data-stu-id="433ca-218">There are several parts of the offer creation process that can be configured by an Attract administrator.</span></span>

- <span data-ttu-id="433ca-219">**Approvazioni di offerta** - Scegliere se le approvazioni di offerta sono obbligatorie affinché l'offerta possa essere inviata al candidato.</span><span class="sxs-lookup"><span data-stu-id="433ca-219">**Offer approvals** - Choose whether offer approvals are required before the offer can be sent to the candidate.</span></span> <span data-ttu-id="433ca-220">In qualità di amministratore, è possibile decidere se tutte le approvazioni di offerta accadranno in modo sequenziale o in un flusso di lavoro di approvazione parallela.</span><span class="sxs-lookup"><span data-stu-id="433ca-220">As an administrator, you can also decide whether all offer approvals will happen in a sequential manner or parallel approval workflow.</span></span> <span data-ttu-id="433ca-221">È inoltre possibile rendere obbligatorio che gli approvatori di offerta devono aggiungere un commento all'approvazione di offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-221">You can also mandate whether offer approvers must add a comment along with their offer approval.</span></span> <span data-ttu-id="433ca-222">Le approvazioni di offerta sono obbligatorie per tutte le offerte non standard.</span><span class="sxs-lookup"><span data-stu-id="433ca-222">Offer approvals are mandatory for all non-standard offers.</span></span>

- <span data-ttu-id="433ca-223">**Esperienza dell'offerta del candidato** - Come amministratore, è possibile scegliere di impostare se tutte le offerte abbiano una data di scadenza e in caso affermativo, quale deve essere l'offset predefinito per la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="433ca-223">**Candidate’s offer experience** - As administrator, you can choose to set whether all offers have an expiration date, and if so, what the default offset for the expiration date should be.</span></span> <span data-ttu-id="433ca-224">È inoltre possibile configurare se i candidati possono rifiutare un'offerta.</span><span class="sxs-lookup"><span data-stu-id="433ca-224">You can also configure whether candidates can decline an offer.</span></span>

- <span data-ttu-id="433ca-225">**Firme elettroniche** - Come amministratore, è inoltre possibile selezionare il metodo che i candidati possono utilizzare per firmare le offerte.</span><span class="sxs-lookup"><span data-stu-id="433ca-225">**e-Signatures** - As an administrator, you can also choose the method that candidates can use to sign offers.</span></span>
    - <span data-ttu-id="433ca-226">Adobe Sign - Tutti i pacchetti di offerta saranno inviati e firmati via Adobe Sign.</span><span class="sxs-lookup"><span data-stu-id="433ca-226">Adobe Sign - All offer packages will be sent and signed via Adobe Sign.</span></span> <span data-ttu-id="433ca-227">Ogni creatore di offerte che pubblica l'offerta deve avere il relativo account Adobe Sign collegato a Attract.</span><span class="sxs-lookup"><span data-stu-id="433ca-227">Each offer creator publishing the offer needs to have their Adobe Sign account connected to Attract.</span></span> <span data-ttu-id="433ca-228">Per le licenze di Adobe Sign e una versione di prova gratuita, visitare la pagina a questo [collegamento](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).</span><span class="sxs-lookup"><span data-stu-id="433ca-228">For Adobe Sign licenses and a free Trial, please visit this [link](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).</span></span>

    - <span data-ttu-id="433ca-229">DocuSign - Tutti i pacchetti di offerta saranno inviati e firmati via DocuSign.</span><span class="sxs-lookup"><span data-stu-id="433ca-229">DocuSign - All offer packages will be sent and signed via DocuSign.</span></span> <span data-ttu-id="433ca-230">Ogni creatore di offerte che pubblica l'offerta deve avere il relativo account DocuSign collegato a Attract.</span><span class="sxs-lookup"><span data-stu-id="433ca-230">Each offer creator publishing the offer needs to have their DocuSign account connected to Attract.</span></span> 
    
    - <span data-ttu-id="433ca-231">ESign – Questa è l'opzione predefinita, dove l'utente può firmare un'offerta digitando il relativo nome e le iniziali.</span><span class="sxs-lookup"><span data-stu-id="433ca-231">ESign - This is the default option, provided out of the box, where the user can sign an offer by typing their name and initials.</span></span>


<span data-ttu-id="433ca-232">Per ulteriori informazioni sul processo di creazione dell'offerta, vedere [Creare, approvare e firmare le offerte](./creating-offers.md).</span><span class="sxs-lookup"><span data-stu-id="433ca-232">To learn more about the offer creation process, see [Create, approve, and sign offers](./creating-offers.md).</span></span>
