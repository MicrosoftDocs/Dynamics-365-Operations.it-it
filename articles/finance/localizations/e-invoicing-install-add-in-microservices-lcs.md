---
title: Installare il componente aggiuntivo per microservizi in Lifecycle Services
description: In questo articolo viene descritto come installare il componente aggiuntivo Fatturazione elettronica in Microsoft Dynamics Lifecycle Services (LCS).
author: gionoder
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: a837b85d4893f2915b5fbb5ffaae8eb95f19bc0e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272271"
---
# <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>Installa il componente aggiuntivo per microservizi in Lifecycle Services

[!include [banner](../includes/banner.md)]

L'autenticazione nel servizio di fatturazione elettronica richiede la registrazione dell'ambiente Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management nella piattaforma dei servizi installando il componente aggiuntivo per il proprio ambiente in Microsoft Dynamics Lifecycle Services (LCS).

Per registrare un ambiente, attenersi a questa procedura.

1. Accedi al tuo account LCS.
2. Nel dashboard di progetto, seleziona un progetto LCS.
2. Nel progetto, nel dashboard **Ambienti**, selezionare il progetto distribuito. L'ambiente selezionato deve essere in esecuzione.
3. Nella scheda **Integrazione di Power Platform**, nella sezione **Componenti aggiuntivi dell'ambiente**, seleziona **Installa un nuovo componente aggiuntivo**.
4. Seleziona **Fatturazione elettronica**.
5. Nel campo **ID applicazione AAD** inserisci **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Questo valore è un valore fisso. Assicurati di inserire solo un identificatore univoco globale (GUID). Non includere altri simboli, come spazi, virgole, punti o virgolette.
6. Nel campo **ID tenant AAD** immettere l'ID tenant dell'account di sottoscrizione di Azure. Il tentant Azure Active Directory (Azure AD) specificato deve essere lo stesso tenant utilizzato per Regulatory Configuration Service (RCS).
7. Esaminare i termini e le condizioni e quindi selezionare la casella di controllo.
8. Seleziona **Installa**. Dopo alcuni minuti, lo stato cambia da **Installazione in corso** in **Installato**. Potrebbe essere necessario aggiornare la pagina per visualizzare la modifica.

La fatturazione elettronica è ora pronta per l'uso.

> [!NOTE]
> Le aziende di solito hanno diversi ambienti Finance o Supply Chain Management. Questi ambienti includono ambienti di produzione, ambienti UAT (User Acceptance Test) e ambienti di sviluppo (sandbox). Devi completare la procedura precedente per tutti gli ambienti che vuoi connettere alla fatturazione elettronica.
