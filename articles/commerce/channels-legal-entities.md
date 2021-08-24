---
title: Crea persone giuridiche
description: In questo argomento viene descritto come creare persone giuridiche in Microsoft Dynamics 365 Commerce, che deve essere creato e configurato prima di creare canali.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: bc5f097a7f941dfa05f4011d9be5caffbb7f01b5f6e67cd7535ef3d1b13f59fe
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740433"
---
# <a name="create-legal-entities"></a>Crea persone giuridiche

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come creare persone giuridiche in Microsoft Dynamics 365 Commerce, che deve essere creato e configurato prima di creare canali.

Una persona giuridica è un'organizzazione dotata di una struttura legale istituita o registrata. Le persone giuridiche possono stipulare contratti e hanno l'obbligo di preparare rendiconti sul loro rendimento.

Una società è un tipo di persona giuridica. Attualmente, le società sono l'unico tipo di persona giuridica che è possibile creare e ogni persona giuridica è associata a un ID società. Questa associazione esiste perché alcune aree funzionali del programma utilizzano un ID società, o *DataAreaId*, nei loro modelli di dati. In queste aree funzionali, le società vengono usate come limite per la sicurezza dei dati. Gli utenti possono accedere solo ai dati della società a cui sono collegati. 

Quando si crea un canale, è necessario specificare a quale persona giuridica appartiene quel canale.

## <a name="create-a-new-legal-entity"></a>Creare una nuova persona giuridica

Per creare una nuova persona giuridica in Dynamics 365 Commerce, completare i passaggi seguenti:

1. Nel pannello di navigazione, andare a **Moduli \> Impostazione sedi centrali \> Persone giuridiche**.
1. Nel Riquadro azioni selezionare **Nuovo**. Il riquadro **Nuova persona giuridica** appare sulla destra.
1. Nel campo **Nome** immettere un valore.
1. Nel campo **Società** immettere un valore.
1. Nel campo **Paese**, immettere o selezionare un valore.
1. Selezionare **OK**. 

   ![Creazione di persone giuridiche.](media/legal-entities.png)

1. Nella sezione **Generale**, immettere le seguenti informazioni generali sulla persona giuridica: 
   1. Immettere un nome di ricerca se è richiesto. Un nome di ricerca è un nome alternativo che è possibile utilizzare per cercare questa persona giuridica. 
   1. Scegliere se la persona giuridica viene utilizzata come società di consolidamento.
   1. Scegliere se la persona giuridica viene utilizzata come società di eliminazione. 
   1. Selezionare la **lingua predefinita** per l'entità. 
   1. Selezionare il **fuso orario** per l'entità.
1. Nella sezione **Indirizzi** selezionare **Modifica** per immettere informazioni sull'indirizzo ovvero via, numero civico, CAP e città.
1. Nella sezione **Informazioni contatto** immettere le informazioni sui metodi di comunicazione, ad esempio indirizzi di posta elettronica, URL e numeri di telefono.
1. Nella sezione **Relazione finanziaria** immettere i numeri di registrazione utilizzati per il reporting statutario.
1. Nella sezione **Numeri di registrazione** immettere le informazioni richieste dalla persona giuridica.
1. Nella sezione **Informazioni conto bancario** immettere i conti bancari e i numeri di registrazione relativi alla persona giuridica.
1. Nella sezione **Commercio estero e logistica** immettere le informazioni di spedizione relative alla persona giuridica.
1. Nella sezione **Sequenze numeriche** è possibile visualizzare le sequenze numeriche associate alla persona giuridica. Inizialmente questa sezione sarà vuota.
1. Nella sezione **Immagine nel dashboard** visualizzare o modificare l'immagine del dashboard e del logo associata alla persona giuridica.
1. Nella sezione **Registrazione fiscale** immettere i numeri di registrazione utilizzati per le dichiarazioni alle autorità fiscali.
1. Nella sezione **Imposta 1099** immettere le informazioni incluse nel modulo 1099 per la persona giuridica.
1. Nella sezione **Informazioni sull'imposta**, immettere le informazioni sull'imposta per la persona giuridica.
1. Selezionare **Salva**.

L'immagine seguente illustra un esempio di persona giuridica.

![Sezione generale della persona giuridica.](media/legal-entities-general.png)
   
## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica organizzazioni e gerarchie organizzative](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Pianificazione della gerarchia organizzativa](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Gerarchie organizzative](channels-org-hierarchies.md)

[Panoramica dei canali](channels-overview.md)

[Prerequisiti di impostazione dei canali](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
