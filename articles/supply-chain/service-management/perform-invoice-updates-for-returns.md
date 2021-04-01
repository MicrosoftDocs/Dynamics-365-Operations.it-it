---
title: Eseguire aggiornamenti di fatture per i resi
description: Questa funzionalità consente di supportare i processi aziendali delle organizzazioni nelle quali gli ordini di reso e gli ordini cliente vengono fatturati contemporaneamente e da parte di uno stesso utente.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f61c3514818365dc250e1313b0e6b2f775d9bc89
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262047"
---
# <a name="perform-invoice-updates-for-returns"></a><span data-ttu-id="e4283-103">Eseguire aggiornamenti di fatture per i resi</span><span class="sxs-lookup"><span data-stu-id="e4283-103">Perform invoice updates for returns</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e4283-104">Un ordine di reso è un tipo di ordine cliente contrassegnato come reso.</span><span class="sxs-lookup"><span data-stu-id="e4283-104">A return order is a type of sales order that is marked as a returned order.</span></span> <span data-ttu-id="e4283-105">Per generare fatture per gli ordini di reso viene pertanto utilizzata la pagina elenco **Tutti gli ordini cliente** anziché il modulo **Ordini di reso**.</span><span class="sxs-lookup"><span data-stu-id="e4283-105">Therefore, the **All sales orders** list page is used to generate invoices for return orders instead of the **Return orders** form.</span></span> <span data-ttu-id="e4283-106">Questa funzionalità consente di supportare i processi aziendali delle organizzazioni nelle quali gli ordini di reso e gli ordini cliente vengono fatturati contemporaneamente e da parte di uno stesso utente.</span><span class="sxs-lookup"><span data-stu-id="e4283-106">This functionality supports the business processes of organizations that choose to have return orders and sales orders invoiced at the same time and by the same person.</span></span>

<span data-ttu-id="e4283-107">Poiché la fattura per un reso è per un importo negativo, viene denominata nota di accredito.</span><span class="sxs-lookup"><span data-stu-id="e4283-107">Because the invoice for a returned item is for a negative amount, it is called a credit note.</span></span>

<span data-ttu-id="e4283-108">Quando si imposta l'aggiornamento della fattura per l'elaborazione batch, lo stato della riga di reso dell'ordine cliente di tipo **Ordine di reso** deve essere **Ricevuto**, che indica che il documento di trasporto dell'ordine è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="e4283-108">When you set up the invoice update for batch processing, the sales order of type **Returned order** must have a return line status of **Received**, which indicates that the order's packing slip has been updated.</span></span>

## <a name="post-an-invoice-for-a-return-order"></a><span data-ttu-id="e4283-109">Registrare una fattura per un ordine di reso</span><span class="sxs-lookup"><span data-stu-id="e4283-109">Post an invoice for a return order</span></span>

1.  <span data-ttu-id="e4283-110">Fare clic su **Contabilità clienti** \> **Comune** \> **Ordini cliente** \> **Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="e4283-110">Click **Accounts receivable** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="e4283-111">Selezionare un ordine cliente per il quale **Ordine di reso** è visualizzato nel campo **Tipo di ordine**.</span><span class="sxs-lookup"><span data-stu-id="e4283-111">Select a sales order for which **Returned order** is displayed in the **Order type** field.</span></span>

3.  <span data-ttu-id="e4283-112">Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, fare clic su **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="e4283-112">On the Action Pane, on the **Invoice** tab, in the **Generate** group, click **Invoice**.</span></span>

4.  <span data-ttu-id="e4283-113">Selezionare la casella di controllo **Registrazione** nella scheda **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="e4283-113">On the **Parameters** tab, select the **Posting** check box.</span></span>

5.  <span data-ttu-id="e4283-114">Verificare le informazioni del modulo e apportare le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="e4283-114">Review information in the form and make any changes that are needed.</span></span>

6.  <span data-ttu-id="e4283-115">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4283-115">Click **OK**.</span></span> <span data-ttu-id="e4283-116">La nota di accredito è stata registrata.</span><span class="sxs-lookup"><span data-stu-id="e4283-116">The credit note is posted.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4283-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4283-117">See also</span></span>

[<span data-ttu-id="e4283-118">Aggiornamenti dei documenti di trasporto per i resi</span><span class="sxs-lookup"><span data-stu-id="e4283-118">Packing slip updates for returns</span></span>](packing-slip-updates-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]