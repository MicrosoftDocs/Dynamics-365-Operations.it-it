---
title: Aggiungere campi dati nelle configurazioni imposte
description: Questo argomento spiega come personalizzare le configurazioni imposte aggiungendo campi dati.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 197a2d1605dd39188841aba02a71d228c7138c54
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921191"
---
# <a name="add-data-fields-in-tax-configurations"></a><span data-ttu-id="a006e-103">Aggiungere campi dati nelle configurazioni imposte</span><span class="sxs-lookup"><span data-stu-id="a006e-103">Add data fields in tax configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a006e-104">Questo argomento spiega come personalizzare le configurazioni imposte utilizzando i [campi di dati aggiunti nell'integrazione fiscale](tax-service-add-data-fields-tax-integration-by-extension.md).</span><span class="sxs-lookup"><span data-stu-id="a006e-104">This topic explains how to customize tax configurations by using [data fields that are added in the tax integration](tax-service-add-data-fields-tax-integration-by-extension.md).</span></span>

## <a name="customize-the-tax-data-model"></a><span data-ttu-id="a006e-105">Personalizzare il modello di dati fiscali</span><span class="sxs-lookup"><span data-stu-id="a006e-105">Customize the tax data model</span></span>

1. <span data-ttu-id="a006e-106">In Microsoft Dynamics 365 Finance, vai a **Creazione di report elettronici** \> **Configurazioni imposte**.</span><span class="sxs-lookup"><span data-stu-id="a006e-106">In Microsoft Dynamics 365 Finance, go to **Electronic Reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="a006e-107">Nell'albero di configurazione seleziona **Modello di dati fiscali - Europa**.</span><span class="sxs-lookup"><span data-stu-id="a006e-107">In the configuration tree, select **Tax Data Model - Europe**.</span></span> <span data-ttu-id="a006e-108">Nel riquadro azioni, seleziona **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="a006e-108">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="a006e-109">Nella casella di dialogo a discesa, seleziona l'opzione **Modello di documento imponibile derivato da Nome: Modello di dati fiscali - Europa, Microsoft**, immetti un nome per il nuovo modello di dati fiscali, quindi seleziona **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="a006e-109">In the drop-down dialog box, select the **Taxable document model derived from Name: Tax Data Model -- Europe, Microsoft** option, enter a name for the new tax data model, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="a006e-110">Seleziona il modello di dati fiscali appena creato e quindi, nel riquadro azioni, seleziona **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="a006e-110">Select the tax data model that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="a006e-111">Espandi l'albero del modello di dati, seleziona **Righe** e quindi seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a006e-111">Expand the data model tree, select **Lines**, and then select **New**.</span></span>
6. <span data-ttu-id="a006e-112">Nella finestra di dialogo **Crea nodo** immetti un nome, specifica il tipo di elemento e quindi seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a006e-112">In the **Create node** dialog box, enter a name, specify the item type, and then select **Add**.</span></span>
7. <span data-ttu-id="a006e-113">Aggiungi eventuali colonne richieste.</span><span class="sxs-lookup"><span data-stu-id="a006e-113">Add any required columns.</span></span>
8. <span data-ttu-id="a006e-114">Nel riquadro azioni seleziona **Salva** e quindi **Completa**.</span><span class="sxs-lookup"><span data-stu-id="a006e-114">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="a006e-115">Chiudi la pagina e visualizza la versione completa del tuo modello di dati fiscali.</span><span class="sxs-lookup"><span data-stu-id="a006e-115">Close the page, and view the completed version of your tax data model.</span></span>

## <a name="customize-the-tax-configuration"></a><span data-ttu-id="a006e-116">Personalizzare la configurazione imposte</span><span class="sxs-lookup"><span data-stu-id="a006e-116">Customize the tax configuration</span></span>

1. <span data-ttu-id="a006e-117">In Finance , vai a **Creazione di report elettronici** \> **Configurazioni imposte**.</span><span class="sxs-lookup"><span data-stu-id="a006e-117">In Finance, go to **Electronic reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="a006e-118">Nell'albero di configurazione seleziona **Configurazione imposte - Europa**.</span><span class="sxs-lookup"><span data-stu-id="a006e-118">In the configuration tree, select **Tax Configuration -- Europe**.</span></span> <span data-ttu-id="a006e-119">Nel riquadro azioni, seleziona **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="a006e-119">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="a006e-120">Nella casella di dialogo a discesa, seleziona l'opzione **Configurazione del servizio per le imposte derivata da Nome: Modello di dati fiscali - Europa, Microsoft**, immetti un nome per la nuova configurazione imposte, quindi seleziona **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="a006e-120">In the drop-down dialog box, select the **Tax service configuration derived from Name: Tax Configuration -- Europe, Microsoft** option, enter a name for the new tax configuration, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="a006e-121">Seleziona la configurazione imposte appena creata e quindi, nel riquadro azioni, seleziona **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="a006e-121">Select the tax configuration that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="a006e-122">Nella sezione **Proprietà** nel campo **Modello di dati** seleziona il modello di dati fiscali personalizzato creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a006e-122">In the **Properties** section, in the **Data model** field, select the customized tax data model that you created earlier.</span></span>
6. <span data-ttu-id="a006e-123">Nel campo **Versione modello di dati** seleziona la versione completa del modello di dati fiscali.</span><span class="sxs-lookup"><span data-stu-id="a006e-123">In the **Data model version** field, select the completed version of the tax data model.</span></span>
7. <span data-ttu-id="a006e-124">Seleziona **Aggiungi** e aggiungi le misure fiscali richieste.</span><span class="sxs-lookup"><span data-stu-id="a006e-124">Select **Add**, and add the required tax measures.</span></span>
8. <span data-ttu-id="a006e-125">Nel riquadro azioni seleziona **Salva** e quindi **Completa**.</span><span class="sxs-lookup"><span data-stu-id="a006e-125">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="a006e-126">Chiudi la pagina e visualizza la versione completa della tua configurazione imposte.</span><span class="sxs-lookup"><span data-stu-id="a006e-126">Close page, and view the completed version of your tax configuration.</span></span>

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a><span data-ttu-id="a006e-127">Implementare le funzioni fiscali nella configurazione imposte personalizzata</span><span class="sxs-lookup"><span data-stu-id="a006e-127">Implement tax features in the customized tax configuration</span></span>

1. <span data-ttu-id="a006e-128">In Regulatory Configuration Services (RCS) vai a **Funzionalità di globalizzazione** \> **Imposte**.</span><span class="sxs-lookup"><span data-stu-id="a006e-128">In Regulatory Configuration Service (RCS), go to **Globalization Features** \> **Tax**.</span></span>
2. <span data-ttu-id="a006e-129">Seleziona **Aggiungi**, inserisci le informazioni sulla nuova funzione, quindi seleziona **Crea funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a006e-129">Select **Add**, enter information about the new feature, and then select **Create feature**.</span></span>
3. <span data-ttu-id="a006e-130">Nella scheda **Versioni** seleziona la funzionalità e quindi seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a006e-130">On the **Versions** tab, select the feature, and then select **Edit**.</span></span>
4. <span data-ttu-id="a006e-131">Nella scheda **Generale** nel campo **Versione di configurazione** seleziona la versione e la configurazione imposte personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a006e-131">On the **General** tab, in the **Configuration version** field, select the customized tax configuration and version.</span></span>
5. <span data-ttu-id="a006e-132">Nella finestra di dialogo **Gestisci colonne** seleziona le colonne di intestazione e riga che vuoi includere nella misura fiscale personalizzata, quindi seleziona il pulsante freccia destra per aggiungerle all'elenco **Colonne selezionate**.</span><span class="sxs-lookup"><span data-stu-id="a006e-132">In the **Manage columns** dialog box, select the header and line columns that you want to include in your customized tax measure, and then select the right arrow button to add them to the **Selected columns** list.</span></span>
