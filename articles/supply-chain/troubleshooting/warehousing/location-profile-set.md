---
title: Il profilo ubicazione impedisce le scorte negative ma non le scorte disponibili negative
description: L'opzione Consenti inventario negativo del profilo ubicazione è impostata su No, ma il sistema consente comunque scorte disponibili negative.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 2a7345281301ee70a512dfadcd553cb4eb33003904d0dddf6967659b693f60d7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742610"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a>Il profilo ubicazione impedisce le scorte negative ma non le scorte disponibili negative

Numero KB: 4613622

## <a name="symptoms"></a>Sintomi

L'opzione **Consenti inventario negativo** del profilo ubicazione è impostata su *No*, ma il sistema consente comunque scorte disponibili negative.

## <a name="example-scenario"></a>Scenario di esempio

Per le transazioni regolamentate dal governo, il sistema deve essere in grado di registrare scorte negative per registrare le perdite. Desideri che un articolo possa mostrare scorte negative, ma solo in ubicazioni designate, come i serbatoi. Tuttavia, se il gruppo di modelli di articoli consente scorte negative, non importa se l'ubicazione è impostata o meno per consentire le scorte negative. Se l'articolo è impostato di modo che le scorte negative non siano consentite, non importa come è impostato il profilo ubicazione.

## <a name="resolution"></a>Risoluzione

L'impostazione **Consenti inventario negativo** del profilo ubicazione si applica solo ai processi di magazzino, come il prelievo. Tuttavia, i gruppi di modelli di articoli impostati per consentire scorte negative influiscono su tutti i processi dei moduli Gestione inventario e Gestione magazzino e il profilo ubicazione non sovrascriverà l'impostazione.

Puoi controllare se per un magazzino è consentito avere scorte negative. Imposta i gruppi di modelli di articoli per disabilitare le scorte fisiche negative e imposta solo il magazzino pertinente per consentire le scorte negative.
