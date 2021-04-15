---
title: Report dei prezzi di vendita al dettaglio
description: In questo argomento viene fornita una panoramica della funzionalità di report dei prezzi che può essere utilizzata per visualizzare le future modifiche dei prezzi per i prodotti assortiti.
author: shajain
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 3e57fd78b3476096100628fe3951f8f9f4e3ac54
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794141"
---
# <a name="retail-price-reports"></a><span data-ttu-id="34f31-103">Report dei prezzi di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="34f31-103">Retail price reports</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="34f31-104">Per fornire prezzi concorrenziali ai clienti, i rivenditori spesso modificano i prezzi dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="34f31-104">In order to provide competitive prices to their customers, retailers often change prices of products.</span></span> <span data-ttu-id="34f31-105">I responsabili punto vendita vogliono avere la possibilità di accedere facilmente alle modifiche recenti o future dei prezzi in modo da poter pianificare le risorse necessarie per aggiornare le etichette dei prezzi visualizzate sugli scaffali del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="34f31-105">Store managers want the ability to easily access recent or upcoming price changes so that they can plan for the required resources to update the price labels displayed on the store shelves.</span></span> <span data-ttu-id="34f31-106">Con Retail versione 10.0, un responsabile punto vendita può aprire il report **Prezzi** accedendo a **Tutti i punti vendita \> Punto vendita \> Report prezzi** e visualizzando i prezzi aggiornati per i prodotti associati al punto vendita.</span><span class="sxs-lookup"><span data-stu-id="34f31-106">With release 10.0 of Retail, a store manager can open the **Price** report by navigating to **All stores \> Store \> Price report** and viewing the updated prices for the products associated to the store.</span></span> 

<span data-ttu-id="34f31-107">Per abilitare il report dei prezzi, il parametro **Abilita report prezzi per punto vendita** deve essere attivato.</span><span class="sxs-lookup"><span data-stu-id="34f31-107">To enable the price report, the **Enable price report for store** parameter must be turned on.</span></span> <span data-ttu-id="34f31-108">Questo parametro si trova nella scheda **Parametri di commercio \> Sconti \> Varie**. L'apertura della pagina **Report prezzi** visualizza una finestra di dialogo con varie configurazioni.</span><span class="sxs-lookup"><span data-stu-id="34f31-108">This parameter is located on the **Commerce parameters \> Discounts \> Miscellaneous** tab. Opening the **Price report** page displays a dialog box with various configurations.</span></span> <span data-ttu-id="34f31-109">Le configurazioni disponibili sono elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="34f31-109">The available configurations are listed below.</span></span>

| <span data-ttu-id="34f31-110">Configurazione</span><span class="sxs-lookup"><span data-stu-id="34f31-110">Configuration</span></span> | <span data-ttu-id="34f31-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34f31-111">Description</span></span> |
|---|---|
| <span data-ttu-id="34f31-112">Dal / Al</span><span class="sxs-lookup"><span data-stu-id="34f31-112">From date / To date</span></span>| <span data-ttu-id="34f31-113">L'intervallo di date per il quale il report dei prezzi deve essere generato.</span><span class="sxs-lookup"><span data-stu-id="34f31-113">The date range for which the price report should be generated.</span></span> <span data-ttu-id="34f31-114">La durata è attualmente limitata a 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="34f31-114">The duration is currently limited to 7 days.</span></span> |
| <span data-ttu-id="34f31-115">Canale</span><span class="sxs-lookup"><span data-stu-id="34f31-115">Channel</span></span>| <span data-ttu-id="34f31-116">Il punto vendita per il quale il report dei prezzi deve essere generato.</span><span class="sxs-lookup"><span data-stu-id="34f31-116">The store for which the price report should be generated.</span></span> |
| <span data-ttu-id="34f31-117">Visualizza prodotti con scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="34f31-117">Display products with available inventory</span></span>| <span data-ttu-id="34f31-118">Impostando questa opzione su **Sì**, verranno visualizzati i prezzi soltanto per i prodotti per i quali l'inventario fisico è disponibile nel punto vendita.</span><span class="sxs-lookup"><span data-stu-id="34f31-118">Setting this to **Yes** will show the prices for only those products which currently have physical inventory available in the store.</span></span> |
| <span data-ttu-id="34f31-119">Visualizza prezzi per varianti</span><span class="sxs-lookup"><span data-stu-id="34f31-119">Display prices for variants</span></span> | <span data-ttu-id="34f31-120">L'impostazione di questa opzione su **Sì** visualizzerà i prezzi delle varianti insieme alle rappresentazioni generali prodotto.</span><span class="sxs-lookup"><span data-stu-id="34f31-120">Setting this to **Yes** will display the prices of the variants along with the product masters.</span></span> <span data-ttu-id="34f31-121">Questa opzione deve essere **attivata** solo se i prezzi sono specifici alle varianti, in quanto il numero di righe diventa molto grande.</span><span class="sxs-lookup"><span data-stu-id="34f31-121">This should only be turned **On** if you have variant-specific prices, because the number of rows grows very large.</span></span> <span data-ttu-id="34f31-122">Nelle versioni future, verranno abilitati i prezzi basati su dimensioni di modo che il responsabile punto vendita possa scegliere le dimensioni per le quali i prezzi devono essere visualizzati.</span><span class="sxs-lookup"><span data-stu-id="34f31-122">In future releases, we will enable the dimensions-based prices so that the store manager can choose the dimensions for which the prices should be displayed.</span></span> |
| <span data-ttu-id="34f31-123">Visualizza prodotti con variazioni di prezzo</span><span class="sxs-lookup"><span data-stu-id="34f31-123">Display products with price changes</span></span> | <span data-ttu-id="34f31-124">L'impostazione di questa opzione su **Sì** visualizzerà i prezzi solo per le date in cui il prezzo è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="34f31-124">Setting this to **Yes** will display the prices for only those dates on which the price has been changed.</span></span> <span data-ttu-id="34f31-125">Il prezzo di *un giorno prima* della **data iniziale** selezionata verrà sempre visualizzato, di modo che il responsabile punto vendita possa facilmente identificare i prodotti senza prezzi modificati per l'intera durata selezionata nonché visualizzare il prezzo corrente.</span><span class="sxs-lookup"><span data-stu-id="34f31-125">The price for *one day before* the selected **From date** will always be displayed, so that the store manager can easily identity the products which have not changed prices for the entire selected duration, and can also view the current price.</span></span> |

<span data-ttu-id="34f31-126">Dopo la generazione del report, il file di Excel può essere scaricato per tutti i requisiti di filtro aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="34f31-126">After the report is generated, the Excel file can be downloaded for any additional filtering needs.</span></span> <span data-ttu-id="34f31-127">Il report dei prezzi può essere utilizzato per verificare i prezzi storici dei prodotti per le date passate.</span><span class="sxs-lookup"><span data-stu-id="34f31-127">The price report can also be used to check the historical prices of products for past dates.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]