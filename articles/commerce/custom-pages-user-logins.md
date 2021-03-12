---
title: Impostare pagine personalizzate per l'accesso degli utenti
description: In questo argomento viene descritto come creare pagine personalizzate in Microsoft Dynamics 365 Commerce che consentono di gestire accessi personalizzati per gli utenti di tenant business-to-consumer (B2C) di Azure Active Directory (Azure AD).
author: brianshook
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a55da9683c43ac75109fd256e481b02a4d565914
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970080"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a>Impostare pagine personalizzate per l'accesso degli utenti


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come creare pagine personalizzate in Microsoft Dynamics 365 Commerce che consentono di gestire accessi personalizzati per gli utenti di tenant business-to-consumer (B2C) di Azure Active Directory (Azure AD).

## <a name="overview"></a>Panoramica

Per utilizzare pagine personalizzate create in Dynamics 365 Commerce per gestire flussi di accesso utente, è necessario configurare i criteri di Azure AD a cui si farà riferimento nell'ambiente di Commerce. È possibile configurare i criteri B2C di Azure AD "Iscrizione e accesso", "Modifica del profilo" e "Reimpostazione password" utilizzando l'applicazione B2C Azure AD. È quindi possibile fare riferimento ai nomi di criteri e al tenant B2C di Azure AD B durante il provisioning effettuato per l'ambiente di Commerce utilizzando Microsoft Dynamics Lifecycle Services.

Le pagine personalizzate di Commerce possono essere generate utilizzando il modulo Accesso, Iscrizione, Modifica profilo account o Reimpostazione password. Agli URL di pagina pubblicati per queste pagine personalizzate è quindi necessario fare riferimento nelle configurazioni dei criteri B2C di Azure AD nel portale di Azure.

## <a name="set-up-b2c-policies"></a>Impostare criteri B2C

Dopo l'impostazione del tenant B2C di Azure AD e l'associazione dello stesso all'ambiente di Commerce, passare alla pagina **Azure AD B2C** nel portale di Azure, quindi scegliere dal menu **Criteri** e selezionare **Flussi utente (criteri)**.

![Comando Flussi utente (criteri)](./media/B2C_CustomPage_PoliciesMenu.png)

Ora è possibile configurare i flussi di accesso utente "Iscrizione e accesso", "Modifica profilo" e "Reimpostazione password".

### <a name="configure-the-sign-up-and-sign-in-policy"></a>Configurare il criterio "Iscrizione e accesso"

Per configurare il criterio "Iscrizione e accesso", effettuare le seguenti operazioni.

1. Selezionare **Nuovo flusso utente**, quindi nella scheda **Consigliato**, selezionare il criterio **Iscrizione e accesso**.
1. Immettere un nome per il criterio (ad esempio **B2C\_1\_SignInSignUp**).
1. Nella sezione **Provider di identità**, selezionare i provider di identità da utilizzare per il criterio. È necessario che almeno **Iscrizione posta elettronica** sia selezionato.
1. Nella colonna **Raccogli l'attributo**, selezionare le caselle di controllo per **Indirizzo di posta elettronica**, **Nome** e **Cognome**.
1. Nella colonna **Restituisci l'attestazione**, selezionare le caselle di controllo **Indirizzi di posta elettronica**, **Nome**, **Provider di identità**, **Cognome** e **ID oggetto utente**.

    ![Attributi e attestazioni selezionati](./media/B2C_SignInSignUp_Attributes.png)

1. Selezionare **OK** per creare il criterio.
1. Fare doppio sul nome del nuovo criterio, quindi, nel pannello di navigazione, selezionare **Proprietà**.
1. Impostare l'opzione **Abilita JavaScript con imposizione del layout di pagina (anteprima)** su **Attivo**.

    ![La pagina delle proprietà per il nuovo criterio](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> Al nome del criterio viene fatto riferimento nell'ambiente di Commerce. Il prefisso **B2C\_1\_** verrà incluso nel riferimento. I criteri non possono essere rinominati dopo essere stati creati. Se si sostituisce un criterio esistente per l'ambiente di Commerce, è possibile eliminare il criterio originale e creare un nuovo criterio che ha lo stesso nome. In alternativa, se è già stato eseguito il provisioning dell'ambiente, è possibile inviare il nuovo criterio mediante una richiesta di assistenza.

Viene visualizzato di nuovo questo criterio per completare la configurazione dopo la creazione delle pagine personalizzate. Per il momento, chiudere il criterio per tornare alla pagina **Flussi utente (criteri)** nel portale di Azure.

### <a name="configure-the-profile-editing-policy"></a>Configurare il criterio "Modifica del profilo"

Per configurare il criterio "Modifica del profilo", effettuare le seguenti operazioni.

1. Selezionare **Nuovo flusso utente**, quindi nella scheda **Consigliato**, selezionare il criterio **Modifica del profilo**.
1. Immettere un nome per il criterio (ad esempio **B2C\_1\_EditProfile**).
1. Nella sezione **Provider di identità**, selezionare i provider di identità da utilizzare per il criterio. È necessario che sia selezionato almeno **Accesso all'account locale**.
1. Nella colonna **Raccogli l'attributo**, selezionare le caselle di controllo per **Indirizzi di posta elettronica** e **Cognome**.
1. Nella colonna **Restituisci l'attestazione**, selezionare le caselle di controllo **Indirizzi di posta elettronica**, **Nome**, **Provider di identità**, **Cognome** e **ID oggetto utente**.
1. Selezionare **OK** per creare il criterio.
1. Fare doppio sul nome del nuovo criterio, quindi, nel pannello di navigazione, selezionare **Proprietà**.
1. Impostare l'opzione **Abilita JavaScript con imposizione del layout di pagina (anteprima)** su **Attivo**.

Viene visualizzato di nuovo questo criterio per completare la configurazione dopo la creazione delle pagine personalizzate. Per il momento, chiudere il criterio per tornare alla pagina **Flussi utente (criteri)** nel portale di Azure.

### <a name="configure-the-password-reset-policy"></a>Configurare il criterio "Reimpostazione password"

Per configurare il criterio "Reimpostazione password", effettuare le seguenti operazioni.

1. Selezionare **Nuovo flusso utente**, quindi nella scheda **Anteprima**, selezionare il criterio **Reimpostazione password v1.1**.

    ![Il criterio Reimpostazione password v1.1 selezionato nella scheda Anteprima](./media/B2C_ForgetPassword_Menu.png)

1. Immettere un nome per il criterio (ad esempio **B2C\_1\_ForgetPassword**).
1. Nella sezione **Provider di identità**, selezionare **Reimposta password utilizzando l'indirizzo di posta elettronica**.
1. Nella colonna **Restituisci l'attestazione**, selezionare le caselle di controllo **Indirizzi di posta elettronica**, **Nome**, **Cognome** e **ID oggetto utente**.

    ![Attestazioni selezionate](./media/B2C_ForgetPassword_Attributes.png)

1. Selezionare **OK** per creare il criterio.
1. Fare doppio sul nome del nuovo criterio, quindi, nel pannello di navigazione, selezionare **Proprietà**.
1. Impostare l'opzione **Abilita JavaScript con imposizione del layout di pagina (anteprima)** su **Attivo**.

Viene visualizzato di nuovo questo criterio per completare la configurazione dopo la creazione delle pagine personalizzate. Per il momento, chiudere il criterio per tornare alla pagina **Flussi utente (criteri)** nel portale di Azure.

## <a name="build-the-custom-pages"></a>Creare pagine personalizzate

Per generare pagine personalizzate per gestire gli accessi utente, effettuare le operazioni indicate di seguito.

1. Negli strumenti di creazione di Commerce, accedere al proprio sito.
1. Creare i seguenti cinque modelli e cinque pagine:

    - Un modello **Accesso** e la pagina che utilizza il modulo Accesso.
    - Un modello **Iscrizione** e la pagina che utilizza il modulo Iscrizione.
    - Un modello **Reimpostazione password** e una pagina che utilizza modulo Reimpostazione password.
    - Un modello **Verifica reimpostazione password** e una pagina che utilizza il modulo Verifica reimpostazione password.
    - Un modello **Modifica profilo** e la pagina che utilizza il modulo Modifica profilo account

Quando si creano le pagine, attenersi alle seguenti indicazioni:

- Per ciascuna pagina o modulo, utilizzare il layout e lo stile più appropriati per i requisiti aziendali.
- Pubblicare tutte le pagine e gli URL che devono essere utilizzati nella configurazione B2C di Azure AD.
- Dopo la pubblicazione di pagine e URL raccogliere gli URL che devono essere utilizzati per le configurazioni dei criteri B2C di Azure AD. Un suffisso **?preloadscripts=true** viene aggiunto a ogni URL quando utilizzato.

> [!IMPORTANT]
> Non riutilizzare intestazioni e piè di pagina universali che hanno collegamenti relativi. Poiché queste pagine saranno ospitate nel dominio B2C di Azure AD quando utilizzate, solo gli URL assoluti devono essere utilizzati per tutti i collegamenti.

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a>Configurare criteri B2C di Azure AD con informazioni sulle pagine personalizzate 

Nel portale di Azure, ritornare alla pagina **Azure AD B2C** quindi nel menu, sotto **Criteri**, selezionare **Flussi utente (criteri)**.

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a>Aggiornare il criterio "Iscrizione e accesso" con informazioni sulle pagine personalizzate

Aggiornare il criterio "Iscrizione e accesso" con informazioni sulle pagine personalizzate, procedere come segue.

1. Nel criterio **Iscrizione e accesso** configurato in precedenza, nel pannello di navigazione, selezionare **Layout di pagina**.
1. Selezionare il layout **Pagina unificata per l'iscrizione o l'accesso**.
1. Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.
1. Nel campo **URI della pagina personalizzata**, immettere l'URL di accesso completo. Includere il suffisso **?preloadscripts=true**. Ad esempio, immettere ``www.<my domain>.com/sign-in?preloadscripts=true``.
1. Nel campo **Versione del layout di pagina (anteprima)** selezionare **1.2.0**.
1. Selezionare il layout **Pagina di iscrizione dell'account locale**.
1. Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.
1. Nel campo **URI della pagina personalizzata**, immettere l'URL di iscrizione completo. Includere il suffisso **?preloadscripts=true**. Ad esempio, immettere ``www.<my domain>.com/sign-up?preloadscripts=true``.
1. Nel campo **Versione del layout di pagina (anteprima)** selezionare **1.2.0**.
1. Nella sezione **Attributi utente**, effettuare le operazioni seguenti:

    1. Per gli attributi **Indirizzo di posta elettronica**, **Nome** e **Cognome**, selezionare **No** nel campo **Richiede la verifica**.
    1. Per gli attributi **Nome** e **Cognome**, selezionare **No** nel campo **Facoltativo**.

    ![Configurazione del criterio Pagina di iscrizione dell'account locale](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a>Aggiornare il criterio "Modifica profilo" con informazioni sulle pagine personalizzate

Per aggiornare il criterio "Modifica profilo" con informazioni sulle pagine personalizzate, procedere come segue.

1. Nel criterio **Modifica profilo** configurato in precedenza, nel pannello di navigazione, selezionare **Layout di pagina**.
1. Selezionare il layout **Pagina di modifica del profilo**.
1. Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.
1. Nel campo **URI della pagina personalizzata**, immettere l'URL di modifica profilo completo. Includere il suffisso **?preloadscripts=true**. Ad esempio, immettere ``www.<my domain>.com/profile-edit?preloadscripts=true``.
1. Nel campo **Versione del layout di pagina (anteprima)** selezionare **1.2.0**.
1. Nella sezione **Attributi utente**, effettuare le operazioni seguenti:

    1. Per gli attributi **Indirizzo di posta elettronica**, **Nome**, selezionare **No** nel campo **Richiede la verifica**.
    1. Per gli attributi **Nome** e **Cognome**, selezionare **No** nel campo **Facoltativo**.

### <a name="update-the-password-reset-policy-with-custom-page-information"></a>Aggiornare il criterio "Reimposta password" con informazioni sulle pagine personalizzate

Per aggiornare il criterio "Reimposta password" con informazioni sulle pagine personalizzate, procedere come segue.

1. Nel criterio **Reimposta password** configurato in precedenza, nel pannello di navigazione, selezionare **Layout di pagina**.
1. Selezionare il layout **Pagina nuova password**.
1. Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.
1. Nel campo **URI della pagina personalizzata**, immettere l'URL di reimpostazione della password completo. Includere il suffisso **?preloadscripts=true**. Ad esempio, immettere ``www.<my domain>.com/passwordreset?preloadscripts=true``.
1. Nel campo **Versione del layout di pagina (anteprima)** selezionare **1.2.0**.
1. Selezionare il layout **Pagina Verifica dell'account**.
1. Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.
1. Nel campo **URI della pagina personalizzata**, immettere l'URL di verifica della reimpostazione della password completo. Includere il suffisso **?preloadscripts=true**. Ad esempio, immettere ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.
1. Nel campo **Versione del layout di pagina (anteprima)** selezionare **1.2.0**.



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a>Personalizzazione stringhe di testo predefinite per etichette e descrizioni

Nella libreria di moduli, i moduli Accesso sono precompilati con stringhe di testo predefinite per etichette e descrizioni. È possibile personalizzare queste stringhe nel kit SDK aggiornando i valori nel file global.json per il modulo Accesso.

Ad esempio, il testo predefinito per il collegamento per la password dimenticata è **Password dimenticata?**. Quanto seguente mostra questo testo predefinito nella pagina di accesso.

![Testo predefinito per il collegamento per la password dimenticata nella pagina di accesso](./media/B2C_SignUp_ModuleFace.png)

Tuttavia, nel file global.json per il modulo Accesso della libreria di moduli, è possibile modificare il testo in **Hai dimenticato la password?**, come illustrato nella figura seguente.

![Testo del collegamento aggiornato nel file global.json del modulo Accesso](./media/B2C_CustomizingStringsForModule.png)

Una volta aggiornato il file global.json e pubblicato le modifiche, il nuovo testo del collegamento è visualizzato nel modulo Accesso in Commerce e nella pagina di accesso live.

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Distribuire un nuovo tenant di e-commerce](deploy-ecommerce-site.md)

[Creare un sito di e-commerce](create-ecommerce-site.md)

[Associare un sito Dynamics 365 Commerce a un canale online](associate-site-online-store.md)

[Gestire i file robots.txt](manage-robots-txt-files.md)

[Caricare reindirizzamenti URL in blocco](upload-bulk-redirects.md)

[Impostare un tenant B2C in Commerce](set-up-B2C-tenant.md)

[Configurare più tenant B2C in un ambiente Commerce](configure-multi-B2C-tenants.md)

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)

[Abilitare il rilevamento del punto vendita basato sull'ubicazione](enable-store-detection.md)
