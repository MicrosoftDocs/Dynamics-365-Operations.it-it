---
title: Registrare le scritture contabili di rettifica della transizione in Leasing cespite
description: In questo argomento viene descritta la funzionalità che consente di trasferire un portafoglio di leasing ai nuovi standard contabili di leasing, Accounting Standards Codification Topic 842 (ASC 842) e International Financial Reporting Standard 16 (IFRS 16).
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 51ae41e22507d77f32b8b0f4685cce797fd19cff
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969555"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a><span data-ttu-id="d219b-103">Registrare le scritture contabili di rettifica della transizione in Leasing cespite</span><span class="sxs-lookup"><span data-stu-id="d219b-103">Post transition adjustment journal entries in Asset leasing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d219b-104">Questo argomento descrive la funzionalità che consente di trasferire un portafoglio leasing ai nuovi standard contabili di leasing: Accounting Standards Codification Topic 842 (ASC 842), che è lo standard in Generally Accepted Accounting Principles negli Stati Uniti (US GAAP) e International Financial Reporting Standard 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="d219b-104">This topic describes the functionality that lets you transition a lease portfolio to the new lease accounting standards: Accounting Standards Codification Topic 842 (ASC 842), which is the standard in Generally Accepted Accounting Principles in the US (US GAAP), and International Financial Reporting Standard 16 (IFRS 16).</span></span>

<span data-ttu-id="d219b-105">Per informazioni su come configurare un libro per la transizione ai nuovi standard, vedi [Configurare libri di leasing](set-up-lease-books.md).</span><span class="sxs-lookup"><span data-stu-id="d219b-105">For information about how to set up a book for the transition to the new standards, see [Set up lease books](set-up-lease-books.md).</span></span>

<span data-ttu-id="d219b-106">Quando crei una scrittura contabile di rettifica di transizione, viene generata una scrittura contabile.</span><span class="sxs-lookup"><span data-stu-id="d219b-106">When you create a transition adjustment journal entry, a journal entry is generated.</span></span> <span data-ttu-id="d219b-107">Questa voce riflette l'impatto dello stato patrimoniale derivante dalla registrazione del leasing secondo i nuovi principi a quella data.</span><span class="sxs-lookup"><span data-stu-id="d219b-107">This entry reflects the balance sheet impact of recording the lease under the new standards on that date.</span></span> <span data-ttu-id="d219b-108">Il valore contabile a tale data viene addebitato sul conto dell'attivo appropriato e accreditato sul conto delle passività.</span><span class="sxs-lookup"><span data-stu-id="d219b-108">The appropriate asset account is debited for the carrying amount on that date, and the liability account is credited.</span></span> <span data-ttu-id="d219b-109">La differenza viene addebitata o accreditata sugli utili non distribuiti.</span><span class="sxs-lookup"><span data-stu-id="d219b-109">The difference is either debited or credited to retained earnings.</span></span>

<span data-ttu-id="d219b-110">Per registrare una rettifica di transizione in conformità con i nuovi principi contabili, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="d219b-110">To post a transition adjustment in compliance with the new accounting standards, follow these steps.</span></span>

1. <span data-ttu-id="d219b-111">Nella pagina **Riepilogo leasing**, seleziona il leasing, quindi seleziona **Libri**.</span><span class="sxs-lookup"><span data-stu-id="d219b-111">On the **Lease summary** page, select the lease, and then select **Books**.</span></span>
2. <span data-ttu-id="d219b-112">Nel libro, seleziona **Scadenziario pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="d219b-112">In the book, select **Payment schedule**.</span></span>
3. <span data-ttu-id="d219b-113">Nella finestra di dialogo **Scadenziario pagamenti**, seleziona **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="d219b-113">In the **Payment schedule** dialog box, select **Confirm**.</span></span> <span data-ttu-id="d219b-114">Quindi, chiudi la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d219b-114">Then close the dialog box.</span></span>
4. <span data-ttu-id="d219b-115">Seleziona **Rettifica di transizione**.</span><span class="sxs-lookup"><span data-stu-id="d219b-115">Select **Transition adjustment**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d219b-116">È possibile creare una rettifica di transizione solo per i libri di leasing assegnati a un libro in cui il campo **Libro di transizione** è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d219b-116">A transition adjustment can be created only for lease books that are assigned to a book where the **Transition book** field is available.</span></span> <span data-ttu-id="d219b-117">Se il valore nel campo **Inizio del leasing** è successivo alla data di transizione, il valore nel campo **Rettifica di transizione** non verrà aggiornato.</span><span class="sxs-lookup"><span data-stu-id="d219b-117">If the value in the **Lease commencement** field is later than the transition date, the value in the **Transition adjustment** field won't be updated.</span></span>

5. <span data-ttu-id="d219b-118">Per visualizzare la scrittura contabile, seleziona **Giornale di registrazione leasing cespiti**.</span><span class="sxs-lookup"><span data-stu-id="d219b-118">To view the journal entry, select **Asset leasing journals**.</span></span>
6. <span data-ttu-id="d219b-119">Seleziona il nuovo giornale di registrazione, quindi seleziona **Registra**.</span><span class="sxs-lookup"><span data-stu-id="d219b-119">Select the new journal, and then select **Post**.</span></span>
