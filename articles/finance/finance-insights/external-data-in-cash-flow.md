---
title: Utilizzare dati esterni nelle previsioni di cassa (anteprima)
description: In questo argomento vengono descritti i passaggi di configurazione che è necessario completare in modo che i dati esterni possano essere immessi o importati nelle previsioni di cassa.
author: rcarlson
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 7d5768a6cb2b3623333fab93a42ac5840e87ec68
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818619"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a><span data-ttu-id="fd759-103">Utilizzare dati esterni nelle previsioni di cassa (anteprima)</span><span class="sxs-lookup"><span data-stu-id="fd759-103">Use external data in cash flow forecasts (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="fd759-104">I dati esterni possono essere inseriti o importati nelle previsioni di cassa.</span><span class="sxs-lookup"><span data-stu-id="fd759-104">External data can be entered or imported into cash flow forecasts.</span></span> <span data-ttu-id="fd759-105">In questo argomento vengono descritti i passaggi di configurazione specifici per l'utilizzo di dati esterni e che consentono di includere i dati esterni in una previsione di cassa.</span><span class="sxs-lookup"><span data-stu-id="fd759-105">This topic describes the setup steps that are specific to the use of external data and that enable the external data to be included in a cash flow forecast.</span></span>

## <a name="external-data-setup"></a><span data-ttu-id="fd759-106">Configurazione dei dati esterni</span><span class="sxs-lookup"><span data-stu-id="fd759-106">External data setup</span></span>

<span data-ttu-id="fd759-107">Utilizza la scheda **Origine esterna** nella pagina **Configurazione della previsione di cassa** (**Cassa e gestione bancaria \> Previsione di cassa**) per inserire impostazioni che supportano l'uso di dati esterni nelle previsioni di cassa.</span><span class="sxs-lookup"><span data-stu-id="fd759-107">Use the **External source** tab on the **Cash flow forecast setup** page (**Cash and bank management \> Cash flow forecasting**) to enter settings that support the use of external data in cash flow forecasts.</span></span>

<span data-ttu-id="fd759-108">Per ulteriori informazioni sulla configurazione, vedi [Previsione di cassa](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).</span><span class="sxs-lookup"><span data-stu-id="fd759-108">For more information about the setup, see [Cash flow forecasting](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).</span></span>

<span data-ttu-id="fd759-109">Per immettere dati esterni per le previsioni di cassa, puoi utilizzare l'esperienza Apri in Excel per immettere e modificare dati esterni.</span><span class="sxs-lookup"><span data-stu-id="fd759-109">To enter external data for cash flow forecasts, you can use the Open in Excel experience for entering and modifying external data.</span></span> <span data-ttu-id="fd759-110">Seleziona il pulsante **Dati esterni** e quindi seleziona **Aggiungi dati esterni** o **Modifica dati esterni esistenti**.</span><span class="sxs-lookup"><span data-stu-id="fd759-110">Select the **External data** button, and then select either **Add External Data** or **Edit existing external data**.</span></span> <span data-ttu-id="fd759-111">Quando il file Microsoft Excel viene aperto, puoi inserire le informazioni nei seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="fd759-111">When the Microsoft Excel file is opened, you can enter information in the following fields:</span></span>

- <span data-ttu-id="fd759-112">**ID immissione**</span><span class="sxs-lookup"><span data-stu-id="fd759-112">**Entry ID**</span></span>
- <span data-ttu-id="fd759-113">**Descrizione** (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="fd759-113">**Description** (optional)</span></span>
- <span data-ttu-id="fd759-114">**Nome origine esterna**: seleziona uno dei valori nell'elenco che hai definito durante la configurazione di Informazioni finanziarie dettagliate.</span><span class="sxs-lookup"><span data-stu-id="fd759-114">**External Source name** – Select one of the values in the list that you defined when you set up Finance Insights.</span></span>
- <span data-ttu-id="fd759-115">**Persona giuridica**</span><span class="sxs-lookup"><span data-stu-id="fd759-115">**Legal Entity**</span></span>
- <span data-ttu-id="fd759-116">**Data**</span><span class="sxs-lookup"><span data-stu-id="fd759-116">**Date**</span></span>
- <span data-ttu-id="fd759-117">**Importo nella valuta della transazione**</span><span class="sxs-lookup"><span data-stu-id="fd759-117">**Amount in transaction currency**</span></span>
- <span data-ttu-id="fd759-118">**Codice valuta**</span><span class="sxs-lookup"><span data-stu-id="fd759-118">**Currency Code**</span></span>
- <span data-ttu-id="fd759-119">**Dimensione predefinita** (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="fd759-119">**Default Dimension** (optional)</span></span>
- <span data-ttu-id="fd759-120">**Numero documento** (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="fd759-120">**Document number** (optional)</span></span>
- <span data-ttu-id="fd759-121">**Numero conto** (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="fd759-121">**Account number** (optional)</span></span>
- <span data-ttu-id="fd759-122">**Nome conto** (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="fd759-122">**Account name** (optional)</span></span>

## <a name="importing-external-data-by-using-the-data-management-framework"></a><span data-ttu-id="fd759-123">Importazione di dati esterni utilizzando il framework Gestione dati</span><span class="sxs-lookup"><span data-stu-id="fd759-123">Importing external data by using the Data Management framework</span></span>

<span data-ttu-id="fd759-124">Puoi importare dati esterni per previsioni di cassa utilizzando l'area di lavoro **Gestione dati** e l'entità denominata **Inserimento origine esterna previsione di cassa**.</span><span class="sxs-lookup"><span data-stu-id="fd759-124">You can import external data for cash flow forecasts by using the **Data Management** workspace and the entity that is named **Cash flow forecast external source entry**.</span></span>

<span data-ttu-id="fd759-125">Inoltre, se è necessario spostare i dati di configurazione da un ambiente a un altro, la seguente area delle entità è disponibile per le tabelle di configurazione richieste:</span><span class="sxs-lookup"><span data-stu-id="fd759-125">Additionally, if you must move setup data from one environment to another, the following entities area available for the setup tables that are required:</span></span>

- <span data-ttu-id="fd759-126">Impostazione origine esterna per previsione di cassa</span><span class="sxs-lookup"><span data-stu-id="fd759-126">Cash flow forecast external source setup</span></span>
- <span data-ttu-id="fd759-127">Impostazione persona giuridica origine esterna per previsione di cassa</span><span class="sxs-lookup"><span data-stu-id="fd759-127">Cash flow forecast external source legal entity setup</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="fd759-128">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="fd759-128">Privacy notice</span></span>
<span data-ttu-id="fd759-129">Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.</span><span class="sxs-lookup"><span data-stu-id="fd759-129">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]