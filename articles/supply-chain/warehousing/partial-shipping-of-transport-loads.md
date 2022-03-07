---
title: Spedizione parziale di un carico di trasporto
description: In questo argomento viene descritto come spedire parzialmente un carico e posticipare la pianificazione della capacità del carico.
author: Mirzaab
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 5ea844531314b4dd2ff3fa46d8f0b57d9c47059e684d677f06f8259b264d4a90
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782301"
---
# <a name="partial-shipment-of-a-transport-load"></a>Spedizione parziale di un carico di trasporto

[!include[banner](../includes/banner.md)]

Con la spedizione parziale dei carichi, è possibile gestire i carichi in cui la capacità non può essere determinata fino a quando tutte le righe di vendita non sono state aggiunte a un carico. Il processo può quindi essere finalizzato una volta che si conosce il conteggio esatto dei pallet. Pertanto, non è necessario decidere quali pallet verranno assegnati a cui trasporto fino al momento in cui un trasporto non viene caricato fisicamente in magazzino approntato.

Questa funzionalità offre un'alternativa all'applicazione di una struttura più rigida, in cui è necessario stabilire quali pallet verranno assegnati a quale trasporto prima di poter creare il lavoro di prelievo o il lavoro di carico. Gli utenti possono invece configurare carichi individuali per la conferma di una spedizione parziale. Possono quindi avvenire i processi di caricamento del trasporto per quei carichi. Di conseguenza, il reparto di pianificazione del trasporto può pianificare i carichi senza dover considerare la capacità dei trasporti individuali.

Al momento del caricamento, i lavoratori possono definire un nuovo carico di trasporto in cui può essere caricato un pallet. In alternativa, è possibile identificare un carico di trasporto esistente. Questi dati possono essere registrati mediante un dispositivo mobile. Di conseguenza, più addetti al magazzino possono caricare scorte dagli stessi carichi o da carichi diversi nello stesso camion. I carichi possono quindi essere spediti in toto o parzialmente.

> [!NOTE] 
> Per caricare scorte da un carico a un determinato carico di trasporto e spedire parzialmente il carico, il lavoro deve essere generato utilizzando una classe di caricamento in un modello di lavoro. Il tipo di prelievo ordinario del tipo **Prelievo** non può essere caricato in un carico di trasporto come un camion.

## <a name="set-up-transport-loads-for-partial-shipment"></a>Impostare carichi di trasporto per la spedizione parziale

L'impostazione della spedizione parziale di carichi è costituita dalle due procedure seguenti.

### <a name="set-the-loading-strategy"></a>Impostare la strategia di caricamento

È necessario attivare il caricamento parziale impostando la strategia di caricamento. È possibile impostare la strategia di caricamento dopo aver creato un carico.

1. Selezionare **Gestione magazzino** \> **Carichi** \> **Tutti i carichi**.
2. Selezionare un carico, quindi fare clic su **Intestazione**.
3. Nel campo **Strategia di caricamento** selezionare **Spedizione carico parziale consentita**.

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a>Creare una voce di menu per il caricamento dei carichi di trasporto

È necessario creare una nuova voce di menu che consenta il caricamento dei carichi di trasporto. Un carico di trasporto consente di raggruppare righe di lavoro di uno o più carichi. Tutto quello che viene aggiunto al carico di trasporto può quindi essere spedito utilizzando uno scanner del dispositivo mobile.

1. Selezionare **Gestione magazzino** \> **Impostazioni** \> **Dispositivo mobile** \> **Voci di menu del dispositivo mobile**.
2. Selezionare **Nuovo**, quindi nel campo **Modo**, selezionare **Lavoro**.
3. Impostare l'opzione **Utilizza lavoro esistente** su **Sì**.
4. Nella scheda **Generale**, nelc ampo **Diretto da** selezionare **Caricamento di trasporto**.
5. Per attivare la conferma di spedizione su uno scanner di dispositivo mobile, nel campo **Tipo consentito di conferma spedizione** selezionare **Carico di trasporto**.

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a>Confermare la spedizione di un carico di trasporto dal client

Questa impostazione consente di confermare un carico di trasporto che include un intero carico o caricato parzialmente da spedire.

1. Selezionare **Gestione magazzino** \> **Carichi** \> **Carichi di trasporto**.
2. Nel riquadro azioni, nella scheda **Spedisci e ricevi**, nel gruppo **Conferma** selezionare **Trasporto**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]