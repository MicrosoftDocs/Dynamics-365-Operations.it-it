---
title: Pubblicare posizioni in LinkedIn da Attract
description: In questo argomento viene descritto come utilizzare Dynamics 365 Talent - Attract per pubblicare posizioni su LinkedIn
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 782a2e5de6edf0e85c4d32a0910f5f3c01981a01
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2019
ms.locfileid: "2833004"
---
# <a name="post-jobs-to-linkedin-from-attract"></a>Pubblicare posizioni in LinkedIn da Attract

[!include [banner](includes/banner.md)]

LinkedIn è la più grande rete professionale online, che consente di contattare i migliori talenti al mondo. Microsoft Dynamics 365 Talent: Attract aiuta a trovare i talenti necessari a un'azienda attraverso la pubblicazione di posizioni direttamente da Attract in LinkedIn.

Attract consente di pubblicare inserzioni limitate su LinkedIn senza costi aggiuntivi. Queste inserzioni sono disponibili solo tra i partner software di LinkedIn come Attract. Non vengono visualizzate nel pannello **Carriere** della pagina di LinkedIn della società, perché in questo pannello appaiono solo le inserzioni a pagamento. Tuttavia, vengono visualizzate quando potenziali candidati visualizzano tutte le posizioni disponibili. Le inserzioni limitate vengono visualizzate anche nelle ricerche di lavoro di LinkedIn.

Dopo la [creazione di una posizione](./creating-jobs-attract.md) in Attract, è sufficiente selezionare un pulsante per presentarla a migliaia di potenziali candidati su LinkedIn.

Nella seguente tabella vengono illustrate le azioni che è possibile eseguire su LinkedIn, a seconda del ruolo utente.

| Ruolo | Azioni che è possibile eseguire |
|---|---|
| Amministratore | Pubblicare, ripubblicare e cancellare una pubblicazione |
| Responsabile assunzioni | Sola lettura |
| Selezionatore | Pubblicare, ripubblicare e cancellare una pubblicazione |
| Responsabile del colloquio | Nessun accesso |
| Sola lettura | Sola lettura |

Per ulteriori informazioni sui ruoli utente in Attract, vedere [Gestione della sicurezza e dei ruoli in Attract](./security-attract.md).

Se si è un amministratore e sono necessarie ulteriori informazioni su come configurare l'integrazione di LinkedIn con Attract, vedere [Impostare l'integrazione con LinkedIn per Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md).

Le posizioni che vengono pubblicate in LinkedIn vengono visualizzate direttamente nel sito di LinkedIn. LinkedIn non dispone di un ambiente di test per la pubblicazione delle posizioni. Assicurarsi quindi di non pubblicare accidentalmente annunci di prova.

## <a name="post-jobs-to-linkedin"></a>Pubblicare posizioni in LinkedIn

1. In Attract, aprire la posizione che si intende pubblicare su LinkedIn.
2. Nella scheda **Registrazioni** selezionare il pulsante **Pubblica ora** che corrisponde a LinkedIn.

    [![Pubblicare posizioni da Attract su LinkedIn](./media/attract-post-job-to-linkedin.png)](./media/attract-post-job-to-linkedin.png)

3. Nella finestra di dialogo **Crea un indirizzo Web "Invia ora domanda di lavoro"**, selezionare un'opzione in **I candidati possono presentare domanda di lavoro mediante**. È consigliabile selezionare **Collegamento in Attract**.
4. Selezionare **Fine**.
5. Nella finestra di messaggio per l'**invio per la pubblicazione** selezionare **Conferma**.

Dopo il completamento della pubblicazione su LinkedIn, lo stato LinkedIn nella sezione **Registrazioni** dell'annuncio di lavoro in Attract è **Pubblicato**. La visualizzazione della posizione in LinkedIn può richiedere fino a 48 ore.

Quando i candidati interessati selezionano **Visualizza** accanto all'annuncio, vengono visualizzati tutti i dettagli della posizione, insieme alle informazioni su come candidarsi.

Tutte le pubblicazioni di posizioni eseguite attraverso Attract sono inserzioni limitate. Per ulteriori informazioni sulle inserzioni limitate su LinkedIn, vedere [Inserzioni limitate e slot di lavoro Premium per il wrapping di lavoro](https://www.linkedin.com/help/recruiter/answer/79049).

Se si verificano problemi nell'accesso o nella pubblicazione di posizioni in LinkedIn da Attract, vedere [Risoluzione dei problemi di integrazione con LinkedIn e Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md).

## <a name="see-also"></a>Vedere anche

[Domande frequenti sull'integrazione di Attract con LinkedIn](./attract-linkedin-faq.md)

[Impostazione dell'integrazione con LinkedIn per Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md)

[Creare, approvare e pubblicare annunci di mansioni in Attract](./creating-jobs-attract.md)

[Selezionare i candidati con LinkedIn Recruiter](./attract-linkedin-recruiter.md)

[Risoluzione dei problemi di integrazione con LinkedIn](./attract-troubleshoot-linkedin.md)
