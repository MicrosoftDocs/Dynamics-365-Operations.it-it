---
title: Creare una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio
description: In questo argomento viene descritto come creare una cartella di lavoro di Excel in modo da poter modificare le transazioni di vendita al dettaglio in Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: a2d41dd0470a4abae1a8238be8f1549fb094a026
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795741"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a>Creare una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come creare una cartella di lavoro di Excel in modo da poter modificare le transazioni di vendita al dettaglio in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Esiste un modello Excel predefinito a cui i clienti possono accedere da diverse parti del sistema e utilizzare per modificare e controllare le transazioni di vendita al dettaglio. Tuttavia, i clienti possono anche creare una cartella di lavoro Excel personalizzata per questo scopo.

## <a name="create-and-configure-an-excel-workbook"></a>Creare e configurare una cartella di lavoro di Excel

Per creare e configurare una cartella di lavoro di Excel in modo da poter modificare le transazioni di vendita al dettaglio, effettuare le seguenti operazioni.

1. Aprire Excel e creare una cartella di lavoro vuota.
1. Nella scheda **Inserisci**, selezionare **Miei componenti aggiuntivi**.
1. Nel riquadro di destra, selezionare il collegamento **Aggiungi informazioni sul server**.
1. Immettere l'URL del server e quindi selezionare **OK**.
1. Se si riceve un messaggio di errore "Nessuna registrazione applet trovata", seguire questi passaggi per risolvere il problema:

    1. In Commerce, passare a **Amministrazione sistema \> Imposta \> Parametri app di Office**.
    1. Nella Scheda dettaglio **Parametri app**, selezionare **Inizializza parametri app**.
    1. Nella finestra del messaggio di conferma, selezionare **OK**.
    1. Nella Scheda dettaglio **Applet registrati**, selezionare **Inizializza registrazione applet**.
    1. Ripetere i tre passaggi precedenti secondo le specifiche esigenze.

1. Selezionare **Progettazione** e quindi selezionare **Aggiungi tabella**.
1. In base ai dati che devono essere modificati, selezionare le entità che devono essere aggiunte alla cartella di lavoro di Excel per la modifica. Utilizzare la tabella seguente come riferimento.

    | Tipo di transazione | Entità di dati da utilizzare |
    |------------------|----------------------|
    | Transazioni cash-and-carry, ordini online, ordini cliente asincroni, offerte cliente asincrone | Transazione (verificabile), Transazione di vendita (verificabile), Transazioni di pagamento (verificabili), Transazioni fiscali (verificabili), Transazioni di sconto (verificabili), Transazioni di addebito (verificabili) |
    | Deposito bancario | Transazione (verificabile), Transazioni di metodo di pagamento bancario (verificabile) |
    | Deposito in cassaforte | Transazione (verificabile), Transazioni di pagamento in cassaforte (verificabile) |
    | Riepilogo incassi | Transazione (verificabile), Transazioni di riepilogo incassi (verificabile) |
    | Ricavi, Spese | Transazione (verificabile), Transazioni ricavi/spese (verificabili), Transazioni di pagamento (verificabili) |
    | Dichiara importo iniziale, Rimozione metodo di pagamento, Transazione fondo di cassa, Metodo di pagamento con resto, Fattura di pagamento, Deposito sul conto cliente | Transazione (verificabile), Transazioni di pagamento (verificabile) |

    > [!NOTE]
    > È importante aggiungere una sola entità di dati a ciascuna cartella di lavoro di Excel. Inoltre, tutti i campi contrassegnati dal simbolo della chiave devono essere aggiunti alla cartella di lavoro pertinente.

1. Dopo aver configurato la cartella di lavoro, applicare i filtri richiesti. Assicurati di applicare gli stessi filtri a tutti i fogli di lavoro nel file. Evitare di caricare grandi quantità di dati nel file Excel. In caso contrario, le prestazioni potrebbero risentirne ed Excel e il sistema potrebbero essere più lenti. È consigliabile utilizzare sempre "Azienda" e "Numero rendiconto" o "Numero transazione" come filtri per il file.
1. Dopo aver configurato i filtri, selezionare **Aggiorna** per caricare i dati.
1. Modificare i dati richiesti e quindi pubblicarli. Se il pulsante **Pubblica** non è disponibile, alcuni campi chiave probabilmente non sono stati aggiunti alla cartella di lavoro di Excel.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modificare e controllare le transazioni di cash-and-carry e di gestione di cassa](edit-cash-trans.md)

[Modificare e controllare le transazioni di ordini online e di ordini cliente asincroni](edit-order-trans.md)

[Modificare le dimensioni finanziarie per le transazioni di vendita al dettaglio](edit-financial-dim.md)

[Aggiungere campi a una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]