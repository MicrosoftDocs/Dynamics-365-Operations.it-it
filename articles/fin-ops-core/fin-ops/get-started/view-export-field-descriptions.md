---
title: Visualizzare ed esportare le descrizioni campi
description: In questo articolo viene descritto come visualizzare le descrizioni dei campi e come utilizzare la pagina Descrizioni campi per esportare le descrizioni.
author: twheeloc
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.form: FieldDescriptions
ms.openlocfilehash: d2d59796b312d50d69bf7722b605c159a933a283
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292368"
---
# <a name="view-and-export-field-descriptions"></a>Visualizzare ed esportare le descrizioni campi

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

In questo articolo viene descritto come visualizzare le descrizioni dei campi e come utilizzare la pagina Descrizioni campi per esportare le descrizioni.

Alcuni dei campi più complessi hanno le descrizioni. Queste descrizioni vengono visualizzate quando si passa su un campo con il mouse. È anche possibile visualizzare ed esportare le descrizioni dalla pagina **Descrizioni campi**.

Non tutte le pagine presentano descrizioni dei campi. Sono riportate solo le descrizioni dei campi più complessi, non di quelli il cui uso è ovvio. Pertanto, le descrizioni dei campi non sono presenti in alcune pagine, alcune pagine hanno alcune descrizioni e alcune delle pagine più complesse, ad esempio molte delle pagine di parametri, includono molte descrizioni.

Se si ha accesso all'ambiente di sviluppo è possibile aggiungere nuove descrizioni dei campi e personalizzare quelle esistenti. Ad esempio, è possibile aggiungere informazioni specifiche della società per la descrizione di un campo. Per ulteriori informazioni, vedere [Personalizzare le descrizioni dei campi](../../dev-itpro/user-interface/customize-field-help.md).

## <a name="see-field-descriptions-in-the-user-interface"></a>Vedere le descrizioni dei campi nell'interfaccia utente.

È possibile visualizzare le descrizioni dei campi passando con il mouse su un campo. Se non è disponibile alcuna descrizione, verrà visualizzato il nome del campo al passaggio del mouse sul campo.

> [!NOTE]
> In Dynamics AX 7.0 (Febbraio 2016), le descrizioni dei campi possono essere visualizzate solo nella pagina **Descrizioni campi**.

La seguente illustrazione mostra la descrizione che viene visualizzata quando si passa con il mouse sul campo **Blocca articoli durante il conteggio**.

[![Esempio di una descrizione di campo.](./media/field-description.png)](./media/field-description.png)

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a>Utilizzare la pagina Descrizioni campi per visualizzare ed esportare la Guida sui campi

La pagina **Descrizioni campi** consente di visualizzare ed esportare le descrizioni dei campi. È possibile visualizzare le descrizioni disponibili per una pagina alla volta.

### <a name="view-the-descriptions-for-a-page"></a>Visualizzare le descrizioni per una pagina

Per visualizzare le descrizioni di una pagina, seguire questo passaggio.

- Nel campo **Seleziona pagina** digitare il nome della pagina. In alternativa, fare clic sulla freccia per aprire un elenco di tutte le pagine e quindi cercare o filtrare l'elenco.

È possibile utilizzare il nome della pagina visualizzato nell'interfaccia utente, ad esempio **Clienti**, o il nome in codice (nome AOT) disponibile facendo clic con il pulsante destro del mouse su una pagina, ad esempio **CustTable**.

Per informazioni sui vari modi per filtrare l'elenco delle pagine, vedere la sezione "Ricerca di una pagina" più avanti in questo articolo.

Se si imposta l'opzione **Includi campi senza descrizione** su **Sì**, vengono visualizzati tutti i campi della pagina, anche se non hanno una descrizione.

### <a name="export-the-descriptions-for-a-page"></a>Esportare le descrizioni di una pagina

Per esportare le descrizioni di una pagina, seguire questi passaggi.

1. Nel campo **Seleziona pagina** selezionare una pagina.
2. Fare clic sul pulsante **Apri in Microsoft Office** nell'angolo superiore destro, quindi selezionare **FieldDescriptionTmp**.

### <a name="searching-for-a-page"></a>Ricerca di una pagina

Vi sono diversi modi per cercare una pagina nel campo **Seleziona pagina**. In molti casi è necessario fare clic sulla freccia nel campo **Seleziona pagina** per aprire l'elenco a discesa e selezionare da un elenco filtrato di pagine.

- Digitare parte del nome, quindi aprire l'elenco a discesa per selezionare da un elenco filtrato di pagine.
- Aprire l'elenco a discesa e fare clic sull'intestazione **Nome pagina** nella parte superiore dell'elenco o sull'intestazione **Nome AOT pagina**. Verrà visualizzata una finestra di dialogo in cui è possibile utilizzare opzioni di filtro avanzate, ad esempio **Il nome della pagina inizia con**.
- Digitare il nome completo della pagina. Quando si utilizza questa opzione, è consigliabile aprire l'elenco a discesa e verificare gli altri elementi presenti nell'elenco anche se sono riportate descrizioni dei campi.

    - Se è presente una sola corrispondenza esatta del nome, vengono riportate le descrizioni dei campi per la pagina.
    - Se esiste più di una corrispondenza esatta, nessuna descrizione viene visualizzata. È necessario aprire l'elenco a discesa e selezionare la pagina desiderata.
    - Se il nome digitato è parte del nome di un'altra pagina, sarà possibile visualizzare le descrizioni della pagina. Tuttavia, se si apre l'elenco a discesa, vengono visualizzate altre pagine che contengono il nome.

Ad esempio, nessuna descrizione viene visualizzata quando si digita **Conteggio** nel campo **Seleziona pagina**. Si apre l'elenco a discesa e si nota che ci sono due pagine con il nome **Conteggio**, nonché varie pagine il cui nome contiene la parola "Conteggio". Se si seleziona la pagina che presenta il nome AOT **InventJournalCount**, vengono visualizzate le descrizioni dei campi per tale pagina. Tuttavia, se si apre nuovamente l'elenco a discesa, si noterà che l'elenco ora contiene tutte le pagine che presentano come parte del loro nome AOT "InventJournalCount".

## <a name="troubleshooting"></a>Risoluzione dei problemi

In questa sezione vengono fornite informazioni per consentire la risoluzione dei problemi che si possono riscontrare utilizzando le descrizioni campi.

### <a name="i-cant-find-a-field-description"></a>Impossibile trovare la descrizione di un campo

È in corso l'aggiunta di descrizioni per i campi più complessi. Se sono necessarie informazioni per un campo specifico, è possibile comunicarlo aggiungendo un commento a questo articolo.

### <a name="the-field-description-isnt-helpful"></a>La descrizione di un campo non è utile

Comunicala aggiungendo un commento a questo articolo. Se possibile, descrivere le informazioni aggiuntive necessarie.

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a>Impossibile trovare un campo della pagina Descrizioni campi

Per visualizzare tutti i campi in una pagina, impostare l'opzione **Includi campi senza descrizione** su **Sì**. Fare clic sul campo **Seleziona pagina** per verificare di aver selezionato la pagina corretta. Se il nome digitato è parte di un altro nome di campo, potrebbe essere stata selezionata la pagina con il nome più lungo.

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a>Impossibile trovare una pagina nella pagina Descrizioni campi

Per informazioni sui vari modi per trovare le pagine, vedere la sezione "Ricerca di una pagina" in precedenza in questo articolo. Se si è immesso il nome esatto della pagina, le descrizioni dei campi possono non essere riportate in caso siano presenti più pagine con lo stesso nome. Fare clic sul campo **Seleziona pagina** per aprire un elenco filtrato delle pagine disponibili.

## <a name="additional-resources"></a>Risorse aggiuntive

[Personalizzare le descrizioni dei campi](../../dev-itpro/user-interface/customize-field-help.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
