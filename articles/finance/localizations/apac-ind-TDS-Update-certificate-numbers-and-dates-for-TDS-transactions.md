---
title: Aggiornare i numeri e le date dei certificati per transazioni TDS
description: In questo argomento viene illustrato come aggiornare i numeri e le date dei certificati recuperabili registrati per i conti fornitore, cliente e CoGe per l'imposta dedotta all'origine (TDS).
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
ms.openlocfilehash: 248de8e12703a84482b67d0899857a6efb33531c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023354"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a><span data-ttu-id="e6deb-103">Aggiornare i numeri e le date dei certificati per transazioni TDS</span><span class="sxs-lookup"><span data-stu-id="e6deb-103">Update certificate numbers and dates for TDS transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e6deb-104">In questo argomento viene illustrato come aggiornare i numeri e le date dei certificati recuperabili registrati per i conti fornitore, cliente e CoGe per l'imposta dedotta all'origine (TDS).</span><span class="sxs-lookup"><span data-stu-id="e6deb-104">This topic explains how to update the recoverable certificate numbers and dates that were recorded for vendor, customer, and ledger accounts for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="e6deb-105">Puoi visualizzare i certificati per le transazioni TDS nella pagina **Certificati recuperabili**.</span><span class="sxs-lookup"><span data-stu-id="e6deb-105">You can view the certificates for TDS transactions on the **Recoverable certificates** page.</span></span> <span data-ttu-id="e6deb-106">Puoi aggiornare i certificati utilizzando la pagina **Aggiorna certificati**.</span><span class="sxs-lookup"><span data-stu-id="e6deb-106">You can update the certificates by using the **Update Certificates** page.</span></span>

<span data-ttu-id="e6deb-107">Segui questi passaggi per aggiornare i numeri e le date dei certificati per transazioni TDS.</span><span class="sxs-lookup"><span data-stu-id="e6deb-107">Follow these steps to update certificate numbers and dates for TDS transactions.</span></span>

1. <span data-ttu-id="e6deb-108">Seleziona **Imposta \> Dichiarazioni \> Ritenuta d'acconto \> Aggiorna certificato**.</span><span class="sxs-lookup"><span data-stu-id="e6deb-108">Go to **Tax \> Declarations \> Withholding tax \> Update certificate**.</span></span>

    <span data-ttu-id="e6deb-109">[![Pagina Aggiorna certificato](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span><span class="sxs-lookup"><span data-stu-id="e6deb-109">[![Update certificate page](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span></span>

2. <span data-ttu-id="e6deb-110">Nella pagina **Aggiorna certificato**, nella sezione **Seleziona**, nel campo **Tipo di imposta**, seleziona **TDS**.</span><span class="sxs-lookup"><span data-stu-id="e6deb-110">On the **Update certificate** page, in the **Select** section, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="e6deb-111">Nel campo **Numero certificato** seleziona il numero di certificato TDS del cliente o del fornitore.</span><span class="sxs-lookup"><span data-stu-id="e6deb-111">In the **Certificate number** field, select the customer's or vendor's TDS certificate number.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e6deb-112">Il campo **Numero certificato** elenca solo i numeri di certificato TDS per i quali la casella di controllo **Chiuso** è deselezionata nella pagina **Certificati recuperabili**.</span><span class="sxs-lookup"><span data-stu-id="e6deb-112">The **Certificate number** field lists only TDS certificate numbers that the **Closed** check box is cleared for on the **Recoverable certificates** page.</span></span>

    <span data-ttu-id="e6deb-113">Il campo **Data certificato** mostra la data del certificato.</span><span class="sxs-lookup"><span data-stu-id="e6deb-113">The **Certificate date** field shows the certificate date.</span></span> <span data-ttu-id="e6deb-114">Il campo **Tipo di conto** Il campo mostra il tipo di conto per il quale viene ricevuto il numero di certificato TDS e il campo **Nome** mostra il nome del conto.</span><span class="sxs-lookup"><span data-stu-id="e6deb-114">The **Account type** field shows the type of account that the TDS certificate number is received for, and the **Name** field shows the name of the account.</span></span>

5. <span data-ttu-id="e6deb-115">Nei campi **Data iniziale** e **Data finale**, seleziona le date finale e finale del periodo per cui visualizzare le transazioni TDS.</span><span class="sxs-lookup"><span data-stu-id="e6deb-115">In the **From date** and **To date** fields, select the start and end dates of the period to show the TDS transactions for.</span></span>
6. <span data-ttu-id="e6deb-116">Seleziona **Mostra dati** per visualizzare le transazioni TDS registrate durante il periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="e6deb-116">Select **Show data** to view the TDS transactions that were posted during the selected period.</span></span>

    <span data-ttu-id="e6deb-117">Nella tabella **Panoramica**, la griglia nel riquadro superiore mostra le seguenti informazioni su ciascuna transazione TDS registrata per il fornitore o il cliente durante il periodo selezionato:</span><span class="sxs-lookup"><span data-stu-id="e6deb-117">On the **Overview** tab, the grid in the upper pane shows the following information about each TDS transaction that was posted for the vendor or customer during the selected period:</span></span>

    - <span data-ttu-id="e6deb-118">**Giustificativo** - Il numero di giustificativo della transazione TDS.</span><span class="sxs-lookup"><span data-stu-id="e6deb-118">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="e6deb-119">**Data** - La data della transazione TDS.</span><span class="sxs-lookup"><span data-stu-id="e6deb-119">**Date** – The date of the TDS transaction.</span></span>
    - <span data-ttu-id="e6deb-120">**Importo** - L'importo della fattura su cui è stata calcolata la TDS.</span><span class="sxs-lookup"><span data-stu-id="e6deb-120">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="e6deb-121">**Importo imposta** - L'importo della TDS calcolato per la transazione.</span><span class="sxs-lookup"><span data-stu-id="e6deb-121">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>

7. <span data-ttu-id="e6deb-122">Per spostare specifiche transazioni TDS dalla griglia superiore a quella inferiore, seleziona le transazioni, quindi seleziona **Includi**.</span><span class="sxs-lookup"><span data-stu-id="e6deb-122">To move specific TDS transactions from the upper grid to the lower grid, select the transactions, and then select **Include**.</span></span> <span data-ttu-id="e6deb-123">In alternativa, seleziona **Includi tutto** per spostare tutte le transazioni TDS dalla griglia superiore alla griglia inferiore.</span><span class="sxs-lookup"><span data-stu-id="e6deb-123">Alternatively, select **Include all** to move all TDS transactions from the upper grid to the lower grid.</span></span>

    <span data-ttu-id="e6deb-124">Per spostare specifiche transazioni TDS o tutte le transazioni TDS dalla griglia inferiore a quella superiore, utilizza il pulsante **Escludi** o **Escludi tutto**.</span><span class="sxs-lookup"><span data-stu-id="e6deb-124">To move specific TDS transactions or all TDS transactions from the lower grid to the upper grid, use the **Exclude** or **Exclude all** button.</span></span>

8. <span data-ttu-id="e6deb-125">Seleziona **Aggiorna** per aggiornare i campi **Numero certificato** e **Data certificato** per le transazioni TDS nella griglia inferiore.</span><span class="sxs-lookup"><span data-stu-id="e6deb-125">Select **Update** to update the **Certificate number** and **Certificate date** fields for TDS transactions in the lower grid.</span></span>
10. <span data-ttu-id="e6deb-126">Vai a **Imposta \> Imposte indirette \> Ritenuta d'acconto \> Certificato recuperabile** e seleziona **Richiesta info** per visualizzare le righe di transazioni aggiornate che hanno nuovi numeri di certificato nella pagina **Transazioni certificato**.</span><span class="sxs-lookup"><span data-stu-id="e6deb-126">Go to **Tax \> Indirect taxes \> Withholding tax \> Recoverable certificate**, and select **Inquiry** to view the updated transaction lines that have the new certificate numbers on the **Certificate transactions** page.</span></span>

    <span data-ttu-id="e6deb-127">[![Pagina Transazioni certificato](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span><span class="sxs-lookup"><span data-stu-id="e6deb-127">[![Certificate transactions page](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span></span>
