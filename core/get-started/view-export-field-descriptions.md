---
title: Visualizzare ed esportare le descrizioni campi
description: In questo articolo viene descritto come visualizzare le descrizioni dei campi e come utilizzare la pagina Descrizioni campi per esportare le descrizioni.
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: d4fc9cdee0e2160e363f9defcf6bdbc57ed4db74
ms.lasthandoff: 03/31/2017


---

# <a name="view-and-export-field-descriptions"></a>Visualizzare ed esportare le descrizioni campi

In questo articolo viene descritto come visualizzare le descrizioni dei campi e come utilizzare la pagina Descrizioni campi per esportare le descrizioni.

Microsoft Dynamics 365 for Operations offre descrizioni per alcuni campi più complessi. Queste descrizioni vengono visualizzate quando si passa su un campo con il mouse. È anche possibile visualizzare ed esportare le descrizioni dalla pagina **Descrizioni campi**. 

Non tutte le pagine presentano descrizioni dei campi. Sono riportate solo le descrizioni dei campi più complessi, non di quelli il cui uso è ovvio. Pertanto, le descrizioni dei campi non sono presenti in alcune pagine, alcune pagine hanno alcune descrizioni e alcune delle pagine più complesse, ad esempio molte delle pagine di parametri, includono molte descrizioni. 

Se si ha accesso all'ambiente di sviluppo di Microsoft Dynamics 365 for Operations è possibile aggiungere nuove descrizioni dei campi e personalizzare quelle esistenti. Ad esempio, è possibile aggiungere informazioni specifiche della società per la descrizione di un campo. Per ulteriori informazioni, vedere [Personalizzare la Guida relativa ai campi](/dynamics365/operations/dev-itpro/user-interface/customize-field-help).

## <a name="see-field-descriptions-in-the-user-interface"></a>Vedere le descrizioni dei campi nell'interfaccia utente.
È possibile visualizzare le descrizioni dei campi passando con il mouse su un campo. Se non è disponibile alcuna descrizione, verrà visualizzato il nome del campo al passaggio del mouse sul campo. (Nota: Nella versione l'intervallo, le descrizioni dei campi possono essere visualizzate solo ** descrizioni dei campi ** nella pagina). Nella seguente figura è illustrata la descrizione del campo visualizzato quando sorvolate ** chiudere articoli durante il conteggio ** il campo. 

[esempio![di una descrizione del campo (]. /media/field-description.png)](. /media/field-description.png)

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a>Utilizzare la pagina Descrizioni campi per visualizzare ed esportare la Guida sui campi
La pagina **Descrizioni campi** consente di visualizzare ed esportare le descrizioni dei campi. È possibile visualizzare le descrizioni disponibili per una pagina alla volta.

### <a name="view-the-descriptions-for-a-page"></a>Visualizzare le descrizioni per una pagina

Per visualizzare le descrizioni di una pagina, seguire questo passaggio.

-   Nel campo **Seleziona pagina** digitare il nome della pagina. In alternativa, fare clic sulla freccia per aprire un elenco di tutte le pagine e quindi cercare o filtrare l'elenco.

È possibile utilizzare il nome della pagina visualizzato nell'interfaccia utente, ad esempio **Clienti**, o il nome in codice (nome AOT) disponibile facendo clic con il pulsante destro del mouse su una pagina, ad esempio **CustTable**. 

Per informazioni sui vari modi per filtrare l'elenco delle pagine, vedere la sezione "Ricerca di una pagina" più avanti in questo articolo. 

Se si imposta l'opzione **Includi campi senza descrizione** su **Sì**, vengono visualizzati tutti i campi della pagina, anche se non hanno una descrizione.

### <a name="export-the-descriptions-for-a-page"></a>Esportare le descrizioni di una pagina

Per esportare le descrizioni di una pagina, seguire questi passaggi.

1.  Nel campo **Seleziona pagina** selezionare una pagina.
2.  Fare clic sul pulsante **Apri in Microsoft Office** nell'angolo superiore destro, quindi selezionare **FieldDescriptionTmp**.

### <a name="searching-for-a-page"></a>Ricerca di una pagina

Vi sono diversi modi per cercare una pagina nel campo **Seleziona pagina**. In molti casi è necessario fare clic sulla freccia nel campo **Seleziona pagina** per aprire l'elenco a discesa e selezionare da un elenco filtrato di pagine.

-   Digitare parte del nome, quindi aprire l'elenco a discesa per selezionare da un elenco filtrato di pagine.
-   Aprire l'elenco a discesa e fare clic sull'intestazione **Nome pagina** nella parte superiore dell'elenco o sull'intestazione **Nome AOT pagina**. Verrà visualizzata una finestra di dialogo in cui è possibile utilizzare opzioni di filtro avanzate, ad esempio **Il nome della pagina inizia con**.
-   Digitare il nome completo della pagina. Quando si utilizza questa opzione, è consigliabile aprire l'elenco a discesa e verificare gli altri elementi presenti nell'elenco anche se sono riportate descrizioni dei campi.
    -   Se è presente una sola corrispondenza esatta del nome, vengono riportate le descrizioni dei campi per la pagina.
    -   Se esiste più di una corrispondenza esatta, nessuna descrizione viene visualizzata. È necessario aprire l'elenco a discesa e selezionare la pagina desiderata.
    -   Se il nome digitato è parte del nome di un'altra pagina, sarà possibile visualizzare le descrizioni della pagina. Tuttavia, se si apre l'elenco a discesa, vengono visualizzate altre pagine che contengono il nome.

Ad esempio, nessuna descrizione viene visualizzata in seguito a l ** particolare ** nel **** si seleziona un campo di **** della pagina. Si apre l'elenco a discesa e si nota che ci sono due pagine con il nome **Conteggio**, nonché varie pagine il cui nome contiene la parola "Conteggio". Se si seleziona la pagina che presenta il nome AOT **InventJournalCount**, vengono visualizzate le descrizioni dei campi per tale pagina. Tuttavia, se si apre nuovamente l'elenco a discesa, si noterà che l'elenco ora contiene tutte le pagine che presentano come parte del loro nome AOT "InventJournalCount".

## <a name="troubleshooting"></a>Risoluzione dei problemi
In questa sezione vengono fornite informazioni per consentire la risoluzione dei problemi che si possono riscontrare utilizzando le descrizioni campi.

### <a name="i-cant-find-a-field-description"></a>Impossibile trovare la descrizione di un campo

È in corso l'aggiunta di descrizioni per i campi più complessi. Se sono necessarie informazioni per un campo specifico, è possibile comunicarlo aggiungendo un commento a questo articolo wiki.

### <a name="the-field-description-isnt-helpful"></a>La descrizione di un campo non è utile

Comunicarlo aggiungendo un commento a questo articolo wiki. Se possibile, descrivere le informazioni aggiuntive necessarie.

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a>Impossibile trovare un campo della pagina Descrizioni campi

Per visualizzare tutti i campi in una pagina, impostare l'opzione **Includi campi senza descrizione** su **Sì**. Fare clic sul campo **Seleziona pagina** per verificare di aver selezionato la pagina corretta. Se il nome digitato è parte di un altro nome di campo, potrebbe essere stata selezionata la pagina con il nome più lungo.

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a>Impossibile trovare una pagina nella pagina Descrizioni campi

Per informazioni sui vari modi per trovare le pagine, vedere la sezione "Ricerca di una pagina" in precedenza in questo articolo. Se si è immesso il nome esatto della pagina, le descrizioni dei campi possono non essere riportate in caso siano presenti più pagine con lo stesso nome. Fare clic sul campo **Seleziona pagina** per aprire un elenco filtrato delle pagine disponibili.

<a name="see-also"></a>Vedere anche
--------

[Personalizzare la Guida relativa ai campi](https:/docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/user-interface/customize-field-help.md)


