---
title: Configurare più tenant B2C in un ambiente Commerce
description: Questo argomento descrive quando e come impostare più tenant per canale Microsoft Azure Active Directory (Azure AD) business-to-consumer (B2C) per l'autenticazione dell'utente in un ambiente Dynamics 365 Commerce dedicato.
author: BrianShook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-12
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2ddc8cea42ab0b5a319d4725ce8c75e57529cc63
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477758"
---
# <a name="configure-multiple-b2c-tenants-in-a-commerce-environment"></a>Configurare più tenant B2C in un ambiente Commerce

[!include [banner](includes/banner.md)]

Questo argomento descrive quando e come impostare più tenant Microsoft Azure Active Directory (Azure AD) business-to-consumer (B2C) per l'autenticazione dell'utente in un ambiente Dynamics 365 Commerce dedicato.

Dynamics 365 Commerce usa il servizio di identità cloud Azure AD B2C per supportare le credenziali dell'utente e i flussi di autenticazione. Gli utenti possono utilizzare i flussi di autenticazione per iscriversi, accedere e reimpostare la propria password. Azure AD B2C memorizza le informazioni di autenticazione sensibili di un utente, come il nome utente e la password. Il record utente è univoco per ciascun tenant B2C e utilizza le credenziali del nome utente (indirizzo e-mail) o del provider di identità social.

Nella maggior parte dei casi, un singolo tenant Azure AD B2C viene utilizzato in un ambiente Commerce. I clienti di Commerce possono quindi creare e pubblicare più siti nello stesso ambiente Commerce e le stesse credenziali dei clienti verranno utilizzate in questi siti. Tuttavia, se i siti nell'ambiente devono essere trattati come marchi diversi e apparire agli utenti come attività separate, è possibile configurare un tenant B2C per il canale utilizzato per la separazione sito/marchio.

## <a name="considerations-when-multiple-b2c-tenants-are-set-up-per-channel"></a>Considerazioni sull'impostazione di più tenant B2C per canale

Spesso, quando ogni canale o sito viene trattato come un'attività separata, l'opzione migliore per quanto riguarda i flussi di autenticazione dell'utente in Commerce è quella di utilizzare persone giuridiche separate. Tuttavia, se si desidera mantenere ogni canale/sito nello stesso ambiente e persona giuridica, ma si desidera disporre di un'autenticazione utente separata per ciascun sito, è importante considerare i seguenti punti prima di procedere:

- Gli utenti avranno proprie credenziali distinte per ciascun canale/sito.

    La stessa persona può avere due account separati per canale/sito in quanto ogni account è una voce univoca in un tenant B2C separato.

- Nell'ambiente Microsoft Dynamics, vengono restituiti record separati dei clienti per le ricerche dei record globali.

    Se un utente utilizza lo stesso indirizzo e-mail tra canali/siti, le ricerche globali dei clienti restituiranno risultati per ciascun canale/sito. (Verrà mostrato un indicatore di canale.)

- La rubrica può essere utilizzata per aiutare gli utenti del gruppo, in modo che possano essere monitorati per canale.
- Il numero di record dei clienti per canale potrebbe aumentare e questo aumento potrebbe influire sulle prestazioni delle ricerche globali dei clienti.
- I tenant B2C devono essere accuratamente mappati su un canale, per aiutare a prevenire situazioni in cui i clienti si registrano a un tenant errato. In caso contrario, possono verificarsi problemi di tracciamento o confusione.

La seguente illustrazione mostra più tenant B2C in un ambiente Commerce.

![Più tenant B2C in un ambiente Commerce](media/MultiB2C_In_Environment.png)

Se si decide che l'azienda richiede tenant B2C distinti per canale nello stesso ambiente Commerce, completare le procedure nelle sezioni seguenti per richiedere questa funzione.

## <a name="request-that-b2c-per-channel-be-enabled-in-your-environment"></a>Richiedere che B2C per canale sia abilitato nell'ambiente

Attualmente, se si desidera che tenant B2C distinti per canale siano disponibili nello stesso ambiente Commerce, è necessario inviare una richiesta a Dynamics 365 Commerce. Per ulteriori informazioni, vedere [Ottenere supporto per Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) o discutere questo problema con il contatto per le soluzioni Commerce.

## <a name="configure-b2c-tenants-in-your-environment"></a>Configurare i tenant B2C nell'ambiente

Per configurare i tenant B2C nell'ambiente, completare le procedure pertinenti in questa sezione.

### <a name="add-an-azure-ad-b2c-tenant"></a>Aggiungere un tenant Azure AD B2C

Per aggiungere un tenant Azure AD B2C all'ambiente, attenersi alla seguente procedura.

1. Accedere a Creazione di siti Commerce per l'ambiente come amministratore di sistema. Per configurare i tenant Azure AD B2C è necessario essere un amministratore di sistema per l'ambiente Commerce.
1. Nel riquadro di spostamento sinistro, selezionare **Impostazioni tenant** per espanderlo.
1. Selezionare **Impostazioni B2C** e quindi selezionare **Gestisci**.
1. Selezionare **Aggiungi applicazione B2C**, quindi immettere le seguenti informazioni:

    - **Nome applicazione**: immettere il nome da utilizzare per l'applicazione nel contesto di gestione in Commerce. Si consiglia di utilizzare il nome dell'applicazione che è stato scelto durante l'impostazione dell'applicazione Azure AD B2C nel portale di Azure. In questo modo, è possibile ridurre la confusione quando si gestiscono i tenant B2C in Commerce.
    - **Nome tenant**: immettere il nome del tenant B2C come appare nel portale di Azure.
    - **ID criteri password dimenticata**: immettere l'ID criteri (il nome dei criteri nel portale di Azure).
    - **ID criteri di iscrizione/accesso**: immettere l'ID criteri (il nome dei criteri nel portale di Azure).
    - **GUID client**: immettere l'ID tenant Azure AD B2C come appare nel portale di Azure (non l'ID applicazione per il tenant B2C).
    - **ID criteri di modifica del profilo**: immettere l'ID criteri (il nome dei criteri nel portale di Azure).

1. Dopo aver inserito queste informazioni, selezionare **OK** per salvare le modifiche.

> [!NOTE]
> Lasciare i campi come **Scopo**, **ID criteri non interattivi**, **ID client non interattivo**, **Dominio personalizzato per l'accesso** e **ID criteri di iscrizione** vuoti a meno che il team Dynamics 365 Commerce non indichi diversamente.
Il nuovo tenant Azure AD B2C ora è presente nell'elenco in **Gestisci applicazioni B2C**.

### <a name="manage-or-delete-an-azure-ad-b2c-tenant"></a>Gestire o eliminare un tenant Azure AD B2C

1. Accedere a Creazione di siti Commerce per l'ambiente come amministratore di sistema. Per configurare i tenant Azure AD B2C è necessario essere un amministratore di sistema per l'ambiente Commerce.
1. Nel riquadro di spostamento sinistro, selezionare **Impostazioni tenant** per espanderlo.
1. Selezionare **Impostazioni B2C** e quindi selezionare **Gestisci**.
1. Per modificare un tenant B2C, selezionare il simbolo della matita accanto ad esso. Per eliminare un tenant B2C, selezionare il simbolo del cestino accanto ad esso.
1. Selezionare **Salva**, quindi selezionare **Pubblica** per attivare le modifiche.

> [!WARNING]
> Quando un tenant B2C è configurato per un sito online/pubblicato, gli utenti potrebbero aver effettuato la registrazione utilizzando gli account presenti nel tenant. Se si elimina un tenant configurato nel menu **Impostazioni tenant \> Tenant B2C**, si rimuove l'associazione di quel tenant B2C dai siti associati a tutti i canali del tenant. In questo caso, gli utenti non sono più in grado di accedere ai loro account. Pertanto, prestare la massima attenzione quando si elimina un tenant configurato.
>
> Quando un tenant configurato viene eliminato, il tenant e i record B2C continueranno a essere mantenuti, ma la configurazione del sistema Commerce di quel tenant verrà modificata o rimossa. Gli utenti che tentano di registrarsi o accedere al sito creeranno un nuovo record di account nel tenant B2C predefinito o appena associato che è configurato per il canale del sito.
## <a name="configure-your-channel-with-a-b2c-tenant"></a>Configurare il canale con un tenant B2C

1. Accedere a Creazione di siti Commerce per l'ambiente come amministratore di sistema. Per configurare i tenant Azure AD B2C è necessario essere un amministratore di sistema per l'ambiente Commerce.
1. Nel riquadro di spostamento sinistro, selezionare **Impostazioni sito** per espanderlo.
1. Selezionare **Canali**, quindi selezionare il canale da configurare.
1. Nel riquadro delle proprietà a destra, nel campo **Seleziona applicazione B2C**, selezionare il tenant Azure AD B2C configurato da utilizzare per questo canale.
1. Sulla barra dei comandi, selezionare **Salva e pubblica** per eseguire il commit della configurazione nuova o aggiornata.

> [!WARNING]
> Se si modifica l'applicazione B2C assegnata al canale, si rimuovono i riferimenti correnti che sono stati stabiliti per tutti gli utenti che si sono già registrati nell'ambiente. In questo caso, le credenziali associate all'applicazione B2C attualmente assegnata non saranno disponibili per gli utenti. Pertanto, cambiare una configurazione di canale Azure AD B2C solo se il canale è stato configurato per la prima volta e nessun utente è stato in grado di registrarsi. In caso contrario, gli utenti potrebbero dover registrarsi di nuovo per stabilire un record nel nuovo tenant Azure AD B2C.
## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Distribuire un nuovo tenant di e-commerce](deploy-ecommerce-site.md)

[Creare un sito di e-commerce](create-ecommerce-site.md)

[Associare un sito Dynamics 365 Commerce a un canale online](associate-site-online-store.md)

[Gestire i file robots.txt](manage-robots-txt-files.md)

[Caricare reindirizzamenti URL in blocco](upload-bulk-redirects.md)

[Impostare un tenant B2C in Commerce](set-up-B2C-tenant.md)

[Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)

[Abilitare il rilevamento del punto vendita basato sull'ubicazione](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
