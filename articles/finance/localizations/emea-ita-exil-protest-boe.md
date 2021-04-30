---
title: Importazione di protesti effetti attivi
description: Questo argomento spiega come impostare e importare le informazioni di protesto da un file di protesto effetto attivo.
author: neserovleo
ms.date: 04/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: v-lenest
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: cba30ee43be761ee144e9a8d61a25ec757f55f7d
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894740"
---
# <a name="bills-of-exchange-protest-import"></a><span data-ttu-id="6e603-103">Importazione di protesti effetti attivi</span><span class="sxs-lookup"><span data-stu-id="6e603-103">Bills of exchange protest import</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6e603-104">Questo argomento spiega come impostare e importare le informazioni di protesto dal file di protesto effetto attivo ricevuto dalla banca.</span><span class="sxs-lookup"><span data-stu-id="6e603-104">This topic explains how to set up and import Protest information from the electronic Bill of exchange protest file received from the bank.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6e603-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6e603-105">Prerequisites</span></span>

<span data-ttu-id="6e603-106">Prima di poter utilizzare la funzionalità di importazione del protesto effetto attivo, devono essere soddisfatti i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="6e603-106">Before you can use the Bill of exchange protest import functionality, the following prerequisites must be met:</span></span>

- <span data-ttu-id="6e603-107">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="6e603-107">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="6e603-108">La funzione di gestione di protesti per effetti attivi deve essere attivata nell'area di lavoro **Gestione delle funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="6e603-108">The Protest handling for bills of exchange feature must be turned on in the **Feature management** workspace.</span></span> <span data-ttu-id="6e603-109">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6e603-109">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="import-electronic-reporting-configurations"></a><span data-ttu-id="6e603-110">Importare configurazioni per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="6e603-110">Import Electronic reporting configurations</span></span>

<span data-ttu-id="6e603-111">La configurazione per la creazione di report elettronici, **Protesto effetto attivo RIBA (IT)**, deve essere importata da LCS prima di poterla utilizzare.</span><span class="sxs-lookup"><span data-stu-id="6e603-111">The Electronic Reporting configuration, **RIBA bill of exchange protest (IT)**, must be imported from LCS before you can use it.</span></span> <span data-ttu-id="6e603-112">Dopo aver importato la configurazione, il corrispondente **Modello di pagamento** e il **Mapping di modello di pagamento alle configurazioni RIBA di destinazione** verrà importato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6e603-112">After you import the configuration, the corresponding **Payment model** and **Payment model mapping to destination RIBA configurations** will be imported automatically.</span></span>

## <a name="set-up-method-of-payment"></a><span data-ttu-id="6e603-113">Imposta metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="6e603-113">Set up method of payment</span></span>

<span data-ttu-id="6e603-114">Nella pagina **Metodo di pagamento - clienti**, abilitare il parametro **Formato di importazione elettronica generico**, quindi selezionare **Protesto effetto attivo RIBA (IT)**.</span><span class="sxs-lookup"><span data-stu-id="6e603-114">On the **Method of payments – customers** page, enable the **Generic electronic import format** parameter, and then select **RIBA bill of exchange protest (IT)**.</span></span> 

## <a name="import-protest-information-from-an-electronic-file"></a><span data-ttu-id="6e603-115">Importare le informazioni del protesto da un file elettronico</span><span class="sxs-lookup"><span data-stu-id="6e603-115">Import protest information from an electronic file</span></span>

1. <span data-ttu-id="6e603-116">Per importare il file, creare un giornale di registrazione  **Protesta effetto attivo**, quindi selezionare **Righe giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="6e603-116">To import the file, create a **Protest bill of exchange** journal, and then select **Journal lines**.</span></span>
2. <span data-ttu-id="6e603-117">Selezionare **Funzioni** \> **Importa protesto**.</span><span class="sxs-lookup"><span data-stu-id="6e603-117">Select **Functions** \> **Import protest**.</span></span>
3. <span data-ttu-id="6e603-118">Nella finestra di dialogo selezionare il metodo di pagamento per l'importazione del protesto e allegare il file.</span><span class="sxs-lookup"><span data-stu-id="6e603-118">In the dialog box, select the method of payment for the protest import, and then attach the file.</span></span> <span data-ttu-id="6e603-119">Le righe del giornale di registrazione vengono create in base alle informazioni nel file.</span><span class="sxs-lookup"><span data-stu-id="6e603-119">The journal lines are created based on information in the file.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]