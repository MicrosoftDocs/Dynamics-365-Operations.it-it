---
title: Utilizzare il componente aggiuntivo di Excel
description: "In questo argomento viene illustrato come i dati dell&quot;entità aperta in Microsoft Excel e quindi visualizzare, aggiornare e modificare i dati utilizzando il componente aggiuntivo Office di Microsoft Dynamics in Excel. Per aprire i dati di entità, è possibile iniziare da Excel o da Microsoft Dynamics 365 per le operazioni."
author: ChrisGarty
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: af7e7288f741b3c519227e2778c4c4311c3a2012
ms.openlocfilehash: 8af663b47117759ed3b2e2ed8eee85ae4df100d1
ms.lasthandoff: 03/31/2017


---

# <a name="use-the-excel-add-in"></a>Utilizzare il componente aggiuntivo di Excel

In questo argomento viene illustrato come i dati dell'entità aperta in Microsoft Excel e quindi visualizzare, aggiornare e modificare i dati utilizzando il componente aggiuntivo Office di Microsoft Dynamics in Excel. Per aprire i dati di entità, è possibile iniziare da Excel o da Microsoft Dynamics 365 per le operazioni.

I dati dell'entità di apertura in Microsoft Excel, è possibile visualizzare e modificare modo semplice e rapido i dati utilizzando il componente aggiuntivo Office di Microsoft Dynamics in Excel. Questo componente aggiuntivo richiede Microsoft Excel 2016. ** Nota: ** Se nel titolare di Active Directory di Microsoft Azure (ANNUNCIO azzurrato) viene configurato Active Directory utilizzare Federation Services ANNUNCIO FS), verificare che l'aggiornamento sia del maggio 2016 viene applicato, in modo che il componente aggiuntivo di Excel può firmarvi correttamente in.

## <a name="open-entity-data-in-excel-when-you-start-from-dynamics-365-for-operations"></a>Data dell'entità aperta in Excel quando si inizia da Dynamics 365 per le operazioni
1.  In una pagina in Microsoft Dynamics 365 per le operazioni, fare clic su ** aprire Microsoft Office **. Se l'origine dati principale (scheda della pagina è analoga a quella l'origine dati per tutte le entità, standard principale ** aperto in Excel ** opzioni per il quale è stata generata la pagina. ** Aperto in Excel ** opzioni è possibile individuare le pagine spesso utilizzate, ad esempio ** tutti i fornitori ** ** e tutti i clienti **.
2.  Fare clic su ** aprire in Excel ** un'opzione e aprire la cartella di lavoro generata. Questa cartella di lavoro è obbligatorio per l'entità, un puntatore all'ambiente e un puntatore al componente aggiuntivo Excel.
3.  In Excel, fare clic su ** abilitare modificare ** per attivare il componente aggiuntivo di Excel da eseguire. Il componente aggiuntivo Excel esecuzione nel riquadro a destra della finestra di Excel.
4.  Se si esegue per la prima volta il componente aggiuntivo di Excel, fare clic su fidi ** di questo Componente **.
5.  Se viene richiesto di firma in, fare clic su ** segno in ** quindi segno in utilizzare le stesse credenziali utilizzato per la firma in Dynamics a 365 per le operazioni. Il componente aggiuntivo Excel un precedente verrà utilizzata nel contesto di accesso tramite Internet Explorer e automaticamente vengono firmerà in, se possibile. Di conseguenza, verificare il nome utente nell'angolo superiore destro del componente aggiuntivo Excel.

Il componente aggiuntivo Excel legge automaticamente i dati dell'entità selezionata. Tenere presente che non verrà apportata alcuna dati nella cartella di lavoro finché il componente aggiuntivo di Excel non nel leggere.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Data dell'entità aperta in Excel quando si inizia da Excel
1.  In Excel, il ** inserimento ** cataloghi, ** Componenti ** nel gruppo, fare clic sul record ** ** per aprire la memoria di Office.
2.  Nella memoria di Office, cercare la parola chiave "Dynamics," e fare clic su ** aggiungere ** accanto a ** Componente di Office di Microsoft Dynamics (** il componente aggiuntivo di Excel).
3.  Se si esegue per la prima volta il componente aggiuntivo di Excel, fare clic su fidi ** di questo Componente ** per attivare il componente aggiuntivo di Excel da eseguire. Il componente aggiuntivo Excel esecuzione nel riquadro a destra della finestra di Excel.
4.  Fare clic su ** aggiungere le informazioni sul server ** per aprire ** opzioni ** il riquadro.
5.  Copiare il browser che l'URL dal destinatario Dynamics 365 per le operazioni relativo ad esempio, inserirlo nel server ** URL ** il campo e quindi eliminare tutti dopo il nome host, ad esempio **/? di eliminazione** cmp=usmf&mi=CustTableListPage). L'URL risultante è necessario che soltanto il nome host, ad esempio ** https://xxx.dynamics.com**).
6.  Fare clic su OK ** ** quindi fare clic su Sì ** ** per confermare la modifica. I aggiungere- I valori di Excel e metadati i carichi. ** Progettazione ** il pulsante risulterà disponibile. Se il componente aggiuntivo di Excel è a applet ** del carico ** pulsante, è probabilmente non siano firmati nella modalità di accesso corretto. Per ulteriori informazioni, vedere l'argomento relativo al pulsante di applet del carico è visualizzato nella sezione "Finestra" risoluzione di questo argomento.
7.  Fare clic su ** progettazione **. Il componente aggiuntivo Excel recupera i metadati dell'entità.
8.  Fare clic su ** aggiungere la tabella **. Elenco di entità verrà visualizzato. Le entità vengono elencate nel nome "-" contrassegni il formato.
9.  Selezionare dopo un'entità nell'elenco, ad esempio ** cliente per i clienti ** quindi fare clic su ** **.
10. Per aggiungere un campo ** campi disponibili **elenco a ** campi selezionati ** elenchi, e selezionare il campo e quindi fare clic su ** aggiungere **. In alternativa, fare doppio clic sul campo.
11. Dopo aver aggiunto i campi desiderati ** campi selezionati ** all'elenco, verificare che il cursore non sia nella posizione corretta nel foglio di lavoro, ad esempio cella A1) e fare clic su ** effettuato **. Fare clic su ** effettuato ** per chiudere la finestra di progettazione.
12. Fare clic su ** aggiornare ** per effettuare il pull di una serie di dati.

## <a name="view-and-update-entity-data-in-excel"></a>Consente di visualizzare e aggiornare i dati dell'entità in Excel
Dopo che il componente aggiuntivo di Excel legge i dati dell'entità nella cartella di lavoro, è possibile aggiornare in qualsiasi momento facendo clic sui dati ** aggiornare ** il componente aggiuntivo Excel.

## <a name="edit-entity-data-in-excel"></a>Modifica dei dati dell'entità in Excel
È possibile modificare i dati di entità come ordinati e quindi pubblicate data facendo clic ** pubblicare ** il componente aggiuntivo Excel. Per modificare un record, selezionare una cella del foglio di lavoro quindi modificare il valore di cella. Per aggiungere un nuovo record, eseguire uno dei seguenti passaggi:

-   Fare clic in un punto qualsiasi nel foglio di lavoro e fare clic su ** ** nel nuovo componente aggiuntivo di Excel.
-   Fare clic sull'ultima riga del foglio di lavoro quindi premere il tasto TAB finché il cursore si sposta dall'ultima colonna della riga e una nuova riga venga creata.
-   Fare clic sulla riga immediatamente nel foglio di lavoro e iniziare a immettere dati in una cella. Quando si sposta l'elemento attivo della cella, il foglio di lavoro si espande per includere la nuova riga.

Per eliminare un record, eseguire uno dei seguenti passaggi:

-   Fare clic con il pulsante destro del mouse sul numero di riga accanto alla riga del foglio di lavoro da eliminare e fare clic su Elimina ** **.
-   Fare clic con il pulsante destro del mouse sulla riga del foglio di lavoro da eliminare e fare clic su Elimina ** ** &gt; ** le righe della tabella **.

## <a name="add-or-remove-columns"></a>Aggiungi o rimuovi colonne
È possibile utilizzare la finestra di progettazione per rettificare le colonne aggiunti automaticamente al foglio di lavoro.

1.  Avvia la finestra di progettazione di origine dati del componente aggiuntivo Excel utilizzando opzioni ** ** viene subito (il simbolo di ingranaggio) e facendo ** attivare la progettazione ** la casella di controllo.
2.  Fare clic su ** progettazione ** il componente aggiuntivo Excel. Tutte le origini dati di lavoro.
3.  Accanto all'origine dati, scegliere ** modifica ** il pulsante (il simbolo a matita).
4.  Modificare l'elenco in ** campi selezionati ** elenco come ordinati:
    -   Per aggiungere un campo ** campi disponibili **elenco a ** campi selezionati ** elenchi, e selezionare il campo e quindi fare clic su ** aggiungere **. In alternativa, fare doppio clic sul campo.
    -   Per rimuovere un campo da ** campi selezionati ** elenchi, e selezionare il campo e quindi fare clic su ** rimuovere **. In alternativa, fare doppio clic sul campo.
    -   Per modificare l'ordine dei campi, fare clic sul campo in ** campi selezionati ** elencate e fare clic su ** ** o ** il drill-down **.

5.  Applica le modifiche alla fonte dei dati facendo ** ** aggiornamento. Fare clic su ** effettuato ** per chiudere la finestra di progettazione. Si supponga un campo (colonna), scegliere ** aggiornare ** per effettuare il pull di una serie di dati aggiornati.

## <a name="httpspowerappsmicrosoftcomenustutorialsdataplatforminteractiveexceltroubleshootingtroubleshooting"></a>[](https://powerapps.microsoft.com/enus/tutorials/dataplatforminteractiveexcel/#troubleshooting)Troubleshooting
Sono disponibili alcuni problemi che possono essere risolti per alcuni passaggi semplice.

-   ** Il pulsante di applet del carico è indicato. ** Se il componente aggiuntivo di Excel è a applet ** del carico ** pulsante dopo accesso in, è probabilmente non siano firmati nella modalità di accesso corretto. Per risolvere questo problema, verificare che il nome utente corretto visualizzato nell'angolo superiore destro del componente aggiuntivo Excel. Se un nome utente non viene visualizzato, clicchilo segno di uscita, quindi firmi data di entrata.
-   ** Viene visualizzato un messaggio "grave". ** Se si riceve un messaggio "grave" come componente aggiuntivo Excel viene caricare i metadati, il conto da firmare nel componente aggiuntivo Excel non dispone dell'autorizzazione a utilizzare il servizio, l'istanza, o il database di destinazione. Per risolvere questo problema, verificare che il nome utente corretto visualizzato nell'angolo superiore destro del componente aggiuntivo Excel. Se un nome utente non viene visualizzato, clicchilo segno di uscita, quindi firmi data di entrata.
-   ** La pagina Web vuoto viene visualizzata sopra Excel. ** Se una pagina Web vuoto viene visualizzato durante il processo di accesso, il conto per il ANNUNCIO FS, ma la versione di Excel che esegue il componente aggiuntivo non è sufficiente per caricare accesso nella finestra di dialogo. Per risolvere questo problema, aggiornare la versione di Excel in uso. Per aggiornare la versione di Excel quando si avrà il un'impresa che è al canale restituito, utilizzare [] strumento di distribuzione di Office (https://technet.microsoft.com/library/jj219422.aspx) [spostamento dal canale restituire al canale corrente] (https://technet.microsoft.com/library/mt455210.aspx).



