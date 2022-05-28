---
title: Impostare i modelli di valore
description: In questa procedura viene illustrato come creare un nuovo libro cespiti e associarlo a un gruppo cespite.
author: moaamer
ms.date: 12/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71d256b600956a4e525cde626c958713f6258f5a
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727063"
---
# <a name="set-up-value-models"></a>Impostare i modelli di valore

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

In questa procedura viene illustrato come creare un nuovo libro cespiti e associarlo a un gruppo cespite.

## <a name="create-a-book"></a>Creare un libro
1. Vai a **Cespiti \> Impostazione \> Libri**.
2. Selezionare **Nuovo**.
3. Nel campo **Libro** immetti un valore.
4. Nel campo **Descrizione** immettere un valore.
5. Imposta l'opzione **Calcola ammortamento** su **Sì**.

    Se l'opzione **Calcola ammortamento** è impostata su **Sì**, il libro del cespite associato verrà incluso nelle proposte di ammortamento. Se è impostata su **No**, il libro cespiti non verrà ammortizzato automaticamente.

6. Nel campo **Profilo di ammortamento** immetti o seleziona un valore.

    * Un profilo di ammortamento alternativo è anche noto come metodo di ammortamento alternativo. La proposta di ammortamento passerà a questo profilo quando il profilo alternativo calcolerà un importo di ammortamento uguale o maggiore del profilo di ammortamento predefinito.
    * Parametri di ammortamento straordinario viene utilizzato per l'ammortamento aggiuntivo di un cespite in circostanze insolite. È ad esempio possibile utilizzare questi parametri per registrare l'ammortamento causato da un disastro naturale.
    * Se selezioni **Crea rettifiche all'ammortamento con rettifiche di base**, le rettifiche di ammortamento verranno automaticamente create quando il valore del cespite viene aggiornato. In caso contrario, il valore del cespite aggiornato influirà solo sui futuri calcoli di ammortamento.

7. Imposta l'opzione **Crea rettifiche all'ammortamento con rettifiche di base** su **Sì**.

    * Per impostazione predefinita, le transazioni libro cespiti vengono registrate nella contabilità generale. Tuttavia puoi disabilitare la registrazione nella contabilità generale per il libro impostando l'opzione **Registra nella contabilità generale** su **No**. I libri che non vengono registrati nella contabilità generale sono in genere utilizzati a fini di reporting fiscale. Ciò offre flessibilità aggiuntiva per eliminare le transazioni storiche del libro cespiti perché non sono state impegnate nella contabilità generale.
    * Per impostazione predefinita, il campo **Livello di registrazione** è impostato su **Livello attuale** se il libro è registrato nella contabilità generale e su **Nessuno** se il libro non è registrato nella contabilità generale. Aggiorna il valore del campo **livello di registrazione** se le transazioni per il libro devono essere registrate in un altro livello.

8. Calcola ammortamento positivo.

    * Per impostazione predefinita, l'opzione **Calcola ammortamento positivo** è impostata su **No**. Questa impostazione indica che l'ammortamento accrediterà il libro cespiti selezionato. Inoltre, le opzioni **Consenti valore contabile netto superiore al prezzo di acquisizione** e **Consenti valore contabile netto negativo** sono entrambe impostate su **No** e le impostazioni possono essere modificate indipendentemente. 
    * Per calcolare l'ammortamento positivo, imposta l'opzione **Calcola deprezzamento positivo** su **sì**. Questa impostazione indica che l'ammortamento addebiterà il libro cespiti. Quando l'opzione **Calcola ammortamento positivo** è impostata su **sì**, le opzioni **Consenti valore contabile netto superiore al prezzo di acquisizione** e **Consenti valore contabile netto negativo** verranno automaticamente impostate su **sì**, e saranno bloccate. Questo blocco consente di garantire che l'ammortamento positivo venga applicato solo ai cespiti acquisiti con un valore contabile negativo (credito). 

10. Nel campo **Calendario** immetti o seleziona un valore.

    I libri derivati registreranno transazioni in libri diversi contemporaneamente. Le transazioni si creano con il libro principale e durante la registrazione, una copia esatta della transazione viene registrata nel libro derivato. Non esiste un ricalcolo con le transazioni nei libri derivati, quindi non devono essere utilizzati per le transazioni di ammortamento.

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Associare il libro a un gruppo cespite

1. Seleziona **Gruppi di cespiti**.
2. Nel campo **Gruppo cespite** immettere o selezionare un valore.
3. Immetti un numero nel campo **Vita utile**.

    * I periodi di ammortamento sono calcolati dopo aver inserito la vita utile del bene.
    * La convenzione di ammortamento può essere impostata come richiesto a fini fiscali.
    * Per le attività fisse che sono associate a leasing, il valore nel campo **Vita utile** sarà sovrascritto dal minore tra la durata del leasing nel libro delle attività e la vita utile dell'attività. Se l'opzione **Trasferimento di proprietà** è impostata su **Sì** per il libro delle locazioni, il valore nel campo **Vita** utile sarà sempre la vita utile del cespite.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
