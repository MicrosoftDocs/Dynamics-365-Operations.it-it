---
title: Configurare le modalità e le spese di consegna del servizio clienti
description: In questo articolo viene descritto come impostare le modalità di consegna e le spese per un ordine del servizio clienti in Dynamics 365 Commerce.
author: josaw1
ms.date: 04/26/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: f445e9dabd0210951609170369eae63bcc30ce6b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888300"
---
# <a name="configure-call-center-delivery-modes-and-charges"></a>Configurare le modalità e le spese di consegna del servizio clienti

[!INCLUDE [banner](includes/banner.md)]

Quando un ordine cliente viene inserito in Dynamics 365 Commerce, se la persona che ha immesso l'ordine cliente è collegata a un canale servizio clienti, la logica e le regole vengono utilizzate per convalidare la modalità di consegna e per calcolare le spese per l'ordine.

Quando si crea un ordine cliente, è possibile selezionare una modalità di consegna nell'intestazione dell'ordine cliente e nelle righe dell'ordine cliente. Per impostazione predefinita, la modalità di consegna che si seleziona nell'intestazione viene utilizzata per tutte le righe di ordine cliente. Tuttavia, è possibile sostituire la modalità di consegna predefinita nelle singole righe di vendita in base alle esigenze. È inoltre possibile definire una modalità di consegna per un record cliente. Quando vengono creati ordini per il cliente, viene quindi utilizzata la modalità di consegna per impostazione predefinita nell'intestazione dell'ordine cliente.

Commerce include funzionalità che consentono agli utenti di limitare le modalità di consegna in modo che possano essere utilizzate da un canale, le modalità di consegna che possono essere utilizzate per un prodotto e le modalità di consegna che sono valide per destinazioni di spedizione specifiche. È possibile inoltre definire le spese in modo che le commissioni aggiuntive vengano aggiunte all'ordine di un cliente, in base alla modalità di consegna selezionata per l'ordine e al valore totale dell'ordine.

## <a name="define-delivery-modes"></a>Definire le modalità di consegna

Prima di specificare quali modalità di consegna possono essere utilizzate per gli ordini del servizio clienti e prima di definire le regole e le spese associate, è necessario definire le modalità di consegna. Passare a **Vendite e marketing \> Impostazioni \> Distribuzione \> Modi di consegna**. Selezionare **Nuovo** per creare un nuovo modo di consegna. In alternativa, selezionare un modo di consegna esistente nell'elenco e quindi selezionare **Modifica** per apportare modifiche.

Nel campo **Modo di consegna**, è possibile immettere qualsiasi combinazione di caratteri alfanumerici, in base ai requisiti dell'azienda. È quindi possibile utilizzare il campo **Descrizione** per fornire altro contesto. I campi **Gruppi di spese** e **Urgente** sono facoltativi e verranno descritti più in dettaglio più avanti in questo articolo.

Nella Scheda dettaglio **Canali di commercio**, aggiungere qualsiasi canale che deve poter utilizzare il modo di consegna quando vengono create transazioni di vendita in quel canale.

Nella Scheda dettaglio **Prodotti**, è possibile specificare per quali prodotti e/o categorie di prodotti è possibile specificare o meno il modo di consegna. Ad esempio, se un prodotto non può essere spedito per via aerea a causa delle restrizioni sul materiale pericoloso (hazmat), verificare che il prodotto o la categoria di prodotti venga esclusa da tutti i modi di consegna che implicano il trasporto aereo.

Nella Scheda dettaglio **Indirizzi**, è possibile specificare quali paesi o regioni o stati è possibile utilizzare o meno il modo di consegna. Ad esempio, gli ordini che vengono spediti alle Hawaii o in Alaska non sono idonei per la consegna per via terrestre. Questi stati devono quindi essere esclusi da qualsiasi modo di consegna che è associato a un servizio di consegna per via terrestre e devono essere inclusi in tutti i modi di consegna che sono associati a un servizio di consegna per via aerea.

## <a name="validate-delivery-modes-for-a-call-center-order"></a>Convalidare i modi di consegna per un ordine di servizio clienti

Dopo avere definito i modi di consegna, è necessario eseguire il processo batch **Elabora modalità di consegna**. Questo processo rende disponibili i modi di consegna affinché possano essere utilizzati nei processi di ordine cliente per i canali. Per eseguire il processo **Elabora modalità di consegna**, passare a **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Elabora modalità di consegna**. È consigliabile eseguire questo processo ogni volta che si aggiungono nuovi modi di consegna a un canale o che si apportano modifiche alle relazioni esistenti tra modo di consegna e canale.

Dopo avere eseguito il processo batch **Elabora modalità di consegna**, è possibile passare a **Retail e Commerce \> Canali \> Servizi clienti \> Tutti i servizi clienti**. Nella pagina **Tutti i servizi clienti**, nel riquadro delle azioni, nella scheda **Imposta**, selezionare **Modi di consegna**. La pagina **Modi di consegna** elenca tutti i modi di consegna validi per il canali servizio clienti selezionato. Per modificare i modi di consegna esistenti o aggiungerne di nuovi, selezionare **Gestisci modalità di consegna**. Notare che il processo **Elabora modalità di consegna** deve essere eseguito ogni volta che vengono eseguite modifiche.

## <a name="define-charges-for-delivery-services"></a>Definire le spese per i servizi di consegna

Quando una società crea ordini cliente per i clienti, potrebbe voler aggiungere che spese che vengono calcolate automaticamente in base ai modi di consegna selezionati per gli ordini. Queste spese possono essere configurate in modo che siano uguali per tutti i clienti e tutti i modi di consegna. In alternativa, le spese possono variare, a seconda del cliente e/o del modo di consegna selezionati per l'ordine cliente.

Per definire le spese, passare a **Retail e Commerce \> Impostazione canale \> Spese \> Spese automatiche**. Selezionare **Nuovo** per aggiungere nuove spese. In alternativa, selezionare una voce esistente e quindi selezionare **Modifica**.

Le spese possono essere definite in modo che vengano calcolate a livello di intestazione ordine o di righe ordine. Utilizzare il campo **Livello** per selezionare il livello desiderato.

Le spese possono essere definite per un cliente specifico, un gruppo di clienti o tutti i clienti. Nel campo **Codice conto** selezionare **Tabella** per definire le spese che vengono applicate solo a un cliente specifico. Selezionare **Gruppo** per definire le spese per uno gruppo di clienti specifico. Selezionare **Tutti** per applicare le spese a tutti i clienti che inseriscono un ordine cliente che utilizza il modo di consegna correlato. Se è stato selezionato **Tabella** o **Gruppo** nel campo **Codice conto**, selezionare il cliente o il gruppo di clienti nel campo **Relazione conto**.

Le spese possono essere configurate in modo che vengano applicate a un modo di consegna specifico, un gruppo di modi di consegna o a tutti i modi di consegna. Se si seleziona **Tabella** nel campo **Codice modalità di consegna**, è necessario selezionare un modo di consegna specifico nel campo **Relazione tra modalità di consegna**. Se si seleziona **Gruppo**, è necessario selezionare un gruppo di modi di consegna nel campo **Relazione tra modalità di consegna**. I gruppi di modi di consegna vengono definiti in **Retail e Commerce \> Impostazione canale \> Spese \> Gruppi di spese di consegna**. Possono essere collegati a uno o più modi di consegna nella pagina **Modi di consegna**. Se si seleziona un gruppo quando si definiscono le spese, tutti i modi di consegna che sono collegati al gruppo di consegna selezionato utilizzando queste spese. Infine, se si seleziona **tutti** nel campo **Codice modalità di consegna**, tutti i modi di consegna utilizzano le spese. Pertanto non si seleziona un valore nel campo **Relazione tra modalità di consegna**.

Nella sezione **Righe**, è possibile definire una o più spese per valuta, in base alle esigenze. Le spese devono essere collegate a un codice spese che definisce le regole di registrazione finanziarie per le spese. Il campo **Categoria** viene utilizzato per definire la modalità di calcolo delle spese. Ad esempio, se ai clienti viene addebitata un'aliquota forfettaria di $9,95 per un ordine da spedire con un modo di consegna specifico, utilizzare la categoria **Fisso**. Se l'azienda decide di addebitare ai clienti una percentuale del totale dell'ordine per coprire le spese di consegna, utilizzare la categoria **Percentuale**. Le spese effettive ai clienti vengono definite nel campo **Valore spese**.

Le società spesso configurano le spese a livelli. In questo caso, l'importo che i clienti pagano per la consegna è basato sul valore dell'ordine. Per configurare le spese a livelli, immettere i valori nei campi **Da importo** e **A importo** oltre a definire le spese stesse nel campo **Valore spese**. Ad esempio, per gli ordini con un valore inferiore a $50, un rivenditore addebita $5,95 per una via terra. Per ordini con un valore uguale o maggiore di $50, ma inferiore a $100 il rivenditore addebita $7,95. Infine, per ordini con un valore uguale o maggiore di $100, il rivenditore offre la spedizione gratuita. Nella seguente figura viene illustrata la configurazione di queste spese.

![Esempio di spese a livelli fisse.](media/fixedtieredcharges.png)

È possibile utilizzare un misto di categorie per le spese, in base alle proprie esigenze aziendali. Ad esempio, per tutti gli ordini con un valore inferiore a $100, si applica un addebito fisso di $9,95 per la spedizione. Quindi, per gli ordini con valore uguale o maggiore di $100, le spese di consegna vengono calcolate al tasso del 5% del valore dell'ordine. Nella seguente figura viene illustrata la configurazione di queste spese.

![Esempio di spese a livelli miste.](media/mixedtieredcharges.png)

## <a name="apply-delivery-modes-during-order-entry-in-a-call-center"></a>Applicare modi di consegna durante la registrazione di ordini in un servizio clienti

Quando si crea un nuovo ordine cliente, è necessario specificare un valore nel campo **Modo di consegna** nella Scheda dettaglio **Consegna** dell'intestazione dell'ordine cliente. Questo campo potrebbe essere compilato automaticamente, in base ai valori predefiniti derivati dal record del cliente.

Il modo di consegna che viene definito nell'intestazione dell'ordine viene copiato automaticamente nelle righe dell'ordine cliente man mano che vengono create. È tuttavia possibile modificare l'impostazione del modo di consegna per una riga specifica nella scheda **Consegna** nella sezione **Dettagli riga** della pagina di registrazione dell'ordine cliente.

Se il modo di consegna selezionato non è valido per il prodotto o per l'indirizzo di consegna definito per l'ordine o la riga dell'ordine, viene visualizzato un messaggio di errore. È quindi necessario selezionare un modo di consegna definito per supportare la configurazione del prodotto o dell'indirizzo.

## <a name="calculation-of-delivery-charges-during-entry-of-order"></a>Calcolo delle spese di consegna durante la registrazione dell'ordine

Se l'impostazione **Attiva completamento ordine** viene attivata per il canale servizio clienti, le spese di consegna vengono automaticamente calcolate per gli ordini cliente quando gli utenti selezionano **Completo**. Il messaggio seguente viene visualizzato in cima alla pagina **Riepilogo ordine cliente**: "Spese a livelli calcolate". Le spese calcolate vengono aggiunte al valore del campo **Totale vendite**. Nella Scheda dettaglio **Importo**, il campo **Spese** mostra l'importo totale di tutte le spese che sono state calcolate per l'ordine e le righe. Per vedere una scomposizione dettagliata delle spese, selezionare **Ordine** nella pagina **Riepilogo ordine cliente**, quindi selezionare l'opzione **Spese** per visualizzare, aggiungere o modificare le spese. Notare che il calcolo delle spese di consegna nell'intestazione dell'ordine si basano sul modo di consegna che è collegato all'intestazione. Le spese di consegna a livello di riga vengono calcolate in base al modo di consegna che viene configurato per la riga di vendita. Se per righe differenti vengono utilizzati più modi di consegna, è possibile applicare più spese insieme. L'importo totale viene quindi mostrato nel campo **Spese** nella pagina **Riepilogo ordine cliente**.

Se l'impostazione **Attiva completamento ordine** è disattivato, gli utenti devono attivare manualmente il calcolo delle spese. Nella pagina **Ordine cliente**, nel riquadro delle azioni, nella scheda **Vendi**, nel gruppo **Calcola**, selezionare **Spese a livelli**. Viene visualizzato il messaggio "Spese a livelli calcolate". È quindi possibile selezionare l'opzione **Spese** nella scheda **Vendi** per visualizzare, modificare o eliminare le spese calcolate.

## <a name="use-expedited-delivery-modes-on-call-center-orders"></a>Utilizzare i modi di consegna urgenti sugli ordini del servizio clienti

È facoltativamente possibile collegare un codice di urgenza a un modo di consegna che si configura. Questo codice viene utilizzato come priorità di ordinamento e strumento di creazione report. Attualmente non determina l'aggiunta di altre commissioni da applicare all'ordine. Per impostare i codici di urgenza, passare a **Vendite e marketing \> Impostazioni \> Distribuzione \> Codici urgenza**.

Ad esempio, per gli ordini che verranno spediti il giorno successivo per via aerea, il prelievo dal magazzino deve avvenire alle 13.00 di ogni giorno. In questo caso, è possibile creare un codice di urgenza e collegarlo a un qualsiasi modo di consegna del giorno successivo che viene configurato nel sistema. Quando il magazzino crea l'ondata di prelievi, è possibile utilizzare il codice di urgenza appropriato nel campo **Urgente** come filtro, in modo che il prelievo venga eseguito solo per gli ordini con modi di consegna collegati a quel codice.

Inoltre, quando viene immesso un ordine di servizio clienti, è possibile applicare manualmente un codice di urgenza all'intestazione dell'ordine cliente o a una singola riga dell'ordine cliente. Anche in questo caso, il codice può essere utilizzato per l'ordinamento e i report. Talvolta un ordine deve essere gestito con attenzione a causa di un problema con il servizio clienti. In questo caso, è possibile applicare un codice di urgenza specifico all'intestazione o alle righe ordine per aiutare a identificare e ad assegnare una priorità all'ordine durante il processo di evasione.


[!INCLUDE[footer-include](../includes/footer-banner.md)]