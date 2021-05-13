---
title: Impostare pagine personalizzate per l'accesso degli utenti
description: In questo argomento viene descritto come creare pagine personalizzate in Microsoft Dynamics 365 Commerce che consentono di gestire accessi personalizzati per gli utenti di tenant business-to-consumer (B2C) di Azure Active Directory (Azure AD).
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d4a1c2f45d77c3ff9a7bb4dffaf12d877dc04e69
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936782"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a>Impostare pagine personalizzate per l'accesso degli utenti

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come creare pagine personalizzate in Microsoft Dynamics 365 Commerce che consentono di gestire accessi personalizzati per gli utenti di tenant business-to-consumer (B2C) di Azure Active Directory (Azure AD).

Per utilizzare pagine personalizzate create in Dynamics 365 Commerce per gestire flussi di accesso utente, è necessario configurare i criteri di Azure AD a cui si farà riferimento nell'ambiente di Commerce. È possibile configurare i criteri B2C di Azure AD "Iscrizione e accesso", "Modifica del profilo" e "Reimpostazione password" utilizzando l'applicazione B2C Azure AD. È quindi possibile fare riferimento ai nomi di criteri e al tenant B2C di Azure AD B durante il provisioning effettuato per l'ambiente di Commerce utilizzando Microsoft Dynamics Lifecycle Services.

Le pagine personalizzate di Commerce possono essere generate utilizzando il modulo Accesso, Iscrizione, Modifica profilo account, Reimpostazione password o AAD generico. Agli URL di pagina pubblicati per queste pagine personalizzate è quindi necessario fare riferimento nelle configurazioni dei criteri B2C di Azure AD nel portale di Azure.

> [!WARNING] 
> Azure AD B2C ritirerà i vecchi flussi di utenti (legacy) entro il 1° agosto 2021. Pertanto, è necessario pianificare la migrazione dei flussi utente alla nuova versione consigliata. La nuova versione fornisce funzionalità uguali e nuove funzionalità. Per ulteriori informazioni, vedi [Flussi utente in Azure Active Directory B2C](/azure/active-directory-b2c/user-flow-overview).

>La libreria del modulo per Commerce versione 10.0.15 o successiva deve essere utilizzata con i flussi utente B2C consigliati. Le pagine dei criteri utente predefiniti offerte in Azure AD B2C possono essere utilizzate e consentono l'aggiunta di immagini di sfondo, del logo e del colore di sfondo relativi al marchio aziendale. Sebbene più limitate in capacità di progettazione, le pagine dei criteri utente predefiniti forniscono la funzionalità dei criteri Azure AD B2C senza creare e configurare pagine personalizzate dedicate. 

## <a name="set-up-b2c-policies"></a>Impostare criteri B2C

Dopo l'impostazione del tenant B2C di Azure AD e l'associazione dello stesso all'ambiente di Commerce, passare alla pagina **Azure AD B2C** nel portale di Azure, quindi scegliere dal menu **Criteri** e selezionare **Flussi utente (criteri)**.

![Comando Flussi utente (criteri)](./media/B2C_CustomPage_PoliciesMenu.png)

Ora è possibile configurare i flussi di accesso utente "Iscrizione e accesso", "Modifica profilo" e "Reimpostazione password".

### <a name="configure-the-sign-up-and-sign-in-policy"></a>Configurare il criterio "Iscrizione e accesso"

Per configurare il criterio "Iscrizione e accesso", effettuare le seguenti operazioni.

1. Seleziona **Nuovo flusso utente**, seleziona **Iscrizione e accesso**, seleziona la scheda **Consigliato** e quindi seleziona **Crea**.
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

1. Seleziona **Nuovo flusso utente**, seleziona **Modifica profilo**, seleziona la scheda **Consigliato** e quindi seleziona **Crea**.
1. Immettere un nome per il criterio (ad esempio **B2C\_1\_EditProfile**).
1. Nella sezione **Provider di identità**, selezionare i provider di identità da utilizzare per il criterio. È necessario che sia selezionato almeno **Accesso all'account locale**.
1. Nella colonna **Raccogli l'attributo**, seleziona le caselle di controllo per **Nome specificato** e **Cognome**.
1. Nella colonna **Restituisci l'attestazione**, selezionare le caselle di controllo **Indirizzi di posta elettronica**, **Nome**, **Provider di identità**, **Cognome** e **ID oggetto utente**.
1. Selezionare **OK** per creare il criterio.
1. Fare doppio sul nome del nuovo criterio, quindi, nel pannello di navigazione, selezionare **Proprietà**.
1. Impostare l'opzione **Abilita JavaScript con imposizione del layout di pagina (anteprima)** su **Attivo**.

Viene visualizzato di nuovo questo criterio per completare la configurazione dopo la creazione delle pagine personalizzate. Per il momento, chiudere il criterio per tornare alla pagina **Flussi utente (criteri)** nel portale di Azure.

### <a name="configure-the-password-reset-policy"></a>Configurare il criterio "Reimpostazione password"

Per configurare il criterio "Reimpostazione password", effettuare le seguenti operazioni.

1. Seleziona **Nuovo flusso di utenti**, quindi seleziona l'opzione **Reimpostazione della password** e scegli la scheda **Consigliato** e fai clic su **Crea**.
1. Immettere un nome per il criterio (ad esempio **B2C\_1\_ForgetPassword**).
1. Nella sezione **Provider di identità**, selezionare **Reimposta password utilizzando l'indirizzo di posta elettronica**.
1. Nella colonna **Restituisci l'attestazione**, selezionare le caselle di controllo **Indirizzi di posta elettronica**, **Nome**, **Cognome** e **ID oggetto utente**.
1. Selezionare **OK** per creare il criterio.
1. Fare doppio sul nome del nuovo criterio, quindi, nel pannello di navigazione, selezionare **Proprietà**.
1. Impostare l'opzione **Abilita JavaScript con imposizione del layout di pagina (anteprima)** su **Attivo**.

Viene visualizzato di nuovo questo criterio per completare la configurazione dopo la creazione delle pagine personalizzate. Per il momento, chiudere il criterio per tornare alla pagina **Flussi utente (criteri)** nel portale di Azure.

## <a name="build-the-custom-pages"></a>Creare pagine personalizzate

I moduli Azure AD dedicati sono inclusi in Commerce per creare pagine personalizzate per i criteri utente Azure AD B2C. Le pagine possono essere create specificamente per il layout di ciascuna pagina dei criteri utente utilizzando il modulo principale Azure AD B2C descritto di seguito. In alternativa, il modulo **AAD Generico** può essere utilizzato per tutti i layout di pagina e i criteri in Azure AD B2C (anche per le opzioni di layout di pagina all'interno di criteri non elencati di seguito). 

- I moduli Azure AD specifici della pagina sono associati agli elementi di input dei dati sottoposti a rendering da Azure AD B2C. Questi moduli ti danno un maggiore controllo sul posizionamento degli elementi nelle tue pagine. Tuttavia, potrebbe essere necessario creare più pagine ed estensioni del modulo per tenere conto delle variazioni oltre le impostazioni predefinite descritte di seguito.
- Il modulo **AAD Generico** crea l'elemento "div" per Azure AD B2C per eseguire il rendering di tutti gli elementi nel layout della pagina dei criteri utente, dando maggiore flessibilità alle funzioni B2C della pagina, ma meno controllo del posizionamento e dello stile (sebbene CSS possa essere utilizzato per ottenere l'aspetto del tuo sito).

Puoi creare una singola pagina con il modulo **AAD Generico** e utilizzarlo per tutte le pagine dei criteri utente oppure puoi creare pagine specifiche utilizzando i singoli moduli Azure AD per l'accesso, la registrazione, la modifica del profilo, la reimpostazione della password e la verifica della reimpostazione della password. Puoi anche usare una combinazione di entrambi, usando le pagine specifiche Azure AD per i layout di pagina indicati di seguito e la pagina del modulo AAD generico per i layout di pagina rimanenti all'interno di queste o altre pagine dei criteri utente.

Per saperne di più sui moduli Azure AD forniti con la libreria dei moduli, leggi [Pagine e moduli di gestione delle identità](identity-mgmt-modules.md).

Per generare pagine personalizzate con moduli di identità specifici per gestire gli accessi utente, effettua le operazioni indicate di seguito.

1. In Creazione di siti Web di Commerce, accedere al sito.
1. Crea i seguenti cinque modelli e pagine (se non sono già presenti nel tuo sito):
    - Un modello **Accesso** e la pagina che utilizza il modulo Accesso.
    - Un modello **Iscrizione** e la pagina che utilizza il modulo Iscrizione.
    - Un modello **Reimpostazione password** e una pagina che utilizza modulo Reimpostazione password.
    - Un modello **Verifica reimpostazione password** e una pagina che utilizza il modulo Verifica reimpostazione password.
    - Un modello **Modifica profilo** e la pagina che utilizza il modulo Modifica profilo account.

Quando si creano le pagine, attenersi alle seguenti indicazioni:

- Per ciascuna pagina o modulo, utilizzare il layout e lo stile più appropriati per i requisiti aziendali.
- Pubblicare tutte le pagine e gli URL che devono essere utilizzati nella configurazione B2C di Azure AD.
- Dopo la pubblicazione di pagine e URL raccogliere gli URL che devono essere utilizzati per le configurazioni dei criteri B2C di Azure AD. Un suffisso **?preloadscripts=true** viene aggiunto a ogni URL quando utilizzato.

> [!IMPORTANT]
> Le pagine create per essere utilizzate in Azure AD B2C sono servite direttamente dal dominio del tenant Azure AD B2C. Non riutilizzare intestazioni e piè di pagina universali che hanno collegamenti relativi. Poiché queste pagine saranno ospitate nel dominio B2C di Azure AD quando utilizzate, solo gli URL assoluti devono essere utilizzati per tutti i collegamenti. Si consiglia di creare un'intestazione e un piè di pagina specifici con URL assoluti per le pagine personalizzate correlate ad Azure AD, con qualsiasi modulo specifico di Commerce che richiede la rimozione della connessione a Retail Server. Ad esempio, i preferiti, la barra di ricerca, il collegamento di accesso e i moduli del carrello non devono essere inclusi in nessuna pagina che verrà utilizzata nei flussi utente di Azure AD B2C.

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a>Configurare criteri B2C di Azure AD con informazioni sulle pagine personalizzate 

Nel portale di Azure, ritornare alla pagina **Azure AD B2C** quindi nel menu, sotto **Criteri**, selezionare **Flussi utente (criteri)**.

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a>Aggiornare il criterio "Iscrizione e accesso" con informazioni sulle pagine personalizzate

Aggiornare il criterio "Iscrizione e accesso" con informazioni sulle pagine personalizzate, procedere come segue.

1. Nel criterio **Iscrizione e accesso** configurato in precedenza, nel pannello di navigazione, selezionare **Layout di pagina**.
1. Selezionare il layout **Pagina unificata per l'iscrizione o l'accesso**.
1. Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.
1. Nel campo **URI della pagina personalizzata**, immettere l'URL di accesso completo. Includere il suffisso **?preloadscripts=true**. Ad esempio, immettere ``www.<my domain>.com/sign-in?preloadscripts=true``.
1. Nel campo **Versione layout di pagina** seleziona la versione **2.1.0** o successiva (richiede la libreria di moduli per Commerce versione 10.0.15 o successiva).
1. Selezionare **Salva**.
1. Selezionare il layout **Pagina di iscrizione dell'account locale**.
1. Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.
1. Nel campo **URI della pagina personalizzata**, immettere l'URL di iscrizione completo. Includere il suffisso **?preloadscripts=true**. Ad esempio, immettere ``www.<my domain>.com/sign-up?preloadscripts=true``.
1. Nel campo **Versione layout di pagina** seleziona la versione **2.1.0** o successiva (richiede la libreria di moduli per Commerce versione 10.0.15 o successiva).
1. Nella sezione **Attributi utente**, effettuare le operazioni seguenti:
    1. Per gli attributi **Nome** e **Cognome** seleziona **No** nel campo **Richiede la verifica**.
    1. Per l'attributo **Indirizzo e-mail**, si consiglia di lasciare il valore predefinito **Sì** selezionato nella colonna **Richiede la verifica**. Questa opzione garantisce che gli utenti che si registrano con un determinato indirizzo e-mail verifichino di essere proprietari dell'indirizzo e-mail.
    1. Per gli attributi **Indirizzo di posta elettronica**, **Nome** e **Cognome**, selezionare **No** nella colonna **Facoltativo**.
1. Selezionare **Salva**.

    ![Configurazione del criterio Pagina di iscrizione dell'account locale](./media/B2C_SignInSignUp_Recommended_PageLayoutExample.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a>Aggiornare il criterio "Modifica profilo" con informazioni sulle pagine personalizzate

Per aggiornare il criterio "Modifica profilo" con informazioni sulle pagine personalizzate, procedere come segue.

1. Nel criterio **Modifica profilo** configurato in precedenza, nel pannello di navigazione, selezionare **Layout di pagina**.
1. Seleziona il layout **Pagina di modifica del profilo** (potrebbe essere necessario scorrere verso il basso per vedere altre opzioni di layout, a seconda dello schermo).
1. Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.
1. Nel campo **URI della pagina personalizzata**, immettere l'URL di modifica profilo completo. Includere il suffisso **?preloadscripts=true**. Ad esempio, immettere ``www.<my domain>.com/profile-edit?preloadscripts=true``.
1. Per il campo **Versione layout di pagina** seleziona la versione **2.1.0** o successiva (richiede la libreria di moduli per Commerce versione 10.0.15 o successiva).
1. Nella sezione **Attributi utente**, effettuare le operazioni seguenti:
    1. Per gli attributi **Nome** e **Cognome**, selezionare **No** nella colonna **Facoltativo**.
    1. Per gli attributi **Nome** e **Cognome** seleziona **No** nella colonna **Richiede la verifica**.
1. Selezionare **Salva**.

### <a name="update-the-password-reset-policy-with-custom-page-information"></a>Aggiornare il criterio "Reimposta password" con informazioni sulle pagine personalizzate

Per aggiornare il criterio "Reimposta password" con informazioni sulle pagine personalizzate, procedere come segue.

1. Nel criterio **Reimposta password** configurato in precedenza, nel pannello di navigazione, selezionare **Layout di pagina**.
1. Seleziona il layout **Pagina password dimenticata**.
1. Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.
1. Nel campo **URI della pagina personalizzata**, immettere l'URL di verifica della reimpostazione della password completo. Includere il suffisso **?preloadscripts=true**. Ad esempio, immettere ``www.<my domain>.com/password-reset-verification?preloadscripts=true``.
1. Nel campo **Versione layout di pagina** seleziona la versione **2.1.0** o successiva (richiede la libreria di moduli per Commerce versione 10.0.15 o successiva).
2. Selezionare **Salva**.
3. Seleziona il layout **Pagina modifica password**.
4. Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.
5. Nel campo **URI della pagina personalizzata**, immettere l'URL di reimpostazione della password completo. Includere il suffisso **?preloadscripts=true**. Ad esempio, immettere ``www.<my domain>.com/password-reset?preloadscripts=true``.
6. Nel campo **Versione layout di pagina** seleziona la versione **2.1.0** o successiva (richiede la libreria di moduli per Commerce versione 10.0.15 o successiva).
7. Selezionare **Salva**.

## <a name="customize-default-text-strings-for-labels-and-descriptions"></a>Personalizzazione stringhe di testo predefinite per etichette e descrizioni

Nella libreria di moduli, i moduli Accesso sono precompilati con stringhe di testo predefinite per etichette e descrizioni. Puoi personalizzare le stringhe nel riquadro delle proprietà del modulo su cui stai lavorando. Stringhe aggiuntive nella pagina (come il testo del collegamento **Password dimenticata?** o il testo della chiamata all'azione **Crea un account**) richiederà l'utilizzo dell'SDK di Commerce e l'aggiornamento dei valori nel file global.json per il modulo di accesso.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]