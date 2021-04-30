---
title: Stornare le transazioni di leasing registrate
description: Questo argomento spiega come stornare una transazione di leasing registrata. Qualsiasi transazione creata tramite Leasing cespite può essere stornata.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseLeaseTransactions
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 55eb7c5f2419bf1cb2ac0a33a82ab931a3ef380f
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881544"
---
# <a name="reverse-posted-lease-transactions"></a>Stornare le transazioni di leasing registrate

[!include [banner](../includes/banner.md)]

Qualsiasi transazione creata tramite Leasing cespite può essere stornata. Le transazioni stornate tramite Leasing cespite aggiornano i dati del leasing. Pertanto, aggiornano anche i valori contabili dell'obbligazione sul leasing e l'Asset Right of use (ROU).

Per creare una transazione di storno per un leasing, attieniti alla seguente procedura.

1. Nella pagina **Transazioni cespiti** o **Transazioni di passività**, seleziona la transazione, quindi seleziona **Transazione di storno**.
2. Nella finestra di dialogo che appare, è possibile modificare la data in cui verrà registrato lo storno. Per impostazione predefinita, il campo **Data** è impostato sulla data di registrazione della transazione selezionata. Il movimento di storno non può essere registrato prima della data di registrazione originale della transazione selezionata.
3. Selezionare **OK**. Viene registrata una scrittura contabile che storna il movimento selezionato. Lo storno è mostrato nella pagina **Transazioni cespiti** o **Transazioni di passività** e il totale netto del saldo corrente visualizzato nella pagina viene aggiornato.

Quando selezioni **Tracciatura di storno**, viene visualizzata una finestra di dialogo che mostra sia le transazioni originali che le transazioni stornate, insieme a un numero collegato noto come *numero di traccia*. Per semplificare la comprensione degli storni e migliorare la visibilità, è anche possibile tenere traccia degli storni utilizzando i programmi di leasing.

Il campo **Ultimo numero giornale di registrazione** nella pagina **Programma** mostra i numeri di giornale di registrazione delle transazioni. Quando una transazione viene stornata, questo campo viene aggiornato con il numero di giornale di registrazione di una transazione di storno. Inoltre, la casella di controllo **Stornato** è selezionata per indicare che la transazione è stata stornata e il campo **Registrato** è selezionato.

## <a name="revoke-a-reversed-transaction"></a>Revocare una transazione stornata

Per revocare una transazione stornata, segui questi passaggi.

1. Nella pagina **Programma** o **Transazioni**, seleziona la transazione originale.
2. Eseguire uno dei passaggi riportati di seguito.

    - Se hai selezionato la transazione nella pagina **Programma**, segui i passaggi per creare un giornale di registrazione in [Creare registrazioni a giornale mensili in un batch](create-monthly-journals-batch.md). Devi registrare manualmente il giornale di registrazione.
    - Se hai selezionato la transazione nella pagina **Transazioni**, seleziona **Transazione di storno**. Viene visualizzato un messaggio in cui si afferma che questa revoca è una revoca di uno storno precedente e che è possibile modificare la data di registrazione per questa revoca. Tuttavia, le convalide aziendali generali influiscono sulle date che possono essere inserite nel campo **Data**. 

3. Selezionare **OK**. Viene registrata una scrittura contabile che storna il movimento selezionato. Lo storno viene mostrato nella pagina **Transazioni** e il saldo corrente totale netto viene riportato a quello che era prima del primo storno. Pertanto, l'impatto che lo storno ha avuto sui saldi viene annullato.

Quando selezioni **Tracciatura di storno**, viene visualizzata una finestra di dialogo che mostra sia le transazioni originali che le transazioni stornate, insieme a un numero di traccia collegato.

Puoi anche tenere traccia delle revoche utilizzando la pagina **Programmi** appropriata. Il campo **Storno** viene deselezionato, mentre il campo **Giornale di registrazione registrato** viene selezionato. Inoltre, il campo **Ultimo numero giornale di registrazione** viene aggiornato con il numero del giornale di registrazione della transazione di revoca e il campo **Numero giornale di registrazione** viene aggiornato con il numero di giornale di storno.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
