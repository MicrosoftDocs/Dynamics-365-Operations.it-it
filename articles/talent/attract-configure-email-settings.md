---
title: Configurare le impostazioni di posta elettronica in Microsoft Dynamics 365 for Talent - Attract
description: In questo argomento viene descritto come configurare le impostazioni di posta elettronica inviata da Microsoft Dynamics 365 for Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: a8cf59064dd2f66ee50a0b0566aa712ba1f72dea
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739497"
---
# <a name="configure-email-settings"></a><span data-ttu-id="695e9-103">Configurare impostazioni di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="695e9-103">Configure email settings</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="695e9-104">Il proprio marchio è sinonimo di fiducia e consente di costruire una relazione con i candidati ancor prima che questi inviino la loro candidatura.</span><span class="sxs-lookup"><span data-stu-id="695e9-104">Your brand establishes trust and helps you build a relationship with candidates before they even apply for your positions.</span></span> <span data-ttu-id="695e9-105">Una percezione positiva del marchio attira i migliori talenti e aumenta la fedeltà dei dipendenti esistenti.</span><span class="sxs-lookup"><span data-stu-id="695e9-105">Positive brand perception attracts top talent and increases the loyalty of existing employees.</span></span> <span data-ttu-id="695e9-106">Microsoft Dynamics 365 for Talent: Attract consente di configurare i messaggi di posta elettronica di modo che riflettano il marchio della società.</span><span class="sxs-lookup"><span data-stu-id="695e9-106">Microsoft Dynamics 365 for Talent: Attract lets you configure emails so that they reflect your company's brand.</span></span> <span data-ttu-id="695e9-107">Di conseguenza, è possibile fornire un'esperienza coerente ai candidati durante il processo di candidatura.</span><span class="sxs-lookup"><span data-stu-id="695e9-107">Therefore, you can provide a consistent experience to job candidates as they progress through the application process.</span></span>

<span data-ttu-id="695e9-108">Attract consente di eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="695e9-108">Attract lets you perform these actions:</span></span>

- <span data-ttu-id="695e9-109">Configurare le impostazioni di posta elettronica in modo da utilizzare l'account del servizio di posta elettronica Microsoft Exchange della società.</span><span class="sxs-lookup"><span data-stu-id="695e9-109">Configure email settings so that your company's Microsoft Exchange email service account is used.</span></span> <span data-ttu-id="695e9-110">In questo modo, i candidati sanno che i messaggi di posta elettronica provengono dalla società.</span><span class="sxs-lookup"><span data-stu-id="695e9-110">In this way, candidates know that the emails are coming from your company.</span></span> <span data-ttu-id="695e9-111">Ad esempio, è possibile configurare le impostazioni di modo che i candidati ricevano messaggi di posta elettronica da `recruiting@contoso.com` anziché `contoso@microsoft.com`.</span><span class="sxs-lookup"><span data-stu-id="695e9-111">For example, you can configure your settings so that candidates receive emails from `recruiting@contoso.com` instead of `contoso@microsoft.com`.</span></span>
- <span data-ttu-id="695e9-112">Creare un marchio coerente per tutte le comunicazioni tramite posta elettronica impostando un'intestazione e un piè di pagina globali per i modelli di messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="695e9-112">Create consistent branding for all your email communications by setting a global header and footer for email templates.</span></span> 

> [!NOTE]
> <span data-ttu-id="695e9-113">Per configurare Attract affinché utilizzi l'account del servizio di posta elettronica della società per inviare messaggi di posta elettronica, è necessario disporre del componente aggiuntivo per l'assunzione a livello globale.</span><span class="sxs-lookup"><span data-stu-id="695e9-113">To configure Attract so that it uses your company's email service account to send email, you need the Comprehensive hiring add-on.</span></span>

## <a name="connect-an-email-service-account"></a><span data-ttu-id="695e9-114">Connettere un account del servizio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="695e9-114">Connect an email service account</span></span>

<span data-ttu-id="695e9-115">Mediante la connessione dell'account del servizio di posta elettronica della società, è possibile creare un'esperienza di posta elettronica contraddistinta dal marchio della società per i candidati.</span><span class="sxs-lookup"><span data-stu-id="695e9-115">By connecting your company's email service account, you can create a branded email experience for your job candidates.</span></span> <span data-ttu-id="695e9-116">Se non si connette l'account della società, Attract utilizza l'account predefinito, ovvero quello del servizio di posta elettronica con marchio Microsoft.</span><span class="sxs-lookup"><span data-stu-id="695e9-116">If you don't connect your company account, Attract uses the default Microsoft-branded email service account.</span></span>

1. <span data-ttu-id="695e9-117">Selezionare **Impostazioni** (il simbolo dell'ingranaggio) nell'angolo superiore destro, quindi selezionare **Interfaccia di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="695e9-117">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="695e9-118">Nella scheda **Impostazioni posta elettronica**, sotto **Account del servizio di posta elettronica**, selezionare **Connetti un account società**.</span><span class="sxs-lookup"><span data-stu-id="695e9-118">On the **Email settings** tab, under **Email service accounts**, select **Connect a company account**.</span></span>

    ![Connessione dell'account del servizio di posta elettronica della società in Attract](./media/attract-admin-email-service-accounts.png)

    <span data-ttu-id="695e9-120">Per ulteriori informazioni sulla creazione di un account di posta elettronica condiviso, vedere [Cassette postali condivise in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="695e9-120">For more information about how to create a shared email account, see [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).</span></span>

3. <span data-ttu-id="695e9-121">Nella finestra di accesso di Microsoft, accedere utilizzando le credenziali aziendali.</span><span class="sxs-lookup"><span data-stu-id="695e9-121">In the Microsoft sign-in window, sign in by using your corporate credentials.</span></span>
4. <span data-ttu-id="695e9-122">Se non è ancora stato configurato un account del servizio di posta elettronica, o se si desidera aggiungerne uno, selezionare **Aggiungi nuovo account del servizio**, quindi immettere le informazioni di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="695e9-122">If you haven't yet set up an email service account, or if you want to add a new one, select **Add new service account**, and then enter your email information.</span></span> <span data-ttu-id="695e9-123">Se si è già configurato l'account del servizio di posta elettronica da utilizzare, selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="695e9-123">If you've already set up the email service account that you want to use, select it.</span></span>

<span data-ttu-id="695e9-124">Dopo la configurazione dell'account del servizio di posta elettronica, l'account sarà visualizzato in **Account del servizio di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="695e9-124">When your email service account is successfully configured, you will see it listed under **Email service accounts**.</span></span>

## <a name="disconnect-an-email-service-account"></a><span data-ttu-id="695e9-125">Disconnettere un account del servizio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="695e9-125">Disconnect an email service account</span></span>

<span data-ttu-id="695e9-126">Se non si intende più utilizzare il dominio della società nelle comunicazioni tramite posta elettronica con Attract, è possibile disconnettere un account del servizio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="695e9-126">If you want to stop using your company's domain in email communications through Attract, you can disconnect an email service account.</span></span>

1. <span data-ttu-id="695e9-127">Selezionare **Impostazioni** (il simbolo dell'ingranaggio) nell'angolo superiore destro, quindi selezionare **Interfaccia di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="695e9-127">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="695e9-128">Nella scheda **Impostazioni posta elettronica**, sotto **Account del servizio di posta elettronica**, selezionare il pulsante **Ulteriori informazioni** (tre punti verticali) accanto all'account del servizio di posta elettronica che si desidera disconnettere.</span><span class="sxs-lookup"><span data-stu-id="695e9-128">On the **Email settings** tab, under **Email service accounts**, select the **More** button (three vertical dots) next to the email service account that you want to disconnect.</span></span>
3. <span data-ttu-id="695e9-129">Selezionare **Disconnetti account di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="695e9-129">Select **Disconnect email account**.</span></span>

    ![Disconnessione dell'account del servizio di posta elettronica della società](./media/attract-admin-disconnect-email-account.png)

4. <span data-ttu-id="695e9-131">Quando viene richiesto di confermare l'operazione, selezionare **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="695e9-131">When you're prompted to confirm the operation, select **Disconnect**.</span></span>

    ![Conferma della disconnessione dell'account del servizio di posta elettronica della società](./media/attract-admin-email-confirm-disconnect.png)

<span data-ttu-id="695e9-133">Se non si connette un altro account del servizio di posta elettronica, per i messaggi di posta elettronica inviati da Attract si utilizzerà l'account del servizio di posta elettronica con marchio Microsoft.</span><span class="sxs-lookup"><span data-stu-id="695e9-133">If you don't connect a different email service account, emails that are sent from Attract will use the default Microsoft-branded email service account.</span></span>

## <a name="configure-email-template-settings"></a><span data-ttu-id="695e9-134">Configurare le impostazioni del modello di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="695e9-134">Configure email template settings</span></span>

<span data-ttu-id="695e9-135">È possibile caricare un'immagine del logo della società e altre informazioni come intestazione con marchio per i messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="695e9-135">You can upload an image of your company's logo and other information as a branded header for your emails.</span></span> <span data-ttu-id="695e9-136">È inoltre possibile fornire collegamenti all'informativa sulla privacy e alle condizioni per l'utilizzo nei piè di pagina dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="695e9-136">You can also provide links to your privacy policy and terms of use in email footers.</span></span>

> [!NOTE]
> <span data-ttu-id="695e9-137">È necessario rispettare tutte le leggi applicabili del proprio paese o zona geografica e le leggi del paese o della zona geografica a cui è soggetto il destinatario del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="695e9-137">You must comply with all applicable laws of your country or region, and also the country or region that governs the email recipient.</span></span> <span data-ttu-id="695e9-138">Queste leggi includono le normative relative alla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="695e9-138">These laws include anti-spam regulations.</span></span>

1. <span data-ttu-id="695e9-139">Selezionare **Impostazioni** (il simbolo dell'ingranaggio) nell'angolo superiore destro, quindi selezionare **Interfaccia di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="695e9-139">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="695e9-140">Nella scheda **Impostazioni posta elettronica**, sotto **Impostazioni del modello di messaggio di posta elettronica**, trascinare l'immagine che si desidera utilizzare come intestazione dei messaggi nella casella dell'immagine, oppure fare clic sulla casella dell'immagine per cercare il file.</span><span class="sxs-lookup"><span data-stu-id="695e9-140">On the **Email settings** tab, under **Email template settings**, drag the image that you want to use as your email header into the image box, or click in the image box to browse for the file.</span></span> <span data-ttu-id="695e9-141">Per sostituire un'immagine esistente, è necessario dapprima selezionare **Rimuovi** accanto all'immagine.</span><span class="sxs-lookup"><span data-stu-id="695e9-141">To replace an existing image, you must first select **Remove** next to it.</span></span> <span data-ttu-id="695e9-142">L'immagine deve essere un file JPEG, JPG, PNG o SVG.</span><span class="sxs-lookup"><span data-stu-id="695e9-142">The image must be a JPEG, JPG, PNG, or SVG file.</span></span> <span data-ttu-id="695e9-143">La dimensione consigliata per le immagini è compresa tra 25 e 800 pixel (larghezza) e 25 e 150 pixel (altezza).</span><span class="sxs-lookup"><span data-stu-id="695e9-143">The recommended size for images is between 25 and 800 pixels wide, and between 25 and 150 pixels high.</span></span> <span data-ttu-id="695e9-144">La dimensione di file massima per l'intestazione è 1 megabyte (MB).</span><span class="sxs-lookup"><span data-stu-id="695e9-144">The maximum file size for the header is 1 megabyte (MB).</span></span>

    ![Aggiunta di un'immagine per l'intestazione di posta elettronica della società](./media/attract-admin-email-header.png)

3. <span data-ttu-id="695e9-146">Sotto **Informativa sulla privacy per le comunicazioni**, immettere un collegamento all'informativa sulla privacy della società.</span><span class="sxs-lookup"><span data-stu-id="695e9-146">Under **Your Privacy policy for communications**, provide a link to your company's privacy policy.</span></span> <span data-ttu-id="695e9-147">Sotto **Condizioni per le comunicazioni**, immettere un collegamento alle condizioni per l'utilizzo della società.</span><span class="sxs-lookup"><span data-stu-id="695e9-147">Under **Your Terms and conditions for communication**, provide a link to your company's terms of use.</span></span>

    ![Aggiunta di collegamenti all'informativa sulla privacy e alle condizioni per l'utilizzo della società per il piè di pagina dei messaggi di posta elettronica](./media/attract-admin-email-footer.png)

4. <span data-ttu-id="695e9-149">Selezionare **Salva** per salvare le impostazioni del modello di messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="695e9-149">Select **Save** to save your email template settings.</span></span>
