---
title: Richieste di informazioni e report sui materiali pericolosi
description: Questo argomento spiega come lavorare con i vari report relativi ai materiali pericolosi. Molti di questi report sono necessari per mantenere la conformità con le varie normative sui materiali pericolosi durante la spedizione e lo stoccaggio.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: cee824e9e8f7577d1d4a6c0a21c7341608e1f588
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243131"
---
# <a name="hazardous-materials-inquiries-and-reports"></a>Richieste di informazioni e report sui materiali pericolosi

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Microsoft Dynamics 365 Supply Chain Management fornisce vari report relativi ai materiali pericolosi. Molti di questi report sono necessari per mantenere la conformità con le varie normative sui materiali pericolosi durante la spedizione e lo stoccaggio.

Tutti questi report, tranne il report **Merci pericolose multimodali**, utilizzano la modalità di consegna definita per la spedizione per trovare la normativa da utilizzare per stampare il testo di spedizione per gli articoli. La modalità di consegna è associata al vettore di spedizione e al servizio di trasporto. Pertanto, è necessario impostare un vettore di spedizione e un servizio di trasporto e collegarli a una modalità di consegna. La modalità di consegna è correlata alla normativa sui materiali pericolosi.

La seguente illustrazione mostra la sequenza di attività che si verificano quando il sistema genera report sui materiali pericolosi.

![Sequenza delle attività per i report sui materiali pericolosi](media/hazmat-report-sequence.png "Sequenza delle attività per i report sui materiali pericolosi")

## <a name="set-up-hazardous-materials-reporting"></a><a name="set-up"></a>Impostare la creazione di report sui materiali pericolosi

Di solito, se si spediscono articoli che contengono materiali pericolosi, è necessario generare report specifici per preservare la sicurezza e rispettare le normative sui materiali pericolosi. Per impostare i report effettuare le seguenti operazioni.

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
2. Aprire la scheda **Report**. Nella Scheda dettaglio **Parametro report materiali pericolosi**, impostare i seguenti campi.

    | Sezione | Campo | Descrizione |
    |---|---|---|
    | Merci pericolose multimodali | Codice normativa | Selezionare la normativa da utilizzare quando viene generato il report **Merci pericolose multimodali**. |
    | Limiti delle scorte di materiali pericolosi | Codice normativa | Selezionare la normativa da utilizzare quando vengono valutati i limiti delle scorte. |
    | Trasporto merce su strada | Prodotto gruppo CMR | CMR significa "sostanze cancerogene, mutagene e tossiche per la riproduzione". Impostare questa opzione su **Sì** per configurare il sistema in modo che stampi avvisi e messaggi specifici relativi alla gestione di queste sostanze. |
    | Trasporto merce su strada | Descrizione gruppo materiali pericolosi | Immettere il testo di avvertenze specifiche relative alle CMR e al trasporto di merci su strada. Questo testo viene incluso nel report. |
    | Dichiarazione dello spedizioniere | Avviso | Immettere il testo di un messaggio di avviso che deve essere stampato sul modulo di dichiarazione dello spedizioniere (ad esempio, "Avvertenza: merce pericolosa, infiammabile"). |
    | Dichiarazione dello spedizioniere | Dichiarazione piè di pagina | Immettere il testo di un messaggio da stampare in fondo al documento di dichiarazione di spedizione. |
    | Lingua report merci pericolose | Lingua report nazionale merci pericolose | Selezionare la lingua predefinita per i report sui materiali pericolosi associati alle spedizioni nazionali. |
    | Lingua report merci pericolose | Lingua report esportazione merci pericolose | Selezionare la lingua predefinita per i report sui materiali pericolosi associati alle spedizioni internazionali. |

## <a name="hazardous-materials-report"></a>Report sui materiali pericolosi

Il report **Materiali pericolosi** mostra l'elenco di tutti gli articoli che sono stati impostati e definiti in modo da avere informazioni sulle merci pericolose. È possibile utilizzare questo report per monitorare e rivedere le informazioni che è necessario conservare. La pagina per il report mostra una selezione limitata di campi della configurazione dei materiali pericolosi. Tuttavia, è possibile personalizzarla per aggiungere altri campi come necessario.

Per visualizzare questo report andare a **Gestione informazioni sul prodotto \> Richieste di informazioni e report \> Documentazione per la spedizione di materiali pericolosi \> Materiali pericolosi**.

## <a name="hazardous-material-stock-limit-report"></a><a name="stock-limit-report"></a>Report sui limiti delle scorte di materiali pericolosi

Il report **Limite delle scorte di materiali pericolosi** consente di monitorare i livelli delle scorte di materiali pericolosi nelle ubicazioni del magazzino, per assicurarsi che rimangano entro i limiti di sicurezza stabiliti. Questi limiti provengono dai limiti definiti per ogni prodotto rilasciato.

Per visualizzare questo report andare a **Gestione informazioni sul prodotto \> Richieste di informazioni e report \> Documentazione per la spedizione di materiali pericolosi \> Limiti delle scorte di materiali pericolosi**.

Per ulteriori informazioni su come impostare i limiti delle scorte per un prodotto rilasciato, vedere [Impostare i limiti delle scorte per prodotti pericolosi](hazmat-items.md#stock-limits).

La normativa utilizzata per i limiti delle scorte è definita nella pagina **Parametri di gestione magazzino**. Andare a **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino** e quindi nella scheda **Report**, in **Limite delle scorte di materiali pericolosi**, specificare un codice normativa. Per ulteriori informazioni, vedere la sezione [Impostare la creazione di report sui materiali pericolosi](#set-up) più indietro in questo argomento.

## <a name="verified-gross-mass-report"></a>Report sulla massa lorda verificata

Il report **Massa lorda verificata** consente di stampare le informazioni sul peso di una spedizione.

Per generare e stampare questo report andare a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni** e aprire la spedizione pertinente. Quindi, nel riquadro azioni, nella scheda **Spedizioni**, nel gruppo **Documento sui materiali pericolosi**, selezionare **Massa lorda verificata**.

## <a name="multimodal-dangerous-goods-report"></a>Report sulle merci pericolose multimodali

Il report **Merci pericolose multimodali** viene fornito per le spedizioni che devono essere spostate utilizzando una combinazione di metodi di trasporto. Viene generalmente utilizzato quando una spedizione viene spostata prima su strada e successivamente via mare.

Per generare e stampare questo report andare a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni** e aprire la spedizione pertinente. Quindi, nel riquadro azioni, nella scheda **Spedizioni**, nel gruppo **Documento sui materiali pericolosi**, selezionare **Merci pericolose multimodali**.

Quando si genera questo report, le informazioni vengono salvate in modo da poterlo modificare e/o ristampare se necessario. Per modificare un report generato, andare a **Gestione magazzino \> Richieste di informazioni e report \> Documentazione per la spedizione di materiali pericolosi \> Merci pericolose multimodali** e trovare il report pertinente nell'elenco. Dopo aver modificato il contenuto come necessario, selezionare **Stampa** nel riquadro azioni per stampare il report.

## <a name="shippers-declaration-report"></a>Report di dichiarazione dello spedizioniere

Il report **Dichiarazione dello spedizioniere** consente di stampare le informazioni relative a una dichiarazione dei materiali inclusi nella spedizione.

Per generare e stampare questo report andare a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni** e aprire la spedizione pertinente. Quindi, nel riquadro azioni, nella scheda **Spedizioni**, nel gruppo **Documento sui materiali pericolosi**, selezionare **Dichiarazione dello spedizioniere**.

## <a name="carriage-of-merchandise-by-road-report"></a>Report di trasporto merce su strada

Il report **Trasporto di merce su strada** assomiglia a una polizza di carico, ma è generalmente utilizzato per il trasporto su strada in Europa ai sensi dell'accordo relativo alle normative ADR (International Carriage of Dangerous Goods by Road). Questo report utilizza il testo della stampa della spedizione per un articolo a meno che non si imposta il campo **Descrizione gruppo di materiali pericolosi** nella pagina **Parametri di gestione magazzino**.

Per generare e stampare questo report andare a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni** e aprire la spedizione pertinente. Quindi, nel riquadro azioni, nella scheda **Spedizioni**, nel gruppo **Documento sui materiali pericolosi**, selezionare **Trasporto merce su strada**.

Quando si genera questo report, le informazioni vengono salvate in modo da poterlo modificare e/o ristampare se necessario. Per modificare un report generato, andare a **Gestione magazzino \> Richieste di informazioni e report \> Documentazione per la spedizione di materiali pericolosi \> Trasporto merce su strada** e trovare il report pertinente nell'elenco. Dopo aver modificato il contenuto come necessario, selezionare **Stampa** nel riquadro azioni per stampare il report.

## <a name="shipment-summary-report"></a>Report di riepilogo spedizione

Il report **Riepilogo spedizione** fornisce le informazioni riepilogative della categoria di trasporto correlata agli articoli rilasciati.

Per generare e stampare questo report andare a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni** e aprire la spedizione pertinente. Quindi, nel riquadro azioni, nella scheda **Spedizioni**, nel gruppo **Documento sui materiali pericolosi**, selezionare **Riepilogo spedizione**.

## <a name="bill-of-lading-report"></a>Report di polizza di carico

Quando la funzione dei materiali pericolosi è attivata nel sistema, il report **polizza di carico** include una colonna **Materiali pericolosi** che indica se un carico include materiali pericolosi. Questo report è disponibile nella pagina **Tutti i carichi**, come di consueto.

## <a name="packing-list-report"></a>Report di elenco imballaggio

Quando la funzione dei materiali pericolosi è attivata nel sistema, gli elenchi di imballaggio includono informazioni aggiuntive correlate al testo della stampa della spedizione per un articolo. Questo report è disponibile nella pagina **Tutti i carichi**, come di consueto.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]