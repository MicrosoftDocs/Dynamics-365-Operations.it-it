<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="price-management.md" target-language="it-IT">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>price-management.9d0b0e.afa553fd0562b306f720f2a30c7f901db7ad1b3a.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>afa553fd0562b306f720f2a30c7f901db7ad1b3a</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>0fbfb9b0ab78c804f3931a083028d2ce313d6521</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/21/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\price-management.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Retail sales price management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gestione dei prezzi di vendita al dettaglio in Retail</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes the concepts for creating and managing sales prices in Microsoft Dynamics 365 for Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questo argomento descrive i concetti di creazione e gestione dei prezzi di vendita in Microsoft Dynamics 365 for Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Retail sales price management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gestione dei prezzi di vendita Retail</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>This topic provides information about the process of creating and managing sales prices in Microsoft Dynamics 365 for Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questo argomento fornisce informazioni sul processo di creazione e gestione dei prezzi di vendita in Microsoft Dynamics 365 for Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>It focuses on the concepts that are involved in this process, and on the effects of the various configuration options for sales prices.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si concentra sui concetti coinvolti in questo processo e sugli effetti delle varie opzioni di configurazione per i prezzi di vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>Terminology</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Terminologia</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>The following terms are used in this topic.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo argomento vengono utilizzati i seguenti termini:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Term</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Termine</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Definition, usage, and notes</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Definizione, utilizzo e note</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Price</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prezzo</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The single unit amount that a product sells for in a point of sale (POS) client or on a sales order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'importo unitario in base a cui un prodotto viene venduto in un POS o in un ordine cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>In this topic, the term <bpt id="p1">*</bpt>price<ept id="p1">*</ept> always refers to the sales price, not the inventory price or cost price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo argomento, il termine <bpt id="p1">*</bpt>prezzo<ept id="p1">*</ept> si riferisce sempre al prezzo di vendita, non al prezzo di magazzino o al prezzo di costo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Base price</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prezzo di base</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>The price that is set in the <bpt id="p1">**</bpt>Price<ept id="p1">**</ept> field on a released product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il prezzo impostato nel campo <bpt id="p1">**</bpt>Prezzo<ept id="p1">**</ept> di un prodotto rilasciato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Trade agreement price</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prezzo accordo commerciale</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>The price that is set on a product or variant by using a trade agreement of the <bpt id="p1">**</bpt>Price (sales)<ept id="p1">**</ept> type.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il prezzo di vendita impostato per un prodotto o una variante tramite un accordo commerciale con tipo <bpt id="p1">**</bpt>Prezzo (Vend.)<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Best price</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prezzo migliore</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>When more than one price or discount can be applied to a product, the smallest price amount and/or the largest discount amount that produces the lowest possible net amount that the customer must pay.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando è possibile applicare più di un prezzo o uno sconto a un prodotto, l'importo del prezzo inferiore e/o l'importo di sconto maggiore che produce l'importo netto più basso possibile che il cliente deve pagare.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>In this topic, the concept of best price is always referred to as "the best price."</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo argomento, il concetto di miglior prezzo viene sempre definito "il migliore prezzo".</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>This best price differs from and should not be confused with the <bpt id="p1">**</bpt>Best price<ept id="p1">**</ept> enumeration value for a discount's concurrency mode.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questo prezzo migliore differisce e non deve essere confuso con il valore di enumerazione del prezzo migliore per la modalità di concorrenza di uno sconto <bpt id="p1">**</bpt>Prezzo migliore<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Price groups</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gruppi prezzi</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Price groups are at the heart of price and discount management in Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I gruppi di prezzi sono al centro della gestione dei prezzi e degli sconti in Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Price groups are used to assign prices and discounts to retail entities (that is, channels, catalogs, affiliations, and loyalty programs).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I gruppi di prezzi vengono utilizzati per assegnare prezzi e sconti a entità di vendita al dettaglio (ovvero canali, cataloghi, affiliazioni e programmi fedeltà).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Because price groups are used for all pricing and discounts, it's very important that you plan how you will use them before you start.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Poiché i gruppi di prezzi vengono utilizzati per tutti i prezzi e gli sconti, è molto importante pianificare in che modo si prevede di utilizzarli prima di iniziare.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>By itself, a price group is just a name, a description, and, optionally, a pricing priority.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Di per sé, un gruppo di prezzi è solo un nome, una descrizione e, facoltativamente, una priorità di determinazione prezzo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>The main point to remember about price groups is that they are used to manage the many-to-many relationships that discounts and prices have with retail entities.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'aspetto principale da ricordare sui gruppi di prezzi è che sono utilizzati per gestire le relazioni molti-a-molti che sconti e prezzi hanno con le entità di vendita al dettaglio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>The following illustration shows how price groups are used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La seguente illustrazione mostra come vengono utilizzati i gruppi di prezzi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>In this illustration, notice that "Price group" is literally at the center of pricing and discount management.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questa illustrazione, si noti che "Gruppo di prezzi" è letteralmente al centro della gestione dei prezzi e degli sconti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>The retail entities that you can use to manage differential prices and discounts are on the left, and the actual price and discount records are on the right.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le entità di vendita al dettaglio che è possibile utilizzare per gestire prezzi e sconti differenziali si trovano sulla sinistra e i record di prezzo e sconto effettivi sono sulla destra.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source><bpt id="p1">![</bpt>Price groups<ept id="p1">]</ept><bpt id="p2">(./media/PriceGroups.png "</bpt>Price groups<ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Gruppi di prezzi<ept id="p1">]</ept><bpt id="p2">(./media/PriceGroups.png "</bpt>Gruppi di prezzi<ept id="p2">")</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>When you create price groups, you should not use a single price group for multiple types of retail entities.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando si creano gruppi di prezzi, evitare utilizzare un singolo gruppo di prezzi per più tipi di entità di vendita al dettaglio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Otherwise, it can be difficult to determine why a specific price or discount is being applied to a transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In caso contrario, può essere difficile determinare il motivo per cui un prezzo o uno sconto specifico viene applicato a una transazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>As the red dashed line in the illustration shows, Retail does support the core Microsoft Dynamics 365 functionality of a price group that is set directly on a customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Come mostra la linea tratteggiata rossa nell'illustrazione, Retail supporta la funzionalità principale di Microsoft Dynamics 365 di un gruppo di prezzi che viene impostato direttamente su un cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>However, in this case, you get only sales price trade agreements.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tuttavia, in questo caso, si ottengono solo accordi commerciali sui prezzi di vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>If you want to apply customer-specific prices, we recommend that you not set price groups directly on the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se si desidera applicare prezzi specifici del cliente, si consiglia di non impostare i gruppi di prezzi direttamente sul cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>Instead, you should use affiliations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Utilizzare invece le affiliazioni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>The following sections provide more information about the retail entities that you can use to set distinct prices when the price groups are used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nelle sezioni seguenti vengono fornite ulteriori informazioni sulle entità di vendita che è possibile utilizzare per impostare prezzi distinti quando vengono utilizzati i gruppi di prezzi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>The configuration of prices and discounts for all these entities is a two-step process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La configurazione dei prezzi e degli sconti per tutte queste entità è un processo in due fasi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>These steps can be done in either order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questi passaggi possono essere eseguiti in qualsiasi ordine.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>However, the logical order is to set the price groups on the entities first, because this step is likely to be a one-time setup that is done during implementation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tuttavia, l'ordine logico è di impostare prima i gruppi di prezzi sulle entità, poiché è probabile che questo passaggio sia una configurazione unica eseguita durante l'implementazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>Then, as prices and discounts are created, you can set the price groups on those prices and discounts individually.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quindi, quando vengono creati i prezzi e gli sconti, è possibile impostare i gruppi di prezzi su tali prezzi e sconti singolarmente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Channels</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Canali</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>In the retail industry, it's very typical to have different prices in different channels.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nel settore della vendita al dettaglio, è molto diffusa l'uso di prezzi diversi su canali diversi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>The two primary factors that affect channel-specific prices are costs and local market conditions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I due fattori principali che influenzano i prezzi specifici del canale sono i costi e le condizioni del mercato locale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source><bpt id="p1">**</bpt>Costs<ept id="p1">**</ept> – The farther away a channel is from the product source, the more it costs to stock a product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Costi<ept id="p1">**</ept>: più il canale è lontano dall'origine del prodotto, più costa immagazzinare scorte di un prodotto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>For example, fresh produce has a limited shelf life and specific production requirements (for example, a growing season).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ad esempio, i prodotti freschi hanno una durata a scaffale limitata e requisiti di produzione specifici (ad esempio, una stagione di crescita).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>During the winter, fresh lettuce likely costs more in northern climates than in southern climates.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Durante l'inverno, la lattuga fresca probabilmente costa di più nei climi nordici rispetto ai climi meridionali.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>If you're setting prices for channels over a large geographical area, you will probably want to set different prices in different channels.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se vengono impostati i prezzi per i canali su una vasta area geografica, probabilmente si vorranno impostare prezzi diversi in canali diversi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source><bpt id="p1">**</bpt>Local market conditions<ept id="p1">**</ept> – A store that has a direct competitor across the street will be much more price-sensitive than a store that doesn't have a direct competitor nearby.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Condizioni del mercato locale<ept id="p1">**</ept>: un punto vendita che ha un concorrente diretto dall'altra parte della strada sarà molto più sensibile al prezzo di un punto vendita che non ha un concorrente diretto nelle vicinanze.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Affiliations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rapporti</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>The general definition of an affiliation is a link to or association with a group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La definizione generale di affiliazione è un collegamento o un'associazione con un gruppo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>In Retail, affiliations are groups of customers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In Retail, le affiliazioni sono gruppi di clienti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>Affiliations are a much more flexible tool for customer pricing and discounts than the core Microsoft Dynamics 365 concept of customer groups and discount groups.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le affiliazioni sono uno strumento molto più flessibile per i prezzi e gli sconti dei clienti rispetto al concetto principale di gruppi di clienti e gruppi di sconto di Microsoft Dynamics 365.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>First, an affiliation can be used for both prices and discounts, whereas non-retail pricing has a different group for each type of discount and price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In primo luogo, un'affiliazione può essere utilizzata sia per i prezzi che per gli sconti, mentre i prezzi non al dettaglio hanno un gruppo diverso per ogni tipo di sconto e prezzo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>Next, a customer can belong to multiple affiliations but can belong to only one non-retail pricing group of each type.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Successivamente, un cliente può appartenere a più affiliazioni ma può appartenere a un solo gruppo di prezzi non Retail di ciascun tipo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>Finally, although affiliations can be set up so that they are linked to a customer, they don't have to be.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Infine, anche se le affiliazioni possono essere impostate in modo che siano collegate a un cliente, questo non è necessario.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>An ad-hoc affiliation can be used for anonymous customers at the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un'affiliazione ad hoc può essere utilizzata per i clienti anonimi presso il POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>A typical example of an anonymous affiliation discount is a senior or student discount, where a customer can receive a discount just by showing a group membership card.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un tipico esempio di uno sconto di affiliazione anonimo è uno sconto per studenti o studenti, in cui un cliente può ricevere uno sconto solo mostrando una scheda di appartenenza a un gruppo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Although affiliations are most often associated with discounts, you can also use them to set differential pricing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sebbene le affiliazioni siano spesso associate a sconti,è possibile utilizzarle anche per impostare prezzi diversi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>For example, when a retailer sells to an employee, it might want to change the selling price instead of applying a discount on top of the regular price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ad esempio, quando un rivenditore vende a un dipendente, potrebbe voler cambiare il prezzo di vendita anziché applicare uno sconto al prezzo normale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>As another example, a retailer that sells to both consumer customers and business customers might offer business customers better prices, based on their purchasing volume.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Come altro esempio, un rivenditore che vende sia ai clienti consumer sia ai clienti business potrebbe offrire ai clienti business prezzi migliori, in base al volume degli acquisti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>Affiliations enable both these scenarios.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Report consentono entrambi questi scenari.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Loyalty programs</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Programmi fedeltà</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>In relation to prices and discounts, loyalty programs are basically just an affiliation that has a special name.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In relazione a prezzi e sconti, i programmi fedeltà sono fondamentalmente solo un'affiliazione con un nome speciale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>Both prices and discounts can be set for a loyalty program, just as they can be set for an affiliation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sia i prezzi che gli sconti possono essere impostati per un programma fedeltà, così come possono essere impostati per un'affiliazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>However, the way that customers get loyalty pricing during a transaction or order differs from the way that they get affiliation pricing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tuttavia, il modo in cui i clienti ottengono prezzi fedeltà durante una transazione o un ordine differisce dal modo in cui ottengono i prezzi di affiliazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Customers can get loyalty pricing only if a loyalty card is added to a transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I clienti possono ottenere prezzi fedeltà solo se una carta fedeltà viene aggiunta a una transazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>When a loyalty card is added to a transaction, the loyalty program is also added.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando una carta fedeltà viene aggiunta a una transazione, viene aggiunto anche il programma fedeltà.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>The loyalty program then enables special prices and discounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il programma fedeltà consente quindi prezzi e sconti speciali.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>Loyalty programs can have multiple tiers, and the discounts can differ for different tiers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I programmi fedeltà possono avere più livelli e gli sconti possono differire per i diversi livelli.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>In this way, retailers can give frequent customers larger rewards without having to manually put those customers into a special group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo modo, i rivenditori possono offrire ai clienti frequenti premi più grandi senza doverli aggiungere manualmente in un gruppo speciale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>Loyalty programs have additional functionality besides prices and discounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I programmi fedeltà hanno funzionalità aggiuntive oltre a prezzi e sconti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>However, from the perspective of pricing and discounts, they are the same as affiliations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tuttavia, dal punto di vista dei prezzi e degli sconti, sono uguali alle affiliazioni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>Catalogs</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cataloghi</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Some retailers use physical or virtual catalogs to market products to, and price them for, focused groups of customers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Alcuni rivenditori utilizzano cataloghi fisici o virtuali per commercializzare prodotti e prezzi per gruppi mirati di clienti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>As part of their business model to target marketing via a catalog, these retailers can set differential prices on their various catalogs.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Come parte del loro modello di business per un approccio marketing mirato tramite catalogo, questi rivenditori possono fissare prezzi differenziali nei vari cataloghi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>Microsoft Dynamics 365 supports this capability by letting you define catalog-specific discounts and prices, just as you can define channel-specific or affiliation-specific discounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Microsoft Dynamics 365 supporta questa funzionalità consentendo di definire sconti e prezzi specifici del catalogo, così come è possibile definire sconti specifici per canale o di affiliazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>When you edit a catalog, you can associate price groups with the catalog, just as you can associate them with a channel, affiliation, or loyalty program.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando si modifica un catalogo, è possibile associare i gruppi di prezzi al catalogo, così come è possibile associarli a un canale, affiliazione o programma fedeltà.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>Best practices for price groups</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Procedure consigliate per i gruppi di prezzi</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Don't use a price group for multiple retail entity types.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Non utilizzare un gruppo di prezzi per i tipi di entità Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Instead, use one set of price groups for channels, a different set of price groups for affiliations or loyalty programs, and so on.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Utilizzare invece un gruppo di gruppi di prezzi per i canali, un diverso set di gruppi di prezzi per affiliazioni o programmi fedeltà e così via.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>You can use a prefix or suffix in the name of the price group to visually group the various types of price groups that you're using.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">È possibile utilizzare un prefisso o un suffisso nel nome del gruppo di prezzi per raggruppare visivamente i vari tipi di gruppi di prezzi in uso.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>Avoid setting price groups directly on a customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Evitare di impostare i gruppi di prezzi direttamente per un cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>Instead, use an affiliation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Usare invece un'affiliazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>In this way, you can assign all types of prices and discounts to customers, not just sales price trade agreements.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo modo, è possibile assegnare tutti i tipi di prezzi e sconti ai clienti, non solo gli accordi commerciali sui prezzi di vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Pricing priority</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Priorità determinazione prezzi</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>By itself, a pricing priority is just a number and a description.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Di per sé, una priorità di prezzo è solo un numero e una descrizione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>Pricing priorities can be applied to price groups, or they can be applied directly to discounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le priorità dei prezzi possono essere applicate a gruppi di prezzi oppure direttamente sugli sconti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>When pricing priorities are used, they let a retailer override the principle of the best price by controlling the order in which prices and discounts are applied to products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando vengono utilizzate le priorità di prezzi, queste consentono a un rivenditore di ignorare il principio del prezzo migliore controllando l'ordine in cui i prezzi e gli sconti vengono applicati ai prodotti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>A larger pricing priority number is evaluated before a lower pricing priority number.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un numero di priorità di prezzo superiore viene valutato prima di un numero di priorità di prezzo inferiore.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>Additionally, if a price or discount is found at any priority number, all prices or discounts that have lower priority numbers are ignored.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inoltre, se viene trovato un prezzo o uno sconto per qualsiasi numero di priorità, tutti i prezzi o gli sconti con numeri di priorità inferiori vengono ignorati.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>The price and a discount can come from two different pricing priorities, because pricing priorities apply to prices and discounts independently.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il prezzo e uno sconto possono derivare da due diverse priorità di prezzo, poiché le priorità di prezzo si applicano in modo indipendente a prezzi e sconti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>To use pricing priority for prices, you must assign a pricing priority to a price group and then create a sales price trade agreement for that price group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per utilizzare la priorità di prezzo per i prezzi, è necessario assegnare una priorità di prezzo a un gruppo di prezzi e quindi creare un accordo commerciale di prezzo di vendita per quel gruppo di prezzi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>The pricing priority feature was introduced to support the scenario where a retailer wants to apply higher prices in a specific set of stores.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La funzionalità di priorità dei prezzi è stata introdotta per supportare lo scenario in cui un rivenditore desidera applicare prezzi più elevati in uno specifico gruppo di punti vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>For example, a retailer has defined regional prices for the east coast of the United States but wants higher prices for some products in New York City stores, because it costs more to sell some products in the city, and/or because the local market will bear a higher price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ad esempio, un rivenditore ha definito i prezzi regionali per la costa orientale degli Stati Uniti, ma desidera prezzi più elevati per alcuni prodotti nei punti vendita di New York, poiché il costo di vendita di alcuni prodotti è superiore in città e/o perché il mercato locale supporta un prezzo più alto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>As was described in the "Best price" section of this topic, the retail pricing engine typically selects the lower of two prices.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Come descritto nella sezione "Miglior prezzo" di questo argomento, il motore dei prezzi Retail seleziona in genere valore minimo tra due prezzi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>Therefore, the retailer is usually prevented from using the higher of two prices in a store that has both the East coast and New York price groups.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Di conseguenza, al rivenditore di solito viene impedito di utilizzare il prezzo più alto di due prezzi in un punto vendita che ha sia i gruppi di prezzi della costa orientale sia quelli di New York.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>To resolve this issue before the pricing priority feature was introduced, the retailer had to define prices for every product two times and not assign both price groups.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per risolvere questo problema, prima che fosse introdotta la funzionalità di priorità dei prezzi, il rivenditore doveva definire i prezzi per ogni prodotto due volte e non assegnare entrambi i gruppi di prezzi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>Alternatively, the retailer had to create extra price groups to isolate the products that have higher prices from products that have the usual, lower prices.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In alternativa, il rivenditore ha dovuto creare gruppi di prezzi extra per isolare i prodotti che hanno prezzi più alti da quelli che hanno i prezzi abituali più bassi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>However, the pricing priority feature lets the retailer create a pricing priority for store prices that is higher than the pricing priority for regional prices.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tuttavia, la funzionalità di priorità dei prezzi consente al rivenditore di creare una priorità di prezzo per i prezzi dei punti vendita superiore alla priorità dei prezzi per i prezzi regionali.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>Alternatively, the retailer can create a pricing priority just for store prices and leave regional prices at the default pricing priority, which is 0 (zero).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In alternativa, il rivenditore può creare una priorità di prezzo solo per i prezzi dei punti vendita e lasciare i prezzi regionali con la priorità di prezzo predefinita, che è 0 (zero).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>Both setups help guarantee that store prices will always be used before regional prices.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Entrambe le configurazioni consentono di garantire che i prezzi dei punti vendita vengano sempre utilizzati prima dei prezzi regionali.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>Pricing priority example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Esempio di priorità determinazione prezzi</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>Let's look at an example where store prices override other prices.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Esaminiamo un esempio in cui i prezzi dei punti vendita prevalgono su altri prezzi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>A national retailer sets most prices per region, and it has four regions: North east, South east, Mid-west and West.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un rivenditore nazionale fissa la maggior parte dei prezzi per regione con quattro aree: North east, South east, Mid-west e West.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>It has identified several high-cost markets that can support higher prices.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha identificato diversi mercati ad alto costo in grado di supportare prezzi più elevati.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>These markets are in New York City, Chicago, and the San Francisco Bay area.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questi mercati si trovano a New York, Chicago e nell'area della Baia di San Francisco.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>For this example, we will drill into the North east region.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo esempio, esploreremo la regione North east.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>Store 1 is in Boston, and store 2 is in Manhattan.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il punto vendita 1 corrisponde a Boston e il punto vendita 2 è a Manhattan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>For the Boston store, two price groups are linked to the channel: North East and Store 1.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per il punto vendita di Boston, due canali di prezzo sono collegati al canale: North East e POS 1.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>For the Manhattan store, three price groups are linked to the channel: North East, NYC, and Store 2.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per il punto vendita di Manhattan, tre canali di prezzo sono collegati al canale: North East, NYC e POS 2.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>The retailer sets up two pricing priorities: High cost has a priority number of 5, and Store prices has a priority number of 10.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il rivenditore imposta due priorità di prezzo: il costo elevato ha un numero di priorità 5 e i prezzi del punto vendita hanno un numero di priorità 10.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>(Remember that, by default, the pricing priority is 0 <ph id="ph1">\[</ph>zero<ph id="ph2">\]</ph>, and a price or discount that has a higher priority number is used before a price or discount that has a lower priority number.) For the North East price group, the pricing priority is left at the default value of <bpt id="p1">**</bpt>0<ept id="p1">**</ept> (zero).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tenere presente che, per impostazione predefinita, la priorità di valutazione è 0 <ph id="ph1">\[</ph>zero<ph id="ph2">\]</ph> e un prezzo o uno sconto che ha un numero di priorità più elevato viene utilizzato prima di un prezzo o uno sconto con un numero di priorità inferiore. Per il gruppo di prezzi del North East la priorità del prezzo viene lasciata al valore predefinito di <bpt id="p1">**</bpt>0<ept id="p1">**</ept> (zero).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>For the NYC price group, the pricing priority is set to <bpt id="p1">**</bpt>5<ept id="p1">**</ept>, because New York City is a high-cost market.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per il gruppo di prezzi di New York, la priorità del prezzo è fissata a <bpt id="p1">**</bpt>5<ept id="p1">**</ept>, perché New York City è un mercato ad alto costo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>For the Store 1 and Store 2 price groups, the pricing priority is set to <bpt id="p1">**</bpt>10<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per i gruppi di prezzi POS 1 e POS 2, la priorità del prezzo è impostata su <bpt id="p1">**</bpt>10<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>Two products that the retailer sells are product 1, a commodity T-shirt, and product 2, brand-specific fashion jeans.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I due prodotti venduti dal rivenditore sono il prodotto 1 (una maglietta sportiva) e il prodotto 2 (jeans moda specifici del marchio).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>Product</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prodotto</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>North East price</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prezzo North East</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>NYC price</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prezzo NYC</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>Store price</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prezzo punto vendita</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>T-shirt</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Maglietta</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>$15</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">$15</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>Not set</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Non impostato</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>Not set</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Non impostato</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>Fashion jeans</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeans moda</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>$50</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">$50</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>$70</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">$70</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>Not set</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Non impostato</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>The T-shirt sells for the same price (that is, $15) at both the Boston and Manhattan stores, because only one price is set in the North East price group that is linked to both channels.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La maglietta viene venduta allo stesso prezzo (ovvero $15) nei punti vendita di Boston e Manhattan, perché nel gruppo di prezzi del North East un solo prezzo è collegato a entrambi i canali.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>The fashion jeans sell for $50 in the Boston store, because that price is the only price that is available in that store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I jeans alla moda vengono venduti a $50 nel punto vendita di Boston, perché quel prezzo è l'unico prezzo disponibile in quel punto vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>However, in the Manhattan store, two prices are available: $50 and $70.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tuttavia, nel punto vendita di Manhattan sono disponibili due prezzi: $50 e $70.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>Because the pricing priority of 5 for the NYC price group is higher than the pricing priority of 0 (zero) for the North East price group, the price will be rung up as $70 in the POS system.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Poiché la priorità di prezzo 5 per il gruppo di prezzi di New York è superiore alla priorità di prezzo 0 (zero) per il gruppo di prezzi di North East, il prezzo verrà pubblicato come $70 nel sistema POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>For each pricing priority, a full pass through the logic for the retail pricing engine is required.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per ogni priorità di prezzo, è richiesto un passaggio completo attraverso la logica per il motore dei prezzi di Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>Therefore, to help maintain the performance of the price and discount calculation, you should use pricing priorities sparingly.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pertanto, per contribuire a mantenere le prestazioni del calcolo del prezzo e dello sconto, è necessario utilizzare le priorità del prezzo con parsimonia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>Types of prices</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tipi di prezzi</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>In Microsoft Dynamics 365, you can set the price of a product in three places:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In Microsoft Dynamics 365 è possibile impostare il prezzo di un prodotto in tre aree:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>Directly on the product (base price)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Direttamente nel prodotto (prezzo di base)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>In a sales price trade agreement</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In un accordo commerciale sul prezzo di vendita</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>In a price adjustment</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In una rettifica prezzo</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>The base price and trade agreement price are part of core Microsoft Dynamics 365, and are available even if you don't use Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il prezzo base e il prezzo dell'accordo commerciale fanno parte del core di Microsoft Dynamics 365 e sono disponibili anche se non si utilizza Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>The price adjustment functionality is available only in Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La funzionalità di rettifica prezzo è disponibile solo in Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>The next section provides more information about each of these options for setting prices and explains how the options work together.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La sezione successiva fornisce ulteriori informazioni su ciascuna di queste opzioni per l'impostazione dei prezzi e spiega come le opzioni funzionano insieme.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>Setting prices</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Impostazione dei prezzi</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>Base price</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prezzo di base</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>The easiest place to set the price for a product is directly on the product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il punto più semplice per impostare il prezzo di un prodotto è direttamente nel prodotto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>The value that you set directly on a product is often referred to as the base price for the product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il valore impostato direttamente in un prodotto viene spesso definito come il prezzo base del prodotto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>You set the base price in the <bpt id="p1">**</bpt>Price<ept id="p1">**</ept> field on the <bpt id="p2">**</bpt>Sell<ept id="p2">**</ept> tab of the <bpt id="p3">**</bpt>Released product details<ept id="p3">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">È possibile impostare il prezzo di base nel campo <bpt id="p1">**</bpt>Prezzo<ept id="p1">**</ept> della scheda <bpt id="p2">**</bpt>Vendi<ept id="p2">**</ept> della pagina <bpt id="p3">**</bpt>Dettagli prodotto rilasciato<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>The value that you enter is in the company currency.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il valore immesso è nella valuta della società.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source>By default, the price is for a quantity of 1 of the unit of measure (UoM) that is set in the <bpt id="p1">**</bpt>Unit<ept id="p1">**</ept> field on the <bpt id="p2">**</bpt>Sell<ept id="p2">**</ept> tab. The actual price per unit of a product is based on the UoM, the price quantity, and the currency.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per impostazione predefinita, il prezzo corrisponde a una quantità pari a 1 dell'unità di misura (UdM) impostata nel campo <bpt id="p1">**</bpt>Unità<ept id="p1">**</ept> nella scheda <bpt id="p2">**</bpt>Vendi<ept id="p2">**</ept>. Il prezzo effettivo per unità di un prodotto si basa sull'UdM, sulla quantità del prezzo e sulla valuta.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>If a product has one price for everyone, the base price offers the most efficient way to manage the price of that product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se un prodotto è associato un prezzo uguale per tutti, il prezzo base rappresenta il modo più efficiente per gestire il prezzo di tale prodotto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source>Even if you use trade agreements to set prices, you might also set the base price on a product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Anche se si utilizzano gli accordi commerciali per definire i prezzi, è possibile impostare il prezzo base in un prodotto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>Then, if you don't use an <bpt id="p1">**</bpt>All<ept id="p1">**</ept> trade agreement, you have a fallback price that is used when no trade agreement applies.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo modo,, se non si utilizza un accordo commerciale <bpt id="p1">**</bpt>Tutto<ept id="p1">**</ept>, si ha un prezzo di fallback che viene utilizzato quando non si applica un accordo commerciale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>If a retail channel's currency differs from the company currency, the base price in that retail channel is determined by using currency conversion on the price that is set on the product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se la valuta di un canale di vendita al dettaglio differisce dalla valuta della società, il prezzo di base in quel canale di vendita al dettaglio viene determinato utilizzando la conversione di valuta del prezzo impostato nel prodotto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source>Although the price unit isn't a common retail scenario, the retail pricing engine supports it.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sebbene l'unità di prezzo non sia uno scenario di vendita al dettaglio comune, il motore di determinazione dei prezzi Retail lo supporta.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>If the price unit is set to a value other than <bpt id="p1">**</bpt>0<ept id="p1">**</ept> (zero), the price per unit equals Price ÷ Price unit.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se l'unità di prezzo viene impostata su un valore diverso da <bpt id="p1">**</bpt>0<ept id="p1">**</ept> (zero), il prezzo unitario è uguale a Prezzo ÷ Unità di prezzo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source>For example, if a product's price is $10.00, and the price unit is 50, the price for a quantity of 1 is $0.20 (= $10.00 ÷ 50).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ad esempio, se il prezzo di un prodotto è $ 10,00 e l'unità di prezzo è 50, il prezzo per una quantità di 1 è $ 0,20 (= $ 10,00 ÷ 50).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>Sales price trade agreement</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Accordo commerciale sul prezzo di vendita</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source>By using the trade agreement journal, you can create sales price trade agreements for each product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Utilizzando il giornale di registrazione accordi commerciali, è possibile creare accordi commerciali sui prezzi di vendita per ogni prodotto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="259">
          <source>In Microsoft Dynamics 365, there are three customer scopes for sales price trade agreements: <bpt id="p1">**</bpt>Table<ept id="p1">**</ept>, <bpt id="p2">**</bpt>Group<ept id="p2">**</ept>, and <bpt id="p3">**</bpt>All<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In Microsoft Dynamics 365, sono disponibili tre ambiti per i clienti per gli accordi di commerciali sui prezzi: <bpt id="p1">**</bpt>Tabella<ept id="p1">**</ept>, <bpt id="p2">**</bpt>Gruppo<ept id="p2">**</ept> e <bpt id="p3">**</bpt>Tutto<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="260">
          <source>The customer scope determines the customers that a given sales price trade agreement applies to.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'ambito del cliente determina i clienti ai quali si applica un determinato accordo commerciale di vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="261">
          <source>A <bpt id="p1">**</bpt>Table<ept id="p1">**</ept> sales price trade agreement is for a single customer that is set directly on the trade agreement.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un accordo commerciale sui prezzi di vendita <bpt id="p1">**</bpt>Tabella<ept id="p1">**</ept> è per un singolo cliente che viene impostato direttamente sull'accordo commerciale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="262">
          <source>This scenario isn't a typical retail business-to-consumer (B2C) scenario.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questo scenario non è uno scenario tipico business-to-consumer (B2C).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="263">
          <source>However, if it occurs, the retail pricing engine uses <bpt id="p1">**</bpt>Table<ept id="p1">**</ept> trade agreements when it determines price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tuttavia, se si verifica, il motore dei prezzi Retail utilizza gli accordi commerciali <bpt id="p1">**</bpt>Tabella<ept id="p1">**</ept> quando determina il prezzo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="264">
          <source>A <bpt id="p1">**</bpt>Group<ept id="p1">**</ept> sales price trade agreement is the type that is most often used with retail functionality.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un accordo commerciale sui prezzi di vendita <bpt id="p1">**</bpt>Gruppo<ept id="p1">**</ept> è il tipo più utilizzato con la funzionalità di vendita al dettaglio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="265">
          <source>Outside Retail, <bpt id="p1">**</bpt>Group<ept id="p1">**</ept> sales price trade agreements are for a simple customer group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Al di fuori di Retail, gli accordi commerciali sui prezzi di vendita <bpt id="p1">**</bpt>Gruppo<ept id="p1">**</ept> si riferiscono a un gruppo di clienti semplice.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="266">
          <source>However, in Retail, the concept of a customer group has been extended so that it's a more generic retail price group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tuttavia, in Retail, il concetto di gruppo di clienti è stato esteso in modo tale che si tratti di un gruppo di prezzi al dettaglio più generico.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="267">
          <source>A price group can be linked to a retail channel, affiliation, loyalty program, or catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un gruppo di prezzi può essere collegato a un canale di vendita al dettaglio, un'affiliazione, un programma fedeltà o a un catalogo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="268">
          <source>For detailed information about price groups, see the "Price groups" section earlier in this topic.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per informazioni dettagliate sui gruppi di prezzi, vedere la sezione "Gruppi di prezzi" in precedenza in questo argomento.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="269">
          <source>A trade agreement price is always used before the base price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il prezzo dell'accordo commerciale viene sempre utilizzato prima del prezzo di base.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="270">
          <source>Price adjustment</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rettifica prezzo</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="271">
          <source>As the name implies, a price adjustment is used to modify the price that was either set directly on the product or set by using a trade agreement.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Come suggerisce il nome, una rettifica prezzo viene utilizzata per modificare il prezzo che è stato impostato direttamente sul prodotto o impostato utilizzando un accordo commerciale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="272">
          <source>A price adjustment can be used only to lower the price, not raise it.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Una rettifica prezzo può essere utilizzata solo per ridurre il prezzo, non per aumentarlo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="273">
          <source>A price adjustment is the recommended way for retailers to create, track, and manage price markdowns for their products over time.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Una rettifica prezzo rappresenta il metodo consigliato per i rivenditori per creare, tracciare e gestire i ribassi dei prezzi per i loro prodotti nel tempo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="274">
          <source>There are three types of price adjustments: percentage off, amount off, and price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sono disponibili tre tipi di rettifica prezzo: percentuale sottratta, importo sottratto e prezzo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="275">
          <source>A price adjustment of the percentage off or amount off type is always applied to a sale transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Una rettifica prezzo del tipo percentuale sottratta o importo sottratto viene sempre applicata a una transazione di vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="276">
          <source>However, a price adjustment of the price type is applied only if the adjusted price is less than the price that was set by using the base price or trade agreement price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tuttavia, una rettifica prezzo del tipo di prezzo viene applicata solo se il prezzo rettificato è inferiore al prezzo stabilito utilizzando il prezzo base o il prezzo dell'accordo commerciale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="277">
          <source>Therefore, if the price that is set in a price adjustment is more than the unadjusted price, the price adjustment isn't used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pertanto, se il prezzo impostato in una rettifica di prezzo è superiore al prezzo non rettificato, la rettifica del prezzo non viene utilizzata.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="278">
          <source>Determining price for a product in a transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Determinazione del prezzo per un prodotto in una transazione</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="279">
          <source>The calculation of the price and discount on a transaction uses the principle of finding the best price for the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il calcolo del prezzo e dello sconto su una transazione utilizza il principio di ricerca del prezzo migliore per il cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="280">
          <source>According to this principle, if more than one price is found, the lowest price is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In base a questo principio, se viene trovato più di un prezzo, viene utilizzato il prezzo più basso.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="281">
          <source>Additionally, the combination of discounts that produces the largest discount amount for the whole transaction is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inoltre, viene utilizzata la combinazione di sconti che produce l'importo di sconto maggiore per l'intera transazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="282">
          <source>In some cases, a smaller discount must be used on a single product, so that additional discounts can be applied to other products in the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In alcuni casi, uno sconto minore deve essere utilizzato su un singolo prodotto, in modo che ulteriori sconti possano essere applicati ad altri prodotti nella transazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="283">
          <source>The only exception to the principle of finding the best price for the customer is an option for mix-and-match least-expensive discounts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'unica eccezione al principio di ricerca del prezzo migliore per il cliente è un'opzione per gli sconti gamma meno costosi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="284">
          <source>This option enables least-expensive discounts that favor the retailer when products are selected and grouped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questa opzione consente sconti meno costosi che favoriscono il rivenditore quando i prodotti vengono selezionati e raggruppati.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="285">
          <source>Therefore, when a transaction includes more products than are required to qualify for the least-expensive discount, the retail pricing engine selects the products that produce the smallest possible discount amount for the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pertanto, quando una transazione include più prodotti di quelli necessari per l'idoneità allo sconto meno costoso, il motore di determinazione del prezzo al dettaglio seleziona i prodotti che producono il minor sconto possibile per il cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="286">
          <source>The retail pricing engine returns three prices for every product: the base price, the trade agreement price, and the active price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il motore dei prezzi Retail restituisce tre prezzi per ogni prodotto: il prezzo base, il prezzo dell'accordo commerciale e il prezzo attivo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="287">
          <source>The base price is just the property on the product and is the same for everyone everywhere.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il prezzo base è solo la proprietà sul prodotto ed è uguale per tutti ovunque.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="288">
          <source>On the sales price trade agreement, if the <bpt id="p1">**</bpt>Find next<ept id="p1">**</ept> option is set to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>, the lowest price that is found for applicable sales price trade agreements is used as the trade agreement price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nell'accordo commerciale sul prezzo di vendita, se l'opzione <bpt id="p1">**</bpt>Trova successivo<ept id="p1">**</ept> è impostata su <bpt id="p2">**</bpt>Sì<ept id="p2">**</ept>, il prezzo più basso trovato per gli accordi commerciali sui prezzi di vendita applicabili viene utilizzato come prezzo dell'accordo commerciale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="289">
          <source>Trade agreements can be found by using price groups or the <bpt id="p1">**</bpt>ALL<ept id="p1">**</ept> account code.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gli accordi commerciali possono essere trovati utilizzando i gruppi di prezzi o il codice conto <bpt id="p1">**</bpt>TUTTO<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="290">
          <source>Alternatively, trade agreements can be assigned directly to a customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In alternativa, gli accordi commerciali possono essere assegnati direttamente a un cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="291">
          <source>If the <bpt id="p1">**</bpt>Find next<ept id="p1">**</ept> option is set to <bpt id="p2">**</bpt>No<ept id="p2">**</ept>, the first trade agreement price that is found is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se l'opzione <bpt id="p1">**</bpt>Trova successivo<ept id="p1">**</ept> è impostata su <bpt id="p2">**</bpt>No<ept id="p2">**</ept>, viene utilizzato il primo prezzo dell'accordo commerciale trovato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="292">
          <source>If no sales price trade agreements are found, then the trade agreement price is set equal to the base price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se non vengono trovati accordi commerciali relativi ai prezzi di vendita, il prezzo dell'accordo commerciale viene impostato come pari al prezzo base.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="293">
          <source>The active price is calculated by taking the trade agreement price and applying the largest price adjustment that applies to the product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il prezzo attivo viene calcolato prendendo il prezzo dell'accordo commerciale e applicando la maggiore rettifica prezzo applicabile al prodotto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="294">
          <source>If no price adjustments are found, or if the calculated active price is more than the trade agreement price, the active price is set equal to the trade agreement price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se non viene trovata alcuna rettifica prezzo o se il prezzo attivo calcolato è superiore al prezzo dell'accordo commerciale, il prezzo attivo è pari al prezzo dell'accordo commerciale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="295">
          <source>Remember that you can't raise the price of a product by using a price adjustment.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tenere presente che non è possibile aumentare il prezzo di un prodotto utilizzando una rettifica prezzo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="296">
          <source>The applicable price adjustments can be found only by using price groups that are assigned to a channel, catalog, affiliation, or loyalty program.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le rettifiche di prezzo applicabili possono essere trovate solo utilizzando i gruppi di prezzi assegnati a un canale, un catalogo, un'affiliazione o un programma fedeltà.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="297">
          <source>Category price rules</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Regole prezzi di categoria</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="298">
          <source>The category price rules feature in Retail gives you an easy way to create new trade agreements for all the products in a category.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le regole dei prezzi di categoria presenti in Retail offrono un modo semplice per creare nuovi accordi commerciali per tutti i prodotti di una categoria.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="299">
          <source>This feature also lets you automatically find existing trade agreements for the products in the category and expire them.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questa funzione consente inoltre di trovare automaticamente gli accordi commerciali esistenti per i prodotti nella categoria e la relativa scadenza.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="300">
          <source>When you select the option to expire existing trade agreements, the system creates a new trade agreement journal for the products in the category that have an active trade agreement.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando si seleziona l'opzione di scadenza degli accordi commerciali esistenti, il sistema crea un nuovo giornale di registrazione accordi commerciali per i prodotti della categoria con un accordo commerciale attivo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="301">
          <source>However, the journal must be manually posted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tuttavia, il giornale deve essere registrato manualmente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="302">
          <source>Additionally, the category price rules can find existing trade agreements only if you're using the same price rule (that is, if you create a new price rule that uses the same category that was before).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inoltre, le regole dei prezzi delle categorie possono trovare accordi commerciali esistenti solo se si utilizza la stessa regola dei prezzi (ovvero, se si crea una nuova regola dei prezzi in cui viene utilizzata la stessa categoria precedente).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="303">
          <source>If you aren't using the same price rule, the existing trade agreements won't be expired.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se non si utilizza la stessa regola dei prezzi, gli accordi commerciali esistenti non saranno scaduti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="304">
          <source>The prices can be increased or decreased by using the <bpt id="p1">**</bpt>Price rule<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Price basis<ept id="p2">**</ept> fields of the category price rules.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I prezzi possono essere aumentati o diminuiti utilizzando i campi della <bpt id="p1">**</bpt>Regola prezzo<ept id="p1">**</ept> e <bpt id="p2">**</bpt>Base prezzo<ept id="p2">**</ept> dei prezzi di categoria.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="305">
          <source>In the <bpt id="p1">**</bpt>Price rule<ept id="p1">**</ept> field, select the type of price change to use:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nel campo <bpt id="p1">**</bpt>Regola prezzo<ept id="p1">**</ept>, selezionare il tipo di variazione prezzo da utilizzare:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="306">
          <source><bpt id="p1">**</bpt>Markup<ept id="p1">**</ept> – A percentage of the price basis is used to calculate the sales price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Ricarico<ept id="p1">**</ept>: una percentuale della base di prezzo viene utilizzata per calcolare il prezzo di vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="307">
          <source>For example, a product that costs 10.00 and sells for 15.00 has a markup of 50 percent.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ad esempio, un prodotto che costa 10,00 e viene venduto per 15,00 ha un ricarico del 50%.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="308">
          <source><bpt id="p1">**</bpt>Margin<ept id="p1">**</ept> – A percentage of the sales price is used to calculate the amount of profit.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Margine<ept id="p1">**</ept>: una percentuale del prezzo di vendita utilizzata per calcolare l'importo del profitto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="309">
          <source>For example, a product that costs 10.00 and sells for 15.00 has a margin of 33.3 percent.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ad esempio, un prodotto che costa 10,00 e viene venduto per 15,00 ha un margine del 33,3%.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="310">
          <source><bpt id="p1">**</bpt>Fixed amount<ept id="p1">**</ept> – An amount that is added to the price basis is used to calculate the sales price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Importo fisso<ept id="p1">**</ept>: un importo aggiunto alla base di prezzo utilizzata per calcolare il prezzo di vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="311">
          <source>For example, a product that costs 10.00 and sells for 15.00 has a fixed amount of 5.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ad esempio, un prodotto che costa 10,00 e viene venduto per 15,00 ha un importo fisso di 5,00.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="312">
          <source>In the <bpt id="p1">**</bpt>Price basis<ept id="p1">**</ept> field, select the type of price to modify:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nel campo <bpt id="p1">**</bpt>Base prezzo<ept id="p1">**</ept> selezionare il tipo di prezzo da modificare:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="313">
          <source><bpt id="p1">**</bpt>Base cost<ept id="p1">**</ept> – The amount that the retailer paid to the supplier.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Costo base<ept id="p1">**</ept>: l'importo che il rivenditore ha pagato al fornitore.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="314">
          <source><bpt id="p1">**</bpt>Base price<ept id="p1">**</ept> – The sales price before trade agreements and price adjustments are applied.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Prezzo base<ept id="p1">**</ept>: il prezzo di vendita prima che vengano applicati gli accordi commerciali e le rettifiche prezzo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="315">
          <source><bpt id="p1">**</bpt>Current price<ept id="p1">**</ept> – The sales price after trade agreements and price adjustments are applied.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Prezzo corrente<ept id="p1">**</ept>: il prezzo di vendita dopo che sono stati applicati gli accordi commerciali e le rettifiche prezzo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="316">
          <source>To easily update the prices of various products from different product categories, you can use the supplemental product categories together with the category price rules.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per aggiornare facilmente i prezzi di vari prodotti di diverse categorie di prodotti, è possibile utilizzare le categorie di prodotti supplementari insieme alle regole dei prezzi delle categorie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="317">
          <source>Best practices</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Procedure consigliate</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="318">
          <source>Microsoft SQL Server Express is often used for channel databases because of the cost (free).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Microsoft SQL Server Express viene spesso utilizzato per i database dei canali a causa del costo (gratuito).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="319">
          <source>Keep in mind that SQL Server Express has hardware limitations and limits on data size.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tenere presente che SQL Server Express presenta limitazioni hardware e limiti per la dimensione dei dati.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="320">
          <source>If you don't plan correctly, you can quickly reach the data size limits of SQL Server Express.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se non si pianifica correttamente, è possibile raggiungere rapidamente i limiti delle dimensioni dei dati di SQL Server Express.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="321">
          <source>This consideration applies not only to pricing but also to other areas of the product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questa considerazione si applica non solo ai prezzi, ma anche ad altre aree del prodotto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="322">
          <source>Here are a few best practices that can help you reduce the size of your data:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Di seguito sono riportate alcuni procedure consigliate utili per ridurre la dimensione dei dati:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="323">
          <source>If you're using trade agreements, and your prices change, you should expire the old trade agreements by setting an end date.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se si utilizzano accordi commerciali e i prezzi cambiano, è necessario applicare la scadenza ai vecchi accordi commerciali impostando una data di fine.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="324">
          <source>Over time, this approach helps reduce the number of trade agreements that are kept in channel databases.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nel tempo, tale approccio consente di ridurre il numero di accordi commerciali contenuti nel database del canale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="325">
          <source>It also helps reduce the amount of data that the price calculation algorithm must work with.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inoltre, consente di ridurre la quantità di dati con cui l'algoritmo di calcolo del prezzo deve funzionare.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="326">
          <source>If your prices vary by product variant, consider using the product base price as the price of the most common variant.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se i prezzi variano in base alla variante del prodotto, considera l'utilizzo del prezzo base del prodotto come il prezzo della variante più comune.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="327">
          <source>Then use trade agreements only for the variant prices that are exceptions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quindi utilizza gli accordi commerciali solo per i prezzi varianti che sono eccezioni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="328">
          <source>This approach helps reduce the number of trade agreement records.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questo approccio consente di ridurre il numero di record dell'accordo commerciale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="329">
          <source>Because it's so easy to import data into Microsoft Dynamics 365, you might be tempted to import a trade agreement for every variant of every product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Poiché è semplice importare dati in Microsoft Dynamics 365, si potrebbe essere tentati di importare un accordo commerciale per ogni variante di ogni prodotto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="330">
          <source>However, that approach can produce many trade agreements that have the same value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tuttavia, questo approccio può produrre molti accordi commerciali che hanno lo stesso valore.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="331">
          <source>Therefore, it can needlessly increase the size of your data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Di conseguenza, può aumentare inutilmente la dimensione dei dati.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="332">
          <source>Retail processes variant-specific prices in order from most specific to least specific.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Retail elabora i prezzi specifici della variante in ordine dal più specifico al meno specifico.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="333">
          <source>If a product dimension doesn't affect the price, you don't have to define trade agreements for it.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se una dimensione di prodotto non influisce sul prezzo, non è necessario definire accordi commerciali per essa.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="334">
          <source>For example, a product is available in three colors and four sizes, but the price varies only by size.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ad esempio, un prodotto è disponibile in tre colori e quattro dimensioni, ma il prezzo varia solo in base alle dimensioni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="335">
          <source>If you define a trade agreement for every variant, you create 12 records.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se si definisce un accordo commerciale per ogni variante, si creano 12 record.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="336">
          <source>Instead, you can define a trade agreement just for each size and leave the Color dimension blank.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In alternativa, è possibile definire un accordo commerciale solo per ogni dimensione e lasciare vuota la dimensione Colore.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="337">
          <source>In this case, you produce only four records.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo caso, si producono solo quattro record.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="338">
          <source>Alternatively, if not every value of a dimension produces a different price, you can define one trade agreement for the product master and leave all product dimensions blank.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In alternativa, se non tutti i valori di una dimensione producono un prezzo diverso, è possibile definire un accordo commerciale per la rappresentazione generale prodotto e lasciare vuote tutte le dimensioni prodotto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="339">
          <source>Then define a separate trade agreement just for each dimension value that produces a different price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quindi definire un accordo commerciale distinto solo per ciascun valore di dimensione che produce un prezzo diverso.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="340">
          <source>For example, if the XXL size has a higher price, but all other sizes have the same price, you require only two trade agreements: one for the product master and one for the XXL size.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ad esempio, se la taglia XXL ha un prezzo più alto, ma tutte le altre taglie hanno lo stesso prezzo, sono necessari solo due accordi commerciali: uno per la rappresentazione generale prodotto e uno per la taglia XXL.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="341">
          <source>Prices that include tax vs. prices that exclude tax</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prezzi comprensivi di imposte e prezzi senza imposte</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="342">
          <source>When you set sales prices in Microsoft Dynamics 365, you don't specify whether the price value that you're setting includes or excludes tax.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando si impostano i prezzi di vendita in Microsoft Dynamics 365, non si specifica se il valore del prezzo è comprensivo o meno di imposte.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="343">
          <source>The value is just the price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il valore è solo il prezzo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="344">
          <source>However, the <bpt id="p1">**</bpt>Price includes sales tax<ept id="p1">**</ept> setting on retail channels lets you configure retail channels so that they either include or exclude tax from prices.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tuttavia, l'impostazione <bpt id="p1">**</bpt>Prezzo comprensivo di IVA<ept id="p1">**</ept> nei canali di vendita al dettaglio consente di configurare i canali di vendita al dettaglio in modo che i prezzi siano o meno comprensivi di IVA.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="345">
          <source>This setting is set on the channel and can change even in a single company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questa impostazione viene configurata nel canale e può essere modificata anche in una singola società.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="346">
          <source>If you work with both inclusive and exclusive types of tax, it's very important that you set prices correctly, because the total amount that the customer pays will change if the <bpt id="p1">**</bpt>Price includes sales tax<ept id="p1">**</ept> setting on the channel is changed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se si utilizzano sia tipi di prezzi comprensivi di imposte che non comprensivi di imposte, è molto importante configurare i prezzi correttamente, poiché l'importo totale che il cliente paga cambierà se il campo <bpt id="p1">**</bpt>Prezzo comprensivo di IVA<ept id="p1">**</ept> del canale è stato modificato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="347">
          <source>Differences between retail pricing and non-retail pricing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Differenze tra i prezzi di vendita al dettaglio e i prezzi non al dettaglio</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="348">
          <source>A single pricing engine is used to calculate retail prices across all channels: Call center, Retail store, and Online stores.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un unico motore di determinazione del prezzo viene utilizzato per calcolare i prezzi al dettaglio in tutti i canali: Servizio clienti, Punto vendita al dettaglio e Punto vendita online.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="349">
          <source>This helps in enabling the unified commerce scenarios.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo modo è possibile consentire scenari commerciali unificati.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="350">
          <source>Retail pricing is designed to work with retail entities instead of non-retail entities.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La determinazione dei prezzi di vendita al dettaglio è progettata per funzionare con entità di vendita al dettaglio anziché con entità di vendita non al dettaglio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="351">
          <source>Specifically, it's designed to set prices by store, not by warehouse.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In particolare, è progettata per impostare i prezzi per punto vendita, non per magazzino.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="352">
          <source>The retail pricing engine doesn't support the following pricing features:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il motore di determinazione del prezzo di vendita al dettaglio non supporta le seguenti funzionalità dei prezzi:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="353">
          <source>Setting price by using the Site and Warehouse storage dimensions</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Impostazione del prezzo utilizzando le dimensioni di immagazzinamento del sito e del magazzino</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="354">
          <source>Attribute-based pricing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Determinazione prezzo basata su attributi</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="355">
          <source>Vendor discount pass-through</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pass-through per lo sconto del fornitore</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="356">
          <source>In addition, <bpt id="p1">**</bpt>only<ept id="p1">**</ept> the retail pricing engine supports the following pricing features:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inoltre, <bpt id="p1">**</bpt>solo<ept id="p1">**</ept> il motore di determinazione del prezzo di vendita al dettaglio supporta le seguenti funzionalità dei prezzi:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="357">
          <source>The price is based on product dimensions, in order from the most-specific variant price to the least-specific variant price to the product master price.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il prezzo si basa sulle dimensioni prodotto, in ordine dal prezzo variante più specifico al prezzo variante meno specifico alla rappresentazione generale prodotto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="358">
          <source>A price that is set by using two product dimensions (for example, Color and Size) is used before a price that is set by using only one product dimension (for example, Size).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un prezzo impostato utilizzando due dimensioni prodotto (ad esempio Colore e Dimensione) viene utilizzato prima di un prezzo impostato utilizzando una sola dimensione prodotto (ad esempio, Dimensione).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="359">
          <source>The same price group can be used to control pricing and discounts.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Lo stesso gruppo di prezzi può essere utilizzato per controllare i prezzi e gli sconti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="360">
          <source>Pricing API enhancements</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Miglioramenti dell'API sui prezzi</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="361">
          <source>Price is one of the most important factors that govern the buying decisions of many customers, and many customers compare prices on various sites before they make a purchase.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Il prezzo è uno dei fattori più importanti che governano le decisioni di acquisto di molti clienti e la maggior parte di questi confronta i prezzi in vari siti prima di effettuare un acquisto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="362">
          <source>To help guarantee that they provide competitive prices, retailers keep a close eye on their competitors and often run promotions.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Per avere la certezza di fornire prezzi concorrenziali, i rivenditori vigilano sui loro concorrenti e spesso eseguono promozioni.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="363">
          <source>Therefore, to help these retailers attract customers, it's very important that product search, the browse feature, lists, and the product details page show the most accurate prices.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Di conseguenza, per consentire ai rivenditori di attirare clienti, è molto importante che la ricerca dei prodotti, la funzionalità di esplorazione, gli elenchi e la pagina dei dettagli visualizzino i prezzi più accurati.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="364">
          <source>In an upcoming release of Retail, the <bpt id="p1">**</bpt>GetActivePrices<ept id="p1">**</ept> application programming interface (API) will return prices that include simple discounts (for example, single-line discounts that don't depend on other items in the cart).</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">In una versione imminente di Retail, l'API (Application Programming Interface) <bpt id="p1">**</bpt>GetActivePrices<ept id="p1">**</ept> restituirà i prezzi che includono sconti semplici (ad esempio sconti a riga singola che non dipendono da altri articoli nel carrello).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="365">
          <source>In this way, the prices that are shown are close to the actual amount that customers will pay for items.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">In questo modo, i prezzi visualizzati sono prossimi all'importo effettivo che i clienti pagheranno per gli articoli.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="366">
          <source>This API will include all the types of simple discounts: affiliation-based, loyalty-based, catalog-based, and channel-based discounts.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Questa API includerà tutti i tipi di sconti semplici: sconti in base all'affiliazione, alla fedeltà, al catalogo e al canale.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="367">
          <source>Additionally, the API will return the names and validity information for the applied discounts, so that retailers can provide a more detailed description of the price and create a sense of urgency if the discount's validity will expire soon.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Inoltre, l'API restituirà i nomi e le informazioni di validità per gli sconti applicati, di modo che i rivenditori possano fornire una descrizione più dettagliata del prezzo e creare un senso di urgenza se la validità dello sconto scade ben presto.</target>
        </trans-unit>
      </group>
    </body>
  </file>
</xliff>