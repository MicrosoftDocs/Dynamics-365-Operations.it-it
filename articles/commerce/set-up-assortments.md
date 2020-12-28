---
title: Impostare assortimenti
description: Questo articolo spiega cos'è un assortimento e come impostare gli assortimenti in Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15811
ms.assetid: d2580048-e798-4b33-85f9-d1bad7d262fc
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 26614d319453041177e8072793f09f52ebfd51fc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413555"
---
# <a name="set-up-assortments"></a>Impostare gli assortimenti

[!include [banner](includes/banner.md)]

Questo articolo spiega cos'è un assortimento e come impostare gli assortimenti in Dynamics 365 Commerce.

Un assortimento è una raccolta di prodotti correlati, che vengono assegnati a un canale di commercio, a un punto vendita fisico o un punto vendita online. È possibile utilizzare l'assortimento per identificare i prodotti che sono disponibili in ciascun punto vendita. Un assortimento può includere diverse categorie di prodotti. Di conseguenza, tutti i prodotti assegnati a una categoria specifica vengono inclusi nell'assortimento. Un assortimento può includere anche prodotti specifici e varianti specifiche dei prodotti. Impostando un assortimento, è possibile assegnare contemporaneamente migliaia di prodotti ai canali, in qualunque combinazione richiesta dai punti vendita. È possibile impostare tutti gli assortimenti prodotti necessari. Ogni prodotto può essere incluso in uno o più assortimenti e ogni assortimento può essere assegnato a uno o più canali. Ad esempio, è possibile definire un assortimento che include un set di base di prodotti. Tutti i punti vendita riceveranno questo assortimento. Quindi, è possibile definire un altro assortimento che include solo attrezzature sportive di grandi dimensioni che vengono ricevute solo dai punti vendita più grandi. Lo schema seguente illustra la modalità di assegnazione dei prodotti agli assortimenti e la modalità di assegnazione di tali assortimenti ai canali.

![Relazioni di assortimento prodotti](./media/assortments_relationship.gif)

## <a name="prerequisites"></a>Prerequisiti

Prima di poter impostare un assortimento e assegnarlo a un canale di commercio, è necessario eseguire le operazioni seguenti.

| Compito                              | Descrizione |
|-----------------------------------|-------------|
| Impostare un canale.          | I canali rappresentano un punto vendita fisico, un punto vendita online o un marketplace online. È necessario impostare almeno un canale e configurare le opzioni del punto vendita. Gli assortimenti vengono assegnati ai punti vendita per identificare i prodotti associati a un particolare punto vendita. |
| Consente di creare una gerarchia organizzativa. | Dopo aver impostato i canali di commercio per l'organizzazione, è necessario configurare una gerarchia organizzativa per la vendita al dettaglio che rappresenti la struttura organizzativa dei canali di vendita al dettaglio. La gerarchia organizzativa può essere utilizzata per assortimenti, rifornimento e reporting. Aggiungendo i canali a una gerarchia organizzativa, è possibile assegnare assortimenti a gruppi di punti vendita. Invece di assegnare l'assortimento singolarmente per ogni punto vendita, è possibile assegnare l'assortimento al nodo dell'organizzazione di alto livello. Successivamente, ogni volta che viene aggiunto un nuovo canale al nodo dell'organizzazione di alto livello, tale canale eredita automaticamente tutti gli assortimenti che sono stati assegnati al nodo dell'organizzazione di livello superiore. È possibile assegnare assortimenti solo ai canali inclusi in una gerarchia organizzativa a cui è stato assegnato lo scopo **Assortimento di commercio**. |
| Definire prodotti.                  | Prima di poter aggiungere prodotti a un assortimento, è necessario aggiungerli in Commerce. È possibile aggiungere prodotti manualmente oppure importarli da un fornitore. Dopo aver aggiunto i prodotti, è necessario rilasciarli a una persona giuridica. Solo i prodotti che sono stati rilasciati a una persona giuridica possono essere resi disponibili per i canali. È possibile aggiungere a un assortimento prodotti che non sono stati ancora rilasciati a una persona giuridica e approvare l'assortimento. Tuttavia, i prodotti non possono essere resi disponibili per i canali fino a quando non vengono rilasciati a una persona giuridica. |
| Impostare una gerarchia di categorie.      | Quando si creano prodotti di commercio, è possibile raggrupparli e organizzarli in categorie utilizzando la funzionalità Gerarchia di categorie. È possibile creare una gerarchia di base per raggruppare e organizzare in categorie tutti i prodotti da distribuire tramite i canali. È inoltre possibile creare gerarchie di categorie separate supplementari per raggruppare e organizzare in categorie i prodotti per scopi speciali, come promozioni o assortimenti. Le gerarchie di categorie consentono di assegnare tutti i prodotti in una categoria specifica a un assortimento. Tutti i prodotti che vengono aggiunti alla categoria inclusa nell'assortimento vengono inclusi automaticamente nell'assortimento. Quindi, quando si esegue nuovamente l'utilità di pianificazione di assortimento di commercio, questi prodotti diventano disponibili per i canali di vendita al dettaglio a cui è assegnato l'assortimento. |

## <a name="setting-up-an-assortment"></a>Impostazione di un assortimento

Dopo aver completato i prerequisiti, è possibile creare un assortimento e assegnarlo ai canali. Per impostare un assortimento, è necessario completare le attività indicate di seguito.

1. Creare un nuovo assortimento o copiare un assortimento esistente.
2. Selezionare i canali o i gruppi di canali di alto livello a cui applicare l'assortimento.
3. Aggiungere categorie di prodotti, singoli prodotti o varianti prodotto all'assortimento. È possibile includere tutti i prodotti di una categoria specifica o escludere determinati prodotti da una categoria inclusa nell'assortimento.
4. Pubblicare l'assortimento. Quando si pubblica un assortimento, l'utilità di pianificazione di assortimento viene eseguita automaticamente. Questo processo genera l'elenco dei prodotti. Quando il processo è completo, i prodotti diventano disponibili per i canali a cui è assegnato l'assortimento. Se vengono apportate modifiche a un assortimento che è stato pubblicato o ai canali a cui è assegnato l'assortimento, l'assortimento deve essere aggiornato. Per aggiornare l'assortimento quando vengono apportate modifiche, è possibile eseguire l'utilità di pianificazione di assortimento come processo batch.
