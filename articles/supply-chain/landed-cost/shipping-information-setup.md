---
title: Impostazione delle informazioni di spedizione
description: In questo argomento viene descritto come impostare le informazioni di spedizione per il modulo Costo sbarcato.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 86350acfd056be2b43fc856e3b76b1632989a804
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579690"
---
# <a name="shipping-information-setup"></a>Impostazione delle informazioni di spedizione

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come impostare le informazioni di spedizione per il modulo **Costo sbarcato**.

## <a name="description-of-goods"></a><a name="description-of-goods"></a>Descrizione delle merci

Le descrizioni delle merci aiutano a identificare un viaggio, un contenitore di spedizione o una registrazione di merci e le merci in esso contenute. È possibile selezionare una descrizione delle merci nell'intestazione del contenitore di spedizione o della registrazione.

Selezionare **Costo sbarcato \> Impostazione informazioni di spedizione \> Descrizione delle merci** per visualizzare, aprire, creare ed eliminare record per le descrizioni delle merci. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Descrizione delle merci | Immettere un nome/numero di identificazione univoco per il tipo di merce che utilizzerà questa descrizione. |
| Descrizione | Immettere una descrizione del tipo di merce in questa categoria. |

## <a name="vessels"></a><a name="vessels"></a>Imbarcazioni

Un'imbarcazione è il nome univoco di una nave o di un'imbarcazione utilizzata da una società o un'agenzia di spedizione. Quando si crea un viaggio, si deve sempre selezionare o immettere un'imbarcazione. Se si utilizzano spesso le stesse imbarcazioni, è possibile semplificare e rendere più veloce la creazione di un nuovo viaggio creando un record per ogni imbarcazione, consentendo così agli utenti di selezionare l'imbarcazione da un elenco piuttosto che inserire manualmente il nome o il numero ogni volta.

Selezionare **Costo sbarcato \> Impostazione informazioni di spedizione \> Imbarcazioni** per visualizzare, aprire, creare ed eliminare record per le imbarcazioni. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Imbarcazione | Immettere un nome/numero di identificazione univoco per la nave che verrà utilizzata per il trasporto delle merci in un viaggio. |
| Descrizione | Immettere una descrizione dell'imbarcazione. In genere, questa descrizione identifica il nome della nave e la società e l'agenzia di spedizione. |
| Modalità di consegna | Selezionare la modalità di consegna dell'imbarcazione (come _Via aerea_, _Via mare_ o _Treno_). |

## <a name="exporters"></a>Esportatori

Ogni record di esportatore identifica un fornitore o un esportatore che può essere definito come fornitore di un viaggio. L'esportatore può essere associato a un viaggio e utilizzato per i report.

Selezionare **Costo sbarcato \> Impostazione informazioni di spedizione \> Esportatori** per visualizzare, aprire, creare ed eliminare record per gli esportatori. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Esportatore | Immettere un nome/numero di identificazione univoco per gli esportatori delle merci che vengono trasportate in un viaggio. |
| Descrizione | Immettere una descrizione dell'esportatore. In genere, questa descrizione identifica il nome completo della società/agenzia di spedizione. |

## <a name="commodity-codes"></a>Codici voce doganale

I codici voce doganale facilitano l'identificazione doganale e il calcolo delle aliquote dei dazi per le merci in un viaggio. È possibile selezionare codici voce doganale nella pagina **Prodotti rilasciati**.

Selezionare **Costo sbarcato \> Impostazione informazioni di spedizione \> Codici voce doganale** per visualizzare, aprire, creare ed eliminare record per i codici voce doganale. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Codice voce doganale | Immettere un codice univoco per questo tipo di voce doganale. |
| Descrizione | Immettere una descrizione per il tipo di voce doganale. |

## <a name="customs-description"></a>Descrizione doganale

Le descrizioni doganali aiutano a identificare le merci a fini doganali. È possibile selezionare una descrizione doganale nella pagina **Prodotti rilasciati** o nelle righe di ordine fornitore.

Selezionare **Costo sbarcato \> Impostazione informazioni di spedizione \> Descrizione doganale** per visualizzare, aprire, creare ed eliminare record per le descrizioni doganali. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Descrizione doganale | Immettere un codice univoco per questo tipo di classificazione doganale. Spesso, questo codice sarà la descrizione ufficiale fornita da un'autorità doganale per la descrizione e il valore qualitativo delle merci. |
| Descrizione | Immettere una descrizione della classificazione doganale. |
