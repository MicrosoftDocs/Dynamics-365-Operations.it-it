<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="catch-weight-processing.md" target-language="it-IT">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>catch-weight-processing.d3ca7d.6e295456838ca0195a472518b5979dfdc7819f74.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>6e295456838ca0195a472518b5979dfdc7819f74</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>19859d8566a8c7840066b2c10c6b08b67f1b83f4</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/04/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\supply-chain\warehousing\catch-weight-processing.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Catch weight product processing with warehouse management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Elaborazione di prodotti a peso variabile con la gestione magazzino</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes how to use work templates and location directives to determine how and where work is done in the warehouse.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questo argomento descrive come utilizzare i modelli di lavoro e le direttive di ubicazione per stabilire come e dove il lavoro viene effettuato nel magazzino.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Catch weight product processing with warehouse management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Elaborazione di prodotti a peso variabile con la gestione magazzino</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>Feature exposure</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Esposizione della funzionalità</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>To use warehouse management to process catch weight products, you must use a license configuration key to turn on the functionality.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per elaborare prodotti a peso variabile con la gestione magazzino, è necessario utilizzare una chiave di configurazione di licenza per attivare la funzionalità.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>(Go to <bpt id="p1">**</bpt>System administration <ph id="ph1">\&gt;</ph> Setup <ph id="ph2">\&gt;</ph> License configuration<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Accedere a <bpt id="p1">**</bpt>Amministrazione sistema <ph id="ph1">\&gt;</ph> Impostazioni <ph id="ph2">\&gt;</ph> Configurazione licenza<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Then, on the <bpt id="p1">**</bpt>Configuration keys<ept id="p1">**</ept> tab, expand <bpt id="p2">**</bpt>Trade <ph id="ph1">\&gt;</ph> Warehouse and Transportation management<ept id="p2">**</ept>, and select the check box for <bpt id="p3">**</bpt>Catch weight for warehouse<ept id="p3">**</ept>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quindi, nella scheda <bpt id="p1">**</bpt>Chiavi di configurazione<ept id="p1">**</ept>, espandere <bpt id="p2">**</bpt>Commercio <ph id="ph1">\&gt;</ph> Gestione magazzino e trasporto<ept id="p2">**</ept> e selezionare la casella di controllo <bpt id="p3">**</bpt>Peso variabile per il magazzino<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Both the <bpt id="p1">**</bpt>Warehouse and Transportation management<ept id="p1">**</ept> license configuration key and the <bpt id="p2">**</bpt>Process distribution <ph id="ph1">\&gt;</ph> Catch weight<ept id="p2">**</ept> license configuration keys must also be turned on.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Anche la chiave di configurazione di licenza <bpt id="p1">**</bpt>Gestione magazzino e trasporto<ept id="p1">**</ept> e le chiavi di configurazione di licenza <bpt id="p2">**</bpt>Distribuzione processo <ph id="ph1">\&gt;</ph> Peso variabile<ept id="p2">**</ept> devono essere attivate.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>After the license configuration key is turned on, when you create a released product, you can select <bpt id="p1">**</bpt>Catch weight<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dopo l'attivazione della chiave di configurazione di licenza, quando si crea un prodotto rilasciato, è possibile selezionare <bpt id="p1">**</bpt>Peso variabile<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>You can also associate the released product with a storage dimension group that the <bpt id="p1">**</bpt>Use warehouse management processes<ept id="p1">**</ept> parameter is selected for.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">È inoltre possibile associare il prodotto rilasciato a un gruppo di dimensioni di immagazzinamento per il quale il parametro <bpt id="p1">**</bpt>Usa processi di gestione magazzino<ept id="p1">**</ept> è selezionato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Before you can use the product in Warehouse management, you must do some basic product-specific setup for catch weight:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prima di utilizzare il prodotto nella gestione magazzino, è necessario effettuare alcune impostazioni di base specifiche del prodotto per il peso variabile:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>Define the nominal weight conversion between the catch weight unit (box) and the inventory unit (kilogram <ph id="ph1">\[</ph>kg<ph id="ph2">\]</ph>) as part of a unit conversion definition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Definire la conversione del peso nominale tra l'unità di peso variabile (scatola) e l'unità di magazzino (chilogrammo <ph id="ph1">\[</ph>kg<ph id="ph2">\]</ph>) come parte di una definizione di conversione dell'unità.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Define the minimum and maximum weight tolerances as part of the catch weight unit setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Definire le tolleranze di peso minima e massima nella configurazione dell'unità di peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Set up a unit sequence group where the catch weight unit is defined as the lowest stock keeping unit (SKU).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Impostare un gruppo di sequenze unità dove l'unità a peso variabile è definita come unità di stockkeeping (SKU) minima.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Set up a catch weight item handling policy.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Impostare criteri di gestione articoli a peso variabile</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>For more information, see <bpt id="p1">[</bpt>Setting up and maintaining catch weight items<ept id="p1">](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per ulteriori informazioni, vedere <bpt id="p1">[</bpt>Configurazione e gestione di articoli a peso variabile<ept id="p1">](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Transaction adjustments</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rettifiche transazioni</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Because the weight of inventory when it comes into a warehouse can differ from the weight when the inventory is issued out of the warehouse, the catch weight product processing must adjust the inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Poiché il peso delle scorte all'arrivo in magazzino può differire da quello delle scorte quando escono dal magazzino, l'elaborazione del prodotto a peso variabile deve rettificare le scorte.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source><bpt id="p1">**</bpt>Example 1<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Esempio 1<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>During a <bpt id="p1">**</bpt>Report as finished<ept id="p1">**</ept> production process, the inbound weight of a license plate that contains eight boxes of a catch weight product is captured as 80.1 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Durante un processo di produzione <bpt id="p1">**</bpt>Dichiarazione di finito<ept id="p1">**</ept>, il peso di entrata acquisito di una targa che contiene otto scatole di un prodotto a peso variabile è di 80,1 chilogrammi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>The license plate is then stored away in the finished goods area, and during the storage period, some weight is lost into the air.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La targa viene quindi conservata nell'area dei prodotti finiti e durante il periodo di immagazzinamento, una parte del peso viene persa nell'atmosfera.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Later, as part of a sales order picking process, the weight of the same license plate is captured as 79.8 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Successivamente, in un processo di prelievo ordine cliente, il peso acquisito della stessa targa è di 79,8 chilogrammi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Therefore, in the system, you now have a weight difference as part of the physical dimension set.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pertanto, nel sistema, si ha una differenza di peso nell'ambito del set di dimensioni fisiche.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>In this case, the system automatically adjusts the difference by posting a transaction for the missing 0.3 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo caso, il sistema rettifica automaticamente la differenza registrando una transazione per i 300 g mancanti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source><bpt id="p1">**</bpt>Example 2<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Esempio 2<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>In its definition, a product is set up to tolerate a minimum weight of 8 kg and a maximum weight of 12 kg for the <bpt id="p1">**</bpt>Box<ept id="p1">**</ept> catch weight unit.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nella relativa definizione, un prodotto è impostato per tollerare un peso minimo di 8 chilogrammi e un peso massimo di 12 chilogrammi per l'unità a peso variabile <bpt id="p1">**</bpt>Scatola<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>You have two boxes of the product, and they have a registered weight of 16 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si hanno due scatole del prodotto e il relativo peso registrato è 16 kg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>If a warehouse worker picks and weighs one of the boxes, and the weight is captured as 9 kg, the remaining box will weigh 7 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se un addetto del magazzino preleva e pesa una delle scatole e il peso acquisito è di 9 kg, l'altra scatola peserà 7 kg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>However, because 7 kg is below the minimum weight, the system does an automatic adjustment to increase the weight of the on-hand inventory by 1 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tuttavia, poiché il peso di 7 kg è inferiore al peso minimo, il sistema non esegue una rettifica automatica per aumentare di 1 kg il peso delle scorte disponibili.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>To set up the accounts that these adjustments are posted to, go to <bpt id="p1">**</bpt>Cost management <ph id="ph1">\&gt;</ph> Ledger integration policies setup <ph id="ph2">\&gt;</ph> Posting<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per impostare i conti in cui queste rettifiche sono registrate, accedere a <bpt id="p1">**</bpt>Gestione costi <ph id="ph1">\&gt;</ph> Impostazione criteri integrazione contabilità generale <ph id="ph2">\&gt;</ph> Registrazione<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Then, on the <bpt id="p1">**</bpt>Inventory<ept id="p1">**</ept> tab, define the following accounts:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quindi , nella scheda <bpt id="p1">**</bpt>Scorte<ept id="p1">**</ept>, definire i seguenti conti:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Catch weight loss account</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Conto perdite prodotti a peso variabile</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Catch weight profit account</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Conto profitti prodotti a peso variabile</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>Catch weight item handling policy</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Criteri di gestione articoli a peso variabile</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>The catch weight item handling policy defines two primary warehouse management flows for the items: when the weight of the items is captured, and how it's captured.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I criteri di gestione articoli a peso variabile definiscono due flussi di gestione magazzino primari per gli articoli: quando il peso degli articoli viene acquisito e come viene acquisito.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>You can define when the weight is captured for sales and transfer order processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">È possibile definire quando il peso viene acquisito per l'elaborazione degli ordini cliente e di trasferimento.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>The weight can be captured during either of the following processes:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il peso può essere acquisito durante uno dei seguenti processi:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source><bpt id="p1">**</bpt>Picking<ept id="p1">**</ept> – The weight is captured during the initial pick work lines of order work.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Prelievo<ept id="p1">**</ept> - Il peso viene acquisito durante le righe di lavoro prelievo iniziali dell'ordine.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source><bpt id="p1">**</bpt>Packing<ept id="p1">**</ept> – The weight is captured during manual packing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Imballaggio<ept id="p1">**</ept> - Il peso viene acquisito durante l'imballaggio manuale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>(You must send the items to a packing station.)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">È necessario inviare gli articoli a un centro d'imballaggio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>If the actual weight is captured at the packing station during the container packing processes, warehouse workers won't be prompted to capture the weight during picking work.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se il peso effettivo viene acquisito nel centro d'imballaggio durante i processi di imballaggio del contenitore, agli addetti del magazzino non verrà richiesto di acquisire il peso durante il lavoro di prelievo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Instead, the average weight of the physical inventory will be used as the weight of the picked inventory that goes to the packing area.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il peso medio dell'inventario fisico verrà invece utilizzato come peso delle scorte magazzino prelevate che vengono trasferite all'area di imballaggio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>For internal warehouse management processes like counting and adjustment corrections it is possible to define if the weight should be captured or not.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per i processi di gestione magazzino interni come il conteggio e la rettifica, è possibile definire se il peso deve essere acquisito o meno.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>If not captured the nominal weight will be used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se non viene acquisito, verrà utilizzato il peso nominale.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>You can also define how the weight is captured.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">È inoltre possibile definire il modo in cui peso viene acquisito.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>In one of the two main flows, catch weight tags are tracked and used to capture the weight.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In uno dei due flussi principali, i tag a peso variabile vengono tracciati e utilizzati per acquisire il peso.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>In the other flow, catch weight tags aren't tracked.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nell'altro flusso, i tag a peso variabile non vengono tracciati.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source><bpt id="p1">**</bpt>Yes<ept id="p1">**</ept> – The item uses catch weight tags.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Sì<ept id="p1">**</ept> - L'articolo utilizza tag a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Each tag number represents one catch weight unit (box), and a weight and other information are associated with the tag.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ogni numero di tag rappresenta un'unità a peso variabile (scatola); un peso e altre informazioni sono associate al tag.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>For outbound processes, the weight that is associated with the tag is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per i processi in uscita, viene utilizzato il peso associato al tag.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source><bpt id="p1">**</bpt>No<ept id="p1">**</ept> – The item doesn't use catch weight tags.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>No<ept id="p1">**</ept> - L'articolo non utilizza tag a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The inbound and outbound weighing processes are based on the actual weight that is captured during each process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I processi di pesatura in entrata e in uscita sono basati sul peso effettivo acquisito durante ogni processo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>The process of tracking catch weight tags can be used for items that won't change weight during the storage period.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il processo di tracciabilità di tag a peso variabile può essere utilizzato per gli articoli il cui peso non cambierà durante il periodo di immagazzinamento.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>The weight will be captured only during the inbound warehouse process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il peso verrà acquisito solo durante il processo di magazzino in entrata.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>During the outbound process, the catch weight tags will just be scanned, and the weights that are associated with the tags will be used for the outbound transactional processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Durante il processo in uscita, i tag a peso variabile saranno soltanto analizzati e i pesi associati ai tag saranno utilizzati per l'elaborazione transazionale in uscita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>How to capture catch weight</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Come acquisire il peso variabile</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>When catch weight tag tracking is used, a tag must always be created for every catch weigh unit that is received, and every tag must always be associated with a weight.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando si utilizza la tracciabilità dei tag a peso variabile, un tag deve essere sempre creato per ogni unità di peso variabile ricevuta e ogni tag deve sempre essere associato a un peso.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>For example, <bpt id="p1">**</bpt>Box<ept id="p1">**</ept> is the catch weight unit, and you receive one pallet of eight boxes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ad esempio, <bpt id="p1">**</bpt>Scatola<ept id="p1">**</ept> è l'unità a peso variabile e si riceve un pallet di otto scatole.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>In this case, eight unique catch weight tags must be created, and a weight must be associated with each tag.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo caso, otto tag a peso variabile univoci devono essere creati e un peso deve essere associato a ogni tag.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Depending on the inbound catch weight tag, either the weight of all eight boxes can be captured, and the average weight can then be distributed to each box, or a unique weight can be captured for each box.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A seconda del tag a peso variabile in entrata, è possibile acquisire il peso di tutte e otto le scatole, e il peso medio può quindi essere distribuito a ciascuna scatola, oppure un peso univoco per ogni scatola.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>When catch weight tag tracking isn't used, the weight can be captured for each dimension set (for example, for each license plate and tracking dimension).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando la tracciabilità dei tag a peso variabile non viene utilizzata, il peso può essere acquisito per ogni set di dimensioni (ad esempio, per ogni targa e dimensione di tracciabilità).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>Alternatively, the weight can be captured based on an aggregated level, such as five license plates (pallets).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In alternativa, il peso può essere acquisito in base a un livello di aggregazione, ad esempio cinque targhe (pallet).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>For the methods for capturing outbound weight, you can define whether the weighing is done for each catch weight unit (that is, per box), or whether the weight is captured based on the quantity that will be picked (for example, three boxes).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per i metodi di acquisizione del peso in uscita, è possibile definire se la pesatura viene eseguita per ogni unità a peso variabile (ovvero per scatola), oppure se il peso viene acquisito in base alla quantità che verrà prelevata (ad esempio, tre scatole).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Note that for the production line picking and internal movement processes, the average weight will be used if the <bpt id="p1">**</bpt>Not captured<ept id="p1">**</ept> option is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tenere presente che per i processi di prelievo della riga di produzione e di movimenti interni, il peso medio verrà utilizzato se l'opzione <bpt id="p1">**</bpt>Non acquisito<ept id="p1">**</ept> è utilizzata.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>To restrict the warehouse management picking processes from capturing weights resulting in catch weight profit/loss adjustments, the Outbound weight variance method can be used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per impedire ai processi di prelievo di gestione magazzino di acquisire pesi che danno luogo a rettifiche di profitti/perdite prodotti a peso variabile, è possibile utilizzare il metodo di scostamento del peso in uscita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Supported scenarios</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Scenari supportati</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Not all workflows support catch weight product processing with warehouse management.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Non tutti i flussi di lavoro supportano l'elaborazione di prodotti a peso variabile con la gestione magazzino.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>The following restrictions currently apply.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Attualmente, vengono applicate le restrizioni descritte di seguito.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>Configuring catch weight products for warehouse management processes</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurazione di prodotti a peso variabile per processi di gestione magazzino</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>For catch weight products, the storage dimension group for items can't be changed (so that warehouse management processes can be used for them).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per i prodotti a peso variabile, il gruppo di dimensioni di immagazzinamento per gli articoli non può essere modificato (di conseguenza, è possibile utilizzare processi di gestione magazzino).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>Only formula processing is supported for catch weight products (not bill of materials).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Solo l'elaborazione della formula viene supportata per i prodotti a peso variabile (non la distinta base).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>Catch weight products can't be associated with a tracking dimension group by using the Owner dimension.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I prodotti a peso variabile non possono essere associati a un gruppo di dimensioni di tracciabilità utilizzando la dimensione Proprietario.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Catch weight products can't be used as services.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I prodotti a peso variabile non possono essere utilizzati come servizi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>Catch weight products can be used as "stocked products" only as part the item model group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I prodotti a peso variabile possono essere utilizzati come "prodotti stoccati" solo come parte del gruppo di modelli di articoli.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Catch weight products can't be used together with the functionality for tracking "Active in sales process."</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I prodotti a peso variabile non possono essere utilizzati insieme alla funzionalità per la tracciabilità "Attiva in processo di vendita".</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>Catch weight products can't be used together with the functionality for capturing serial numbers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I prodotti a peso variabile non possono essere utilizzati insieme alla funzionalità per l'acquisizione di numeri di serie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>Therefore, products can't be transferred from a "blank" to a serial number as part of the picking/packing process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Di conseguenza, i prodotti non possono essere trasferiti da un "vuoto" a un numero di serie durante il processo di prelievo/imballaggio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>Catch weight products can't be used together with the functionality for registering serials before consumption.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I prodotti a peso variabile non possono essere utilizzati insieme alla funzionalità per la registrazione di numeri di serie prima del consumo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>Catch weight products that are variant-enabled can't be used together with the functionality for converting variant units of measure.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I prodotti a peso variabile abilitati da variante non possono essere utilizzati insieme alla funzionalità per la conversione delle unità di misura di variante.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Catch weight products can't be marked as a retail "product kit."</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I prodotti a peso variabile non possono essere contrassegnati come kit di prodotti vendita al dettaglio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Catch weight products can be used only with a unit sequence group that has catch weight handling units, and that has the catch weight unit as the lowest sequence.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I prodotti a peso variabile possono essere utilizzati solo con un gruppo di sequenze unità che ha unità movimentazione a peso variabile e l'unità a peso variabile come sequenza inferiore.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>For catch weight products, the inventory unit can be converted to the catch weight unit only if the conversion produces a nominal quantity that is more than 1.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per i prodotti a peso variabile, è possibile convertire l'unità di magazzino in unità a peso variabile solo se la conversione genera una quantità nominale maggiore di 1.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>The setup of bar codes for catch weight products doesn't support a variable weight setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'impostazione di codici a barre per prodotti a peso variabile non supporta un'impostazione peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>Order processing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Elaborazione ordine</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>The creation of advance ship notice (ASN/packing structures) doesn't support weight information.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La creazione di Advance Shipping Notice (strutture di imballaggio/ASN) non supporta informazioni relative al peso.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>The order quantity must be maintained based on the catch weight unit.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La quantità ordine deve essere gestita in base all'unità a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Inbound warehouse processing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Elaborazione di magazzino in entrata</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>Receiving license plates requires that weights be assigned during registration, because weight information isn't supported as part of the advance ship notice.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il ricevimento di targhe richiede che i pesi siano assegnati durante la registrazione in quanto le informazioni relative al peso non sono supportate nell'Advance Shipping Notice.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>When catch weight tag processes are used, the tag number must be manually assigned per catch weight unit.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando si utilizzano i processi dei tag a peso variabile, il numero di tag deve essere assegnato manualmente per unità a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Inventory and warehouse operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Operazioni relative a scorte e magazzino</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>Manual creation of quarantine orders isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La creazione manuale di ordini di quarantena non è supportata per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>Manual movement of inventory that is related to work isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il movimento manuale delle scorte relativo al lavoro non è supportato per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>Consolidation of license plates isn't supported for catch weight products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Il consolidamento di targhe non è supportato per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>License plate loading to initialize warehouse stock isn't supported for catch weight products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Il caricamento targa per inizializzare le scorte di magazzino non è supportato per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>Batch balancing processes aren't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I processi di bilanciamento del batch non sono supportati per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Handling of negative physical inventory isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La gestione dell'inventario fisico negativo non è supportata per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>Inventory marking can't be used for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il contrassegno scorte non può essere utilizzato per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>Outbound warehouse processing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Elaborazione di magazzino in uscita</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>The functionality for cluster picking isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La funzionalità per il prelievo del cluster non è supportata per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>Pick and pack warehouse processing isn't supported for catch weight products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">L'elaborazione di magazzino per prelievo e imballaggio non è supportata per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>For catch weight products, work that is defined in a work template can be run automatically.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Per i prodotti a peso variabile, il lavoro definito in un modello di lavoro può essere eseguito automaticamente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>The functionality for reversing work isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La funzionalità per lo storno del lavoro non è supportata per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>For catch weight products, manual packing station processing where work is created after containers are closed isn't supported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per i prodotti a peso variabile, l'elaborazione manuale presso il centro d'imballaggio in cui il lavoro viene creato dopo la chiusura dei contenitori non è supportata.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>The functionality for pcs-by-pcs scanning isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La funzionalità per la scansione pezzo per pezzo non è supportata per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>Production processing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Elaborazione della produzione</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>For catch weight products, only batch orders for formula products are supported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per i prodotti a peso variabile, sono supportati solo gli ordini batch per prodotti formula.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>Kanban functionality isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La funzionalità kanban non è supportata per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>For catch weight products, serial numbers can't be registered before consumption.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per i prodotti a peso variabile, i numeri di serie non possono essere registrati prima del consumo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>The functionality for reversing license plates isn't supported for catch weight products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">La funzionalità per lo storno delle targhe non è supportata per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>For catch weight products, reporting as finished cannot be registered by serial number.</source><target logoport:matchpercent="94" state="translated" state-qualifier="fuzzy-match">Per i prodotti a peso variabile, la dichiarazione di finito non può essere registrata mediante il numero di serie.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>Transportation management processing</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Elaborazione della gestione trasporto</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Load building workbench processing isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'elaborazione del workbench di allestimento del carico non è supportata per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>Transport request lines aren't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le righe di richiesta trasporto non sono supportate per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>Other restrictions and behaviors for catch weight product processing with warehouse management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Altri restrizioni e comportamenti per l'elaborazione di prodotti a peso variabile con la gestione magazzino</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>During picking processes where the user isn't prompted to identify tracking dimensions, the weight assignment is done based on the average weight.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Durante i processi di prelievo in cui all'utente non viene richiesto di identificare le dimensioni di tracciabilità, l'assegnazione del peso viene effettuata in base al peso medio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>This behavior occurs when, for example, a combination of tracking dimensions is used in the same location and, after a user processes picking, only one tracking dimension value is left in the location.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questo comportamento si verifica quando, ad esempio, una combinazione di dimensioni di tracciabilità viene utilizzata nella stessa ubicazione e, dopo che un utente elabora il prelievo, solo un valore di dimensione di tracciabilità rimane nell'ubicazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>When inventory is reserved for a catch weight product that is configured for warehouse management processes, the reservation is done based on the minimum weight that is defined, even if this quantity is the on-hand last handling quantity.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando le scorte sono prenotate per un prodotto a peso variabile configurato per processi di gestione magazzino, la prenotazione viene eseguita in base al peso minimo definito, anche se questa quantità è l'ultima quantità movimentazioni disponibile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>This behavior differs from the behavior for items that aren't configured for warehouse management processes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questo comportamento differisce da quello degli articoli che non sono configurati per i processi di gestione magazzino.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>Processes that use the weight as part of capacity calculations (wave thresholds, work maximum breaks, container maximums, location load capacities, and so on) don't use the actual weight of the inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I processi che utilizzano il peso per i calcoli di capacità (soglie ondata, interruzioni lavoro massime, numero massimo di contenitori, capacità del carico ubicazione e così via), non utilizzano il peso effettivo delle scorte.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>Instead, the processes are based on the physical handling weight that is defined for the product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">I processi sono invece basati sul peso di gestione fisica definito per il prodotto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>In general, Retail functionality isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In generale, la funzionalità per la vendita al dettaglio non è supportata per i prodotti a peso variabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>Catch weight tags</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tag a peso variabile</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>Currently, the functionality for catch weight tags is supported only as part of the following scenarios:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Attualmente, la funzionalità per i tag a peso variabile è supportata solo nei seguenti scenari:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>When processing purchase order warehouse app receiving.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Durante l'elaborazione del ricevimento di ordini fornitore tramite l'app magazzino.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>When processing load receiving via warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Durante l'elaborazione del ricevimento del carico tramite l'app magazzino.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>For license plate receiving that is related to a purchase order load, weight assignment is requested during the receiving process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per il ricevimento di targhe relativo a un carico ordine fornitore, l'assegnazione del peso è richiesta durante il processo di ricevimento.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>By contrast, for transfer order receiving, the weight from the shipment data for the transfer order is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Di contro, per il ricevimento dell'ordine di trasferimento, viene utilizzato il peso dai dati di spedizione per l'ordine di trasferimento.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>For transfer order item and line receiving that comes from a non-warehouse management process warehouse.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per il ricevimento di righe e articoli dell'ordine di trasferimento da un processo di gestione non di magazzino.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>The processing of sales return order receiving can record catch weight tags, but the processing won't be validated if the tags are the same tags that were originally shipped for a particular sales order line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'elaborazione del ricevimento di ordini di reso cliente può registrare tag a peso variabile, ma l'elaborazione non verrà convalidata se i tag sono gli stessi originariamente spediti per una particolare riga ordine cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>When processing a inventory status changed by using the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando si elabora uno stato delle scorte modificato utilizzando l'app magazzino.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>When a warehouse transfer is done by using the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando un trasferimento tra magazzini viene eseguito mediante l'app magazzino.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>When processing adjustment in and out via the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando si elabora la rettifica in entrata e in uscita via l'app magazzino.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>When picking work is processed for sales and transfer orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando il lavoro di prelievo viene elaborato per ordini cliente e di trasferimento</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>(Note that catch weight tags can't be recorded for production component picking.)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">(da notare che i tag a peso variabile non possono essere registrati per il prelievo di componenti di produzione).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>When picked quantities are reduced from load lines, regardless of whether containers are used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando le quantità prelevate sono ridotte dalle righe di carico, indipendentemente dall'uso o meno di contenitori.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>When products are packed into containers at a packing station.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando i prodotti sono imballati in contenitori presso un centro d'imballaggio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>When containers are reopened.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando i contenitori vengono riaperti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>When formula products are reported as finished by using the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando i prodotti della formula vengono registrati come finiti utilizzando l'app magazzino.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>When transport loads are processed by using the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando i carichi di trasporto sono elaborati mediante l'app magazzino.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>A catch weight tag can either be created using a warehousing app process, manually created in the form, or creating using a data entity process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un tag di peso variabile può essere creato tramite un processo dell'app del magazzino, manualmente nel modulo o utilizzando un processo di entità di dati.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>If a catch weight tag gets associated with an inbound source document line, such as purchase order line, the tag will be registered.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se un tag di peso variabile viene associato a una riga in entrata di documento di origine, ad esempio una riga ordine fornitore, il tag verrà registrato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>If the line is used for outbound processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se la riga viene utilizzata per l'elaborazione in uscita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>The tag will be updated as shipped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il tag verrà aggiornato come spedito.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>