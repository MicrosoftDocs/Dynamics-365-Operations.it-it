---
title: Integrazione di note
description: In questo argomento viene descritta l'integrazione dei dati delle note in doppia scrittura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 221be52b4d66aaa47f9a1919d5d0b9f8459b7ff9
ms.sourcegitcommit: db9b35ce6968cad8874b3c13d4c02d84e2617c8b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "5577608"
---
# <a name="note-integration"></a><span data-ttu-id="69620-103">Integrazione di note</span><span class="sxs-lookup"><span data-stu-id="69620-103">Note integration</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="69620-104">Durante i processi aziendali, gli utenti di Microsoft Dynamics 365 spesso raccolgono informazioni sui propri clienti.</span><span class="sxs-lookup"><span data-stu-id="69620-104">During business processes, Microsoft Dynamics 365 users often gather information about their customers.</span></span> <span data-ttu-id="69620-105">Queste informazioni vengono registrate come attività e note.</span><span class="sxs-lookup"><span data-stu-id="69620-105">This information is recorded as activities and notes.</span></span> <span data-ttu-id="69620-106">In questo argomento viene descritta l'integrazione dei dati delle note in doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="69620-106">This topic describes the integration of note data in dual-write.</span></span>

<span data-ttu-id="69620-107">Le informazioni sui clienti possono essere classificate nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="69620-107">Customer information can be classified in the following ways:</span></span>

+ <span data-ttu-id="69620-108">**Informazioni utilizzabili che un utente Dynamics 365 gestisce per conto di un cliente** - Ad esempio, Contoso (un utente di Dynamics 365) conduce un gioco a premi.</span><span class="sxs-lookup"><span data-stu-id="69620-108">**Actionable information that a Dynamics 365 user handles on behalf of a customer** – For example, Contoso (a Dynamics 365 user) is conducting a game show.</span></span> <span data-ttu-id="69620-109">Uno dei clienti di Contoso (un cliente) vuole partecipare al gioco a premi.</span><span class="sxs-lookup"><span data-stu-id="69620-109">One of Contoso's customers (a customer) wants to attend the game show.</span></span> <span data-ttu-id="69620-110">Il cliente chiede a un dipendente di Contoso di iscriverlo a tale gioco a premi.</span><span class="sxs-lookup"><span data-stu-id="69620-110">The customer asks a Contoso employee to book a slot in the game show for them.</span></span> <span data-ttu-id="69620-111">La prenotazione viene effettuata nel calendario del partecipante all'evento di Contoso.</span><span class="sxs-lookup"><span data-stu-id="69620-111">The booking occurs in Contoso's event attendee's calendar.</span></span>
+ <span data-ttu-id="69620-112">**Informazioni utilizzabili per un utente Dynamics 365** - Ad esempio, un cliente che acquista un'unità Surface inserisce istruzioni speciali con cui richiede una confezione regalo per il dispositivo prima della consegna.</span><span class="sxs-lookup"><span data-stu-id="69620-112">**Actionable information for a Dynamics 365 user** – For example, a customer who is purchasing a Surface unit enters special instructions that indicate that the device should be gift wrapped before delivery.</span></span> <span data-ttu-id="69620-113">Queste istruzioni sono informazioni utilizzabili che devono essere gestite dal dipendente Contoso responsabile della confezione regalo.</span><span class="sxs-lookup"><span data-stu-id="69620-113">These instructions are actionable information that should be handled by the Contoso employee who is responsible for packaging.</span></span>
+ <span data-ttu-id="69620-114">**Informazioni non utilizzabili** - Ad esempio, un cliente visita il punto vendita Contoso e, durante la conversazione con un addetto del punto vendita, esprime interesse per i giochi e gli accessori per giochi *Halo*.</span><span class="sxs-lookup"><span data-stu-id="69620-114">**Non-actionable information** – For example, a customer visits the Contoso store and, during their conversation with a store associate, expresses interest in *Halo* games and gaming accessories.</span></span> <span data-ttu-id="69620-115">L'addetto del punto vendita prende nota di queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="69620-115">The store associate makes a note of this information.</span></span> <span data-ttu-id="69620-116">Il motore dei suggerimenti sui prodotti le utilizza quindi per fornire suggerimenti al cliente.</span><span class="sxs-lookup"><span data-stu-id="69620-116">The product recommendations engine then uses it to make recommendations to the customer.</span></span>

<span data-ttu-id="69620-117">In genere, le informazioni utilizzabili vengono acquisite come *attività* nelle app Finance and Operations e nelle app di interazione con i clienti.</span><span class="sxs-lookup"><span data-stu-id="69620-117">In general, actionable information is captured as *activities* in Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="69620-118">Le informazioni non utilizzabili vengono acquisite come *note* nelle app Finance and Operations e come *annotazioni* nelle app di interazione con i clienti.</span><span class="sxs-lookup"><span data-stu-id="69620-118">Non-actionable information is captured as *notes* in Finance and Operations apps, and as *annotations* in customer engagement apps.</span></span>

> [!TIP]
> <span data-ttu-id="69620-119">Sebbene le note siano destinate alle informazioni non utilizzabili, le app non ne impediranno l'utilizzo per archiviare e gestire informazioni utilizzabili se si intende farlo.</span><span class="sxs-lookup"><span data-stu-id="69620-119">Although notes are intended for non-actionable information, the apps won't prevent you from using them to store and handle actionable information if you want to use them in that way.</span></span>

<span data-ttu-id="69620-120">Microsoft sta attualmente rilasciando funzionalità per l'integrazione delle note.</span><span class="sxs-lookup"><span data-stu-id="69620-120">Microsoft is currently releasing functionality for note integration.</span></span> <span data-ttu-id="69620-121">(la funzionalità per l'integrazione delle attività verrà rilasciata in seguito). L'integrazione delle note è disponibile per clienti, fornitori, ordini di vendita e ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="69620-121">(Functionality for activity integration will be released later.) Note integration is available for customers, vendors, sales orders, and purchase orders.</span></span>

## <a name="create-a-note-in-a-customer-engagement-app"></a><span data-ttu-id="69620-122">Creare una nota in un'app di interazione con i clienti</span><span class="sxs-lookup"><span data-stu-id="69620-122">Create a note in a customer engagement app</span></span>

<span data-ttu-id="69620-123">Per creare una nota in un'app di interazione con i clienti e quindi sincronizzarla con un'app Finance and Operations, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="69620-123">To create a note in a customer engagement app and then sync it to a Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="69620-124">Nell'app di interazione con i clienti, aprire il record account per un cliente.</span><span class="sxs-lookup"><span data-stu-id="69620-124">In the customer engagement app, open the account record for a customer.</span></span>
2. <span data-ttu-id="69620-125">Nel riquadro **Sequenza temporale**, selezionare il segno più (**+**), quindi selezionare **Nota** per creare una nota.</span><span class="sxs-lookup"><span data-stu-id="69620-125">In the **Timeline** pane, select the plus sign (**+**), and then select **Note** to create a note.</span></span>

    ![Creare una nota nell'app di interazione con i clienti](media/notes-ce-1.png)

3. <span data-ttu-id="69620-127">Immettere un titolo e una descrizione, quindi selezionare **Aggiungi nota**.</span><span class="sxs-lookup"><span data-stu-id="69620-127">Enter a title and description, and then select **Add note**.</span></span>

    ![Immettere un titolo e una descrizione](media/notes-ce-2.png)

    <span data-ttu-id="69620-129">La nuova nota viene aggiunta alla sequenza temporale del cliente.</span><span class="sxs-lookup"><span data-stu-id="69620-129">The new note is added to the customer timeline.</span></span>

    ![Nuova nota nella sequenza temporale del cliente](media/notes-ce-3.png)

4. <span data-ttu-id="69620-131">Accedere all'app Finance and Operations e aprire lo stesso record cliente.</span><span class="sxs-lookup"><span data-stu-id="69620-131">Sign in to the Finance and Operations app, and open the same customer record.</span></span> <span data-ttu-id="69620-132">Si noti che il pulsante **Allegati** (simbolo della graffetta) nell'angolo in alto a destra indica che il record ha un allegato.</span><span class="sxs-lookup"><span data-stu-id="69620-132">Notice that the **Attachments** button (paperclip symbol) in the upper-right corner indicates that the record has an attachment.</span></span>

    ![Notifica su un allegato](media/notes-ce-4.png)

5. <span data-ttu-id="69620-134">Selezionare il pulsante **Allegati** per aprire la pagina **Allegati**.</span><span class="sxs-lookup"><span data-stu-id="69620-134">Select the **Attachments** button to open the **Attachments** page.</span></span> <span data-ttu-id="69620-135">La nota creata dovrebbe essere nell'app di interazione con i clienti.</span><span class="sxs-lookup"><span data-stu-id="69620-135">You should find the note that you created in the customer engagement app.</span></span>

    ![Nota nell'app di interazione con i clienti](media/notes-ce-5.png)

<span data-ttu-id="69620-137">Tutti gli aggiornamenti della nota vengono sincronizzati tra l'app Finance and Operations e l'app di interazione con i clienti.</span><span class="sxs-lookup"><span data-stu-id="69620-137">Any updates to the note are synced back and forth between the Finance and Operations app and the customer engagement app.</span></span>

## <a name="create-a-note-in-a-finance-and-operations-app"></a><span data-ttu-id="69620-138">Creare una nota in un'app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="69620-138">Create a note in a Finance and Operations app</span></span>

<span data-ttu-id="69620-139">È anche possibile creare una nota in un'app Finance and Operations, che verrà sincronizzata con un'app di interazione con i clienti.</span><span class="sxs-lookup"><span data-stu-id="69620-139">You can also create a note in a Finance and Operations app, and it will be synced to a customer engagement app.</span></span>

<span data-ttu-id="69620-140">Per creare una nota in un'app Finance and Operations e quindi sincronizzarla con un'app di interazione con i clienti, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="69620-140">To create a note in a Finance and Operations app and then sync it to a customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="69620-141">Nell'app Finance and Operations, nella pagina **Allegati**, selezionare **Nuovo** \> **Nota**.</span><span class="sxs-lookup"><span data-stu-id="69620-141">In the Finance and Operations app, on the **Attachments** page, select **New** \> **Note**.</span></span>

    ![Creare una nota nell'app Finance and Operations](media/notes-fo-1.png)

2. <span data-ttu-id="69620-143">Immettere un titolo e una breve serie di istruzioni, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="69620-143">Enter a title and a brief set of instructions, and then select **Save**.</span></span>

    ![Immettere un titolo e istruzioni](media/notes-fo-2.png)

3. <span data-ttu-id="69620-145">Nell'app di di interazione con i clienti, aggiornare il record.</span><span class="sxs-lookup"><span data-stu-id="69620-145">In the customer engagement app, update the record.</span></span> <span data-ttu-id="69620-146">La nuova nota dovrebbe essere nella sequenza temporale.</span><span class="sxs-lookup"><span data-stu-id="69620-146">You should find the new note on the timeline.</span></span>

    ![Nuova nota nella sequenza temporale dell'app di interazione con i clienti](media/notes-fo-3.png)

<span data-ttu-id="69620-148">È possibile classificare una nota come interna o esterna.</span><span class="sxs-lookup"><span data-stu-id="69620-148">You can classify a note as either internal or external.</span></span>

- <span data-ttu-id="69620-149">Nell'app Finance and Operations, nella pagina **Allegati**, aprire la nota e nel campo **Restrizione**, selezionare **Interna** o **Esterna**.</span><span class="sxs-lookup"><span data-stu-id="69620-149">In the Finance and Operations app, on the **Attachments** page, open the note, and then, in the **Restriction** field, select **Internal** or **External**.</span></span>

    ![Campo Restrizione](media/notes-fo-4.png)

<span data-ttu-id="69620-151">È inoltre possibile creare un URL.</span><span class="sxs-lookup"><span data-stu-id="69620-151">You can also create a URL.</span></span>

1. <span data-ttu-id="69620-152">Nell'app Finance and Operations, nella pagina **Allegati**, selezionare **Nuovo** \> **URL**.</span><span class="sxs-lookup"><span data-stu-id="69620-152">In the Finance and Operations app, on the **Attachments** page, select **New** \> **URL**.</span></span>
2. <span data-ttu-id="69620-153">Immettere un titolo e un URL.</span><span class="sxs-lookup"><span data-stu-id="69620-153">Enter a title and the URL.</span></span>
3. <span data-ttu-id="69620-154">Nel campo **Restrizione**, selezionare **Interna** o **Esterna**.</span><span class="sxs-lookup"><span data-stu-id="69620-154">In the **Restriction** field, select **Internal** or **External**.</span></span>

    ![Creare un URL nell'app Finance and Operations](media/notes-fo-5.png)

4. <span data-ttu-id="69620-156">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="69620-156">Select **Save**.</span></span>

    <span data-ttu-id="69620-157">Poiché le app di interazione dei clienti non hanno un tipo di URL, l'URL è integrato con la doppia scrittura come nota.</span><span class="sxs-lookup"><span data-stu-id="69620-157">Because customer engagement apps don't have a URL type, the URL is integrated with dual-write as a note.</span></span>

    ![URL visualizzato come nota nell'app di interazione con i clienti](media/notes-ce-6.png)

> [!NOTE]
> <span data-ttu-id="69620-159">Gli allegati di file non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="69620-159">File attachments aren't supported.</span></span>

## <a name="templates"></a><span data-ttu-id="69620-160">Modelli</span><span class="sxs-lookup"><span data-stu-id="69620-160">Templates</span></span>

<span data-ttu-id="69620-161">L'integrazione delle note include una raccolta di mappe della tabella che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="69620-161">Note integration includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="69620-162">App Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="69620-162">Finance and Operations app</span></span> | <span data-ttu-id="69620-163">App di interazione con i clienti</span><span class="sxs-lookup"><span data-stu-id="69620-163">Customer engagement app</span></span> | <span data-ttu-id="69620-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69620-164">Description</span></span> |
|----------------------------|-------------------------|-------------|
| [<span data-ttu-id="69620-165">Allegati cliente</span><span class="sxs-lookup"><span data-stu-id="69620-165">Customer Attachments</span></span>](mapping-reference.md#230) | <span data-ttu-id="69620-166">Annotazioni</span><span class="sxs-lookup"><span data-stu-id="69620-166">Annotations</span></span> | <span data-ttu-id="69620-167">Aziende che utilizzano testo normale e URL per acquisire informazioni specifiche sui clienti (per le organizzazioni e per le persone).</span><span class="sxs-lookup"><span data-stu-id="69620-167">Businesses that use plain text and URLs to capture customer-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="69620-168">Allegati documento fornitore</span><span class="sxs-lookup"><span data-stu-id="69620-168">Vendor document attachments</span></span>](mapping-reference.md#231) | <span data-ttu-id="69620-169">Annotazioni</span><span class="sxs-lookup"><span data-stu-id="69620-169">Annotations</span></span> | <span data-ttu-id="69620-170">Aziende che utilizzano testo normale e URL per acquisire informazioni specifiche sui fornitori (per le organizzazioni e per le persone).</span><span class="sxs-lookup"><span data-stu-id="69620-170">Businesses that use plain text and URLs to capture vendor-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="69620-171">Allegati documento intestazione ordine cliente</span><span class="sxs-lookup"><span data-stu-id="69620-171">Sales order header document attachments</span></span>](mapping-reference.md#229) | <span data-ttu-id="69620-172">Annotazioni</span><span class="sxs-lookup"><span data-stu-id="69620-172">Annotations</span></span> | <span data-ttu-id="69620-173">Aziende che utilizzano testo normale e URL per acquisire informazioni specifiche sugli ordini di vendita.</span><span class="sxs-lookup"><span data-stu-id="69620-173">Businesses that use plain text and URLs to capture sales order–specific information.</span></span> |
| [<span data-ttu-id="69620-174">Allegati documento intestazione ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="69620-174">Purchase order header document attachments</span></span>](mapping-reference.md#232) | <span data-ttu-id="69620-175">Annotazioni</span><span class="sxs-lookup"><span data-stu-id="69620-175">Annotations</span></span> | <span data-ttu-id="69620-176">Aziende che utilizzano testo normale e URL per acquisire informazioni specifiche sugli ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="69620-176">Businesses that use plain text and URLs to capture purchase order–specific information.</span></span> |

<span data-ttu-id="69620-177">Per ulteriori informazioni, vedere [Riferimento per il mapping a doppia scrittura](mapping-reference.md).</span><span class="sxs-lookup"><span data-stu-id="69620-177">For more information, see [Dual-write mapping reference](mapping-reference.md).</span></span>
