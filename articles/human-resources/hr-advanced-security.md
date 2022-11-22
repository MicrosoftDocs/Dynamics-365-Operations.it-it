---
title: Limita l'accesso ai lavoratori per persona giuridica
description: Questo articolo spiega come configurare l'accesso ai lavoratori in base alla persona giuridica.
author: twheeloc
ms.date: 11/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fadd2c34d31bbd259255596c06a8e7517f7a774b
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780392"
---
# <a name="restrict-access-to-workers-by-legal-entity"></a>Limita l'accesso ai lavoratori per persona giuridica

Questo articolo spiega come configurare l'accesso ai lavoratori in base alla persona giuridica.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I dipendenti sono impiegati in persone giuridiche. Di seguito sono riportati alcuni esempi.

- Aaron Con è impiegato nella persona giuridica USSI.
- Ahmed Barnett è impiegato nella persona giuridica USMF.
- Alicia Thornber è impiegata nelle persone giuridiche GLSI e USMF.

A seconda del ruolo di un utente nella società, potrebbe richiedere l'accesso per visualizzare tutti i dipendenti in tutte le persone giuridiche. In alternativa, potrebbe essere necessario limitare un utente, in modo che possa visualizzare solo i dipendenti della persona giuridica a cui ha accesso. Per controllare quali dipendenti un utente può visualizzare, seleziona il parametro **Limita l'accesso alle informazioni sui lavoratori** parametro nella pagina **Parametri condivisi delle risorse umane**.

Ad esempio, un utente ha accesso alla pagina **Lavoratore** e ha accesso solo alla persona giuridica USMF. In questo caso, l'utente può visualizzare le seguenti informazioni per i dipendenti nell'elenco precedente:

- Se la funzionalità per limitare l'accesso alle informazioni sui lavoratori non è abilitata, l'utente può visualizzare le informazioni per Aaron, Ahmed e Alicia.
- Se la funzionalità è abilitata, l'utente può visualizzare le informazioni solo per Alicia e Ahmed, perché sono anche impiegati nella persona giuridica USMF.

Le informazioni visualizzate variano a seconda dell'applicazione in uso.

## <a name="dynamics-365-human-resources-stand-alone"></a>Dynamics 365 Human Resources autonoma

Se la funzionalità per limitare l'accesso alle informazioni sul lavoratore è abilitata, l'utente limitato vedrà un valore vuoto in alcuni elenchi che contengono il nome del lavoratore.

Ad esempio, un utente che ha accesso solo alla persona giuridica USMF registrerà il seguente comportamento:

- Nell'elenco **Posizioni attive**, la colonna **Lavoratore** sarà vuota per la posizione di Aaron, perché l'utente non ha accesso ai dipendenti nella persona giuridica USSI.
- Se l'utente esegue il drill-down sul nome del lavoratore, una pagina vuota **Lavoratore** verrà visualizzata.

## <a name="dynamics-365-human-resources-on-finance-infrastructure"></a>Dynamics 365 Human Resources dell'infrastruttura Finance

Se la funzionalità per limitare l'accesso alle informazioni sul lavoratore è abilitata, l'utente limitato vedrà il nome del lavoratore in alcuni elenchi.

Ad esempio, un utente che ha accesso solo alla persona giuridica USMF registrerà il seguente comportamento:

- Nell'elenco **Posizioni attive**, la colonna **Lavoratore** mostrerà il nome di Aaron. Se l'utente passa il mouse sopra il nome del lavoratore, verranno visualizzati solo il nome e il titolo.
- Se l'utente esegue il drill-down sul nome del lavoratore, una pagina vuota **Lavoratore** verrà visualizzata.

> [!TIP]
> Se utilizzi Dynamics 365 Human Resources nell'infrastruttura Finance e vuoi che gli utenti con restrizioni vedano valori vuoti per i nomi dei lavoratori, puoi aggiungere il privilegio di sicurezza **Limita l'accesso ai lavoratori** ai ruoli utente nella pagina **Configurazione sicurezza**.

Dopo aver abilitato la funzionalità, devi completare alcuni passaggi extra per impostare le autorizzazioni per ciascun utente la cui visualizzazione deve essere limitata.

1. Nella pagina **Utenti** selezionare un utente.
2. Selezionare un ruolo per l'utente. Diventa disponibile l'opzione **Assegna organizzazioni**.
3. Selezionare **Assegna organizzazioni**.
4. Nella nuova pagina, selezionare **Concedi l'accesso a singole organizzazioni specifiche**, quindi selezionare le organizzazioni a cui l'utente dovrebbe avere accesso.
5. Ripetere i passaggi da 2 a 4 per ogni altro ruolo dell'utente, incluso il ruolo utente di sistema.

> [!NOTE]
> Le persone giuridiche a cui un utente ha accesso devono corrispondere a tutti i ruoli dell'utente.
