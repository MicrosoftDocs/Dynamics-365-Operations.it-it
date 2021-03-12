---
title: Verifica della data del documento di trasporto nelle fatture per l'Italia
description: Per l'Italia, la data della fattura è verificata sui documenti di trasporto e sulle proposte di fatturazione. In questo argomento vengono fornite informazioni aggiuntive sulla verifica eseguita.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPackingSlipJournal
audience: Application User
ms.reviewer: kfend
ms.custom: 263824
ms.search.region: Italy
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 80c2c34f5a0a5337121ef28470638cec05fc8928
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978226"
---
# <a name="packing-slip-date-verification-on-invoices-for-italy"></a><span data-ttu-id="b476c-104">Verifica della data del documento di trasporto nelle fatture per l'Italia</span><span class="sxs-lookup"><span data-stu-id="b476c-104">Packing slip date verification on invoices for Italy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b476c-105">Per l'Italia, la data della fattura è verificata sui documenti di trasporto e sulle proposte di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="b476c-105">For Italy, the invoice date is verified on packing slips and invoice proposals.</span></span> <span data-ttu-id="b476c-106">In questo argomento vengono fornite informazioni aggiuntive sulla verifica eseguita.</span><span class="sxs-lookup"><span data-stu-id="b476c-106">This topic provides additional information about the verification that occurs.</span></span> 

<span data-ttu-id="b476c-107">Per le persone giuridiche il cui indirizzo principale è in Italia è presente un passaggio di verifica della data documento di trasporto per gli utenti che generano fatture di vendita o fatture progetto.</span><span class="sxs-lookup"><span data-stu-id="b476c-107">For legal entities with primary addresses in Italy there is a packing slip date verification step for users who generate sales invoices or project invoices.</span></span>

-   <span data-ttu-id="b476c-108">I documenti di trasporto che hanno data successiva alla fattura non devono essere inclusi nella quantità di aggiornamento consigliata.</span><span class="sxs-lookup"><span data-stu-id="b476c-108">Packing slips that are dated later than the invoice are not be included in the suggested update quantity.</span></span>
-   <span data-ttu-id="b476c-109">Per Gestione progetti e contabilità, quando si crea una proposta di fatturazione, solo i documenti di trasporto del cliente datati anteriore alla proposta di fatturazione vengono inclusi nella proposta.</span><span class="sxs-lookup"><span data-stu-id="b476c-109">For project management and accounting, when you create an invoice proposal, only the customer packing slips that are dated earlier than the invoice proposal are included in the proposal.</span></span> <span data-ttu-id="b476c-110">**Nota**: Se la data di input utente per la proposta di fatturazione è vuota, la data di sistema viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="b476c-110">**Note**: If the user input date for the invoice proposal is empty, the system date is used.</span></span>




