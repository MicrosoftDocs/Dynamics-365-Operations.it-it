---
title: Modulo contenitore
description: In questo argomento vengono descritti i moduli contenitore e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 22a09b61fbe3bd1cca96011d3fb81a12ef1bc844
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697062"
---
# <a name="container-module"></a><span data-ttu-id="25788-103">Modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="25788-103">Container module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="25788-104">In questo argomento vengono descritti i moduli contenitore e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="25788-104">This topic covers container modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="25788-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="25788-105">Overview</span></span>

<span data-ttu-id="25788-106">Un modulo contenitore è un modulo che include altri moduli.</span><span class="sxs-lookup"><span data-stu-id="25788-106">A container module is a module that hosts other modules inside it.</span></span> <span data-ttu-id="25788-107">Si tratta del contenitore più generico utilizzato in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="25788-107">It's the most generic container that is used in Dynamics 365 Commerce.</span></span> <span data-ttu-id="25788-108">Lo scopo principale di un modulo contenitore è definire, mediante le proprietà impostate per lo stesso, il layout dei moduli che include.</span><span class="sxs-lookup"><span data-stu-id="25788-108">The primary purpose of a container module is to define, through the properties that are set for it, the layout of the modules that are inside.</span></span> <span data-ttu-id="25788-109">Ad esempio, tali moduli possono apparire affiancati in un layout a due, tre, quattro o sei colonne.</span><span class="sxs-lookup"><span data-stu-id="25788-109">For example, those modules can appear side by side in a two-column, three-column, four-column, or six-column layout.</span></span> <span data-ttu-id="25788-110">Possono anche essere limitati alla larghezza del contenitore, oppure riempire tutto lo schermo.</span><span class="sxs-lookup"><span data-stu-id="25788-110">They can also be limited to width of the container, or they can fill the screen.</span></span> <span data-ttu-id="25788-111">Un'intestazione può inoltre essere aggiunta a ogni modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="25788-111">A heading can also be added to every container module.</span></span>

<span data-ttu-id="25788-112">Sono disponibili tre tipi standard di moduli contenitore: contenitore, contenitore con 2 slot e contenitore con 3 slot.</span><span class="sxs-lookup"><span data-stu-id="25788-112">There are three standard types of container modules: container, container with 2-slots, and container with 3-slots.</span></span> <span data-ttu-id="25788-113">Questi contenitori possono includere moduli di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="25788-113">Modules of any type of module can be put inside these containers.</span></span> <span data-ttu-id="25788-114">Vi sono inoltre tipi speciali di moduli contenitore, ad esempio Sequenza, Blocco ricco di contenuti, Posizionamento contenuti, Carrello, Checkout, Casella acquisti, Intestazione e Piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="25788-114">There are also special types of container modules, such as carousel, content rich block, content placement, cart, checkout, buy box, header, and footer.</span></span> <span data-ttu-id="25788-115">Questi contenitori hanno scopi specifici e possono includere solo specifici tipi di moduli supportati.</span><span class="sxs-lookup"><span data-stu-id="25788-115">These containers have specific purposes, and only specific supported types of modules can be put inside them.</span></span>

<span data-ttu-id="25788-116">Si consiglia di includere moduli in un contenitore, di modo che possano essere limitati alla larghezza del contenitore.</span><span class="sxs-lookup"><span data-stu-id="25788-116">We recommend that you put modules inside a container, so that they can be limited to the width of the container.</span></span>

## <a name="examples-of-container-modules-in-e-commerce"></a><span data-ttu-id="25788-117">Esempi di moduli contenitore in e-Commerce</span><span class="sxs-lookup"><span data-stu-id="25788-117">Examples of container modules in e-Commerce</span></span>

- <span data-ttu-id="25788-118">Un autore di siti desidera un layout a tre colonne, in cui tre moduli appaiono affiancati.</span><span class="sxs-lookup"><span data-stu-id="25788-118">A site author wants a three-column layout, where three modules appear side by side.</span></span> <span data-ttu-id="25788-119">Di conseguenza, l'autore utilizza un modulo contenitore del contenitore con un tipo a 3 slot.</span><span class="sxs-lookup"><span data-stu-id="25788-119">Therefore, the site author uses a container module of the container with 3-slots type.</span></span>
- <span data-ttu-id="25788-120">Un autore di siti desidera un layout a sei colonne, in cui sei moduli appaiono affiancati.</span><span class="sxs-lookup"><span data-stu-id="25788-120">A site author wants a six-column layout, where six modules appear side by side.</span></span> <span data-ttu-id="25788-121">Di conseguenza, l'autore utilizza un contenitore del tipo con sei colonne.</span><span class="sxs-lookup"><span data-stu-id="25788-121">Therefore, the site author uses a container of the contain type that has six columns inside it.</span></span>
- <span data-ttu-id="25788-122">Un autore di siti desidera includere un modulo in una pagina che non deve essere visualizzato a schermo intero.</span><span class="sxs-lookup"><span data-stu-id="25788-122">A site author wants to put a module on a page but doesn't want it to fill the screen.</span></span> <span data-ttu-id="25788-123">Di conseguenza, l'autore aggiunge il modulo a un modulo contenitore e imposta la proprietà **Larghezza** del contenitore su **Adatta a contenitore**.</span><span class="sxs-lookup"><span data-stu-id="25788-123">Therefore, the site author adds the module to a container module and sets the container's **Width** property to **Fit container**.</span></span>

## <a name="container-module-properties"></a><span data-ttu-id="25788-124">Proprietà del modulo contenitore</span><span class="sxs-lookup"><span data-stu-id="25788-124">Container module properties</span></span>

| <span data-ttu-id="25788-125">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="25788-125">Property name</span></span>     | <span data-ttu-id="25788-126">Valori</span><span class="sxs-lookup"><span data-stu-id="25788-126">Values</span></span> | <span data-ttu-id="25788-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25788-127">Description</span></span> |
|-------------------|--------|-------------|
| <span data-ttu-id="25788-128">Intestazione</span><span class="sxs-lookup"><span data-stu-id="25788-128">Heading</span></span>           | <span data-ttu-id="25788-129">Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**),</span><span class="sxs-lookup"><span data-stu-id="25788-129">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="25788-130">Un'intestazione facoltativa può essere fornita per il contenitore.</span><span class="sxs-lookup"><span data-stu-id="25788-130">An optional heading can be provided for the container.</span></span> <span data-ttu-id="25788-131">Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione.</span><span class="sxs-lookup"><span data-stu-id="25788-131">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="25788-132">Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="25788-132">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="25788-133">Larghezza</span><span class="sxs-lookup"><span data-stu-id="25788-133">Width</span></span>             | <span data-ttu-id="25788-134">**Adatta a contenitore** o **Riempi schermo**</span><span class="sxs-lookup"><span data-stu-id="25788-134">**Fit container** or **Fill screen**</span></span> | <span data-ttu-id="25788-135">Se il valore è **Adatta a contenitore** (il valore predefinito), i moduli nel contenitore sono limitati alla larghezza del contenitore.</span><span class="sxs-lookup"><span data-stu-id="25788-135">If the value is set to **Fit container** (the default value), the modules inside the container are limited to the width of the container.</span></span> <span data-ttu-id="25788-136">Se il valore impostato è **Riempi schermo**, i moduli non sono limitati alla larghezza del contenitore ma possono essere visualizzati in modalità a schermo intero.</span><span class="sxs-lookup"><span data-stu-id="25788-136">If the value is set to **Fill screen**, the modules aren't limited to the container width but can fill the screen.</span></span> |
| <span data-ttu-id="25788-137">Numero di colonne</span><span class="sxs-lookup"><span data-stu-id="25788-137">Number of columns</span></span> | <span data-ttu-id="25788-138">**1**, **2**, **3**, **4**, **6** o **12**</span><span class="sxs-lookup"><span data-stu-id="25788-138">**1**, **2**, **3**, **4**, **6**, or **12**</span></span> | <span data-ttu-id="25788-139">Questa proprietà definisce il numero di colonne nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="25788-139">This property defines the number of columns in the container.</span></span> <span data-ttu-id="25788-140">Un contenitore può avere fino a 12 colonne.</span><span class="sxs-lookup"><span data-stu-id="25788-140">A container can have up to 12 columns.</span></span> |

## <a name="container-with-2-slots"></a><span data-ttu-id="25788-141">Contenitore con 2 slot</span><span class="sxs-lookup"><span data-stu-id="25788-141">Container with 2-slots</span></span>

<span data-ttu-id="25788-142">Il contenitore con un tipo a 2 slot è ottimizzato per un layout a due colonne.</span><span class="sxs-lookup"><span data-stu-id="25788-142">The container with 2-slots type is optimized for a two-column layout.</span></span> <span data-ttu-id="25788-143">Questo tipo di contenitore dispone di due slot per consentire una visualizzazione affiancata dei moduli che include.</span><span class="sxs-lookup"><span data-stu-id="25788-143">This type of container has two slots to allow for a side-by-side view of the modules that are inside.</span></span>

<span data-ttu-id="25788-144">Ulteriori proprietà possono essere utilizzate per ottimizzare il layout per differenti porte di visualizzazione (dispositivi mobili, tablet, computer e così via).</span><span class="sxs-lookup"><span data-stu-id="25788-144">Additional properties can be used to optimize the layout for different view ports (mobile devices, tablets, computers, and so on).</span></span> <span data-ttu-id="25788-145">Per ogni porta di visualizzazione, è possibile definire la larghezza di ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="25788-145">For every view port, the width of each column can be defined.</span></span> <span data-ttu-id="25788-146">Le seguenti impostazioni sono disponibili per la larghezza di colonna:</span><span class="sxs-lookup"><span data-stu-id="25788-146">The following column width settings are available:</span></span>

- <span data-ttu-id="25788-147">**75%/25%** - Il primo modulo ha una larghezza di colonna del 75% e il secondo modulo ha una larghezza di colonna del 25%.</span><span class="sxs-lookup"><span data-stu-id="25788-147">**75%/25%** – The first module has a column width of 75 percent, and the second module has a column width of 25 percent.</span></span> <span data-ttu-id="25788-148">È inoltre disponibile un'opzione **25%/75%**.</span><span class="sxs-lookup"><span data-stu-id="25788-148">A **25%/75%** option is also available.</span></span>
- <span data-ttu-id="25788-149">**50%/50%** - Entrambi i moduli hanno una larghezza di colonna uguale.</span><span class="sxs-lookup"><span data-stu-id="25788-149">**50%/50%** – Both modules have equal column width.</span></span>
- <span data-ttu-id="25788-150">**67%/33%** - Il primo modulo ha una larghezza di colonna del 67% e il secondo modulo ha una larghezza di colonna del 33%.</span><span class="sxs-lookup"><span data-stu-id="25788-150">**67%/33%** – The first module has a column width of 67 percent, and the second module has a column width of 33 percent.</span></span> <span data-ttu-id="25788-151">È inoltre disponibile un'opzione **33%/67%**.</span><span class="sxs-lookup"><span data-stu-id="25788-151">A **33%/67%** option is also available.</span></span>
- <span data-ttu-id="25788-152">**100%** - Entrambi i moduli hanno una larghezza di colonna del 100%.</span><span class="sxs-lookup"><span data-stu-id="25788-152">**100%** – Both modules have a full-column width.</span></span> <span data-ttu-id="25788-153">Di conseguenza, i moduli sono impilati verticalmente in una singola colonna.</span><span class="sxs-lookup"><span data-stu-id="25788-153">Therefore, the modules are vertically stacked in a single column.</span></span> <span data-ttu-id="25788-154">Sebbene questo layout a singola colonna non rientra nell'ambito del contenitore con il tipo a 2 slot, potrebbe essere preferibile per alcune porte di visualizzazione (ad esempio porte di visualizzazione molto piccole come i dispositivi mobili).</span><span class="sxs-lookup"><span data-stu-id="25788-154">Although this single-column layout goes against intent of the container with 2-slots type, it might be preferable for some view ports (for example, extra-small view ports such as mobile devices).</span></span>

### <a name="container-with-2-slots-properties"></a><span data-ttu-id="25788-155">Proprietà del contenitore con 2 slot</span><span class="sxs-lookup"><span data-stu-id="25788-155">Container with 2-slots properties</span></span>

| <span data-ttu-id="25788-156">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="25788-156">Property name</span></span>                   | <span data-ttu-id="25788-157">Valori</span><span class="sxs-lookup"><span data-stu-id="25788-157">Values</span></span> | <span data-ttu-id="25788-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25788-158">Description</span></span> |
|---------------------------------|--------|-------------|
| <span data-ttu-id="25788-159">Intestazione</span><span class="sxs-lookup"><span data-stu-id="25788-159">Heading</span></span>                         | <span data-ttu-id="25788-160">Testo e tag di intestazione</span><span class="sxs-lookup"><span data-stu-id="25788-160">Heading text and heading tag</span></span> | <span data-ttu-id="25788-161">Un'intestazione facoltativa può essere fornita per il contenitore.</span><span class="sxs-lookup"><span data-stu-id="25788-161">An optional can be provided for the container.</span></span> |
| <span data-ttu-id="25788-162">Configurazione per porte di visualizzazione molto piccole</span><span class="sxs-lookup"><span data-stu-id="25788-162">X-Small view port configuration</span></span> | <span data-ttu-id="25788-163">**25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** o **100%**</span><span class="sxs-lookup"><span data-stu-id="25788-163">**25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%**, or **100%**</span></span> | <span data-ttu-id="25788-164">Questa proprietà definisce il layout per le porte di visualizzazione molto piccole.</span><span class="sxs-lookup"><span data-stu-id="25788-164">This property defines the layout for extra-small view ports.</span></span> |
| <span data-ttu-id="25788-165">Configurazione per porte di visualizzazione molto piccole</span><span class="sxs-lookup"><span data-stu-id="25788-165">Small view port configuration</span></span>   | <span data-ttu-id="25788-166">**25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** o **100%**</span><span class="sxs-lookup"><span data-stu-id="25788-166">**25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%**, or **100%**</span></span> | <span data-ttu-id="25788-167">Questa proprietà definisce il layout per le porte di visualizzazione molto piccole come i dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="25788-167">This property defines the layout for small view ports, such as mobile devices.</span></span> |
| <span data-ttu-id="25788-168">Configurazione per porte di visualizzazione medie</span><span class="sxs-lookup"><span data-stu-id="25788-168">Medium view port configuration</span></span>  | <span data-ttu-id="25788-169">**25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** o **100%**</span><span class="sxs-lookup"><span data-stu-id="25788-169">**25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%**, or **100%**</span></span> | <span data-ttu-id="25788-170">Questa proprietà definisce il layout per le porte di visualizzazione medie come i tablet.</span><span class="sxs-lookup"><span data-stu-id="25788-170">This property defines the layout for medium view ports, such as tablets.</span></span> |
| <span data-ttu-id="25788-171">Configurazione per porte di visualizzazione grandi</span><span class="sxs-lookup"><span data-stu-id="25788-171">Large view port configuration</span></span>   | <span data-ttu-id="25788-172">**25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** o **100%**</span><span class="sxs-lookup"><span data-stu-id="25788-172">**25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%**, or **100%**</span></span> | <span data-ttu-id="25788-173">Questa proprietà definisce il layout per le porte di visualizzazione grandi come i computer.</span><span class="sxs-lookup"><span data-stu-id="25788-173">This property defines the layout for large view ports, such as computers.</span></span> |

## <a name="container-with-3-slots"></a><span data-ttu-id="25788-174">Contenitore con 3 slot</span><span class="sxs-lookup"><span data-stu-id="25788-174">Container with 3-slots</span></span>

<span data-ttu-id="25788-175">Il contenitore con il tipo di moduli a 3 slot è ottimizzato per un layout a tre colonne.</span><span class="sxs-lookup"><span data-stu-id="25788-175">The container with 3-slots modules type is optimized for a three-column layout.</span></span>

<span data-ttu-id="25788-176">Ulteriori proprietà possono essere utilizzate per ottimizzare il layout per differenti porte di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="25788-176">Additional properties can be used to optimize the layout for different view ports.</span></span> <span data-ttu-id="25788-177">Per ogni porta di visualizzazione, è possibile definire la larghezza di ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="25788-177">For every view port, the width of each column can be defined.</span></span> <span data-ttu-id="25788-178">Le seguenti impostazioni sono disponibili per la larghezza di colonna:</span><span class="sxs-lookup"><span data-stu-id="25788-178">The following column width settings are available:</span></span>

- <span data-ttu-id="25788-179">**33%/33%/33%** - Tutti e tre i moduli hanno una larghezza di colonna uguale.</span><span class="sxs-lookup"><span data-stu-id="25788-179">**33%/33%/33%** – All three modules have equal column width.</span></span>
- <span data-ttu-id="25788-180">**50%/25%/25%** - Il primo modulo ha una larghezza di colonna del 50% e ognuno dei due moduli rimanenti ha una larghezza di colonna del 25%.</span><span class="sxs-lookup"><span data-stu-id="25788-180">**50%/25%/25%** – The first module has a column width of 50 percent, and each of the remaining two modules has a column width of 25 percent.</span></span> <span data-ttu-id="25788-181">Sono disponibili anche le opzioni **25%/50%/25%** e**25%/25%/50%**.</span><span class="sxs-lookup"><span data-stu-id="25788-181">**25%/50%/25%** and **25%/25%/50%** options are also available.</span></span>
- <span data-ttu-id="25788-182">**16%/16%/67%** - Ognuno dei due primi moduli ha una larghezza di colonna del 16% e il terzo modulo ha una larghezza di colonna del 67%.</span><span class="sxs-lookup"><span data-stu-id="25788-182">**16%/16%/67%** – Each of the first two modules has a column width of 16 percent, and the third module has a column width of 67 percent.</span></span> <span data-ttu-id="25788-183">Sono disponibili anche le opzioni **16%/67%/16%** e**67%/16%/16%**.</span><span class="sxs-lookup"><span data-stu-id="25788-183">**16%/67%/16%** and **67%/16%/16%** options are also available.</span></span>

### <a name="container-with-3-slots-properties"></a><span data-ttu-id="25788-184">Proprietà del contenitore con 3 slot</span><span class="sxs-lookup"><span data-stu-id="25788-184">Container with 3-slots properties</span></span>

| <span data-ttu-id="25788-185">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="25788-185">Property name</span></span>                   | <span data-ttu-id="25788-186">Valori</span><span class="sxs-lookup"><span data-stu-id="25788-186">Values</span></span> | <span data-ttu-id="25788-187">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25788-187">Description</span></span> |
|---------------------------------|--------|-------------|
| <span data-ttu-id="25788-188">Intestazione</span><span class="sxs-lookup"><span data-stu-id="25788-188">Heading</span></span>                         | <span data-ttu-id="25788-189">Testo e tag di intestazione</span><span class="sxs-lookup"><span data-stu-id="25788-189">Heading text and heading tag</span></span> | <span data-ttu-id="25788-190">Un'intestazione facoltativa può essere aggiunta al contenitore.</span><span class="sxs-lookup"><span data-stu-id="25788-190">An optional heading can be added to the container.</span></span> |
| <span data-ttu-id="25788-191">Configurazione per porte di visualizzazione molto piccole</span><span class="sxs-lookup"><span data-stu-id="25788-191">X-Small view port configuration</span></span> | <span data-ttu-id="25788-192">**33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** o **67%/16%/16%**</span><span class="sxs-lookup"><span data-stu-id="25788-192">**33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%**, or **67%/16%/16%**</span></span> | <span data-ttu-id="25788-193">Questa proprietà definisce il layout per le porte di visualizzazione molto piccole.</span><span class="sxs-lookup"><span data-stu-id="25788-193">This property defines the layout for extra-small view ports.</span></span> |
| <span data-ttu-id="25788-194">Configurazione per porte di visualizzazione molto piccole</span><span class="sxs-lookup"><span data-stu-id="25788-194">Small view port configuration</span></span>   | <span data-ttu-id="25788-195">**33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** o **67%/16%/16%**</span><span class="sxs-lookup"><span data-stu-id="25788-195">**33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%**, or **67%/16%/16%**</span></span> | <span data-ttu-id="25788-196">Questa proprietà definisce il layout per le porte di visualizzazione molto piccole come i dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="25788-196">This property defines the layout for small view ports, such as mobile devices.</span></span> |
| <span data-ttu-id="25788-197">Configurazione per porte di visualizzazione medie</span><span class="sxs-lookup"><span data-stu-id="25788-197">Medium view port configuration</span></span>  | <span data-ttu-id="25788-198">**33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** o **67%/16%/16%**</span><span class="sxs-lookup"><span data-stu-id="25788-198">**33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%**, or **67%/16%/16%**</span></span> | <span data-ttu-id="25788-199">Questa proprietà definisce il layout per le porte di visualizzazione medie come i tablet.</span><span class="sxs-lookup"><span data-stu-id="25788-199">This property defines the layout for medium view ports, such as tablets.</span></span> |
| <span data-ttu-id="25788-200">Configurazione per porte di visualizzazione grandi</span><span class="sxs-lookup"><span data-stu-id="25788-200">Large view port configuration</span></span>   | <span data-ttu-id="25788-201">**33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** o **67%/16%/16%**</span><span class="sxs-lookup"><span data-stu-id="25788-201">**33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%**, or **67%/16%/16%**</span></span> | <span data-ttu-id="25788-202">Questa proprietà definisce il layout per le porte di visualizzazione grandi come i computer.</span><span class="sxs-lookup"><span data-stu-id="25788-202">This property defines the layout for large view ports, such as computers.</span></span> |

## <a name="add-a-container-module-to-a-page"></a><span data-ttu-id="25788-203">Aggiungere un modulo contenitore a una pagina</span><span class="sxs-lookup"><span data-stu-id="25788-203">Add a container module to a page</span></span>

<span data-ttu-id="25788-204">Per aggiungere un modulo contenitore a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="25788-204">To add a container player module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="25788-205">Creare un modello pagina denominato **Modello contenitore**.</span><span class="sxs-lookup"><span data-stu-id="25788-205">Create a page template that is named **container template**.</span></span>
1. <span data-ttu-id="25788-206">Nello slot **Principale** della pagina predefinita, aggiungere un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="25788-206">In the **Main** slot of the default page, add a container module.</span></span>
1. <span data-ttu-id="25788-207">Aggiungere un modulo Funzionalità al modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="25788-207">In the container module, add a feature module.</span></span>
1. <span data-ttu-id="25788-208">Archiviare il modello e pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="25788-208">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="25788-209">Utilizzare il modello contenitore appena creato per creare una pagina denominata **Pagina contenitore**.</span><span class="sxs-lookup"><span data-stu-id="25788-209">Use the container template that you just created to create a page that is named **container page**.</span></span>
1. <span data-ttu-id="25788-210">Nello slot **Principale** della nuova pagina, aggiungere un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="25788-210">In the **Main** slot of the new page, add a container module.</span></span>
1. <span data-ttu-id="25788-211">Nel riquadro delle proprietà del modulo contenitore, impostare la proprietà **Numero di colonne** su **1** e la proprietà **Larghezza** su **Adatta a contenitore**.</span><span class="sxs-lookup"><span data-stu-id="25788-211">In the property pane for the container module, set the **Number of columns** property to **1** and the **Width** property to **Fit container**.</span></span>
1. <span data-ttu-id="25788-212">Aggiungere un modulo Funzionalità al modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="25788-212">In the container module, add a feature module.</span></span>
1. <span data-ttu-id="25788-213">Nel riquadro delle proprietà del modulo Funzionalità, configurare un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="25788-213">In the property pane for the feature module, configure a heading.</span></span>
1. <span data-ttu-id="25788-214">Salvare la pagina e visualizzarne l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="25788-214">Save and preview the page.</span></span> <span data-ttu-id="25788-215">Dovrebbe essere visualizzato un modulo Funzionalità adattato alla larghezza del modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="25788-215">You should see one feature module that fits within the width of the container module.</span></span>
1. <span data-ttu-id="25788-216">Nel riquadro delle proprietà del modulo contenitore, impostare la proprietà **Numero di colonne** su **3**.</span><span class="sxs-lookup"><span data-stu-id="25788-216">In the property pane for the container module, change the the value of the **Number of columns** property to **3**.</span></span>
1. <span data-ttu-id="25788-217">Aggiungere due o più moduli Funzionalità al modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="25788-217">Add two more feature modules to the container module.</span></span>
1. <span data-ttu-id="25788-218">Salvare la pagina e visualizzarne l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="25788-218">Save and preview the page.</span></span> <span data-ttu-id="25788-219">Ora dovrebbero essere visualizzati tre moduli Funzionalità affiancati.</span><span class="sxs-lookup"><span data-stu-id="25788-219">You should now see three feature modules that appear side by side.</span></span>
1. <span data-ttu-id="25788-220">Dopo aver ottenuto il layout desiderato, archiviare la pagina e pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="25788-220">After you've achieved the layout that you want, check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25788-221">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="25788-221">Additional resources</span></span>

[<span data-ttu-id="25788-222">Panoramica starter kit</span><span class="sxs-lookup"><span data-stu-id="25788-222">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="25788-223">Modulo Sequenza</span><span class="sxs-lookup"><span data-stu-id="25788-223">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="25788-224">Modulo Blocco ricco di contenuti</span><span class="sxs-lookup"><span data-stu-id="25788-224">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="25788-225">Modulo Posizionamento contenuti</span><span class="sxs-lookup"><span data-stu-id="25788-225">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="25788-226">Modulo Casella acquisti</span><span class="sxs-lookup"><span data-stu-id="25788-226">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="25788-227">Modulo Carrello</span><span class="sxs-lookup"><span data-stu-id="25788-227">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="25788-228">Modulo Checkout</span><span class="sxs-lookup"><span data-stu-id="25788-228">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="25788-229">Modulo Intestazione</span><span class="sxs-lookup"><span data-stu-id="25788-229">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="25788-230">Modulo Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="25788-230">Footer module</span></span>](author-footer-module.md)