---
title: Localizzazione italiana - Tracciabilità dei pagamenti
description: Questo argomento spiega come controllare l'identificazione della procedura di gara e i codici CIPE durante l'elaborazione end-to-end dalla fattura originale al pagamento.
author: neserovleo
manager: AnnBe
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: v-lenest
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8aba43cb8262c6943bbaa76e3490173a31158ce0
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104456"
---
# <a name="italian-localization---payment-traceability"></a><span data-ttu-id="9ef69-103">Localizzazione italiana - Tracciabilità dei pagamenti</span><span class="sxs-lookup"><span data-stu-id="9ef69-103">Italian localization - Payment traceability</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="9ef69-104">Per le aziende italiane che lavorano con aziende del settore pubblico, potrebbero essere presenti dei requisiti per controllare l'identificazione della procedura di gara e i codici CIPE durante l'elaborazione end-to-end dalla fattura originale al pagamento.</span><span class="sxs-lookup"><span data-stu-id="9ef69-104">For Italian companies who work with public sector companies, there might be requirements to control the Tender procedure identification and CIPE codes during end-to-end processing from the original invoice to the payment.</span></span> <span data-ttu-id="9ef69-105">Questo controllo richiesto può essere nei moduli Contabilità clienti e Contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="9ef69-105">This required control can be in both the Accounts Receivable and Accounts Payable modules.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9ef69-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9ef69-106">Prerequisites</span></span>

<span data-ttu-id="9ef69-107">Per poter utilizzare la funzionalità di tracciabilità dei pagamenti, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="9ef69-107">Before you can use the payment traceability functionality, the following prerequisites must be met:</span></span>

- <span data-ttu-id="9ef69-108">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="9ef69-108">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="9ef69-109">La funzione **(Italia) Miglioramenti al tracciamento del documento di base** deve essere attivata nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="9ef69-109">The feature **(Italy) Base document tracking improvements** must be turned on in the **Feature management** workspace.</span></span> <span data-ttu-id="9ef69-110">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9ef69-110">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="feature-details"></a><span data-ttu-id="9ef69-111">Dettagli delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="9ef69-111">Feature details</span></span>

<span data-ttu-id="9ef69-112">Con la funzionalità attivata, i codici CIG (Tender Procedure Identification) e CIPE (CUP) vengono ereditati in relazione alla particolare transazione del cliente o del fornitore.</span><span class="sxs-lookup"><span data-stu-id="9ef69-112">With the feature activated, the Tender procedure identification (CIG) and CIPE (CUP) codes are inherited in relation to the particular customer or vendor transaction.</span></span> <span data-ttu-id="9ef69-113">Questa eredità consente una maggiore tracciabilità in tutto il sistema e può essere rivista utilizzando il meccanismo di personalizzazione standard.</span><span class="sxs-lookup"><span data-stu-id="9ef69-113">This inheritance allows for higher traceability across the system and could be reviewed by using the standard personalization mechanism.</span></span> <span data-ttu-id="9ef69-114">Per ereditare i valori dalla transazione fattura originale durante la proposta di pagamento, nella pagina **Metodi di pagamento** attiva l'attributo **Pagamento documento di base**.</span><span class="sxs-lookup"><span data-stu-id="9ef69-114">To inherit the values from the original invoice transaction during payment proposal, on the **Methods of payment** page, activate the **Base document payment** attribute.</span></span> <span data-ttu-id="9ef69-115">Per garantire che i campi obbligatori corrispondano ai codici CIG e CUP siano popolati nella transazione, contrassegna il conto cliente, il conto fornitore o il gruppo come con il parametro del settore pubblico.</span><span class="sxs-lookup"><span data-stu-id="9ef69-115">To ensure that the mandatory fields correspond to the CIG and CUP codes are populated in the transaction, mark the Customer account, Vendor account, or group as with Public sector parameter.</span></span>

