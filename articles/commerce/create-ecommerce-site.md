---
title: Creare un sito di e-commerce
description: Questo articolo descrive i passaggi e le informazioni richiesti per creare un nuovo sito di e-commerce in Creazione di siti Web di Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b4ac8d1b930c89bf330a2332c0b510dadb92e51f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855772"
---
# <a name="create-an-e-commerce-site"></a>Creare un sito di e-commerce

[!include [banner](includes/banner.md)]

Questo articolo descrive i passaggi e le informazioni richiesti per creare un nuovo sito di e-commerce in Creazione di siti Web di Dynamics 365 Commerce.

Quando si concedono in licenza le funzionalità di Dynamics 365 Commerce, all'autore del sito verrà fornito un sito di partenza che è possibile utilizzare come base per il proprio sito. Tuttavia, se si desidera iniziare da zero o se si desidera creare un secondo sito, sarà necessario stabilire un nuovo sito nell'ambiente di creazione del sito. 

## <a name="site-creation-prerequisites"></a>Prerequisiti per la creazione del sito

Un utente del generatore di siti deve avere un account utente Microsoft Azure Active Directory (Azure AD) incluso nel gruppo di sicurezza Azure AD assegnato agli amministratori del sistema di e-commerce. Per altre informazioni, vedi [Distribuire un nuovo tenant di e-commerce](deploy-ecommerce-site.md).

> [!NOTE]
> Gli utenti guest di Azure AD potrebbero avere autorizzazioni di accesso diverse nel tuo tenant Azure AD. Anche se incluso nel gruppo di sicurezza Azure AD assegnato agli amministratori del sistema di e-commerce, un utente guest potrebbe aver bisogno che le impostazioni dell'autorizzazione come **utenti esterni** Azure AD vengano regolate per creare un sito di e-commerce in Commerce. 

Per regolare le impostazioni **Utenti esterni** di Azure AD, attenersi alla seguente procedura.

1. Nel portale di Azure, accedi al tenant Azure AD.
1. Vai a **Impostazioni utente \> Utenti esterni** e seleziona il collegamento **Gestisci impostazioni collaborazione esterna**. Si apre la pagina **Impostazioni collaborazione esterna** in cui è possibile impostare l'accesso degli utenti guest, le impostazioni degli inviti degli ospiti e le restrizioni alla collaborazione. 
1. Regola le impostazioni della collaborazione esterna in base ai criteri di sicurezza della tua azienda. 

## <a name="set-up-your-site"></a>Configurare il sito

Per configurare il sito, effettuare la procedura seguente.

1. Aprire l'ambiente di Creazione di siti Web. È possibile trovare un collegamento a Creazione di siti Web in Microsoft Lifecycle Services (LCS) nella pagina Funzionalità ambiente per Commerce.
1. Nella home page dell'ambiente di creazione di siti, selezionare **Nuovo sito**.
1. Nella finestra di dialogo **Nuovo sito** immettere le informazioni seguenti.

| Campo                               | Descrizione |
|-------------------------------------|-------------|
| Nome sito                           | Immettere il nome visualizzato da utilizzare per il sito nell'ambiente di creazione di siti. Questo nome è visibile solo nell'ambiente di creazione e non ai clienti. |
| Gruppo di sicurezza dell'amministratore del sito | Specificare il gruppo di sicurezza di Microsoft Azure Active Directory (Azure AD) che gestisce gli utenti con il ruolo di amministratore sito nel sito. |
| Canale predefinito (numero unità operativa) | Selezionare il punto vendita online per il quale il sito viene utilizzato come vetrina virtuale Web. Se il sito di e-commerce deve supportare più punti vendita online, è necessario associare i punti vendita al sito in **Impostazioni sito** dopo la configurazione del sito. |
| Lingua predefinita                            | Specificare la lingua predefinita per il mercato e il punto vendita online. Un punto vendita online può supportare più lingue. Se si desidera supportare più lingue per questo punto vendita online o un altro punto vendita online, è possibile configurare tale supporto in **Impostazioni sito** dopo la configurazione del sito.  |
| Dominio                              | Selezionare un nome di dominio che sarà utilizzato come dominio per il punto vendita online. Se non è stato configurato alcun dominio in LCS, è possibile lasciare vuoto questo campo. Dopo che il dominio è configurato in LCS, è necessario aggiungerlo al punto vendita online in **Impostazioni sito**.  |
| Percorso                              | Quando il sito supporta più lingue per un nome di dominio specifico, utilizzare il campo del percorso per creare un URL di sito univoco per quella combinazione di dominio e lingua. Se la lingua specificata nel campo **Lingua predefinita** è l'unica lingua che verrà supportata per il dominio, o sarà sempre la lingua predefinita dopo aver localizzato il sito in altre lingue, è consigliabile lasciare vuoto questo campo. |

Dopo la creazione del sito, è possibile verificare che sia associato al punto vendita online selezionando la scheda **Prodotti**. Dovrebbe essere visualizzato l'assortimento di prodotti che è stato allocato al punto vendita online. È anche possibile utilizzare il menu a discesa nell'angolo in alto a sinistra della pagina per accedere ai prodotti allocati per categoria.

## <a name="rename-your-site"></a>Rinominare il sito

Per rinominare il sito nello strumento di creazione siti, effettua le seguenti operazioni.

1. Per aprire la visualizzazione elenco dei siti, seleziona **Cambia sito** nell'angolo in alto a destra, quindi seleziona **Gestisci siti**. 
1. Seleziona la casella di controllo accanto al sito che desideri rinominare, quindi seleziona **Rinomina** sulla barra dei comandi.
1. Nella finestra di dialogo **Nuovo nome sito**, immetti il nuovo nome del sito, quindi seleziona **OK**. L'elenco dei siti si aggiornerà per mostrare il nuovo nome del sito.

## <a name="delete-a-site"></a>Elimina un sito

Per eliminare un sito nel generatore siti, seguire questa procedura.

1. Per aprire la visualizzazione elenco dei siti, seleziona **Cambia sito** nell'angolo in alto a destra, quindi seleziona **Gestisci siti**.
1. Seleziona il sito che desideri eliminare, quindi sulla barra dei comandi, seleziona **Elimina**.
1. Nella finestra di dialogo **Elimina \<site name\>**, immetti il nome del sito e seleziona **Elimina**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Distribuire un nuovo tenant di e-commerce](deploy-ecommerce-site.md)

[Associare un sito Dynamics 365 Commerce a un canale online](associate-site-online-store.md)

[Gestire i file robots.txt](manage-robots-txt-files.md)

[Caricare reindirizzamenti URL in blocco](upload-bulk-redirects.md)

[Impostare un tenant B2C in Commerce](set-up-B2C-tenant.md)

[Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)

[Configurare più tenant B2C in un ambiente Commerce](configure-multi-B2C-tenants.md)

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)

[Abilitare il rilevamento del punto vendita basato sull'ubicazione](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
