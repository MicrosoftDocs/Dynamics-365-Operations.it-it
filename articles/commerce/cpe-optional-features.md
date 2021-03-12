---
title: Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce
description: Questo argomento spiega come configurare funzionalità facoltative per un ambiente di valutazione Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6639de250557ce9a25fc2cde3807abf64b0ddc18
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993452"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="529bb-103">Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="529bb-103">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="529bb-104">Questo argomento spiega come configurare funzionalità facoltative per un ambiente di valutazione Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="529bb-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="529bb-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="529bb-105">Prerequisites</span></span>

<span data-ttu-id="529bb-106">Se si desidera valutare le funzionalità di posta elettronica transazionali, è necessario soddisfare i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="529bb-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="529bb-107">Si dispone di un server di posta elettronica disponibile (Serve Simple Mail Transfer Protocol \[SMTP\]), che può essere utilizzato dalla sottoscrizione Microsoft Azure in cui si effettua il provisioning dell'ambiente di valutazione.</span><span class="sxs-lookup"><span data-stu-id="529bb-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the evaluation environment.</span></span>
- <span data-ttu-id="529bb-108">Si dispone del nome di dominio completo (FQDN)/indirizzo IP, numero della porta SMTP e dei dettagli di autenticazione del server.</span><span class="sxs-lookup"><span data-stu-id="529bb-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="529bb-109">Configurare il back-end dell'immagine</span><span class="sxs-lookup"><span data-stu-id="529bb-109">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="529bb-110">Individuare l'URL di base multimediale</span><span class="sxs-lookup"><span data-stu-id="529bb-110">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="529bb-111">Prima di poter completare questa procedura, è necessario completare i passaggi in [Configura il tuo sito in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span><span class="sxs-lookup"><span data-stu-id="529bb-111">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="529bb-112">Accedi alla Creazione di siti Web di Commerce utilizzando l'URL di cui hai preso nota quando hai inizializzato l'e-Commerce durante il provisioning (vedere [Inizializzare l'e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="529bb-112">Sign in to the Commerce site builder by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="529bb-113">Aprire il sito **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="529bb-113">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="529bb-114">Nel menu a sinistra scegliere **Libreria multimediale**.</span><span class="sxs-lookup"><span data-stu-id="529bb-114">On the menu on the left, select **Media Library**.</span></span>
1. <span data-ttu-id="529bb-115">Selezionare qualsiasi singolo asset di immagine.</span><span class="sxs-lookup"><span data-stu-id="529bb-115">Select any single image asset.</span></span>
1. <span data-ttu-id="529bb-116">Nel controllo proprietà a destra, individuare la proprietà **URL pubblico**.</span><span class="sxs-lookup"><span data-stu-id="529bb-116">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="529bb-117">Il valore è un URL.</span><span class="sxs-lookup"><span data-stu-id="529bb-117">The value is a URL.</span></span> <span data-ttu-id="529bb-118">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="529bb-118">Here is an example:</span></span>

    <span data-ttu-id="529bb-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="529bb-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="529bb-120">Sostituire l'ultimo identificatore nell'URL (**MA1nQC** nel precedente esempio) con la stringa **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="529bb-120">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="529bb-121">Ecco come appare l'URL di esempio dopo aver apportato questa modifica:</span><span class="sxs-lookup"><span data-stu-id="529bb-121">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="529bb-122">Questo è l'URL di base multimediale.</span><span class="sxs-lookup"><span data-stu-id="529bb-122">This URL is your media base URL.</span></span> <span data-ttu-id="529bb-123">Prenderne nota.</span><span class="sxs-lookup"><span data-stu-id="529bb-123">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="529bb-124">Aggiornare l'URL di base multimediale</span><span class="sxs-lookup"><span data-stu-id="529bb-124">Update the media base URL</span></span>

1. <span data-ttu-id="529bb-125">Accedere a Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="529bb-125">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="529bb-126">Utilizzando il menu a sinistra, selezionare **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Profili canale**.</span><span class="sxs-lookup"><span data-stu-id="529bb-126">Use the menu on the left to go to **Modules \> Retail and commerce \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="529bb-127">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="529bb-127">Select **Edit**.</span></span>
1. <span data-ttu-id="529bb-128">In **Proprietà profilo**, sostituire il valore della proprietà **URL di base server multimediale** con l'URL di base multimediale creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="529bb-128">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="529bb-129">Selezionare il canale denominato **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="529bb-129">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="529bb-130">In **Proprietà profilo**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="529bb-130">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="529bb-131">Per la proprietà che è stata aggiunta, selezionare **URL di base server multimediale** come chiave proprietà.</span><span class="sxs-lookup"><span data-stu-id="529bb-131">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="529bb-132">Come valore della proprietà, inserisci l'URL di base multimediale che hai creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="529bb-132">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="529bb-133">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="529bb-133">Select **Save**.</span></span>

## <a name="configure-and-test-the-email-server"></a><span data-ttu-id="529bb-134">Configurare e testare il server di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="529bb-134">Configure and test the email server</span></span>

> [!NOTE]
> <span data-ttu-id="529bb-135">il server SMTP o il servizio di posta elettronica specificato qui deve essere accessibile dalla sottoscrizione di Azure utilizzata per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="529bb-135">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="529bb-136">Accedere a Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="529bb-136">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="529bb-137">Utilizzare il menu a sinistra per selezionare **Moduli \> Retail e Commerce \>  Impostazione sedi centrali \> Parametri \> Parametri posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="529bb-137">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Email parameters**.</span></span>
1. <span data-ttu-id="529bb-138">Nella scheda **Impostazioni SMTP**, nel campo **Server di posta in uscita**, immettere il nome FQDN o l'indirizzo IP del server SMTP o del servizio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="529bb-138">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="529bb-139">Nel campo **Numero porta SMTP** immettere il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="529bb-139">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="529bb-140">(Se non si utilizza Secure Sockets Layer \[SSL\], il numero di porta predefinito è **25** .)</span><span class="sxs-lookup"><span data-stu-id="529bb-140">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="529bb-141">Se è richiesta l'autenticazione, immettere i valori nei campi **Nome utente** e **Password**.</span><span class="sxs-lookup"><span data-stu-id="529bb-141">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="529bb-142">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="529bb-142">Select **Save**.</span></span>
1. <span data-ttu-id="529bb-143">Selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="529bb-143">Select **Refresh**.</span></span>
1. <span data-ttu-id="529bb-144">Sulla scheda **Messaggio e-mail di prova** nel campo **Provider di posta elettronica**, selezionare **SMTP**.</span><span class="sxs-lookup"><span data-stu-id="529bb-144">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="529bb-145">Nel campo **Invia a**, immettere l'indirizzo di posta elettronica a cui inviare il messaggio e-mail di prova.</span><span class="sxs-lookup"><span data-stu-id="529bb-145">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="529bb-146">Selezionare **Invia messaggio e-mail di prova**.</span><span class="sxs-lookup"><span data-stu-id="529bb-146">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="529bb-147">Configurare modelli di messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="529bb-147">Configure email templates</span></span>

<span data-ttu-id="529bb-148">Per ciascun evento transazionale per il quale si desidera inviare messaggi di posta elettronica, è necessario aggiornare il modello di messaggio di posta elettronica con un indirizzo di posta elettronica del mittente valido.</span><span class="sxs-lookup"><span data-stu-id="529bb-148">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="529bb-149">Accedere a Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="529bb-149">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="529bb-150">Utilizzare il menu a sinistra per selezionare **Moduli \> Retail e Commerce \>  Impostazione sedi centrali \> Parametri \> Modelli di posta elettronica a livello di organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="529bb-150">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="529bb-151">Selezionare **Mostra elenco**.</span><span class="sxs-lookup"><span data-stu-id="529bb-151">Select **Show list**.</span></span>
1. <span data-ttu-id="529bb-152">Per ogni modello dell'elenco, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="529bb-152">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="529bb-153">Nel campo **Indirizzo di posta elettronica del mittente** immettere l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="529bb-153">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="529bb-154">Facoltativo: nel campo **Nome mittente**, inserire il nome che dovrebbe essere usato come nome del mittente.</span><span class="sxs-lookup"><span data-stu-id="529bb-154">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="529bb-155">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="529bb-155">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="529bb-156">Personalizzare i modelli di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="529bb-156">Customize email templates</span></span>

<span data-ttu-id="529bb-157">Potresti voler personalizzare i modelli di messaggio di posta elettronica in modo che utilizzino immagini diverse.</span><span class="sxs-lookup"><span data-stu-id="529bb-157">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="529bb-158">Oppure potresti voler aggiornare i collegamenti nei modelli in modo che vadano nell'ambiente di valutazione.</span><span class="sxs-lookup"><span data-stu-id="529bb-158">Or you might want to update the links in the templates so that they go to your evaluation environment.</span></span> <span data-ttu-id="529bb-159">Questa procedura illustra come scaricare i modelli predefiniti, personalizzarli e aggiornarli nel sistema.</span><span class="sxs-lookup"><span data-stu-id="529bb-159">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="529bb-160">In un browser Web, scaricare il [file ZIP dei modelli di messaggio di posta elettronica predefiniti della valutazione di Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="529bb-160">In a web browser, download the [Microsoft Dynamics 365 Commerce Evaluation default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="529bb-161">Questo file contiene i seguenti documenti HTML:</span><span class="sxs-lookup"><span data-stu-id="529bb-161">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="529bb-162">Modello Conferma ordine</span><span class="sxs-lookup"><span data-stu-id="529bb-162">Order confirmation template</span></span>
    - <span data-ttu-id="529bb-163">Modello Emetti gift card</span><span class="sxs-lookup"><span data-stu-id="529bb-163">Issue gift card template</span></span>
    - <span data-ttu-id="529bb-164">Modello Nuovo ordine</span><span class="sxs-lookup"><span data-stu-id="529bb-164">New order template</span></span>
    - <span data-ttu-id="529bb-165">Modello Ordine di imballaggio</span><span class="sxs-lookup"><span data-stu-id="529bb-165">Pack order template</span></span>
    - <span data-ttu-id="529bb-166">Modello Preleva ordine</span><span class="sxs-lookup"><span data-stu-id="529bb-166">Pick order template</span></span>

1. <span data-ttu-id="529bb-167">Personalizzare i modelli utilizzando un editor di testo o HTML.</span><span class="sxs-lookup"><span data-stu-id="529bb-167">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="529bb-168">Vedere l'elenco dei [token supportati](#supported-tokens-in-the-email-template) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="529bb-168">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="529bb-169">Accedere a Commerce.</span><span class="sxs-lookup"><span data-stu-id="529bb-169">Sign in to Commerce.</span></span>
1. <span data-ttu-id="529bb-170">Utilizzare il menu a sinistra per selezionare **Moduli \> Amministrazione organizzazione \> Impostazione \> Modelli di posta elettronica a livello di organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="529bb-170">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="529bb-171">Espandere l'elenco a sinistra per visualizzare tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="529bb-171">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="529bb-172">Per ogni modello che si desidera personalizzare, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="529bb-172">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="529bb-173">Selezionare il modello nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="529bb-173">Select the template in the list.</span></span>
    1. <span data-ttu-id="529bb-174">In **Contenuto messaggio posta elettronica**, selezionare la versione appropriata della lingua nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="529bb-174">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="529bb-175">Il valore predefinito della lingua è **en-us**.</span><span class="sxs-lookup"><span data-stu-id="529bb-175">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="529bb-176">In **Contenuto messaggio posta elettronica**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="529bb-176">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="529bb-177">Viene visualizzato il riquadro **Carica modello di messaggio di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="529bb-177">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="529bb-178">Selezionare **Sfoglia** e trovare il file HTML con il contenuto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="529bb-178">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="529bb-179">Selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="529bb-179">Select **Upload**.</span></span> <span data-ttu-id="529bb-180">Il modello viene caricato nel sistema e viene visualizzata un'anteprima.</span><span class="sxs-lookup"><span data-stu-id="529bb-180">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="529bb-181">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="529bb-181">Select **OK**.</span></span>
    1. <span data-ttu-id="529bb-182">Facoltativo: Personalizzare la proprietà **Oggetto** del modello.</span><span class="sxs-lookup"><span data-stu-id="529bb-182">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="529bb-183">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="529bb-183">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="529bb-184">Token supportati nel modello di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="529bb-184">Supported tokens in the email template</span></span>

<span data-ttu-id="529bb-185">Durante il rendering del messaggio di posta elettronica questi token verranno sostituiti con i valori effettivi applicabili al cliente e al relativo ordine.</span><span class="sxs-lookup"><span data-stu-id="529bb-185">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="529bb-186">Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="529bb-186">Sales order</span></span>

<span data-ttu-id="529bb-187">I token seguenti si applicano a tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="529bb-187">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="529bb-188">Nome del token</span><span class="sxs-lookup"><span data-stu-id="529bb-188">Name of the token</span></span> | <span data-ttu-id="529bb-189">Token </span><span class="sxs-lookup"><span data-stu-id="529bb-189">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="529bb-190">Numero ordine</span><span class="sxs-lookup"><span data-stu-id="529bb-190">Order number</span></span>      | <span data-ttu-id="529bb-191">%salesid%</span><span class="sxs-lookup"><span data-stu-id="529bb-191">%salesid%</span></span> |
| <span data-ttu-id="529bb-192">Nome cliente</span><span class="sxs-lookup"><span data-stu-id="529bb-192">Customer's name</span></span>   | <span data-ttu-id="529bb-193">%customername%</span><span class="sxs-lookup"><span data-stu-id="529bb-193">%customername%</span></span> |
| <span data-ttu-id="529bb-194">Indirizzo di consegna</span><span class="sxs-lookup"><span data-stu-id="529bb-194">Delivery address</span></span>  | <span data-ttu-id="529bb-195">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="529bb-195">%deliveryaddress%</span></span> |
| <span data-ttu-id="529bb-196">Indirizzo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="529bb-196">Billing address</span></span>   | <span data-ttu-id="529bb-197">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="529bb-197">%customeraddress%</span></span> |
| <span data-ttu-id="529bb-198">Data ordine</span><span class="sxs-lookup"><span data-stu-id="529bb-198">Order date</span></span>        | <span data-ttu-id="529bb-199">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="529bb-199">%shipdate%</span></span> |
| <span data-ttu-id="529bb-200">Modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="529bb-200">Delivery mode</span></span>     | <span data-ttu-id="529bb-201">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="529bb-201">%modeofdelivery%</span></span> |
| <span data-ttu-id="529bb-202">Sconto</span><span class="sxs-lookup"><span data-stu-id="529bb-202">Discount</span></span>          | <span data-ttu-id="529bb-203">%discount%</span><span class="sxs-lookup"><span data-stu-id="529bb-203">%discount%</span></span> |
| <span data-ttu-id="529bb-204">IVA</span><span class="sxs-lookup"><span data-stu-id="529bb-204">Sales tax</span></span>         | <span data-ttu-id="529bb-205">%tax%</span><span class="sxs-lookup"><span data-stu-id="529bb-205">%tax%</span></span> |
| <span data-ttu-id="529bb-206">Totale ordine</span><span class="sxs-lookup"><span data-stu-id="529bb-206">Order total</span></span>       | <span data-ttu-id="529bb-207">%total%</span><span class="sxs-lookup"><span data-stu-id="529bb-207">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="529bb-208">Riga di vendita</span><span class="sxs-lookup"><span data-stu-id="529bb-208">Sales line</span></span>

<span data-ttu-id="529bb-209">I seguenti token vengono sostituiti con i valori di ogni prodotto nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="529bb-209">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="529bb-210">Inserire il token **Elenco prodotti - Inizio** all'inizio del blocco HTML che si ripete per ogni prodotto e inserire il token **Elenco prodotti - Fine** alla fine del blocco.</span><span class="sxs-lookup"><span data-stu-id="529bb-210">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="529bb-211">Nome del token</span><span class="sxs-lookup"><span data-stu-id="529bb-211">Name of the token</span></span>      | <span data-ttu-id="529bb-212">Token</span><span class="sxs-lookup"><span data-stu-id="529bb-212">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="529bb-213">Elenco prodotti - Inizio</span><span class="sxs-lookup"><span data-stu-id="529bb-213">Product list - start</span></span>   | \<!--%tablebegin.salesline% --\> |
| <span data-ttu-id="529bb-214">Elenco prodotti - Fine</span><span class="sxs-lookup"><span data-stu-id="529bb-214">Product list - end</span></span>     | \<!--%tableend.salesline%--\> |
| <span data-ttu-id="529bb-215">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="529bb-215">Product name</span></span>           | <span data-ttu-id="529bb-216">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="529bb-216">%lineproductname%</span></span> |
| <span data-ttu-id="529bb-217">descrizione</span><span class="sxs-lookup"><span data-stu-id="529bb-217">Description</span></span>            | <span data-ttu-id="529bb-218">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="529bb-218">%lineproductdescription%</span></span> |
| <span data-ttu-id="529bb-219">Quantità</span><span class="sxs-lookup"><span data-stu-id="529bb-219">Quantity</span></span>               | <span data-ttu-id="529bb-220">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="529bb-220">%linequantity%</span></span> |
| <span data-ttu-id="529bb-221">Riga prezzo unitario</span><span class="sxs-lookup"><span data-stu-id="529bb-221">Line unit price</span></span>        | <span data-ttu-id="529bb-222">%lineprice% (verify)</span><span class="sxs-lookup"><span data-stu-id="529bb-222">%lineprice% (verify)</span></span> |
| <span data-ttu-id="529bb-223">Totale voci</span><span class="sxs-lookup"><span data-stu-id="529bb-223">line item total</span></span>        | <span data-ttu-id="529bb-224">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="529bb-224">%linenetamount%</span></span> |
| <span data-ttu-id="529bb-225">Riga sconto</span><span class="sxs-lookup"><span data-stu-id="529bb-225">line discount</span></span>          | <span data-ttu-id="529bb-226">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="529bb-226">%linediscount%</span></span> |
| <span data-ttu-id="529bb-227">Data di spedizione</span><span class="sxs-lookup"><span data-stu-id="529bb-227">Ship date</span></span>              | <span data-ttu-id="529bb-228">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="529bb-228">%lineshipdate%</span></span> |
| <span data-ttu-id="529bb-229">Metodo di approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="529bb-229">Procurement method</span></span>     | <span data-ttu-id="529bb-230">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="529bb-230">%linedeliverymode%</span></span> |
| <span data-ttu-id="529bb-231">Indirizzo di consegna</span><span class="sxs-lookup"><span data-stu-id="529bb-231">delivery address</span></span>       | <span data-ttu-id="529bb-232">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="529bb-232">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="529bb-233">Unità di vendita della riga</span><span class="sxs-lookup"><span data-stu-id="529bb-233">Sales unit of the line</span></span> | <span data-ttu-id="529bb-234">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="529bb-234">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="529bb-235">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="529bb-235">Additional resources</span></span>

[<span data-ttu-id="529bb-236">Panoramica dell'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="529bb-236">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="529bb-237">Provisioning di un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="529bb-237">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="529bb-238">Configurare un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="529bb-238">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="529bb-239">Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="529bb-239">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="529bb-240">Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="529bb-240">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="529bb-241">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="529bb-241">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="529bb-242">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="529bb-242">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="529bb-243">Portale di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="529bb-243">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="529bb-244">Sito Web di Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="529bb-244">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
