---
title: Verificare la configurazione della doppia scrittura nelle app Finance and Operations e Dataverse
description: Questo argomento spiega come determinare se è configurata la doppia scrittura nelle app Finance and Operations e in Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 361d6555b60e02832c337b6f416b2b3627b6d365
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "5129309"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a><span data-ttu-id="fc92b-103">Verificare la configurazione della doppia scrittura nelle app Finance and Operations e Dataverse</span><span class="sxs-lookup"><span data-stu-id="fc92b-103">Verify dual-write configuration in Finance and Operations apps and Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="fc92b-104">In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="fc92b-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="fc92b-105">In particolare, spiega come determinare se è configurata la doppia scrittura nelle app Finance and Operations e in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="fc92b-105">Specifically, it explains how you can determine whether dual-write is configured in Finance and Operations apps and in Dataverse.</span></span>

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a><span data-ttu-id="fc92b-106">Verificare che sia configurata la doppia scrittura in un'app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fc92b-106">Verify that dual-write is configured in a Finance and Operations app</span></span>

<span data-ttu-id="fc92b-107">Per determinare se gli errori visualizzati quando si tentano di salvare le righe per l'aggiornamento provengono dalla doppia scrittura, verificare innanzitutto che la doppia scrittura sia configurata.</span><span class="sxs-lookup"><span data-stu-id="fc92b-107">To determine whether the errors that you see when you try to save rows for update come from dual-write, first verify that dual-write is configured.</span></span>

+ <span data-ttu-id="fc92b-108">Se si dispone dei privilegi di amministratore nell'app Finance and Operations, andare a **Aree di lavoro \> Gestione dei dati** e selezionare il riquadro **Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="fc92b-108">If you have admin privileges in the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Dual-write** tile.</span></span> <span data-ttu-id="fc92b-109">Se vengono visualizzati i dettagli degli ambienti collegati e l'elenco delle mappe della tabella in esecuzione, è configurata la doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="fc92b-109">If the details of the linked environments and the list of table maps that are running are shown, dual-write is configured.</span></span>

    ![Verifica della connessione dell'app Finance and Operations quando si dispone dei privilegi di amministratore](media/verify_fin_ops_1.png)

+ <span data-ttu-id="fc92b-111">Se non si dispone dei privilegi di amministratore, viene visualizzato un messaggio di errore, *Impossibile scrivere i dati nell'entità \<entity name\>*.</span><span class="sxs-lookup"><span data-stu-id="fc92b-111">If you don't have admin privileges, you will receive an error message, *Unable to write data to entity \<entity name\>*.</span></span> <span data-ttu-id="fc92b-112">Nell'esempio della figura seguente, non è possibile creare una riga cliente nell'app Finance and Operations perché la doppia scrittura è configurata, ma i dati di riferimento del gruppo di clienti e dei termini di pagamento non esistono in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="fc92b-112">In the example in the following illustration, you can't create a customer row in the Finance and Operations app, because dual-write is configured, but the customer group and payment terms reference data don't exist in Dataverse.</span></span>

    ![Verifica della connessione dell'app Finance and Operations quando non si dispone dei privilegi di amministratore](media/verify_fin_ops_2.png)

<span data-ttu-id="fc92b-114">Per informazioni su come risolvere i problemi durante la creazione di dati nelle app Finance and Operations, vedere [Risoluzione dei problemi di sincronizzazione in tempo reale](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="fc92b-114">For information about how to fix issues when you create data in Finance and Operations apps, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a><span data-ttu-id="fc92b-115">Verificare che sia configurata la doppia scrittura in Dataverse</span><span class="sxs-lookup"><span data-stu-id="fc92b-115">Verify that dual-write is configured in Dataverse</span></span>

<span data-ttu-id="fc92b-116">Quando si creano i dati, se la colonna **Società** è presente nelle pagine di Dataverse, la doppia scrittura è configurata.</span><span class="sxs-lookup"><span data-stu-id="fc92b-116">When you create data, if you see the **Company** column on pages in Dataverse, dual-write is configured.</span></span>

![Verifica della connessione Dataverse](media/verify_cds.png)

<span data-ttu-id="fc92b-118">Per informazioni su come risolvere i problemi durante la creazione di dati in Dataverse, vedere [Risoluzione dei problemi di sincronizzazione in tempo reale](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="fc92b-118">For information about how to fix issues when you create data in Dataverse, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

<span data-ttu-id="fc92b-119">Per informazioni su come visualizzare i dettagli dell'errore se si verificano errori durante la creazione dei dati in Dataverse, vedere [Abilitare e visualizzare il log di traccia del plug-in Dataverse per visualizzare i dettagli dell'errore](dual-write-troubleshooting.md#enable-view-trace).</span><span class="sxs-lookup"><span data-stu-id="fc92b-119">For information about how to view error details if you encounter any errors while you create data in Dataverse, see [Enable and view the plug-in trace log in Dataverse to view error details](dual-write-troubleshooting.md#enable-view-trace).</span></span>
