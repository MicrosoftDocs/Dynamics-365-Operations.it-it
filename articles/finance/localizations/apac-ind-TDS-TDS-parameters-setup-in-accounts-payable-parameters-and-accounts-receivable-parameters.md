---
title: Impostare parametri TDS in Contabilità fornitori e Contabilità clienti
description: In questo argomento viene illustrato come impostare parametri in Contabilità fornitori e Contabilità clienti per supportare le detrazioni dell'imposta dedotta all'origine (TDS).
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
ms.openlocfilehash: 4540cdfff2362d8fb7cc2b4cccf9c340be9750ce
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023358"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a><span data-ttu-id="8b331-103">Impostare parametri TDS in Contabilità fornitori e Contabilità clienti</span><span class="sxs-lookup"><span data-stu-id="8b331-103">Set TDS parameters in Accounts payable and Accounts receivable</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8b331-104">In questo argomento viene illustrato come impostare parametri in Contabilità fornitori e Contabilità clienti per supportare le detrazioni dell'imposta dedotta all'origine (TDS).</span><span class="sxs-lookup"><span data-stu-id="8b331-104">This topic explains how to set parameters in Accounts payable and Accounts receivable to support Tax Deducted at Source (TDS) deductions.</span></span>

1. <span data-ttu-id="8b331-105">Vai a **Imposta \> Impostazione \> Parametri \> Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="8b331-105">Go to **Tax \> Setup \> Parameters \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="8b331-106">Nella scheda **Aggiornamenti**, seleziona **Aggiorna righe ordine** per aprire la finestra di dialogo **Aggiorna righe ordine**.</span><span class="sxs-lookup"><span data-stu-id="8b331-106">On the **Updates** tab, select **Update order lines** to open the **Update order lines** dialog box.</span></span>
3. <span data-ttu-id="8b331-107">Nella sezione **Gruppo TDS**, nel campo **Aggiornamento gruppo TDS**, specifica il metodo da utilizzare per aggiornare il gruppo TDS a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="8b331-107">In the **TDS group** section, in the **Updating TDS group** field, specify the method to use to update the TDS group at the line level.</span></span> <span data-ttu-id="8b331-108">Questa impostazione viene utilizzata quando il gruppo TDS viene aggiornato in un'intestazione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="8b331-108">This setting is used when the TDS group is updated on an order header.</span></span> <span data-ttu-id="8b331-109">Di seguito vengono illustrate le opzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="8b331-109">The following options are available:</span></span>

    - <span data-ttu-id="8b331-110">**Mai** - Il gruppo TDS non viene aggiornato nelle righe dell'ordine quando viene aggiornato nell'intestazione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="8b331-110">**Never** – The TDS group isn't updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="8b331-111">**Sempre** - Il gruppo TDS viene aggiornato automaticamente nelle righe dell'ordine quando viene aggiornato nell'intestazione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="8b331-111">**Always** – The TDS group is automatically updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="8b331-112">**Richiesta** - Gli utenti ricevono un messaggio che richiede loro di aggiornare il gruppo TDS nelle righe ordine.</span><span class="sxs-lookup"><span data-stu-id="8b331-112">**Prompt** – Users receive a message that prompts them to update the TDS group on the order lines.</span></span>
4. <span data-ttu-id="8b331-113">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b331-113">Select **OK**.</span></span>

    <span data-ttu-id="8b331-114">[![Finestra di dialogo Aggiorna righe ordine](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span><span class="sxs-lookup"><span data-stu-id="8b331-114">[![Update order lines dialog box](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span></span>

5. <span data-ttu-id="8b331-115">Vai a **Imposta \> Impostazione \> Parametri \> Parametri contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="8b331-115">Go to **Tax \> Setup \> Parameters \> Accounts payable parameters**.</span></span>
6. <span data-ttu-id="8b331-116">Nella scheda **Generale**, nella Scheda dettaglio **Dividi in base alle informazioni di consegna**, imposta l'opzione **Entrata prodotti** su **Sì** per registrare e dividere un'entrata prodotti che ha diversi indirizzi di consegna e numeri di conto imposta (TAN).</span><span class="sxs-lookup"><span data-stu-id="8b331-116">On the **General** tab, on the **Split based on delivery information** FastTab, set the **Product receipt** option to **Yes** to post and split a product receipt that has different delivery addresses and tax account numbers (TANs).</span></span> <span data-ttu-id="8b331-117">Se questa opzione è impostata su **No**, non è possibile registrare un documento di trasporto di acquisto che ha differenti indirizzi di consegna e TAN.</span><span class="sxs-lookup"><span data-stu-id="8b331-117">If this option is set to **No**, you can't post a purchase packing slip that has different delivery addresses and TANs.</span></span>
7. <span data-ttu-id="8b331-118">Imposta l'opzione **Fattura** su **Sì** per registrare e dividere una fattura di acquisto che ha diversi indirizzi di consegna e TAN.</span><span class="sxs-lookup"><span data-stu-id="8b331-118">Set the **Invoice** option to **Yes** to post and split a purchase invoice that has different delivery addresses and TANs.</span></span>

    <span data-ttu-id="8b331-119">[![Scheda dettaglio Dividi in base alle informazioni di consegna](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span><span class="sxs-lookup"><span data-stu-id="8b331-119">[![Split based on delivery information FastTab](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span></span>

8. <span data-ttu-id="8b331-120">Chiudi la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b331-120">Close the page.</span></span>
