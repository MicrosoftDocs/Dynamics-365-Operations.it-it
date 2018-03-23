---
title: Panoramica dei suggerimenti sul prodotto personalizzati
description: In questo argomento vengono fornite informazioni sui suggerimenti sul prodotto di Dynamics 365 for Retail visualizzabili nel dispositivo POS.
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: c5b9ee57b0b855766628caca239059205c103b86
ms.openlocfilehash: 4a0586324dddc10d64ad6760222f2540f31d6bce
ms.contentlocale: it-it
ms.lasthandoff: 03/08/2018

---

# <a name="personalized-product-recommendations-overview"></a><span data-ttu-id="f828a-103">Panoramica dei suggerimenti sul prodotto personalizzati</span><span class="sxs-lookup"><span data-stu-id="f828a-103">Personalized product recommendations overview</span></span>

[!include[banner](includes/banner.md)]


> [!NOTE]
> <span data-ttu-id="f828a-104">Durante la nuova progettazione della funzionalità del servizio di suggerimenti prodotto con un algoritmo migliore e nuove funzionalità orientate alla vendita al dettaglio, verrà rimossa la versione corrente di tale servizio.</span><span class="sxs-lookup"><span data-stu-id="f828a-104">We are removing the current version of the product recommendation service as we redesign this feature with a better algorithm and newer retail-oriented capabilities.</span></span> <span data-ttu-id="f828a-105">Per ulteriori informazioni vedere [Funzionalità rimosse o deprecate](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span><span class="sxs-lookup"><span data-stu-id="f828a-105">For more information see [Removed or deprecated features](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span></span> <span data-ttu-id="f828a-106">Passare alla parte inferiore della pagina se si riscontrano problemi con suggerimenti sul prodotto già abilitati per l'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="f828a-106">Navigate to the bottom of the page if you are facing issues with already-enabled product recommendations for your environment.</span></span> 

<span data-ttu-id="f828a-107">In Dynamics 365 for Retail, i suggerimenti d prodotti possono essere visualizzati nel dispositivo POS.</span><span class="sxs-lookup"><span data-stu-id="f828a-107">In Dynamics 365 for Retail, product recommendations can be displayed on the point of sale (POS) device.</span></span> <span data-ttu-id="f828a-108">I suggerimenti sono articoli a cui il cliente potrebbe essere interessato in base al relativo storico acquisti, articoli nell'elenco preferenze e che altri clienti hanno acquistato online e in punti vendita fisici.</span><span class="sxs-lookup"><span data-stu-id="f828a-108">The recommendations are items that the customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="f828a-109">Per i rivenditori con cataloghi di grandi dimensioni, i suggerimenti aiutano il cliente a individuare i prodotti.</span><span class="sxs-lookup"><span data-stu-id="f828a-109">For retailers with large catalogs, recommendations help the customer with product discovery.</span></span> <span data-ttu-id="f828a-110">Mostrando i prodotti mirati agli interessi e alle abitudini di acquisto di un cliente, i suggerimenti sul prodotto possono aiutare i rivenditori con l'upselling e il cross-selling e possono aumentare la ritenuta cliente.</span><span class="sxs-lookup"><span data-stu-id="f828a-110">By showcasing products targeted to a customer’s interests and buying habits, product recommendations can help retailers with up-sell and cross-sell, and can enhance customer retention.</span></span> <span data-ttu-id="f828a-111">In Dynamics 365 for Retail i suggerimenti sul prodotto sono generati da servizi cognitivi e da Microsoft Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="f828a-111">In Dynamics 365 for Retail, product recommendations are powered by cognitive services and Microsoft Azure machine learning.</span></span>


<a name="scenarios"></a><span data-ttu-id="f828a-112">Scenari</span><span class="sxs-lookup"><span data-stu-id="f828a-112">Scenarios</span></span>
---------

<span data-ttu-id="f828a-113">I suggerimenti sul prodotto sono abilitati per i seguenti scenari di POS.</span><span class="sxs-lookup"><span data-stu-id="f828a-113">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="f828a-114">Sono disponibili in Cloud POS o Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="f828a-114">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1.  <span data-ttu-id="f828a-115">Nella pagina **Dettagli prodotto**:</span><span class="sxs-lookup"><span data-stu-id="f828a-115">On the **Product details** page:</span></span>

-   <span data-ttu-id="f828a-116">Se un associato del punto vendita visita una pagina **Dettagli prodotto** quando visualizza le transazioni precedenti su più canali diversi, il motore dei suggerimenti suggerisce articoli aggiuntivi che è probabile vengano acquistati insieme.</span><span class="sxs-lookup"><span data-stu-id="f828a-116">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendation engine suggests additional items that are likely to be purchased together.</span></span>
-   <span data-ttu-id="f828a-117">Se l'associato del punto vendita aggiunge un cliente alla transazione e quindi visita una pagina **Dettagli prodotto**, il motore dei suggerimenti fornisce suggerimenti personalizzati utilizzando lo storico transazioni del cliente.</span><span class="sxs-lookup"><span data-stu-id="f828a-117">If the store associate adds a customer to the transaction and then visits a **Product details** page, the recommendation engine provides personalized recommendations using the customer's transaction history.</span></span>

<span data-ttu-id="f828a-118">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="f828a-118">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span></span>

2.  <span data-ttu-id="f828a-119">Nella pagina **Transazione**:</span><span class="sxs-lookup"><span data-stu-id="f828a-119">On the **Transaction** page:</span></span>

-   <span data-ttu-id="f828a-120">Il motore dei suggerimenti suggerisce articoli in base all'intero elenco di articoli nel carrello.</span><span class="sxs-lookup"><span data-stu-id="f828a-120">The recommendation engine suggests items based on the entire list of items in the basket.</span></span>
-   <span data-ttu-id="f828a-121">Se l'associato del punto vendita aggiunge un cliente alla transazione, il motore dei suggerimenti fornisce suggerimenti personalizzati utilizzando lo storico transazioni del cliente e l'elenco di articoli nel carrello.</span><span class="sxs-lookup"><span data-stu-id="f828a-121">If the store associate adds a customer to the transaction, the recommendation engine provides personal recommendations using the customer’s transaction history and the list of items in the basket.</span></span>

> [!NOTE]
> <span data-ttu-id="f828a-122">Per visualizzare i suggerimenti nella pagina **Transazione**, il rivenditore deve aggiornare il layout dello schermo in Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="f828a-122">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="f828a-123">Il controllo **Suggerimenti** deve essere rilasciato nella pagina **Transazione**.</span><span class="sxs-lookup"><span data-stu-id="f828a-123">The **Recommendations** control must be dropped on to the **Transaction** page.</span></span> <span data-ttu-id="f828a-124">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="f828a-124">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

3.  <span data-ttu-id="f828a-125">Nella pagina **Dettagli cliente**:</span><span class="sxs-lookup"><span data-stu-id="f828a-125">On the **Customer details** page:</span></span>
    -   <span data-ttu-id="f828a-126">Il motore dei suggerimenti suggerisce articoli in base all'ID utente e articoli nell'elenco preferenze del cliente.</span><span class="sxs-lookup"><span data-stu-id="f828a-126">The recommendation engine suggests items based on the user ID and items in the customer’s wish list.</span></span>

<span data-ttu-id="f828a-127">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span><span class="sxs-lookup"><span data-stu-id="f828a-127">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span></span>

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a><span data-ttu-id="f828a-128">Configurare Dynamics 365 for Retail per abilitare i suggerimenti POS</span><span class="sxs-lookup"><span data-stu-id="f828a-128">Configure Dynamics 365 for Retail to enable POS recommendations</span></span>
<span data-ttu-id="f828a-129">Per impostare i suggerimenti sul prodotto, è necessario effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="f828a-129">To set up product recommendations, you need to do the following.</span></span>

1.  <span data-ttu-id="f828a-130">Assicurarsi di aver selezionato la **Persona giuridica** corretta.</span><span class="sxs-lookup"><span data-stu-id="f828a-130">Make sure that you have selected the correct **Legal entity**.</span></span>
2.  <span data-ttu-id="f828a-131">Accedere a **Archivio entità**, selezionare **Vendite al dettaglio**, quindi fare clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="f828a-131">Navigate to **Entity store**, select **Retail sales**, and then click **Refresh**.</span></span> <span data-ttu-id="f828a-132">Verranno utilizzati i dati dimostrativi (o i dati dell'utente) provenienti dal database operativo che verranno spostati nell'Archivio entità.</span><span class="sxs-lookup"><span data-stu-id="f828a-132">This will use the demo data (or your data) from your operational database and move it to Entity store.</span></span>
3.  <span data-ttu-id="f828a-133">Facoltativo: per visualizzare i suggerimenti sulla schermata della transazione, passare a **Layout schermo**, scegliere il layout dello schermo, avviare **Progettazione layout schermo**, quindi rilasciare il controllo **suggerimenti** dove necessario.</span><span class="sxs-lookup"><span data-stu-id="f828a-133">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>

4.  <span data-ttu-id="f828a-134">Passare a **Parametri di vendita al dettaglio**, selezionare **Machine learning**, quindi scegliere **Sì** in **Abilita suggerimenti POS**.</span><span class="sxs-lookup"><span data-stu-id="f828a-134">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5.  <span data-ttu-id="f828a-135">Per visualizzare i suggerimenti sul POS, eseguire il processo di configurazione globale **1110**.</span><span class="sxs-lookup"><span data-stu-id="f828a-135">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="f828a-136">Per riflettere le modifiche apportate a Progettazione layout schermo POS, eseguire il processo di configurazione dei canali **1070**.</span><span class="sxs-lookup"><span data-stu-id="f828a-136">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="f828a-137">[]()Come funziona?</span><span class="sxs-lookup"><span data-stu-id="f828a-137">[]()How does it work?</span></span>
<span data-ttu-id="f828a-138">Quando si aggiorna l'entità **Archivio entità**, verranno effettuate le azioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f828a-138">When you refresh the **Entity store** entity, the following actions take place.</span></span>

-   <span data-ttu-id="f828a-139">I dati nel formato richiesto dai servizi cognitivi vengono estratti dal database operativo Dynamics 365 for Retail e vengono inviati all'Archivio entità.</span><span class="sxs-lookup"><span data-stu-id="f828a-139">Data in the format required by the Cognitive services is extracted from the Dynamics 365 for Retail operational database and sent to the Entity store.</span></span>
-   <span data-ttu-id="f828a-140">I dati vengono utilizzati da Azure Data Factory (ADF) per eseguire la pulitura dei dati tramite gli script Hive come parte delle attività ADF.</span><span class="sxs-lookup"><span data-stu-id="f828a-140">The data is used by Azure Data Factory (ADF) to cleanse the data using Hive scripts as part of ADF activities.</span></span> <span data-ttu-id="f828a-141">I dati puliti vengono archiviati nell'archiviazione BLOB.</span><span class="sxs-lookup"><span data-stu-id="f828a-141">Cleansed data is stored in blob storage.</span></span>
-   <span data-ttu-id="f828a-142">I dati nell'archiviazione BLOB vengono utilizzati dall'API dei servizi cognitivi per preparare un modello di suggerimento.</span><span class="sxs-lookup"><span data-stu-id="f828a-142">Data from blob storage is used by the Cognitive services API to train a recommendation model.</span></span>

<span data-ttu-id="f828a-143">Quando si attiva **Abilita suggerimenti** e si eseguono i processi di configurazione, verranno effettuate le azioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f828a-143">When you turn on **Enable recommendations** and run the configuration jobs, the following actions take place.</span></span>

-   <span data-ttu-id="f828a-144">L'ID e le credenziali di modello vengono recuperate dall'API e archiviate nel database operativo di Dynamics 365 for Retail, nel file web.config per AOS e nel server vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f828a-144">Model credentials and ID are picked up from the API and stored in the Dynamics 365 for Retail operational database, in the web.config for AOS, and also in the retail server.</span></span>
-   <span data-ttu-id="f828a-145">L'ID e le credenziali del modello vengono rese disponibili a CRT in modo da poter soddisfare le richieste di suggerimenti sul prodotto da Cloud POS e MPOS in modalità online.</span><span class="sxs-lookup"><span data-stu-id="f828a-145">Model credentials and ID are made available to CRT so that calls for product recommendations from Cloud POS and MPOS in online mode can be honored.</span></span>

> ## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a><span data-ttu-id="f828a-146">Risolvere i problemi in caso di suggerimenti sul prodotto già abilitati</span><span class="sxs-lookup"><span data-stu-id="f828a-146">Troubleshoot issues where you have Product recommendations already enabled</span></span> 
>- <span data-ttu-id="f828a-147">Passare a **Parametri di vendita al dettaglio** > **Machine Learning** > **Disabilita suggerimenti sul prodotto** ed eseguire il **Processo di configurazione globale [1110]**.</span><span class="sxs-lookup"><span data-stu-id="f828a-147">Navigate to **Retail Parameters** > **Machine learning** > **Disable product recommendations** and run **Global configuration job [1110]**.</span></span> <span data-ttu-id="f828a-148">Se non è possibile individuare la scheda **Machine Learning**, contattare il supporto Dynamics.</span><span class="sxs-lookup"><span data-stu-id="f828a-148">If you are not able to locate **Machine learning** tab, please contact Dynamics Support.</span></span> 

>- <span data-ttu-id="f828a-149">Se si è aggiunto il **Controllo per suggerimenti** alla schermata di transazione mediante la **Progettazione layout schermo**, rimuovere anche tale elemento.</span><span class="sxs-lookup"><span data-stu-id="f828a-149">If you added the **Recommendations control** to your transaction screen using the **Screen layout designer**, please remove that as well.</span></span> 



<a name="see-also"></a><span data-ttu-id="f828a-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f828a-150">See also</span></span>
--------

[<span data-ttu-id="f828a-151">Aggiungere un controllo di suggerimenti alla pagina della transazione su un dispositivo POS</span><span class="sxs-lookup"><span data-stu-id="f828a-151">Add a recommendations control to the transaction page on a POS device</span></span>](add-recommendations-control-pos-screen.md)




