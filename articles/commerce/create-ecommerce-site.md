---
title: Creare un sito di e-Commerce
description: In questo argomento vengono descritte le attività associate alla creazione di un nuovo sito di e-Commerce in Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fd87a51b73deae64867b0420c00db9fce7c79336
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697131"
---
# <a name="create-an-e-commerce-site"></a>Creare un sito di e-Commerce

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritte le attività associate alla creazione di un nuovo sito di e-Commerce in Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Per iniziare a sviluppare il sito di e-Commerce, è innanzitutto necessario configurare un nuovo sito nell'ambiente di creazione di siti. Prima di poter creare un nuovo sito, almeno un punto vendita online deve essere creato in Dynamics 365 Retail. 

## <a name="set-up-your-site"></a>Configurare il sito

Per configurare il sito, effettuare la procedura seguente.

1. In Microsoft Lifecycle Services (LCS), selezionare il collegamento per l'ambiente di creazione di siti. 
1. Nella home page dell'ambiente di creazione di siti, selezionare **Nuovo sito**.
1. Nella finestra di dialogo **Nuovo sito** immettere le informazioni seguenti.

| Campo                               | Descrizione |
|-------------------------------------|-------------|
| Nome sito                           | Immettere il nome visualizzato da utilizzare per il sito nell'ambiente di creazione di siti. Questo nome è visibile solo nell'ambiente di creazione e non ai clienti. |
| Gruppo di sicurezza dell'amministratore del sito | Specificare il gruppo di sicurezza di Microsoft Azure Active Directory (Azure AD) che gestisce gli utenti con il ruolo di amministratore sito nel sito. |
| Canale predefinito (numero unità operativa) | Selezionare il punto vendita online per il quale il sito viene utilizzato come vetrina virtuale Web. Se il sito di e-Commerce deve supportare più punti vendita online, è necessario associare i punti vendita al sito in **Impostazioni sito** dopo la configurazione del sito. |
| Lingua predefinita                            | Specificare la lingua predefinita per il mercato e il punto vendita online. Un punto vendita online può supportare più lingue. Se si desidera supportare più lingue per questo punto vendita online o un altro punto vendita online, è possibile configurare tale supporto in **Impostazioni sito** dopo la configurazione del sito.  |
| Dominio                              | Selezionare un nome di dominio che sarà utilizzato come dominio per il punto vendita online. Se non è stato configurato alcun dominio in LCS, è possibile lasciare vuoto questo campo. Dopo che il dominio è configurato in LCS, è necessario aggiungerlo al punto vendita online in **Impostazioni sito**.  |
| Percorso                              | Quando il sito supporta più lingue per un nome di dominio specifico, utilizzare il campo del percorso per creare un URL di sito univoco per quella combinazione di dominio e lingua. Se la lingua specificata nel campo **Lingua predefinita** è l'unica lingua che verrà supportata per il dominio, o sarà sempre la lingua predefinita dopo aver localizzato il sito in altre lingue, è consigliabile lasciare vuoto questo campo. |


Dopo la creazione del sito, è possibile verificare che sia associato al punto vendita online selezionando la scheda **Prodotti**. Dovrebbe essere visualizzato l'assortimento di prodotti che è stato allocato al punto vendita online. È anche possibile utilizzare il menu a discesa nell'angolo in alto a sinistra della pagina per accedere ai prodotti allocati per categoria.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dei negozi online](online-store-overview.md)

[Distribuire un nuovo sito di e-Commerce](deploy-ecommerce-site.md)

[Associare un sito online a un canale](associate-site-online-store.md)

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)

[Abilitare il rilevamento del punto vendita basato sull'ubicazione](enable-store-detection.md)

[Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)

[Panoramica della home page di creazione](authoring-home-overview.md)

[Aggiungere una nuova pagina del sito](add-new-page.md)
