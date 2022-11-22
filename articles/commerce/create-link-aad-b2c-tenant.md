---
title: Creare o collegare un tenant Azure AD B2C esistente nel portale di Azure
description: Questo articolo descrive come creare o collegarsi a un tenant business-to-consumer (B2C) Azure Active Directory (Azure AD) esistente nel portale di Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 0aa12387f00ffc3dd10688c6385c7952f089ab12
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785302"
---
# <a name="create-or-link-to-an-existing-azure-ad-b2c-tenant-in-the-azure-portal"></a>Creare o collegare un tenant Azure AD B2C esistente nel portale di Azure

[!include [banner](includes/banner.md)]

Questo articolo descrive come creare o collegarsi a un tenant business-to-consumer (B2C) Azure Active Directory (Azure AD) nel portale di Microsoft Azure. Per ulteriori informazioni, vedi [Esercitazione: Creare un tenant Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-create-tenant).

Per creare o collegarsi a un tenant B2C Azure AD esistente nel portale di Azure, attenersi alla seguente procedura.

1. Accedere al [portale Azure](https://portal.azure.com/).
1. Dal menu del portale di Azure, selezionare **Crea una risorsa**. Assicurarsi di utilizzare la sottoscrizione e la directory che saranno collegati al tuo ambiente Commerce.

    ![Creare una risorsa nel portale di Azure.](./media/B2CImage_1.png)

1. Andare a **Identità \> Azure Active Directory B2C**.
1. Una volta nella pagina **Crea nuovo tenant B2C o collegamento a tenant esistente**, utilizzare una delle opzioni seguenti più adatta alle esigenze dell'azienda:

    - **Creare uno nuovo tenant Azure AD B2C**: utilizza questa opzione per creare un nuovo tenant Azure AD B2C.
        1. Selezionare **Crea un nuovo tenant Azure AD B2C**.
        1. In **Nome organizzazione**, immettere il nome dell'organizzazione.
        1. In **Nome di dominio iniziale**, immettere il nome del dominio iniziale.
        1. Per **Paese o area geografica**, selezionare il paese o l'area geografica.
        1. Selezionare **Crea** per creare il tenant.

     ![Creare un nuovo tenant Azure AD.](./media/B2CImage_2.png)

     - **Collega un tenant Azure AD B2C esistente alla sottoscrizione di Azure**: utilizzare questa opzione se si dispone già di un tenant Azure AD B2C che si desidera collegare.
        1. Selezionare **Collega un tenant Azure AD B2C esistente alla sottoscrizione di Azure**.
        1. Per **Tenant Azure AD B2C**, selezionare il tenant B2C appropriato. Se nella casella di selezione viene visualizzato il messaggio "Nessun tenant B2C idoneo trovato", non si dispone di un tenant B2C idoneo esistente e sarà necessario crearne uno nuovo.
        1. Per **Gruppo di risorse**, selezionare **Crea nuovo**. Immettere un **nome** per il gruppo di risorse che conterrà il tenant, selezionare **Ubicazione del gruppo di risorse**, quindi selezionare **Crea**.

    ![Collegare un tenant Azure AD B2C esistente alla sottoscrizione di Azure.](./media/B2CImage_3.png)

1. Una volta creata la nuova directory Azure AD B2C (l'operazione potrebbe richiedere alcuni istanti) sul dashboard verrà visualizzato un collegamento alla nuova directory. Questo collegamento indirizzerà alla pagina di "Benvenuto in Azure Active Directory B2C".

    ![Collega la nuova directory Azure AD.](./media/B2CImage_4.png)

> [!NOTE]
> Se sono presenti più sottoscrizioni nell'account Azure o è stato impostato il tenant B2C senza collegamento a una sottoscrizione attiva, un banner **Risoluzione dei problemi** esegue il reindirizzamento al collegamento del tenant a una sottoscrizione. Selezionare il messaggio della risoluzione dei problemi e seguire le istruzioni per risolvere il problema di sottoscrizione.

L'immagine seguente mostra un esempio di banner **Risoluzione dei problemi** Azure AD B2C.

![Avviso indicante che la directory non ha una sottoscrizione attiva.](./media/B2CImage_5.png)

## <a name="next-steps"></a>Passaggi successivi

Per continuare il processo di configurazione di un tenant B2C in Commerce, passa a [Creare l'applicazione B2C](create-b2c-app.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un tenant B2C in Commerce](set-up-b2c-tenant.md)

[Creare l'applicazione B2C](create-b2c-app.md)

[Creare criteri di flusso utente](create-user-flow-policies.md)

[Aggiungere provider di identità social (facoltativo)](add-social-identity-providers.md)

[Aggiornare Commerce headquarters con le nuove informazioni di Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurare il tenant B2C in Creazione di siti Web di Commerce](config-b2c-tenant-site-builder.md)

[Ulteriori informazioni su B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
