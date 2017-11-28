---
title: "Configurare un'attività automatica in un flusso di lavoro"
description: "In questo argomento viene descritto come configurare le proprietà per un'attività automatica."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e8189f8d16e9b6dcbc339a23c1af5402c0316ce3
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="configure-an-automated-task-in-a-workflow"></a>Configurare un'attività automatica in un flusso di lavoro

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto come configurare le proprietà per un'attività automatica.

Per configurare un'attività automatica, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sull'attività e scegliere **Proprietà** per aprire la pagina **Proprietà**. Per configurare le proprietà dell'attività automatica, attenersi alle procedure indicate di seguito.

## <a name="name-the-task"></a>Assegnare un nome all'attività
Per immettere un nome per l'attività automatica, effettuare le operazioni indicate di seguito.

1.  Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2.  Nel campo **Nome** immettere un nome univoco per l'attività.

## <a name="specify-when-notifications-are-sent"></a>Specificare quando verranno inviate le notifiche
È possibile inviare notifiche agli utenti quando è stata eseguita o annullata un'attività automatica. Per specificare quando e a chi verranno inviate le notifiche, effettuare le operazioni indicate di seguito.

1.  Nel riquadro sinistro fare clic su **Notifiche**.
2.  Selezionare la casella di controllo accanto agli eventi per cui inviare notifiche:
    -   **Esecuzione**: le notifiche vengono inviate all'esecuzione dell'attività.
    -   **Annullato**: le notifiche vengono inviate se l'attività viene annullata.

3.  Scegliere la riga per un evento selezionato nel passaggio 2.
4.  Nella scheda **Testo notifiche** immettere il testo della notifica nella casella di testo.
5.  Per personalizzare la notifica, è possibile inserire segnaposto. I segnaposto verranno sostituiti con i dati appropriati al momento della visualizzazione della notifica. Per inserire un segnaposto, effettuare le operazioni seguenti:
    1.  Fare clic sulla casella di testo per specificare il punto in cui deve essere inserito il segnaposto.
    2.  Fare clic su **Inserisci segnaposto**.
    3.  Nell'elenco visualizzato selezionare il segnaposto da inserire.
    4.  Fare clic su **Inserisci**.

6.  Per aggiungere traduzioni della notifica, effettuare le operazioni seguenti:
    1.  Fare clic su **Traduzioni**.
    2.  Nella pagina visualizzata fare clic su **Aggiungi**.
    3.  Nell'elenco visualizzato selezionare la lingua in cui immettere il testo.
    4.  Nel campo **Testo tradotto** immettere il testo.
    5.  Per personalizzare il testo, è possibile inserire segnaposto come indicato nel passaggio 5.
    6.  Fare clic su **Chiudi**.

7.  Nella scheda **Destinatario** specificare il destinatario cui inviare le notifiche. Selezionare una delle opzioni nella tabella indicata di seguito, quindi seguire le altre indicazioni per l'opzione prima di procedere al passaggio 8.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Opzione</th>
    <th>Destinatari delle notifiche</th>
    <th>Passaggi aggiuntivi</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Partecipante</td>
    <td>Utenti assegnati a un ruolo o un gruppo specifico</td>
    <td><ol>
    <li>Dopo aver selezionato <strong>Partecipante</strong>, nella scheda <strong>Basato sui ruoli</strong> selezionare il tipo di gruppo o il ruolo a cui inviare le notifiche nell'elenco <strong>Tipo di partecipante</strong>.</li>
    <li>Nell'elenco <strong>Partecipante</strong> selezionare il tipo di gruppo o ruolo a cui inviare notifiche.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Utente del flusso di lavoro</td>
    <td>Utenti che partecipano al flusso di lavoro corrente</td>
    <td><ul>
    <li>Dopo aver selezionato <strong>Utente del flusso di lavoro</strong>, nella scheda <strong>Utente del flusso di lavoro</strong>, nell'elenco <strong>Utente del flusso di lavoro</strong> selezionare un utente che partecipa al flusso di lavoro.</li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td>Utente</td>
    <td>Utenti specifici di Microsoft Dynamics 365 for Finance and Operations</td>
    <td><ol>
    <li>Dopo aver selezionato <strong>Utente</strong>, fare clic sulla scheda <strong>Utente</strong>.</li>
    <li>Nell'elenco <strong>Utenti disponibili</strong> sono inclusi tutti gli utenti di Finance and Operations. Selezionare gli utenti a cui inviare notifiche, quindi spostarli nell'elenco <strong>Utenti selezionati</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  Ripetere i passaggi dal 3 al 7 per ciascun evento selezionato nel passaggio 2.





