---
title: Abilitare l'autenticazione Azure Active Directory per l'accesso POS
description: Questo argomento spiega come configurare l'esperienza di accesso per il punto vendita (POS) di Microsoft Dynamics 365 Commerce in modo che utilizzi l'autenticazione Azure Active Directory.
author: boycezhu
manager: annbe
ms.date: 03/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: f030e8382627191dd32d855e15432fc85dca4bbd
ms.sourcegitcommit: 1789a78de1cbeac19d96767812df653a191c67e9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2020
ms.locfileid: "3100382"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a><span data-ttu-id="d3019-103">Abilitare l'autenticazione Azure Active Directory per l'accesso POS</span><span class="sxs-lookup"><span data-stu-id="d3019-103">Enable Azure Active Directory authentication for POS sign-in</span></span>
[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="d3019-104">Molti clienti che usano Microsoft Dynamics 365 Commerce utilizzano anche altri servizi cloud Microsoft e potrebbero utilizzare Azure Active Directory (Azure AD) per gestire le credenziali dell'utente per tali servizi.</span><span class="sxs-lookup"><span data-stu-id="d3019-104">Many customers who use Microsoft Dynamics 365 Commerce also use other Microsoft cloud services, and they might use Azure Active Directory (Azure AD) to manage user credentials for those services.</span></span> <span data-ttu-id="d3019-105">In questi casi, i clienti potrebbero voler utilizzare lo stesso account Azure AD per tutte le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d3019-105">In those cases, the customers might want to use the same Azure AD account across applications.</span></span> <span data-ttu-id="d3019-106">Questo argomento spiega come configurare l'esperienza di accesso per il punto vendita (POS) di Commerce per utilizzare l'autenticazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d3019-106">This topic explains how to configure the Commerce point of sale (POS) sign-in experience to use Azure AD authentication.</span></span>

## <a name="configure-azure-ad-authentication"></a><span data-ttu-id="d3019-107">Configurare l'autenticazione Azure AD</span><span class="sxs-lookup"><span data-stu-id="d3019-107">Configure Azure AD authentication</span></span>

<span data-ttu-id="d3019-108">Per rendere Azure AD disponibile come metodo di autenticazione per l'accesso POS per un negozio, è necessario configurare le impostazioni del profilo di funzionalità del negozio e quindi applicare tali impostazioni ai client POS.</span><span class="sxs-lookup"><span data-stu-id="d3019-108">To make Azure AD available as the authentication method for POS sign-in for a store, you must configure the settings of the store's functionality profile and then apply those setting to POS clients.</span></span>

<span data-ttu-id="d3019-109">Per configurare un nuovo profilo di funzionalità, completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3019-109">To configure a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="d3019-110">Passare a **Retail e Commerce** \> **Impostazione canale** \> **Impostazione POS** \> **Profili POS** \> **Profili funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="d3019-110">Go to **Retail and Commerce** \> **Channel setup** \> **POS setup** \> **POS profiles** \> **Functionality profiles**.</span></span>
1. <span data-ttu-id="d3019-111">Selezionare il profilo di funzionalità da modificare.</span><span class="sxs-lookup"><span data-stu-id="d3019-111">Select the functionality profile to change.</span></span>
1. <span data-ttu-id="d3019-112">Nella scheda dettaglio **Funzioni**, nella sezione **Accesso personale POS**, modificare il valore del campo **Metodo di autenticazione di accesso** da **ID personale e password** in **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d3019-112">On the **Functions** FastTab, in the **POS staff logon** section, change the value of the **Logon Authentication Method** field from **Personnel ID and Password** to **Azure Active Directory**.</span></span>

<span data-ttu-id="d3019-113">Per impostazione predefinita, tutti i profili di funzionalità utilizzano **ID personale e password** come metodo di autenticazione POS.</span><span class="sxs-lookup"><span data-stu-id="d3019-113">By default, all functionality profiles use **Personnel ID and Password** as the POS authentication method.</span></span> <span data-ttu-id="d3019-114">Pertanto, è necessario modificare il valore del campo **Metodo di autenticazione di accesso** se si desidera utilizzare Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d3019-114">Therefore, you must change the value of the **Logon Authentication Method** field if you want to use Azure AD.</span></span> <span data-ttu-id="d3019-115">Ogni punto vendita al dettaglio collegato al profilo di funzionalità selezionato sarà interessato da questa modifica.</span><span class="sxs-lookup"><span data-stu-id="d3019-115">Every retail store that is linked to the selected functionality profile will be affected by this change.</span></span>

<span data-ttu-id="d3019-116">Per applicare le impostazioni ai client POS, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="d3019-116">To apply the settings to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="d3019-117">Selezionare **Retail e Commerce** \> **Vendita al dettaglio e commercio IT** \> **Programmazione della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="d3019-117">Go to **Retail and Commerce** \> **Retail and Commerce IT** \> **Distribution schedule**.</span></span>
1. <span data-ttu-id="d3019-118">Eseguire la programmazione della distribuzione **1070** (**Configurazione canale**).</span><span class="sxs-lookup"><span data-stu-id="d3019-118">Run the **1070** (**Channel configuration**) distribution schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="d3019-119">L'autenticazione Azure AD richiede una connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="d3019-119">Azure AD authentication requires an internet connection.</span></span> <span data-ttu-id="d3019-120">Non funziona quando il POS è in modalità offline.</span><span class="sxs-lookup"><span data-stu-id="d3019-120">It won't work when POS is in offline mode.</span></span>

## <a name="associate-an-azure-ad-account-with-a-worker"></a><span data-ttu-id="d3019-121">Associare un account Azure AD a un lavoratore</span><span class="sxs-lookup"><span data-stu-id="d3019-121">Associate an Azure AD account with a worker</span></span>

<span data-ttu-id="d3019-122">Prima che un addetto del negozio possa usare un account Azure AD per accedere all'applicazione POS, l'account Azure AD deve essere associato a quel lavoratore.</span><span class="sxs-lookup"><span data-stu-id="d3019-122">Before a store worker can use an Azure AD account to sign in to the POS application, the Azure AD account must be associated with that worker.</span></span>

<span data-ttu-id="d3019-123">Per associare un account Azure AD a un lavoratore, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="d3019-123">To associate an Azure AD account with a worker, follow these steps.</span></span>

1. <span data-ttu-id="d3019-124">Passare a **Retail e Commerce** \> **Dipendenti** \> **Lavoratori**.</span><span class="sxs-lookup"><span data-stu-id="d3019-124">Go to **Retail and Commerce** \> **Employees** \> **Workers**.</span></span>
1. <span data-ttu-id="d3019-125">Aprire la pagina dei dettagli per un lavoratore.</span><span class="sxs-lookup"><span data-stu-id="d3019-125">Open the details page for a worker.</span></span>
1. <span data-ttu-id="d3019-126">Nel riquadro azioni, nella scheda **Commerce**, nel gruppo **Identità esterna**, selezionare **Associa identità esistente**.</span><span class="sxs-lookup"><span data-stu-id="d3019-126">On the Action Pane, on the **Commerce** tab, in the **External identity** group, select **Associate existing identity**.</span></span>
1. <span data-ttu-id="d3019-127">Nella finestra di dialogo **Usa identità esterna esistente**, selezionare **Cerca tramite e-mail**, inserire un indirizzo e-mail Azure AD, quindi selezionare **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="d3019-127">In the **Use existing external identity** dialog box, select **Search using email**, enter an Azure AD email address, and then select **Search**.</span></span>
1. <span data-ttu-id="d3019-128">Selezionare l'account Azure AD che viene restituito, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3019-128">Select the Azure AD account that is returned, and then select **OK**.</span></span>

<span data-ttu-id="d3019-129">I campi **Alias**, **UPN** e **Identificatore secondario esterno** nella scheda **Commerce** della pagina dei dettagli del lavoratore verranno compilati.</span><span class="sxs-lookup"><span data-stu-id="d3019-129">The **Alias**, **UPN**, and **External sub identifier** fields on the **Commerce** tab of the worker's details page will be filled in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d3019-130">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d3019-130">Additional resources</span></span>

[<span data-ttu-id="d3019-131">Impostare la funzionalità di accesso esteso per MPOS e Cloud POS</span><span class="sxs-lookup"><span data-stu-id="d3019-131">Set up extended logon functionality for MPOS and Cloud POS</span></span>](extended-logon.md)

[<span data-ttu-id="d3019-132">Creare un profilo funzionalità di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="d3019-132">Create a retail functionality profile</span></span>](retail-functionality-profile.md)

[<span data-ttu-id="d3019-133"> Configurare un lavoratore</span><span class="sxs-lookup"><span data-stu-id="d3019-133">Configure a worker</span></span>](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)
