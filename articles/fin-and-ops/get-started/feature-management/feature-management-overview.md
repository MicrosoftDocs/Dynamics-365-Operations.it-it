---
title: Panoramica della gestione funzionalità
description: In questo argomento viene descritta la caratteristica Gestione funzionalità e come è possibile utilizzarla.
author: mikefalkner
manager: AnnBe
ms.date: 04/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: e75e42926db22d4fccda86c755b12d9d121a9c0e
ms.sourcegitcommit: be447fc81bc874982bc0185fcb4d87d99bd742c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538695"
---
# <a name="feature-management-overview"></a>Panoramica della gestione funzionalità

[!include[banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Le funzionalità vengono aggiunte e aggiornate in ogni versione di Microsoft Dynamics 365 for Finance and Operations. L'esperienza di gestione delle funzionalità offre un'area di lavoro in cui è possibile visualizzare un elenco delle funzionalità incluse in ciascuna versione. Per impostazione predefinita, le nuove funzionalità sono disabilitate. È possibile utilizzare l'area di lavoro per accendere alle funzionalità e visualizzare la documentazione correlata.

## <a name="the-feature-management-workspace"></a>Area di lavoro Gestione funzionalità

È possibile aprire l'area di lavoro **Gestione funzionalità** selezionando i riquadri appropriati nel dashboard. Verrà visualizzata una pagina che mostra un elenco di funzionalità per tutte le versioni supportate dall'esperienza di gestione delle funzionalità. Nel corso del tempo, Microsoft migliorerà l'esperienza di gestione delle funzionalità in modo che includa caratteristiche aggiuntive per agevolare la gestione delle funzionalità.

L'elenco delle funzionalità include le seguenti informazioni:

- **Nome funzionalità** - Una descrizione della funzionalità che è stata aggiunta.
- **Stato abilitato** - Un simbolo indica se una funzione è stata abilitata (segno di spunta), non è abilitata (vuoto), se è stata programmata per essere abilitata (orologio) o se è obbligatorio abilitarla (blocco). L'impostazione mostrata qui viene utilizzata per tutte le persone giuridiche. Tenere presente che anche quando una funzione è stata abilitata, è comunque controllata dalla sicurezza. Di conseguenza, la funzionalità sarà disponibile solo per gli utenti che hanno accesso ad essa, in base al ruolo di sicurezza. Inoltre è disponibile solo per le persone giuridiche a cui l'utente può accedere.
- **Data abilitazione** - La data in cui la funzionalità è stata o verrà abilitata se si tratta di una data futura.
- **Funzionalità aggiunta** - La data in cui la funzionalità è stata aggiunta all'ambiente. Questa data viene immessa automaticamente quando si aggiorna l'ambiente durante i cicli mensili di rilascio.
- **Modulo** - Il modulo interessato dalla nuova funzionalità.

Quando si seleziona una funzionalità, ulteriori informazioni vengono visualizzate nel riquadro dei dettagli a destra dell'elenco delle funzionalità. Nella parte superiore del riquadro, verrà visualizzato il nome della funzionalità, la data in cui la funzionalità è stata aggiunta, il modulo interessato dalla funzionalità e un collegamento **Ulteriori informazioni**. Selezionare il collegamento per visualizzare la documentazione relativa alla funzionalità. Se la documentazione non è disponibile, si verrà reindirizzati a una pagina temporanea. Nel riquadro Dettagli è presente anche un campo **Commenti** in cui è possibile aggiungere i propri commenti sulla funzionalità.

L'area lavoro **Gestione funzionalità** contiene anche più schede con un elenco delle funzionalità incluse. 
- **Nuove** - Visualizza tutte le funzionalità aggiunte dall'ultimo aggiornamento mensile. Se sono stati ignorato degli aggiornamenti mensili, conterrà tutte le nuove funzionalità dall'ultima volta che hai aggiornato. Le nuove funzionalità compaiono nella parte superiore dell'elenco. Il numero totale di nuove funzionalità è mostrato anche in un riquadro nella parte superiore della pagina.
- **Non abilitate** - Visualizza tutte le funzionalità che non sono state abilitate. Le nuove funzionalità compaiono nella parte superiore dell'elenco. Il numero totale di nuove funzionalità è mostrato anche in un riquadro nella parte superiore della pagina.
- **Programmate** - Mostra tutte le funzionalità che sono state programmate per essere abilitate in una data futura. Le funzionalità con la data programmata più prossima verranno visualizzate nella parte superiore dell'elenco. Il numero totale di nuove funzionalità è mostrato anche in un riquadro nella parte superiore della pagina.
- **Tutte** - Mostra tutte le funzionalità. Le nuove funzionalità compaiono nella parte superiore dell'elenco.


## <a name="enable-a-feature"></a>Abilitare una funzionalità

Se una funzionalità non è stata abilitata, un pulsante **Abilita** viene visualizzato nel riquadro dei dettagli. È possibile utilizzare questo pulsante per abilitare la funzionalità.

1. Selezionare la funzionalità che si desidera abilitare, quindi nel riquadro dei dettagli, selezionare **Abilita**.
2. Viene visualizzato un dispositivo di scorrimento, in cui è possibile specificare la data in cui la funzionalità deve essere abilitata. Per impostazione predefinita, la data corrisponde a quella corrente.
3. Selezionare **Abilita** per abilitare la funzionalità.

Alcune funzionalità non possono essere disabilitate dopo l'abilitazione. Se la funzionalità che si sta cercando di abilitare non può essere disabilitata, viene visualizzato un avviso. A questo punto, è possibile selezionare **Annulla** per annullare l'operazione e per lasciare la funzionalità disabilitata. Tuttavia, se si seleziona **Abilita** e si abilita la funzionalità, non sarà possibile disabilitarla in un secondo momento.

Una volta abilitata la funzionalità, sotto il collegamento **Ulteriori informazioni** viene visualizzato un messaggio nel riquadro dei dettagli. Questo messaggio informa che la funzionalità è stata abilitata o indica quando la funzionalità verrà abilitata in futuro. Se si utilizza una data futura, la funzionalità visualizzata nell'elenco **Programmate**. Questo messaggio verrà visualizzato ogni volta che si seleziona la funzionalità nell'elenco delle caratteristiche. Le funzionalità programmate nel futuro verranno abilitate a mezzanotte mediante un processo batch in base al fuso orario rappresentato dalla data di sistema. 

## <a name="reschedule-a-feature"></a>Ripianificare una funzionalità

Se una funzionalità è stata abilitata nel futuro, un pulsante **Riprogramma** viene visualizzato nel riquadro dei dettagli. È possibile utilizzare questo pulsante per cambiare **Data abilitazione** con una data diversa.

1. Selezionare una funzionalità programmata che si desidera riprogrammare, quindi nel riquadro dei dettagli, selezionare **Riprogramma**.
2. Viene visualizzato un dispositivo di scorrimento, in cui è possibile specificare la data in cui la funzionalità deve essere abilitata. 
3. Selezionare **Abilita** per riprogrammare la funzionalità o **Disabilita** per annullare la programmazione.

## <a name="disable-a-feature"></a>Disabilitare una funzionalità

Se una funzionalità è stata già abilitata, un pulsante **Disabilita** viene visualizzato nel riquadro dei dettagli. È possibile utilizzare questo pulsante per disabilitare la funzionalità. Il pulsante **Disabilita** non è disponibile se la funzionalità non può essere disabilitata dopo che è stata abilitata.

- Selezionare la funzionalità che si desidera disabilitare, quindi nel riquadro dei dettagli, selezionare **Disabilita**.

- La funzionalità viene disabilitata e la data viene deselezionata.

Una volta disabilitata la funzionalità, sotto il collegamento **Ulteriori informazioni** viene visualizzato un messaggio nel riquadro dei dettagli. Questo messaggio indica che la funzione non è stata ancora abilitata e verrà visualizzata nell'elenco **Non abilitata**. Il messaggio verrà visualizzato ogni volta che si seleziona la funzionalità nell'elenco delle caratteristiche.

## <a name="features-that-must-be-enabled"></a>Funzionalità che devono essere abilitate

Quando si esegue un aggiornamento, potrebbe venire fornita una funzionalità fondamentale che deve essere abilitata automaticamente. Sarà abilitata automaticamente nella **Data abilitazione**. Sotto il collegamento **Ulteriori informazioni** viene visualizzato un messaggio nel riquadro dei dettagli. Questo messaggio indicherà che la funzione è stata abilitata o sarà abilitata automaticamente nella **Data abilitazione**. Il messaggio verrà visualizzato ogni volta che si seleziona la funzionalità nell'elenco delle caratteristiche.

## <a name="assigning-roles"></a>Assegnare i ruoli

L'area di lavoro **Gestione funzionalità** può essere aperta dagli amministratori di sistema e dagli utenti assegnati ai ruoli di responsabile delle funzionalità o visualizzatore delle funzionalità creati per supportare l'esperienza di gestione delle funzionalità. Gli utenti con ruolo di responsabile delle funzionalità possono attivare o disattivare tutte le funzionalità. Possono anche aggiornare la sezione dei commenti relativi alla funzionalità. Gli utenti con ruolo di visualizzatore della funzionalità possono visualizzare solo l'area di lavoro **Gestione funzionalità**. Non possono attivare o disattivare le funzionalità.

I ruoli di responsabile delle funzionalità e visualizzatore delle funzionalità non sostituiscano la protezione esistente dell'utente. I ruoli controllano solo l'accesso all'abilitazione delle funzionalità. Non consente di accedere alle funzionalità vere e proprie.

## <a name="using-feature-management-to-enable-isv-features-or-custom-features"></a>Utilizzare la gestione delle funzionalità per abilitare le funzionalità ISV o le funzionalità personalizzate

Il processo di gestione delle funzionalità non è attualmente disponibile per le funzionalità ISV o personalizzate. Si stanno aggiungendo ulteriori funzionalità per migliorare la gestione delle funzionalità e, quando tali miglioramenti saranno completati, apriremo la gestione delle funzionalità a tutte le funzionalità e forniremo istruzioni specifiche su come aggiornare la funzione per utilizzarla.

## <a name="feature-management-and-flighting"></a>Gestione delle funzionalità e versione di anteprima

La gestione delle funzionalità consente di controllare le funzionalità fornite in ogni versione. La versione di anteprima consente ai team Microsoft di rilasciare funzionalità per un numero limitato di clienti, in modo che le funzionalità possano essere testate e convalidate senza influire su tutti i clienti. La gestione delle funzionalità non controlla la versione di anteprima di alcuna funzionalità.
