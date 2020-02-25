---
title: Configurare le funzionalità facoltative per un ambiente di anteprima Dynamics 365 Commerce
description: Questo argomento spiega come configurare funzionalità facoltative per un ambiente di anteprima di Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 43b23b9ef881b2ab2f3d005d4ba761848a7fa4ed
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024731"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-preview-environment"></a><span data-ttu-id="ae27b-103">Configurare le funzionalità facoltative per un ambiente di anteprima Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ae27b-103">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ae27b-104">Questo argomento spiega come configurare funzionalità facoltative per un ambiente di anteprima di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ae27b-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ae27b-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ae27b-105">Prerequisites</span></span>

<span data-ttu-id="ae27b-106">Se si desidera valutare le funzionalità di posta elettronica transazionali, è necessario soddisfare i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae27b-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ae27b-107">Si dispone di un server di posta elettronica disponibile (Serve Simple Mail Transfer Protocol \[SMTP\]), che può essere utilizzato dalla sottoscrizione Microsoft Azure in cui si effettua il provisioning dell'ambiente di anteprima.</span><span class="sxs-lookup"><span data-stu-id="ae27b-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the preview environment.</span></span>
- <span data-ttu-id="ae27b-108">Si dispone del nome di dominio completo (FQDN)/indirizzo IP, numero della porta SMTP e dei dettagli di autenticazione del server.</span><span class="sxs-lookup"><span data-stu-id="ae27b-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

<span data-ttu-id="ae27b-109">Se si desidera valutare le funzionalità di Gestione delle risorse digitali inserendo nuove immagini multicanale, è necessario disporre del nome del tenant del sistema di gestione dei contenuti (CMS).</span><span class="sxs-lookup"><span data-stu-id="ae27b-109">If you want to evaluate Digital Asset Management features by ingesting new omni-channel images, you must have the name of your content management system (CMS) tenant available.</span></span> <span data-ttu-id="ae27b-110">Le istruzioni per trovare questo nome sono fornite più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ae27b-110">Instructions for finding this name are provided later in this topic.</span></span> <span data-ttu-id="ae27b-111">>>> (D: dove sono le istruzioni?)</span><span class="sxs-lookup"><span data-stu-id="ae27b-111">>>>(Q: where are the instructions?)</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="ae27b-112">Configurare il back-end dell'immagine</span><span class="sxs-lookup"><span data-stu-id="ae27b-112">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="ae27b-113">Individuare l'URL di base multimediale</span><span class="sxs-lookup"><span data-stu-id="ae27b-113">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="ae27b-114">Prima di poter completare questa procedura, è necessario completare i passaggi in [Configura il tuo sito in Commerce ](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span><span class="sxs-lookup"><span data-stu-id="ae27b-114">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="ae27b-115">Accedi allo strumento di gestione del sito Commerce utilizzando l'URL di cui hai preso nota quando hai inizializzato l'e-Commerce durante il provisioning (vedi [Inizializzare l'e-Commerce ](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="ae27b-115">Sign in to the Commerce site management tool by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="ae27b-116">Aprire il sito **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-116">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="ae27b-117">Nel menu a sinistra scegliere **Risorse**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-117">On the menu on the left, select **Assets**.</span></span>
1. <span data-ttu-id="ae27b-118">Selezionare qualsiasi singolo asset di immagine.</span><span class="sxs-lookup"><span data-stu-id="ae27b-118">Select any single image asset.</span></span>
1. <span data-ttu-id="ae27b-119">Nel controllo proprietà a destra, individuare la proprietà **URL pubblico**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-119">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="ae27b-120">Il valore è un URL.</span><span class="sxs-lookup"><span data-stu-id="ae27b-120">The value is a URL.</span></span> <span data-ttu-id="ae27b-121">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="ae27b-121">Here is an example:</span></span>

    <span data-ttu-id="ae27b-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="ae27b-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="ae27b-123">Sostituire l'ultimo identificatore nell'URL (**MA1nQC** nel precedente esempio) con la stringa **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-123">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="ae27b-124">Ecco come appare l'URL di esempio dopo aver apportato questa modifica:</span><span class="sxs-lookup"><span data-stu-id="ae27b-124">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="ae27b-125">Questo è l'URL di base multimediale.</span><span class="sxs-lookup"><span data-stu-id="ae27b-125">This URL is your media base URL.</span></span> <span data-ttu-id="ae27b-126">Prenderne nota.</span><span class="sxs-lookup"><span data-stu-id="ae27b-126">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="ae27b-127">Aggiornare l'URL di base multimediale</span><span class="sxs-lookup"><span data-stu-id="ae27b-127">Update the media base URL</span></span>

1. <span data-ttu-id="ae27b-128">Accedere a Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="ae27b-128">Sign in to Dynamics 365 Retail.</span></span>
1. <span data-ttu-id="ae27b-129">Utilizzando il menu a sinistra, selezionare **Moduli \> Vendita al dettaglio \> Impostazione canale \> Profili canale**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-129">Use the menu on the left to go to **Modules \> Retail \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="ae27b-130">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-130">Select **Edit**.</span></span>
1. <span data-ttu-id="ae27b-131">In **Proprietà profilo**, sostituire il valore della proprietà **URL di base server multimediale** con l'URL di base multimediale creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ae27b-131">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="ae27b-132">Nell'elenco a sinistra, nel canale **Predefinito** selezionare l'altro canale.</span><span class="sxs-lookup"><span data-stu-id="ae27b-132">In the list on the left, under the **Default** channel, select the other channel.</span></span>
1. <span data-ttu-id="ae27b-133">In **Proprietà profilo**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-133">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="ae27b-134">Per la proprietà che è stata aggiunta, selezionare **URL di base server multimediale**come chiave proprietà.</span><span class="sxs-lookup"><span data-stu-id="ae27b-134">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="ae27b-135">Come valore della proprietà, inserisci l'URL di base multimediale che hai creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ae27b-135">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="ae27b-136">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-136">Select **Save**.</span></span>

## <a name="configure-the-email-server"></a><span data-ttu-id="ae27b-137">Configurare il server di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ae27b-137">Configure the email server</span></span>

> [!NOTE]
> <span data-ttu-id="ae27b-138">il server SMTP o il servizio di posta elettronica specificato qui deve essere accessibile dalla sottoscrizione di Azure utilizzata per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="ae27b-138">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="ae27b-139">Accedere a Retail.</span><span class="sxs-lookup"><span data-stu-id="ae27b-139">Sign in to Retail.</span></span>
1. <span data-ttu-id="ae27b-140">Utilizzando il menu a sinistra, selezionare **Moduli \> Amministrazione sistema \> Impostazioni \> Posta elettronica \> Parametri posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-140">Use the menu on the left to go to **Modules \> System administration \> Setup \> Email \> Email parameters**.</span></span>
1. <span data-ttu-id="ae27b-141">Nella scheda **Impostazioni SMTP**, nel campo **Server di posta in uscita**, immettere il nome FQDN o l'indirizzo IP del server SMTP o del servizio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ae27b-141">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="ae27b-142">Nel campo **Numero porta SMTP** immettere il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="ae27b-142">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="ae27b-143">(Se non si utilizza Secure Sockets Layer \[SSL \], il numero di porta predefinito è **25** .)</span><span class="sxs-lookup"><span data-stu-id="ae27b-143">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="ae27b-144">Se è richiesta l'autenticazione, immettere i valori nei campi **Nome utente**e **Password**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-144">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="ae27b-145">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-145">Select **Save**.</span></span>
1. <span data-ttu-id="ae27b-146">Selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-146">Select **Refresh**.</span></span>
1. <span data-ttu-id="ae27b-147">Sulla scheda **Messaggio e-mail di prova** nel campo **Provider di posta elettronica**, selezionare **SMTP**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-147">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="ae27b-148">Nel campo **Invia a**, immettere l'indirizzo di posta elettronica a cui inviare il messaggio e-mail di prova.</span><span class="sxs-lookup"><span data-stu-id="ae27b-148">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="ae27b-149">Selezionare **Invia messaggio e-mail di prova**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-149">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="ae27b-150">Configurare modelli di messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ae27b-150">Configure email templates</span></span>

<span data-ttu-id="ae27b-151">Per ciascun evento transazionale per il quale si desidera inviare messaggi di posta elettronica, è necessario aggiornare il modello di messaggio di posta elettronica con un indirizzo di posta elettronica del mittente valido.</span><span class="sxs-lookup"><span data-stu-id="ae27b-151">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="ae27b-152">Accedere a Retail.</span><span class="sxs-lookup"><span data-stu-id="ae27b-152">Sign in to Retail.</span></span>
1. <span data-ttu-id="ae27b-153">Utilizzare il menu a sinistra per selezionare **Moduli \> Amministrazione organizzazione \> Impostazione \> Modelli di posta elettronica a livello di organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-153">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="ae27b-154">Selezionare **Mostra elenco**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-154">Select **Show list**.</span></span>
1. <span data-ttu-id="ae27b-155">Per ogni modello dell'elenco, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="ae27b-155">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="ae27b-156">Nel campo **Indirizzo di posta elettronica del mittente** immettere l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="ae27b-156">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="ae27b-157">Facoltativo: nel campo **Nome mittente**, inserire il nome che dovrebbe essere usato come nome del mittente.</span><span class="sxs-lookup"><span data-stu-id="ae27b-157">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="ae27b-158">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-158">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="ae27b-159">Personalizzare i modelli di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ae27b-159">Customize email templates</span></span>

<span data-ttu-id="ae27b-160">Potresti voler personalizzare i modelli di messaggio di posta elettronica in modo che utilizzino immagini diverse.</span><span class="sxs-lookup"><span data-stu-id="ae27b-160">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="ae27b-161">Oppure potresti voler aggiornare i collegamenti nei modelli in modo che vadano nell'ambiente di anteprima.</span><span class="sxs-lookup"><span data-stu-id="ae27b-161">Or you might want to update the links in the templates so that they go to your preview environment.</span></span> <span data-ttu-id="ae27b-162">Questa procedura illustra come scaricare i modelli predefiniti, personalizzarli e aggiornarli nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ae27b-162">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="ae27b-163">In un browser Web, scaricare il [file ZIP dei modelli di messaggio di posta elettronica predefiniti dell'anteprima di Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="ae27b-163">In a web browser, download the [Microsoft Dynamics 365 Commerce Preview default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="ae27b-164">Questo file contiene i seguenti documenti HTML:</span><span class="sxs-lookup"><span data-stu-id="ae27b-164">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="ae27b-165">Modello Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="ae27b-165">Order confirmation template</span></span>
    - <span data-ttu-id="ae27b-166">Modello Emetti gift card</span><span class="sxs-lookup"><span data-stu-id="ae27b-166">Issue gift card template</span></span>
    - <span data-ttu-id="ae27b-167">Modello Nuovo ordine</span><span class="sxs-lookup"><span data-stu-id="ae27b-167">New order template</span></span>
    - <span data-ttu-id="ae27b-168">Modello Ordine di imballaggio</span><span class="sxs-lookup"><span data-stu-id="ae27b-168">Pack order template</span></span>
    - <span data-ttu-id="ae27b-169">Modello Preleva ordine</span><span class="sxs-lookup"><span data-stu-id="ae27b-169">Pick order template</span></span>

1. <span data-ttu-id="ae27b-170">Personalizzare i modelli utilizzando un editor di testo o HTML.</span><span class="sxs-lookup"><span data-stu-id="ae27b-170">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="ae27b-171">Vedere l'elenco dei [token supportati](#supported-tokens-in-the-email-template) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ae27b-171">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="ae27b-172">Accedere a Retail.</span><span class="sxs-lookup"><span data-stu-id="ae27b-172">Sign in to Retail.</span></span>
1. <span data-ttu-id="ae27b-173">Utilizzare il menu a sinistra per selezionare **Moduli \> Amministrazione organizzazione \> Impostazione \> Modelli di posta elettronica a livello di organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-173">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="ae27b-174">Espandere l'elenco a sinistra per visualizzare tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="ae27b-174">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="ae27b-175">Per ogni modello che si desidera personalizzare, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="ae27b-175">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="ae27b-176">Selezionare il modello nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ae27b-176">Select the template in the list.</span></span>
    1. <span data-ttu-id="ae27b-177">In **Contenuto messaggio posta elettronica**, selezionare la versione appropriata della lingua nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ae27b-177">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="ae27b-178">Il valore predefinito della lingua è **en-us**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-178">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="ae27b-179">In **Contenuto messaggio posta elettronica**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-179">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="ae27b-180">Viene visualizzato il riquadro **Carica modello di messaggio di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-180">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="ae27b-181">Selezionare **Sfoglia**e trovare il file HTML con il contenuto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ae27b-181">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="ae27b-182">Selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-182">Select **Upload**.</span></span> <span data-ttu-id="ae27b-183">Il modello viene caricato nel sistema e viene visualizzata un'anteprima.</span><span class="sxs-lookup"><span data-stu-id="ae27b-183">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="ae27b-184">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-184">Select **OK**.</span></span>
    1. <span data-ttu-id="ae27b-185">Facoltativo: Personalizzare la proprietà **Oggetto** del modello.</span><span class="sxs-lookup"><span data-stu-id="ae27b-185">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="ae27b-186">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ae27b-186">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="ae27b-187">Token supportati nel modello di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ae27b-187">Supported tokens in the email template</span></span>

<span data-ttu-id="ae27b-188">Durante il rendering del messaggio di posta elettronica questi token verranno sostituiti con i valori effettivi applicabili al cliente e al relativo ordine.</span><span class="sxs-lookup"><span data-stu-id="ae27b-188">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="ae27b-189">Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="ae27b-189">Sales order</span></span>

<span data-ttu-id="ae27b-190">I token seguenti si applicano a tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="ae27b-190">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="ae27b-191">Nome del token</span><span class="sxs-lookup"><span data-stu-id="ae27b-191">Name of the token</span></span> | <span data-ttu-id="ae27b-192">Token </span><span class="sxs-lookup"><span data-stu-id="ae27b-192">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="ae27b-193">Numero ordine</span><span class="sxs-lookup"><span data-stu-id="ae27b-193">Order number</span></span>      | <span data-ttu-id="ae27b-194">%salesid%</span><span class="sxs-lookup"><span data-stu-id="ae27b-194">%salesid%</span></span> |
| <span data-ttu-id="ae27b-195">Nome cliente</span><span class="sxs-lookup"><span data-stu-id="ae27b-195">Customer's name</span></span>   | <span data-ttu-id="ae27b-196">%customername%</span><span class="sxs-lookup"><span data-stu-id="ae27b-196">%customername%</span></span> |
| <span data-ttu-id="ae27b-197">Indirizzo di consegna</span><span class="sxs-lookup"><span data-stu-id="ae27b-197">Delivery address</span></span>  | <span data-ttu-id="ae27b-198">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="ae27b-198">%deliveryaddress%</span></span> |
| <span data-ttu-id="ae27b-199">Indirizzo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="ae27b-199">Billing address</span></span>   | <span data-ttu-id="ae27b-200">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="ae27b-200">%customeraddress%</span></span> |
| <span data-ttu-id="ae27b-201">Data ordine</span><span class="sxs-lookup"><span data-stu-id="ae27b-201">Order date</span></span>        | <span data-ttu-id="ae27b-202">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="ae27b-202">%shipdate%</span></span> |
| <span data-ttu-id="ae27b-203">Modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="ae27b-203">Delivery mode</span></span>     | <span data-ttu-id="ae27b-204">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="ae27b-204">%modeofdelivery%</span></span> |
| <span data-ttu-id="ae27b-205">Sconto</span><span class="sxs-lookup"><span data-stu-id="ae27b-205">Discount</span></span>          | <span data-ttu-id="ae27b-206">%discount%</span><span class="sxs-lookup"><span data-stu-id="ae27b-206">%discount%</span></span> |
| <span data-ttu-id="ae27b-207">IVA</span><span class="sxs-lookup"><span data-stu-id="ae27b-207">Sales tax</span></span>         | <span data-ttu-id="ae27b-208">%tax%</span><span class="sxs-lookup"><span data-stu-id="ae27b-208">%tax%</span></span> |
| <span data-ttu-id="ae27b-209">Totale ordine</span><span class="sxs-lookup"><span data-stu-id="ae27b-209">Order total</span></span>       | <span data-ttu-id="ae27b-210">%total%</span><span class="sxs-lookup"><span data-stu-id="ae27b-210">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="ae27b-211">Riga di vendita</span><span class="sxs-lookup"><span data-stu-id="ae27b-211">Sales line</span></span>

<span data-ttu-id="ae27b-212">I seguenti token vengono sostituiti con i valori di ogni prodotto nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="ae27b-212">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="ae27b-213">Inserire il token **Elenco prodotti - Inizio** all'inizio del blocco HTML che si ripete per ogni prodotto e inserire il token **Elenco prodotti - Fine** alla fine del blocco.</span><span class="sxs-lookup"><span data-stu-id="ae27b-213">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="ae27b-214">Nome del token</span><span class="sxs-lookup"><span data-stu-id="ae27b-214">Name of the token</span></span>      | <span data-ttu-id="ae27b-215">Token </span><span class="sxs-lookup"><span data-stu-id="ae27b-215">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="ae27b-216">Elenco prodotti - Inizio</span><span class="sxs-lookup"><span data-stu-id="ae27b-216">Product list - start</span></span>   | <span data-ttu-id="ae27b-217">\<!--%tablebegin.salesline% --\></span><span class="sxs-lookup"><span data-stu-id="ae27b-217">\<!--%tablebegin.salesline% --\></span></span> |
| <span data-ttu-id="ae27b-218">Elenco prodotti - Fine</span><span class="sxs-lookup"><span data-stu-id="ae27b-218">Product list - end</span></span>     | <span data-ttu-id="ae27b-219">\<!--%tableend.salesline%--\></span><span class="sxs-lookup"><span data-stu-id="ae27b-219">\<!--%tableend.salesline%--\></span></span> |
| <span data-ttu-id="ae27b-220">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="ae27b-220">Product name</span></span>           | <span data-ttu-id="ae27b-221">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="ae27b-221">%lineproductname%</span></span> |
| <span data-ttu-id="ae27b-222">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae27b-222">Description</span></span>            | <span data-ttu-id="ae27b-223">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="ae27b-223">%lineproductdescription%</span></span> |
| <span data-ttu-id="ae27b-224">Quantità</span><span class="sxs-lookup"><span data-stu-id="ae27b-224">Quantity</span></span>               | <span data-ttu-id="ae27b-225">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="ae27b-225">%linequantity%</span></span> |
| <span data-ttu-id="ae27b-226">Riga prezzo unitario</span><span class="sxs-lookup"><span data-stu-id="ae27b-226">Line unit price</span></span>        | <span data-ttu-id="ae27b-227">%lineprice% (verify)</span><span class="sxs-lookup"><span data-stu-id="ae27b-227">%lineprice% (verify)</span></span> |
| <span data-ttu-id="ae27b-228">Totale voci</span><span class="sxs-lookup"><span data-stu-id="ae27b-228">line item total</span></span>        | <span data-ttu-id="ae27b-229">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="ae27b-229">%linenetamount%</span></span> |
| <span data-ttu-id="ae27b-230">Riga sconto</span><span class="sxs-lookup"><span data-stu-id="ae27b-230">line discount</span></span>          | <span data-ttu-id="ae27b-231">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="ae27b-231">%linediscount%</span></span> |
| <span data-ttu-id="ae27b-232">Data di spedizione</span><span class="sxs-lookup"><span data-stu-id="ae27b-232">Ship date</span></span>              | <span data-ttu-id="ae27b-233">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="ae27b-233">%lineshipdate%</span></span> |
| <span data-ttu-id="ae27b-234">Metodo di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="ae27b-234">Procurement method</span></span>     | <span data-ttu-id="ae27b-235">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="ae27b-235">%linedeliverymode%</span></span> |
| <span data-ttu-id="ae27b-236">Indirizzo di consegna</span><span class="sxs-lookup"><span data-stu-id="ae27b-236">delivery address</span></span>       | <span data-ttu-id="ae27b-237">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="ae27b-237">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="ae27b-238">Unità di vendita della riga</span><span class="sxs-lookup"><span data-stu-id="ae27b-238">Sales unit of the line</span></span> | <span data-ttu-id="ae27b-239">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="ae27b-239">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="ae27b-240">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ae27b-240">Additional resources</span></span>

[<span data-ttu-id="ae27b-241">Panoramica dell'ambiente di anteprima Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ae27b-241">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="ae27b-242">Eseguire il provisioning dell'ambiente di anteprima di Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ae27b-242">Provision a Dynamics 365 Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="ae27b-243">Configurare un ambiente di anteprima Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ae27b-243">Configure a Dynamics 365 Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="ae27b-244">Domande frequenti sull'ambiente di anteprima Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ae27b-244">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="ae27b-245">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="ae27b-245">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="ae27b-246">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="ae27b-246">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="ae27b-247">Portale di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="ae27b-247">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="ae27b-248">Sito Web di Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ae27b-248">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
