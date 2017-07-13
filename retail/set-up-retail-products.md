---
title: Impostare prodotti di vendita al dettaglio
description: Questo articolo descrive come impostare prodotti al dettaglio in Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 2be44e0000e9730aa93076f21a4204f5d56f6aac
ms.contentlocale: it-it
ms.lasthandoff: 06/20/2017



---

# <a name="set-up-retail-products"></a>Impostare prodotti di vendita al dettaglio

[!include[banner](includes/banner.md)]


Questo articolo descrive come impostare prodotti al dettaglio in Microsoft Dynamics 365 for Retail.

Prima di poter offrire i prodotti da rivendere nei canali di vendita al dettaglio, è necessario creare e configurare i prodotti in Dynamics 365 for Retail. Retail utilizza le funzionalità di prodotto in Dynamics 365 for Retail per creare i prodotti a livello di organizzazione nella rappresentazione generale prodotto. È possibile creare i prodotti, definire le proprietà e gli attributi prodotto e assegnare i prodotti alle gerarchie di categorie di vendite al dettaglio. Per rendere disponibili i prodotti ai canali di vendita al dettaglio e per aggiungerli a un assortimento attivo, è necessario rilasciare i prodotti alle persone giuridiche in cui sono disponibili. Per impostare i prodotti venduti tramite i canali di vendita al dettaglio, è necessario completare le attività seguenti.

1.  Definire una gerarchia di prodotti al dettaglio. Utilizzando le funzionalità di gerarchia di categorie in Dynamics 365 for Retail, è possibile definire le gerarchie di categorie di vendita al dettaglio per raggruppare e classificare i prodotti distribuiti nei canali di vendita al dettaglio. Gli attributi di sistema e definiti dall'utente possono essere specificati a livello di categoria. Quindi, tutti i prodotti assegnati alla categoria ereditano quegli attributi. È possibile definire più gerarchie di categorie e ogni prodotto può essere assegnato a più gerarchie. Tuttavia, in una singola gerarchia, ogni prodotto può essere assegnato solo a una categoria.
2.  Consente di aggiungere prodotti e varianti prodotto alla rappresentazione generale prodotto. I prodotti aggiunti alla rappresentazione generale prodotto costituiscono un elenco globale dei prodotti. È possibile aggiungere i prodotti manualmente, uno alla volta, oppure è possibile importare i dati prodotto dai fornitori.
3.  Rilasciare i prodotti a persone giuridiche. Solo i prodotti che sono stati rilasciati a persone giuridiche possono essere resi disponibili per i canali di vendita al dettaglio. Quando si definisce un prodotto per la prima volta, lo si definisce a livello di organizzazione. È possibile selezionare uno o più persone giuridiche a cui rilasciare il prodotto. Il prodotto diventerà disponibili in più canali di vendita al dettaglio nella propria organizzazione. È possibile utilizzare questa funzione per creare un prodotto, aggiungere e aggiornare attributi e proprietà prodotto in una posizione e quindi distribuire il prodotto nell'organizzazione in canali di vendita al dettaglio in cui è disponibile.
4.  Aggiunta di prodotti agli assortimenti. Un assortimento rappresenta una raccolta di prodotti offerti nei canali di vendita al dettaglio. È possibile definire uno o più assortimenti e ogni prodotto può essere assegnato a uno o più assortimenti. Per assegnare prodotti a canali di vendita al dettaglio, si assegnano gli assortimenti a tali canali. Quando si crea un assortimento, è possibile aggiungere prodotti non sono ancora rilasciati a una persona giuridica. Tuttavia, è necessario rilasciare i prodotti a una persona giuridica prima che possano essere resi disponibili per i canali di vendita al dettaglio.
5.  Aggiungere prodotti alle gerarchie di navigazione. Prima che i prodotti possono essere esplorati online o nel POS, devono essere classificati in una gerarchia di navigazione al dettaglio.
6.  Aggiungere prodotti ai cataloghi. Sebbene questo passaggio sia facoltativo per il POS, i punti vendita online richiedono che i prodotti siano inclusi in almeno un catalogo.





