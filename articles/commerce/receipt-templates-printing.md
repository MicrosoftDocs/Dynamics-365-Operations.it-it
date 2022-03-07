---
title: Impostare e progettare formati di ricevute
description: In questo articolo viene descritto come modificare layout modulo per controllare la modalità di stampa di ricevute, fatture e altri documenti. Dynamics 365 Commerce include una progettazione layout modulo che è possibile utilizzare per creare e modificare con facilità vari tipi di layout modulo.
author: BrianShook
ms.date: 09/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFormLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 57841
ms.assetid: e530dd8e-95e2-4021-90bd-ce1235f9e250
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: dac0ad75ff35367b5d6ac84c75c68e22e2cb0cb1
ms.sourcegitcommit: f4823a97c856e9a9b4ae14116a43c87f9482dd90
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2021
ms.locfileid: "7779403"
---
# <a name="set-up-and-design-receipt-formats"></a>Impostare e progettare formati di ricevute

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come modificare layout modulo per controllare la modalità di stampa di ricevute, fatture e altri documenti. Dynamics 365 Commerce include una progettazione layout modulo che è possibile utilizzare per creare e modificare con facilità vari tipi di layout modulo.

> [!IMPORTANT]
> È necessario impostare i layout modulo e i profili della ricevuta per stampare le ricevute e altri documenti da Retail Modern POS e POS cloud. È possibile includere più layout modulo in un profilo ricevuta. È possibile quindi assegnare il profilo della ricevuta a una stampante modificando un profilo hardware.

## <a name="set-up-a-receipt-format"></a>Impostare un formato di ricevuta

1. Fare clic su **Retail e Commerce** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **POS** &gt; **Formati ricevuta**.
2. Nella pagina **Formati ricevuta** fare clic su **Nuovo** per creare un nuovo layout modulo o selezionare un layout modulo esistente.
3. Nel campo **Formati ricevuta** immettere un identificativo per il layout modulo e quindi selezionare il tipo di ricevuta per cui viene utilizzato per layout. È inoltre possibile immettere una descrizione e un nome breve per la ricevuta nel campo **Titolo**.
4. Nella scheda dettaglio **Generale** selezionare un'opzione per definire il comportamento di stampa:

    - **Stampa sempre**: la ricevuta viene stampata automaticamente, come appropriato.
    - **Non stampare**: la ricevuta non viene stampata.
    - **Richiedi conferma all'utente**: all'utente viene chiesto se stampare la ricevuta.
    - **Come richiesto**: questa opzione viene utilizzata solo per le ricevute di regali. Se questa opzione è selezionata, l'utente può stampare le ricevute di regali dalla pagina **Modifica** se richieste.

## <a name="print-images"></a>Stampare le immagini

La finestra di progettazione della ricevuta include una variabile **Logo**. Puoi utilizzare questa variabile per specificare un'immagine da stampare sulle ricevute. Le immagini stampate sulle ricevute utilizzando la variabile **Logo** devono essere di tipi di file bitmap monocromatici (.bmp). Se un'immagine bitmap è specificata nella finestra di progettazione della ricevuta ma non viene stampata quando la ricevuta viene inviata alla stampante, la causa potrebbe essere uno dei seguenti problemi:

- La dimensione del file è troppo grande o le dimensioni in pixel dell'immagine non sono compatibili con la stampante. In questo caso, prova a ridurre la risoluzione o le dimensioni del file immagine.
- Alcuni driver di stampante Object Linking and Embedding for Point of Sale (OPOS) non implementano il metodo **PrintMemoryBitmap** utilizzato dalle stazioni hardware per stampare le immagini del logo. In questo caso, prova ad aggiungere il seguente flag al file **HardwareStation.Extension.config** della stazione hardware dedicata o condivisa:

    `<add name="HardwareStation.UsePrintBitmapMethod" value="true"/>`

## <a name="design-a-receipt-format"></a>Progettare un formato di ricevuta

Utilizzare il progetto del layout modulo per creare graficamente il layout del documento del modulo. La pagina **Progettazione formato ricevuta** include tre sezioni: **Intestazione**, **Righe** e **Piè di pagina**. Alcuni tipi di layout modulo utilizzano elementi di tutte e tre le sezioni, mentre altri tipi utilizzano elementi solo di una o due sezioni. Per visualizzare gli elementi disponibili per ogni sezione, fare clic sul pulsante nell'area di navigazione a sinistra della pagina.

1. Fare clic su **Retail e Commerce** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **POS** &gt; **Formati ricevuta**.
2. Nella pagina **Formato ricevuta** selezionare un layout modulo e quindi fare clic su **Progettazione**.
3. Fare clic su **Esegui** per avviare l'installazione dell'host della progettazione Commerce.
4. Nella barra di notifica visualizzata nella parte inferiore della finestra di Internet Explorer, fare clic su **Apri** per avviare l'installazione della progettazione con un clic. La barra di notifica potrebbe apparire in una posizione diversa in altri browser. L'indicatore di avanzamento mostra l'avanzamento del processo di installazione.
5. Dopo che l'impostazione è stata completata, immettere nome utente e password di Commerce e quindi fare clic **Accedi** per avviare la finestra di progettazione.
6. Dopo che le credenziali vengono convalidate e si avvia la progettazione, è possibile iniziare a progettare il formato ricevuta o a modificare un formato esistente.
7. Per creare gli elementi del modulo, selezionare la sezione **Intestazione**, **Righe** o **Piè di pagina** e quindi trascinare un elemento dalla sezione all'area di lavoro. La maggior parte degli elementi contengono variabili che sono automaticamente compilate con dati ricavati dal database. Altre elementi, ad esempio il **Testo**, consentono di stampare testo personalizzato sulla ricevuta.

    > [!NOTE]
    > È possibile specificare su quante righe si estenderà ciascuna sezione modificando il numero nell'angolo inferiore destro della sezione. Per semplificare la modifica di una sezione, aumentare l'altezza della sezione trascinando la barra di ridimensionamento nella parte inferiore della sezione. L'altezza della sezione nell'area di lavoro non influisce sul numero di righe della ricevuta effettiva.

8. Dopo aver trascinato un elemento nello spazio di lavoro, impostare le proprietà per la parte nel riquadro **Informazioni oggetto** in fondo al modulo. Immettere una o più delle seguenti informazioni:

    - **Allinea**: impostare l'allineamento del campo su **A sinistra** o **A destra**.
    - **Carattere di riempimento**: specificare il carattere di spazio vuoto. Per impostazione predefinita, viene utilizzato uno spazio vuoto ma può essere immesso qualsiasi carattere.
    - **Prefisso**: immettere il valore che viene visualizzato all'inizio del campo. Questa impostazione è valida solo per la sezione **Righe** del layout.
    - **Caratteri**: consente di specificare il numero massimo di caratteri che il campo può contenere se l'elemento contiene una variabile. Se il testo del campo ha una lunghezza superiore al numero di caratteri specificati, il testo viene troncato in modo che si adatti al campo.
    - **Variabile**: se l'elemento contiene una variabile e non può essere personalizzato, la casella di controllo viene automaticamente selezionata.
    - **Tipo di carattere**: impostare lo stile di carattere su **Normale** o **Grassetto**. Le lettere in grassetto utilizzano due volte lo spazio delle lettere normali. Pertanto, alcuni caratteri potrebbero essere troncati.
    - **Dimensione carattere**: impostare le dimensioni del carattere su **Normale** o **Grande**. Le dimensioni delle lettere grandi sono due volte maggiori delle lettere normali. Di conseguenza, l'utilizzo di lettere grandi può causare una sovrapposizione del testo nella ricevuta.
    - **Elimina**: fare clic su questo pulsante per rimuovere la parte selezionata dal layout modulo.

## <a name="assign-receipt-profiles"></a>Assegnazione di profili ricevuta

I profili ricevuta vengono assegnati direttamente alle stampanti nel profilo hardware.

1. Aprire il profilo hardware facendo clic su **Retail e Commerce** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Profili POS** &gt; **Profilo hardware**.
2. Selezionare la stampante e quindi, nel campo **Profilo ricevuta** assegnare il profilo ricevuta da utilizzare nel registro.

> [!NOTE]
> Se vengono utilizzate due stampanti, una stampante può essere utilizzata per stampare le ricevute termali a 40 colonne standard. La seconda stampante viene in genere utilizzata per stampare i tipi di ricevuta a pagina intera che richiedono ulteriori informazioni. Questi tipi di ricevuta includono le ricevute per l'ordine cliente e le fatture cliente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
