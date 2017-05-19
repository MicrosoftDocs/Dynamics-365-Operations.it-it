---
title: Domande frequenti sulle traduzioni relative ai prodotti
description: In questo argomento viene descritto come gestire le traduzioni per i prodotti, i valori di dimensione prodotto e gli attributi del prodotto.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysTranslationDetail, SysTranslationLanguage, SysTranslationList
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 201853
ms.assetid: c0286bba-f54b-42de-904c-81fd796bdd1d
ms.search.region: global
ms.search.industry: Product information
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 809b853634aa4a44b8aa3aebea317f6bc47da697
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="product-related-translations-faq"></a>Domande frequenti sulle traduzioni relative ai prodotti

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto come gestire le traduzioni per i prodotti, i valori di dimensione prodotto e gli attributi del prodotto. 

<a name="what-product-related-data-can-be-translated"></a>Quali dati relativi al prodotto possono essere tradotti?
--------------------------------------------

È possibile creare le traduzioni per le seguenti informazioni relative al prodotto:
-   Nomi e descrizioni dei prodotti.
-   Descrizioni, nomi descrittivi e testo della Guida dei valori degli attributi del prodotto.
-   Nomi e descrizione dei valori di dimensione prodotto.

È possibile tradurre le informazioni relative al prodotto in qualsiasi lingua disponibile nella pagina **Traduzione testo**. Per ulteriori informazioni, vedere la sezione successiva **“Come creare le traduzioni per le informazioni relative al prodotto**".

## <a name="where-can-i-view-the-translated-information"></a>Dove si possono visualizzare le informazioni tradotte?
È possibile visualizzare le traduzioni delle informazioni relative al prodotto in qualsiasi documento di origine esterno, ad esempio una fattura, che utilizza una lingua in cui le traduzioni sono disponibili.

## <a name="how-do-i-create-translations-for-productrelated-information"></a>Come si creano le traduzioni per le informazioni relative al prodotto?
Per creare le traduzioni per un prodotto, completare i passaggi seguenti:
1.  Fare clic su **Gestione informazioni sul prodotto** &gt; **Comune** &gt; **Prodotti rilasciati**.
2.  Selezionare un prodotto e, nel riquadro azioni, gruppo **Lingue**, fare clic su **Traduzioni**.
3.  Nel campo **Lingua** della pagina **Traduzione testo**, selezionare una lingua. Per aggiungere più lingue, espandere il campo **Lingua** e fare clic su **OK**.
4.  Nel gruppo **Testo tradotto** immettere le traduzioni nei campi **Descrizione** e **Nome prodotto**.

Per creare le traduzioni per gli attributi del prodotto, completare i passaggi seguenti:
1.  Fare clic su **Gestione informazioni sul prodotto** &gt; **Comune** &gt; **Prodotti rilasciati**.
2.  In **Impostazione**fare clic su **Attributi**, quindi su **Attributi**.
3.  Nella pagina **Attributi**, fare clic su **Traduci**.
4.  Nel campo **Lingua** della pagina **Traduzione testo**, selezionare una lingua. Per aggiungere più lingue, espandere il campo **Lingua** e fare clic su **OK**.
5.  Nel gruppo **Testo tradotto** immettere le traduzioni nei campi **Descrizione** , **Nome descrittivo** e **Testo Guida**.

Per creare le traduzioni per i valori delle dimensioni prodotto, completare i passaggi seguenti:
1.  Fare clic su **Gestione informazioni sul prodotto** &gt; **Comune** &gt; **Prodotti rilasciati**.
2.  Selezionare un prodotto, quindi fare clic su **Dimensioni prodotto**.
3.  Selezionare uno dei collegamenti per le dimensioni prodotto: **Configurazioni**, **Dimensioni**, **Colori** o **Stile**.
4.  Selezionare un valore di dimensione, quindi fare clic su **Traduci**.
5.  Nel campo **Lingua** della pagina **Traduzione testo**, selezionare una lingua. Per aggiungere più lingue, espandere il campo **Lingua** e fare clic su **OK**.
6.  Nel gruppo **Testo tradotto** immettere le traduzioni nei campi **Nome** e **Descrizione**.

## <a name="can-the-names-of-product-variants-be-translated"></a>Possono essere tradotti i nomi delle varianti prodotto?
Le varianti prodotto si basano sulle dimensioni di un prodotto rilasciato. I nomi delle varianti prodotto sono basati su una combinazione di valori di dimensione. Quando i valori di dimensione associati a una variante prodotto vengono tradotti, il nome della variante prodotto viene visualizzato nella versione tradotta.  

**Esempio**  

Il prodotto è una maglietta che ha dimensioni e colori diversi e i nomi delle varianti si basano sui seguenti dettagli:
-   Numero prodotto: \#3
-   Dimensioni: Size and color
-   Valori della dimensione: Small, Medium, Large
-   Valori della dimensione colore: Red, Green, Black

Il nome di una variante prodotto che si basa sui valori di dimensione Small e Red è **\#3:Small:Red**.  

Un cliente desidera acquistare alcune magliette piccole e rosse e il nome della maglietta deve essere presente in francese nella fattura. Tradurre i valori delle dimensioni, Small e Red, in francese e il nome della variante prodotto diventa **\#3:Petit:Rouge**.
<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Suggerimento</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Per impostare la lingua preferita di un cliente, effettuare le operazioni seguenti:
<ol>  
<li>Fare clic su <strong>Vendite e marketing</strong> &gt; <strong>Comune</strong> &gt; <strong>Clienti</strong> &gt; <strong>Tutti</strong>  <strong>i clienti</strong>.</li>
<li>Fare doppio clic su un cliente per aprire la pagina <strong>Clienti</strong>. Nella scheda <strong>Generale</strong> selezionare la <strong>lingua</strong> nel campo <strong>Lingua</strong>..</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="what-happens-if-a-customer-has-a-preferred-language-for-which-no-translations-are-available"></a>Cosa succede se per la lingua preferita del cliente non sono disponibili le traduzioni?
Se le traduzioni non sono disponibili nella lingua preferita del cliente, i nomi e le descrizioni vengono visualizzate nella lingua globale della società specifica.

## <a name="can-i-manage-translations-for-a-series-of-dimension-values-at-the-same-time"></a>Le traduzioni possono essere gestite per una serie di valori di dimensione contemporaneamente?
I valori di dimensione sono specifici del prodotto ed è possibile gestire le traduzioni per i valori di dimensione di ogni prodotto. Tuttavia, se si crea un gruppo di valori di dimensione e si creano le traduzioni per i valori del gruppo di valori, è più semplice gestire le traduzioni.   

**Esempio**  

La società produce magliette in stili diversi e per ogni stile sono disponibili tutte le dimensioni (Small, Medium e Large). Le dimensioni vengono raccolte in un gruppo di valori di dimensione. Quando un nuovo stile di maglietta viene aggiunto, è possibile associarlo al gruppo di valori di dimensione che viene utilizzato per le dimensioni, in modo che tutte le dimensioni siano disponibili per il prodotto. È inoltre possibile aggiungere o modificare le traduzioni per le dimensioni presenti nel gruppo di valori di dimensione in qualsiasi momento.  

Un valore di dimensione associato a un prodotto tramite un gruppo di varianti dimensione deve essere gestito da un gruppo di varianti prodotto.   
Per creare un gruppo di valori di dimensione, completare i passaggi seguenti:
1.  Fare clic su **Gestione informazioni sul prodotto** &gt; **Impostazione** &gt; **Gruppi di varianti**.
2.  Selezionare **Gruppi** **di dimensioni**, **Gruppi di colori** o **Gruppi di stili**.
3.  Fare clic su **Nuovo** e immettere un nome per il gruppo nel campo **Gruppo** **di dimensioni**, **Gruppo di colori** o **Gruppo di stili**. Fare clic su **Dimensioni**, **Colori** o **Stili** per creare le righe per i gruppi.
4.  Nella pagina **Righe** **gruppo** di dimensioni, **Righe** **gruppo** **di colori** o **Righe gruppi di stil**i, fare clic su **Nuovo** e creare le dimensioni, i colori e gli stili per i gruppi.

Per gestire le traduzioni per i valori in un gruppo di valori di dimensione, effettuare le operazioni seguenti:
1.  Seguire i passaggi della procedura precedente per creare un gruppo di valori di dimensioni per aprire la pagina **Righe gruppo di dimensioni** **Righe gruppo di colori** o **Righe gruppo di stili**.
2.  Fare clic su **Traduzione testo**. Nella pagina **Traduzione testo**, gruppo **Testo tradotto** immettere le traduzioni nei campi **Nome** e **Descrizione**.

## <a name="when-can-translations-of-productrelated-information-be-managed"></a>Quando è possibile gestire le traduzioni delle informazioni relative al prodotto?
Le traduzioni delle informazioni relative al prodotto possono essere gestite in qualsiasi momento. Quando le traduzioni vengono aggiornate per un valore di dimensione associato a un prodotto, le informazioni del prodotto vengono aggiornate, indipendentemente dalla presenza delle transazioni del prodotto.






