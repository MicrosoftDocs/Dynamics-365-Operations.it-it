---
title: Suggerimenti sul prodotto nel dispositivo POS
description: In questo argomento viene descritto l'utilizzo dei suggerimenti sul prodotto in un dispositivo POS .
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
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
ms.openlocfilehash: 98c84e987c40adf136d0240117f7b0f119bf2f59
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811119"
---
# <a name="product-recommendations-on-pos"></a><span data-ttu-id="21843-103">Suggerimenti sul prodotto nel dispositivo POS</span><span class="sxs-lookup"><span data-stu-id="21843-103">Product recommendations on POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="21843-104">Fondamentalmente, i suggerimenti sul prodotto sono un'applicazione aziendale trasformativa che si estende su tutte le aree commerciali per creare esperienze di scoperta di prodotti ricchi, coinvolgenti e personalizzati.</span><span class="sxs-lookup"><span data-stu-id="21843-104">At its core, product Recommendations are a transformative business application that span across all retail spaces to create rich, engaging, and tailored product discovery experiences.</span></span> <span data-ttu-id="21843-105">Per implementare questa funzionalità sul POS, seguire i passaggi in [come aggiungere i suggerimenti si dispositivi POS.](add-recommendations-control-pos-screen.md)</span><span class="sxs-lookup"><span data-stu-id="21843-105">To implement this feature on POS, follow the steps on [how to add recommendations to your POS devices.](add-recommendations-control-pos-screen.md)</span></span> 

<span data-ttu-id="21843-106">Per ulteriori informazioni sulle funzionalità di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto.](../commerce/product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="21843-106">For more information about product recommendations features, read the [product recommendations overview.](../commerce/product-recommendations.md)</span></span> 

## <a name="scenarios"></a><span data-ttu-id="21843-107">Scenari</span><span class="sxs-lookup"><span data-stu-id="21843-107">Scenarios</span></span>

<span data-ttu-id="21843-108">I suggerimenti sul prodotto sono abilitati per i seguenti scenari di POS.</span><span class="sxs-lookup"><span data-stu-id="21843-108">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="21843-109">Sono disponibili in Cloud POS o Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="21843-109">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1. <span data-ttu-id="21843-110">Nella pagina **Dettagli prodotto**:</span><span class="sxs-lookup"><span data-stu-id="21843-110">On the **Product details** page:</span></span>

    - <span data-ttu-id="21843-111">Se un associato del punto vendita visita una pagina **Dettagli prodotto** quando visualizza le transazioni precedenti su più canali diversi, il servizio dei suggerimenti suggerisce articoli aggiuntivi che è probabile vengano acquistati insieme.</span><span class="sxs-lookup"><span data-stu-id="21843-111">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendations service suggests additional items that are likely to be purchased together.</span></span>

    <span data-ttu-id="21843-112">[![Suggerimenti sulla pagina Dettagli prodotto](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="21843-112">[![Recommendations on the Product details page](./media/proddetails.png)](./media/proddetails.png)</span></span>

2. <span data-ttu-id="21843-113">Nella pagina **Transazione**:</span><span class="sxs-lookup"><span data-stu-id="21843-113">On the **Transaction** page:</span></span>

    - <span data-ttu-id="21843-114">Il motore dei suggerimenti suggerisce gli articoli in base all'intero elenco di articoli nel carrello che vengono acquistati insieme di frequente.</span><span class="sxs-lookup"><span data-stu-id="21843-114">The recommendation engine suggests items based on the entire list of items in the basket that are frequently bought together.</span></span>

    > [!NOTE]
    > <span data-ttu-id="21843-115">Per visualizzare i suggerimenti nella pagina **Transazione**, il rivenditore deve aggiornare il layout dello schermo in Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="21843-115">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="21843-116">Il controllo **Suggerimenti** deve essere rilasciato nella pagina **Transazione**.</span><span class="sxs-lookup"><span data-stu-id="21843-116">The **Recommendations** control must be dropped onto the **Transaction** page.</span></span>

    <span data-ttu-id="21843-117">[![Suggerimenti nella pagina Transazione](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="21843-117">[![Recommendations on the Transaction page](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

## <a name="configure-dynamics-365-retail-to-enable-pos-recommendations"></a><span data-ttu-id="21843-118">Configurare Dynamics 365 Retail per abilitare i suggerimenti POS</span><span class="sxs-lookup"><span data-stu-id="21843-118">Configure Dynamics 365 Retail to enable POS recommendations</span></span>

<span data-ttu-id="21843-119">Per impostare i suggerimenti sul prodotto, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="21843-119">To set up product recommendations, follow these steps:</span></span>

1. <span data-ttu-id="21843-120">Verificare che il servizio sia stato aggiornato alla **build 10.0.6.**</span><span class="sxs-lookup"><span data-stu-id="21843-120">Ensure your service has been updated to the **10.0.6 build.**</span></span>
2. <span data-ttu-id="21843-121">Seguire le istruzioni su come [abilitare i suggerimenti sul prodotto](../commerce/enable-product-recommendations.md) per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="21843-121">Follow the instructions on how to [enable product recommendations](../commerce/enable-product-recommendations.md) for your business.</span></span>
3. <span data-ttu-id="21843-122">Facoltativo: per visualizzare i suggerimenti sulla schermata della transazione, passare a **Layout schermo**, scegliere il layout dello schermo, avviare **Progettazione layout schermo**, quindi rilasciare il controllo **suggerimenti** dove necessario.</span><span class="sxs-lookup"><span data-stu-id="21843-122">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>
4. <span data-ttu-id="21843-123">Passare a **Parametri di vendita al dettaglio**, selezionare **Machine learning**, quindi scegliere **Sì** in **Abilita suggerimenti POS**.</span><span class="sxs-lookup"><span data-stu-id="21843-123">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5. <span data-ttu-id="21843-124">Per visualizzare i suggerimenti sul POS, eseguire il processo di configurazione globale **1110**.</span><span class="sxs-lookup"><span data-stu-id="21843-124">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="21843-125">Per riflettere le modifiche apportate a Progettazione layout schermo POS, eseguire il processo di configurazione dei canali **1070**.</span><span class="sxs-lookup"><span data-stu-id="21843-125">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>



## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a><span data-ttu-id="21843-126">Risolvere i problemi in caso di suggerimenti sul prodotto già abilitati</span><span class="sxs-lookup"><span data-stu-id="21843-126">Troubleshoot issues where you have Product recommendations already enabled</span></span>

- <span data-ttu-id="21843-127">Passare a **Parametri di vendita al dettaglio** \> **Elenchi di suggerimenti** \> **Disabilita suggerimenti sul prodotto** ed eseguire il **Processo di configurazione globale \[9999\]**.</span><span class="sxs-lookup"><span data-stu-id="21843-127">Navigate to **Retail Parameters** \> **Recommendation lists** \> **Disable product recommendations** and run **Global configuration job \[9999\]**.</span></span> 
- <span data-ttu-id="21843-128">Se si è aggiunto il **Controllo per suggerimenti** alla schermata di transazione mediante la **Progettazione layout schermo**, rimuovere anche tale elemento.</span><span class="sxs-lookup"><span data-stu-id="21843-128">If you added the **Recommendations control** to your transaction screen using the **Screen layout designer**, please remove that as well.</span></span>
- <span data-ttu-id="21843-129">Per eventuali domande aggiuntive, leggere le [domande frequenti su suggerimenti prodotto](../commerce/faq-recommendations.md) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="21843-129">If you have additional questions, check out the [Product recommendations FAQ](../commerce/faq-recommendations.md) for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="21843-130">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="21843-130">Additional resources</span></span>

[<span data-ttu-id="21843-131">Aggiungere un controllo di suggerimenti alla schermata della transazione su dispositivi POS</span><span class="sxs-lookup"><span data-stu-id="21843-131">Add a recommendations control to the transaction screen on POS devices</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="21843-132">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="21843-132">Product recommendations overview</span></span>](../commerce/product-recommendations.md)

[<span data-ttu-id="21843-133">Abilitare suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="21843-133">Enable product recommendations</span></span>](../commerce/enable-product-recommendations.md) 
