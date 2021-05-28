---
title: Impossibile applicare un modello a un prodotto rilasciato
description: Impossibile applicare un modello a un prodotto rilasciato.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ad6efdced9bce924fbf5bc207c92fa2c3a6c79d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026636"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a><span data-ttu-id="31c96-103">Impossibile applicare un modello per creare un prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="31c96-103">You can't apply a template to create a released product</span></span>

<span data-ttu-id="31c96-104">Numero KB: 4612097</span><span class="sxs-lookup"><span data-stu-id="31c96-104">KB number: 4612097</span></span>

## <a name="symptoms"></a><span data-ttu-id="31c96-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="31c96-105">Symptoms</span></span>

<span data-ttu-id="31c96-106">Quando crei un nuovo prodotto rilasciato utilizzando la finestra di dialogo **Nuovo prodotto rilasciato**, puoi selezionare un modello.</span><span class="sxs-lookup"><span data-stu-id="31c96-106">When you create a new released product by using the **New released product** dialog box, you can select a template.</span></span> <span data-ttu-id="31c96-107">Il modello dovrebbe fornire le impostazioni predefinite di molti campi del nuovo prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="31c96-107">The template is supposed to provide default settings for many fields of the new released product.</span></span> <span data-ttu-id="31c96-108">Tuttavia, alcuni o tutti i campi non vengono impostati dopo aver selezionato il modello.</span><span class="sxs-lookup"><span data-stu-id="31c96-108">However, some or all of the fields aren't set after you select the template.</span></span>

## <a name="cause"></a><span data-ttu-id="31c96-109">Causa</span><span class="sxs-lookup"><span data-stu-id="31c96-109">Cause</span></span>

<span data-ttu-id="31c96-110">Molte pagine in Microsoft Dynamics 365 Supply Chain Management ti consentono di creare un modello che stabilisce le impostazioni iniziali dei record visualizzati in quelle pagine.</span><span class="sxs-lookup"><span data-stu-id="31c96-110">Many pages in Microsoft Dynamics 365 Supply Chain Management let you create a template that establishes initial settings for the records that are shown on those pages.</span></span> <span data-ttu-id="31c96-111">Puoi creare uno di questi modelli selezionando **Informazioni sui record** nella scheda **Opzioni** del riquadro Azioni.</span><span class="sxs-lookup"><span data-stu-id="31c96-111">You can create one of these templates by selecting **Record info** on the **Options** tab of the Action Pane.</span></span> <span data-ttu-id="31c96-112">Tuttavia, i prodotti rilasciati sono molto più complessi della maggior parte degli altri tipi di record.</span><span class="sxs-lookup"><span data-stu-id="31c96-112">However, released products are much more complex than most other types of records.</span></span> <span data-ttu-id="31c96-113">Sebbene sia possibile selezionare **Informazioni sui record** nella pagina **Prodotti rilasciati** per creare un modello e, sebbene sia possibile selezionare quel modello quando si crea un prodotto rilasciato, il modello non fornirà i valori di campo previsti per il nuovo prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="31c96-113">Although you can select **Record info** on the **Released products** page to create a template, and although you can select that template when you create a released product, the template won't provide the expected field values for the new released product.</span></span> <span data-ttu-id="31c96-114">Pertanto, non puoi utilizzare i modelli "Informazioni sui record" per i prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="31c96-114">Therefore, you can't use "record info" templates for released products.</span></span> <span data-ttu-id="31c96-115">Devi invece creare modelli prodotto dedicati.</span><span class="sxs-lookup"><span data-stu-id="31c96-115">Instead, you must create dedicated product templates.</span></span>

## <a name="resolution"></a><span data-ttu-id="31c96-116">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="31c96-116">Resolution</span></span>

<span data-ttu-id="31c96-117">Per creare un modello prodotto, utilizza il menu **Modello** nella scheda **Prodotto** del riquadro Azioni, non il pulsante **Informazioni sui record** nella scheda **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="31c96-117">To create a product template, use the **Template** menu on the **Product** tab of the Action Pane, not the **Record info** button on the **Options** tab.</span></span>

1. <span data-ttu-id="31c96-118">Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="31c96-118">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="31c96-119">Nel riquadro Azioni, nella scheda **Prodotto**, nel gruppo **Nuovo**, seleziona **Modello**, quindi seleziona **Crea un modello personale** o **Crea modello condiviso**, come appropriato.</span><span class="sxs-lookup"><span data-stu-id="31c96-119">On the Action Pane, on the **Product** tab, in the **New** group, select **Template**, and then select either **Create personal template** or **Create shared template**, as appropriate.</span></span>
