---
title: Registrare numeri di certificati di concessione TDS
description: In questo argomento viene illustrato come registrare i numeri di certificati di concessione dell'imposta dedotta all'origine (TDS) rilasciati ai fornitori.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: f543adc8bab5ca224bdb672d6b3c282c2d8531d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023346"
---
# <a name="record-tds-concession-certificate-numbers"></a><span data-ttu-id="8cce7-103">Registrare numeri di certificati di concessione TDS</span><span class="sxs-lookup"><span data-stu-id="8cce7-103">Record TDS concession certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8cce7-104">In questo argomento viene illustrato come registrare i numeri di certificati di concessione dell'imposta dedotta all'origine (TDS) rilasciati ai fornitori.</span><span class="sxs-lookup"><span data-stu-id="8cce7-104">This topic explains how to record the Tax Deducted at Source (TDS) concession certificate numbers that are issued to vendors.</span></span>

1. <span data-ttu-id="8cce7-105">Vai a **Imposta \> Imposte indirette \> Ritenuta d'acconto \> Concessioni ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="8cce7-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax concessions**.</span></span>
2. <span data-ttu-id="8cce7-106">Nel campo **Tipo di imposta**, seleziona **TDS** per registrare certificati di concessione per il tipo di imposta TDS.</span><span class="sxs-lookup"><span data-stu-id="8cce7-106">In the **Tax type** field, select **TDS** to record concession certificates for the TDS tax type.</span></span>
3. <span data-ttu-id="8cce7-107">Nella scheda **Panoramica**, seleziona **ALT+N** per creare una riga.</span><span class="sxs-lookup"><span data-stu-id="8cce7-107">On the **Overview** tab, select **Alt+N** to create a line.</span></span>

    <span data-ttu-id="8cce7-108">[![Intestazione della nuova riga](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span><span class="sxs-lookup"><span data-stu-id="8cce7-108">[![Header of the new line](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)</span></span>

4. <span data-ttu-id="8cce7-109">Nel campo **Codice ritenuta d'acconto**, seleziona il codice imposta TDS per il quale vengono emessi certificati di concessione.</span><span class="sxs-lookup"><span data-stu-id="8cce7-109">In the **Withholding tax code** field, select the TDS tax code that the vendor concession certificates are issued for.</span></span> <span data-ttu-id="8cce7-110">Il campo **Nome codice ritenuta d'acconto** mostra il nome del codice imposta TDS.</span><span class="sxs-lookup"><span data-stu-id="8cce7-110">The **Withholding tax code name** field shows the name of the TDS tax code.</span></span>
5. <span data-ttu-id="8cce7-111">Nei campo **Data iniziale** e **Data finale**, definisci il periodo di validità del certificato di concessione che utilizza il codice imposta TDS per calcolare la TDS per il fornitore sulla base di una concessione.</span><span class="sxs-lookup"><span data-stu-id="8cce7-111">In the **From date** and **To date** fields, define the period of validity for the concession certificate that uses the TDS tax code to calculate TDS for the vendor on a concessional basis.</span></span>
6. <span data-ttu-id="8cce7-112">Nel campo **Osservazioni**, immetti eventuali commenti.</span><span class="sxs-lookup"><span data-stu-id="8cce7-112">In the **Remarks** field, enter any remarks.</span></span>
7. <span data-ttu-id="8cce7-113">Nel campo **Sezione** immetti il codice sezione giuridica del certificato di concessione TDS.</span><span class="sxs-lookup"><span data-stu-id="8cce7-113">In the **Section** field, enter the legal section code that the TDS concession certificate is availed under.</span></span>

    <span data-ttu-id="8cce7-114">Se il codice sezione è 197, il valore "A" appare sia nella colonna "Motivo per non detrazione/detrazione ridotta" nel modulo 26Q che nella colonna "Motivo per non detrazione/detrazione ridotta/calcolo del lordo (se presente)" nel Modulo 27Q.</span><span class="sxs-lookup"><span data-stu-id="8cce7-114">If the section code is 197, the value "A" appears in both the "Reason for non-deduction/lower deduction" column in Form 26Q and the "Reason for non-deduction/lower deduction/grossing up (if any)" column in Form 27Q.</span></span> <span data-ttu-id="8cce7-115">Se il codice sezione è 197A, il valore "B" appare in entrambe le colonne.</span><span class="sxs-lookup"><span data-stu-id="8cce7-115">If the section code is 197A, the value "B" appears in both those places.</span></span>

8. <span data-ttu-id="8cce7-116">Seleziona la Scheda dettaglio **Certificato** per registrare i numeri di certificati di concessione TDS per i fornitori.</span><span class="sxs-lookup"><span data-stu-id="8cce7-116">Select the **Certificate** FastTab to record TDS concession certificate numbers for vendors.</span></span>
9. <span data-ttu-id="8cce7-117">Nel campo **Conto fornitore** seleziona il conto fornitore per cui viene emesso il certificato di concessione TDS.</span><span class="sxs-lookup"><span data-stu-id="8cce7-117">In the **Vendor account** field, select the vendor account that the TDS concession certificate is issued for.</span></span>
10. <span data-ttu-id="8cce7-118">Nei campi **Data iniziale** e **Data finale**, definisci il periodo di validità del certificato di concessione TDS.</span><span class="sxs-lookup"><span data-stu-id="8cce7-118">In the **From date** and **To date** fields, define the period of validity for the TDS concession certificate.</span></span>

    <span data-ttu-id="8cce7-119">Il calcolo del TDS sulla base di una concessione si basa sul periodo in cui il certificato viene creato per il fornitore.</span><span class="sxs-lookup"><span data-stu-id="8cce7-119">The calculation of TDS on a concessional basis is based on the period when the certificate is created for the vendor.</span></span>

11. <span data-ttu-id="8cce7-120">Nel campo **Certificato**, immetti il numero di certificato di concessione TDS.</span><span class="sxs-lookup"><span data-stu-id="8cce7-120">In the **Certificate** field, enter the TDS concession certificate number.</span></span>

    <span data-ttu-id="8cce7-121">[![Scheda dettaglio Certificato](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span><span class="sxs-lookup"><span data-stu-id="8cce7-121">[![Certificate FastTab](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)</span></span>

12. <span data-ttu-id="8cce7-122">Chiudi la pagina.</span><span class="sxs-lookup"><span data-stu-id="8cce7-122">Close the page.</span></span>
