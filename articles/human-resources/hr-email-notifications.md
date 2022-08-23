---
title: Notifica tramite posta elettronica sui benefit
description: In questo articolo viene fornita una panoramica della funzionalità Notifica tramite posta elettronica sulla gestione di benefit in Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/01/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d550cbb2f639535dbb43765c9fb0632a514fbe8c
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229909"
---
# <a name="benefits-email-notification"></a>Notifica tramite posta elettronica sui benefit

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [banner](../includes/preview-banner.md)]

La funzione di notifica tramite posta elettronica consente di inviare notifiche e promemoria tramite posta elettronica ai dipendenti nei seguenti scenari:

- Iscrizione nuova assunzione
- Iscrizione aperta
- Eventi di vita qualificanti

Puoi creare e impostare più modelli di posta elettronica e inviare le notifiche utilizzando l'area di lavoro **Gestione benefit** e la pagina **Benefit lavoratore**. Puoi anche tenere traccia dello storico di notifiche/promemoria.

## <a name="set-up-human-resources-shared-parameters"></a>Configurare Parametri condivisi Risorse umane

Nella pagina **Parametri condivisi Risorse umane**, puoi creare modelli di posta elettronica relativi ai benefit per differenti tipi di comunicazione con dipendenti o gruppi di dipendenti.

## <a name="create-a-new-email-id-template"></a>Creare un nuovo modello di ID posta elettronica

Per creare un nuovo modello di ID posta elettronica, procedi come segue.

1. Vai a **Modelli di posta elettronica a livello di sistema**.
2. Selezionare **Nuovo**.
3. Nel campo **ID posta elettronica**, immetti un nome.
4. Imposta altri campi come necessario.
5. Seleziona **Messaggio di posta elettronica** per caricare il modello.
6. Nella pagina **Parametri condivisi Risorse umane**, seleziona il nuovo modello in **Modelli di sistema** e spostalo sotto **Modelli per benefit**.

## <a name="send-email-to-employees"></a>Inviare messaggi e-mail a dipendenti

Per inviare un messaggio e-mail a un nuovo assunto che non ha ancora iniziato, segui questi passaggi.

1. Aprire l'area di lavoro **Gestione benefit**.
2. Seleziona il riquadro per il gruppo di dipendenti a cui desideri inviare il messaggio e-mail.
3. Seleziona **Invia posta elettronica**.
4. Seleziona i dipendenti a cui vuoi inviare il messaggio e-mail.
5. Seleziona **Invia posta elettronica**.
6. Seleziona il modello che vuoi usare.
7. Seleziona **OK** per inviare il messaggio e-mail.

    Puoi esaminare il messaggio e-mail e lo stato nella pagina **Benefit lavoratore** del dipendente o selezionando **Storico e-mail benefit** nella sezione **Collegamenti** dell'area di lavoro **Gestione benefit**. Puoi anche inviare il messaggio e-mail dalla pagina **Piano di benefit lavoratori**.

8. Per visualizzare lo storico dei messaggi e-mail relativi ai benefit, nell'area di lavoro **Gestione benefit**, nella sezione **Collegamenti**, seleziona **Storico e-mail benefit**.
9. Visualizza lo storico completo dei messaggi e-mail relativi ai benefit che sono stati inviati. Per esaminare il contenuto del messaggio e-mail, seleziona **Mostra messaggio**.
10. Seleziona **Lavoratore**.
11. Nella pagina **Piano di benefit lavoratori**, puoi inviare messaggi e-mail e visualizzare lo storico dei messaggi e-mail relativi ai benefit.

L'area di lavoro **Gestione benefit** include differenti riquadri. Puoi inviare messaggi e-mail selezionando il modello correlato. Se i messaggi e-mail di iscrizione di nuove assunzioni sono stati inviati, seleziona il riquadro **Nuova assunzione non iniziata**, quindi seleziona il collegamento **Invia promemoria**. Puoi selezionare un modello di promemoria e impostare il titolo della notifica come primo, secondo o terzo promemoria.
