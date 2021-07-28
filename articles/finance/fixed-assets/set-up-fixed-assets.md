---
title: Impostare i cespiti
description: In questo argomento viene fornita una panoramica dell'impostazione del modulo Cespiti.
author: moaamer
ms.date: 06/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13771
ms.assetid: 8be64197-fea1-4a34-8af2-d939919c28b1
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9c26b45fc94d9983157eef9af5c0af6845d24056
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356753"
---
# <a name="set-up-fixed-assets"></a>Impostare i cespiti

[!include [banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica dell'impostazione del modulo **Cespiti**. 

I parametri controllare il comportamento generale dei cespiti. I gruppi cespite consentono di raggruppare i cespiti e specificare gli attributi predefiniti per ciascun cespite assegnato a un gruppo. I libri sono assegnati a gruppi cespite. I libri tengono traccia del valore finanziario di un cespite nel tempo utilizzando la configurazione di ammortamento definita nel profilo di ammortamento.

I cespiti vengono assegnati a un gruppo nel momento in cui vengono creati. Per impostazione predefinita, i libri assegnati al gruppo cespite vengono assegnati al cespite. I libri configurati per la registrazione nella contabilità generale sono associati a un profilo di registrazione. I conti CoGe vengono definiti per ogni libro nel profili di registrazione e vengono utilizzati nella registrazione delle transazioni cespiti.

![Componenti dei cespiti.](./media/FAComponents_Updated.png)

## <a name="depreciation-profiles"></a>Profili di ammortamento

I profili di ammortamento devono essere impostati come primi. Nel profilo di ammortamento, configurate in che modo il valore di un cespite viene ammortizzato nel tempo. È necessario definire il metodo di ammortamento, l'anno di ammortamento (anno di calendario o anno fiscale) e la frequenza di ammortamento. Per ulteriori informazioni, vedere [Impostare e creare profili di ammortamento](tasks/set-up-depreciation-profiles.md).

## <a name="books"></a>Libri

Dopo aver impostato i profili di ammortamento, è necessario creare i libri necessari per i cespiti. Ciascun libro tiene traccia di un ciclo di vita finanziario indipendente di un cespite. I libri possono essere configurati per registrare le transazioni associate nella contabilità generale. Questa configurazione è l'impostazione predefinita, poiché viene utilizzata in genere per i report finanziari aziendali. I libri che non registrano nella contabilità generale registrano solo nel giornale di registrazione cespiti secondario e in genere vengono utilizzati ai fini delle dichiarazioni fiscali.

Un profilo di ammortamento primario viene assegnato a ciascun libro. I libri hanno anche un profilo di ammortamento alternativo, se questo tipo di profilo è applicabile. Per includere automaticamente il libro cespiti nelle esecuzioni di ammortamento, è necessario abilitare l'opzione **Calcola ammortamento**. Se l'opzione non è abilitata per un cespite, la proposta di ammortamento salta il cespite.

È inoltre possibile impostare libri derivati. Le transazioni derivate specificate vengono registrate rispetto ai libri derivati come copia esatta della transazione primaria. Di conseguenza, le transazioni derivate sono impostate in genere per le acquisizioni e le dismissioni, non per le transazioni di ammortamento. Per ulteriori informazioni, vedere [Impostare i modelli di valore](tasks/set-up-value-models.md).

Un'opzione nella pagina **Parametri cespiti** permette di bloccare e sbloccare questa funzionalità. È possibile abilitare questa funzione nell'**area di lavoro Gestione funzionalità**.

## <a name="fixed-asset-posting-profiles"></a>Profili registrazione cespiti

Una volta impostato il libro, è possibile creare il profilo di registrazione. Il profilo di registrazione deve essere definito per libro, ma può anche essere definito a livello più dettagliato. Ad esempio, è possibile definire il profilo di registrazione per la combinazione di libro e gruppo cespite, o persino per un singolo libro cespiti. Per impostazione predefinita, i conti CoGe definiti vengono utilizzati per le transazioni cespiti.

È necessario definire i conti CoGe utilizzati durante i processi di dismissione, sia vendita per dismissione che scarti per dismissione. Al momento della dismissione, le transazioni cespiti precedentemente registrate vengono stornate dai conti originali. Gli importi netti vengono spostati in un conto appropriato per profitti e perdite per dismissioni cespiti. Per contribuire a garantire che le transazioni siano stornate correttamente, è necessario impostare conti per ogni tipo di transazione utilizzato nella società. Il conto principale deve essere il conto originale impostato per il tipo di transazione nel profilo di registrazione, mentre il conto di contropartita deve essere il conto profitti e perdite per la dismissione. L'eccezione è il valore contabile netto. In questo caso, il conto principale e il conto di contropartita devono essere impostati sul conto profitti e perdite per la dismissione. Per ulteriori informazioni, vedere [Impostare i profili registrazione cespiti](tasks/set-up-fixed-asset-posting-profiles.md).

## <a name="fixed-asset-groups"></a>Gruppi cespite

Il campo **Gruppo cespite** è l'unico campo obbligatorio quando si crea un cespite. Il valore di questo campo determina il valore predefinito dei diversi campi informativi per il cespite. I libri vengono impostati in modo da assegnare un libro predefinito a ciascun cespite in un gruppo. In questo modo, gli attributi impostati per i libri possono essere specifici in un gruppo di cespiti. Tali attributi includono la vita utile e la convenzione di ammortamento.

È inoltre possibile definire i fondi di ammortamento speciale, o ammortamento aggiuntivo, per una specifica combinazione di gruppo cespite e libro. È necessario assegnare una priorità al fondo di ammortamento speciale per specificare l'ordine in cui i fondi vengono calcolati quando più fondi vengono assegnati a un libro. Per ulteriori informazioni, vedere [Impostare gruppi di cespiti](tasks/set-up-fixed-asset-groups.md).

## <a name="journal-names"></a>Nomi giornale di registrazione

Nella pagina **Nomi giornale di registrazione**, è necessario creare i nomi di giornale di registrazione da utilizzare per il giornale di registrazione cespiti. È necessario impostare il campo **Tipo di giornale di registrazione** su **Registra cespiti**. Impostare il campo **Serie giustificativi** in modo da utilizzare i nomi di giornale di registrazione per il giornale di registrazione cespiti. I giornali di registrazione cespiti non devono utilizzare l'impostazione **Un solo numero di giustificativo**, in quanto per più processi automatizzati, ad esempio i trasferimenti e le suddivisioni, viene richiesto un numero univoco per il giustificativo.

## <a name="fixed-asset-parameters"></a>Parametri Cespiti

L'ultimo passaggio è l'aggiornamento dei parametri del cespite.

Il campo **Soglia di capitalizzazione** determina i cespiti che verranno ammortizzati. Se una riga di acquisto è selezionata come cespite, ma non corrisponde al valore soglia di capitalizzazione, il cespite viene ancora creato o aggiornato, ma l'opzione **Calcola ammortamento** è impostata su **No**. Di conseguenza, il cespite non verrà ammortizzato automaticamente come parte delle proposte di ammortamento.

Un'importante opzione è **Crea automaticamente importi di rettifica all'ammortamento con dismissione**. Quando si imposta questa opzione su **Sì**, l'ammortamento del cespite viene rettificato automaticamente, in base alle impostazioni di ammortamento al momento della dismissione. Un'altra opzione consente di detrarre gli sconti di cassa dall'importo dell'acquisizione quando si acquistano i cespiti utilizzando una fattura fornitore.

Il parametro **Blocca libri cespiti in un giornale di registrazione ammortamenti** permette di bloccare i libri cespiti in un giornale di registrazione degli ammortamenti. Quando vengono registrate le transazioni di ammortamento, il sistema verificherà che lo stesso libro cespiti non sia stato aggiunto a più di un giornale di registrazione degli ammortamenti. In caso affermativo, il libro cespiti verrà bloccato e la registrazione verrà interrotta. Se un ID libro cespiti si trova in un giornale bloccato, verrà sbloccato automaticamente al termine della registrazione per il giornale originale. È anche possibile sbloccare il giornale di registrazione manualmente. 

Nella scheda dettaglio **Ordini fornitore**, è possibile configurare la modalità secondo cui i cespiti vengono creati durante il processo di acquisto. La prima opzione è denominata **Consenti acquisizione cespiti da Acquisto**. Se si imposta questa opzione su **Sì**, l'acquisizione del cespite verrà applicata quando viene registrata la fattura. Se si imposta questa opzione su **No**, sarà comunque possibile inserire un cespite in un ordine fornitore (PO) e in fattura, ma l'acquisizione non verrà registrata. La registrazione deve essere eseguita come passaggio distinto dal giornale di registrazione cespiti. L'opzione **Crea cespite durante la registrazione entrata prodotti o fattura** consente di creare un nuovo cespite immediatamente durante la registrazione. Di conseguenza, il cespite non deve essere impostato come cespite prima della transazione. L'ultima opzione, **Verifica creazione cespiti durante l'immissione riga**, si applica solo alle richieste di acquisto.

I codici motivo possono essere configurati come necessari per le modifiche a un cespite o per transazioni cespiti specifiche.

Infine, nella scheda **Sequenze numeriche**, è necessario definire le sequenze numeriche per i cespiti. La sequenza numerica **Cespiti** può essere sostituita dalla sequenza numerica del **Gruppo cespite** se è stata specificata.

Per ulteriori informazioni, vedere [Creare un cespite](tasks/create-fixed-asset.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
