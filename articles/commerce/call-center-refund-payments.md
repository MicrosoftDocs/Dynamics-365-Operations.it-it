---
title: Elaborazione di pagamento per il rimborso nei servizi clienti
description: Questo argomento spiega come vengono generati i rimborsi dei pagamenti tramite i servizi clienti quando vengono creati i resi o quando gli ordini o le righe ordine vengono annullati.
author: hhainesms
ms.date: 01/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: e3837ccebca0e6644ac5ded98344a5135cfb5d7a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799591"
---
# <a name="refund-payment-processing-in-call-centers"></a>Elaborazione di pagamento per il rimborso nei servizi clienti

Questo argomento spiega come vengono generati i rimborsi dei pagamenti tramite i servizi clienti quando vengono creati i resi o quando gli ordini o le righe ordine vengono annullati.

Un utente che crea un ordine di reso per un cliente come utente del servizio clienti in Microsoft Dynamics 365 Commerce headquarters utilizza la pagina **Ordine di reso** per creare l'autorizzazione per la restituzione dei materiali iniziale (NAR). L'autorizzazione per la restituzione dei materiali definisce i prodotti che il cliente desidera restituire o sostituire e crea un ordine cliente di reso collegato che ha un tipo di ordine di **Ordine di reso**. Questo ordine di reso collegato viene utilizzato per tenere traccia della registrazione delle scorte restituite e di eventuali note di credito o rimborsi di pagamento registrati.

Se l'opzione **Abilita completamento ordine** è impostata su **Sì** per il canale del servizio clienti, l'utente del servizio clienti che crea l'autorizzazione per la restituzione dei materiali deve eseguire il flusso di elaborazione di completamento ordine selezionando **Completa** nella pagina **Ordine di reso**. La funzione **Completa** fornisce un riepilogo del reso calcolato che indica l'importo del rimborso dovuto. Inoltre, quando è configurata correttamente, crea sistematicamente una riga di pagamento del rimborso sull'ordine di reso.

La logica del servizio clienti determina il metodo di pagamento per la riga di pagamento del rimborso, in base al metodo di pagamento utilizzato per l'ordine originale. Se l'ordine di reso creato non è collegato a un ordine originale, viene applicato un metodo di pagamento predefinito tratto da un parametro di sistema.

## <a name="how-a-call-center-determines-which-payment-method-to-apply-to-a-return-order"></a>In che modo un servizio clienti determina quale metodo di pagamento applicare a un ordine di reso

Il servizio clienti utilizza il metodo di pagamento dell'ordine originale per determinare il metodo di pagamento da applicare a un ordine di reso. Ecco come funziona questo processo per i seguenti metodi di pagamento originali:

- **NoAutorizzazione per la restituzione dei materiali** (contanti) o **Assegno** - Quando un ordine di reso creato fa riferimento a un ordine originale pagato utilizzando il tipo di pagamento noAutorizzazione per la restituzione dei materiali (contanti) o assegno, l'applicazione del servizio clienti fa riferimento alle configurazioni nella pagina **Metodi di rimborso servizio clienti**. Questa pagina consente alle organizzazioni di definire, in base alla valuta dell'ordine, come vengono emessi i rimborsi ai clienti per gli ordini che erano stati originariamente pagati utilizzando il tipo di pagamento noAutorizzazione per la restituzione dei materiali o assegno. La pagina **Metodi di rimborso servizio clienti** consente inoltre alle organizzazioni di selezionare se al cliente viene inviato un assegno di rimborso generato dal sistema o se viene creato un accredito sul conto cliente a fronte del saldo del conto cliente interno. In questi scenari, la logica del servizio clienti fa riferimento alla valuta dell'ordine di reso e quindi utilizza il valore di **Metodo di pagamento vendita al dettaglio** per quella valuta per creare una riga di pagamento del rimborso nell'ordine cliente di reso. Successivamente, un giornale di registrazione pagamenti cliente contabilità clienti (AR) che utilizza il metodo di pagamento AR mappato viene collegato alla valuta.

    La figura seguente mostra la configurazione per uno scenario in cui un cliente restituisce prodotti da un ordine cliente collegato alla valuta USD e che è stato originariamente pagato utilizzando il tipo di pagamento noAutorizzazione per la restituzione dei materiali o assegno. In questo scenario, verrà emesso un rimborso al cliente tramite un assegno di rimborso generato dal sistema. Il metodo di pagamento AR **REF-CHK** è stato configurato come tipo di pagamento assegno di rimborso.

    ![Configurazione dei metodi di rimborso del servizio clienti per pagamenti noAutorizzazione per la restituzione dei materiali e verifica dei pagamenti originali](media/callcenterrefundmethods.png)

- **Carta di credito** - Quando un ordine di reso creato fa riferimento a un ordine originale pagato utilizzando una carta di credito, la logica del servizio clienti per i pagamenti di rimborso applica la stessa carta di credito originale all'ordine di reso.
- **Carta fedeltà** - Quando un ordine di reso creato fa riferimento a un ordine originale pagato utilizzando una carta fedeltà del cliente, la logica del servizio clienti per i pagamenti di rimborso applica il rimborso alla stessa carta fedeltà.
- **Gift card** (interno) - Quando un ordine di reso creato fa riferimento a un ordine originale che è stato pagato utilizzando una gift card emessa da Dynamics 365 Commerce (funzionalità gift card interna), la logica del servizio clienti per i pagamenti di rimborso applica il rimborso allo stesso numero di gift card originale.
- **Gift card** (Esterno): quando un ordine di reso creato fa riferimento a un ordine originale pagato utilizzando una gift card esterna di terze parti, la logica del servizio clienti per i pagamenti con rimborso applica il metodo di pagamento del reso predefinito definito nella scheda **NAR/Reso** della pagina **Parametri del servizio clienti**.

Se il tipo di pagamento dell'ordine originale è sconosciuto per qualsiasi motivo o se sono stati utilizzati più metodi di pagamento per pagare l'ordine originale, la logica del servizio clienti applica il metodo di pagamento del reso predefinito definito nella scheda **NAR/Reso** della pagina **Parametri servizio clienti**.

La figura seguente mostra il campo **Metodo di pagamento** nella scheda **NAR/Reso** della pagina **Parametri servizio clienti**.

![Campo Metodo di pagamento nella scheda NAR/Reso della pagina Parametri servizio clienti](media/callcenterrefundparameters.png)

> [!NOTE]
> Le regole di elaborazione del rimborso descritte in precedenza si applicano anche agli ordini o alle righe ordine che un utente del servizio clienti annulla in Commerce headquarters. Se l'annullamento di un ordine o di righe di ordine specifiche causa pagamenti in eccesso, le stesse regole verranno utilizzate per generare righe di pagamento per il rimborso.

In genere, un ordine di reso passa attraverso un processo standard, in cui l'inventario viene ricevuto (o scartato), un documento di trasporto viene registrato a fronte dell'ordine di reso e quindi viene eseguito un processo di registrazione della fattura per l'ordine di reso cliente. L'ordine di reso cliente è collegato e generato sistematicamente come parte del processo di creazione dell'ordine di reso. In scenari tipici, i rimborsi di pagamento non vengono emessi ai clienti fino a quando non viene registrata la fattura per l'ordine di reso cliente.

### <a name="what-happens-when-an-invoice-is-posted-on-a-return-sales-order"></a>Cosa succede quando una fattura viene registrata in un ordine di reso cliente

I seguenti scenari spiegano cosa succede quando una fattura viene registrata in un ordine di reso cliente:

- Se il pagamento del rimborso sull'ordine di reso è per una carta di credito, viene richiamata una logica aggiuntiva al momento della registrazione della fattura. Questa logica chiama il processore di pagamento per rimborsare il pagamento sulla carta di credito del cliente. Viene inoltre creato un giustificativo di pagamento per il rimborso del cliente e registrato sistematicamente sul conto del cliente. Questo giornale di registrazione pagamenti verrà liquidato in base al giustificativo della nota di credito dell'ordine di reso.
- Se il pagamento del rimborso che deve essere emesso è per il tipo di pagamento con assegno, viene creato un giustificativo di pagamento cliente che utilizza il metodo di pagamento AR e deve essere registrato o stampato manualmente prima che il giustificativo di pagamento possa essere registrato nel conto cliente. Per elaborare l'assegno di rimborso, gli utenti possono utilizzare la pagina **Giornale di registrazione pagamenti cliente** in Contabilità clienti o la pagina **Elaborazione dell'assegno di rimborso** specializzata in Retail e Commerce.
- Se il pagamento del rimborso che deve essere emesso è per il tipo di pagamento gift card o carta fedeltà interna, quando l'ordine di reso viene fatturato, il giustificativo di pagamento rimborso viene creato e registrato nel conto cliente. Questa fase di fatturazione aggiunge anche l'importo del rimborso al saldo della gift card tracciato internamente o al saldo dei punti fedeltà del cliente.
- Se un metodo di pagamento che utilizza la funzione **Cliente** (ad esempio, un conto cliente) è collegata all'ordine di reso cliente, le convalide del limite di credito vengono ignorate quando il pagamento viene elaborato. Nessun giustificativo di pagamento viene creato o registrato in questo contesto. Quando un tipo di pagamento cliente viene utilizzato in un ordine di reso, il giustificativo della nota di credito creato dal processo di registrazione della fattura funge da giustificativo del credito del cliente e indica un rimborso sul saldo AR del cliente.

## <a name="advance-credit"></a>Anticipa credito

Quando un utente elabora gli ordini di reso come utente del servizio clienti in un servizio clienti in cui l'opzione **Abilita completamento ordine** è impostata su **Sì**, si può verificare un'eccezione al processo descritto in precedenza per la registrazione del pagamento del rimborso se l'utente del servizio clienti che crea l'ordine di reso imposta l'opzione **Credito anticipato** su **Sì** nella scheda **NAR/Reso** della pagina **Parametri servizio clienti**. In questo caso, il rimborso del pagamento avviene immediatamente dopo che l'ordine di reso è stato inviato utilizzando la funzione **Invia** della pagina **Riepilogo reso**. Il sistema crea immediatamente un giustificativo di pagamento del cliente con pagamento anticipato per il valore di reso, anche se l'ordine di reso cliente non è stato ancora fatturato. Questo approccio può essere utilizzato in situazioni in cui un'organizzazione deve emettere rimborsi ai clienti in anticipo a causa di problemi con il servizio clienti e non desidera richiedere che l'inventario restituito venga ricevuto prima dell'emissione dei rimborsi.

## <a name="replacement-orders"></a>Ordini sostitutivi

Quando viene emesso un ordine di reso, la funzione **Ordine di sostituzione** può essere utilizzata per generare un nuovo ordine cliente per il cliente. Questo approccio può essere utilizzato negli scenari di scambio. La funzione **Ordine di sostituzione** crea un altro ordine cliente per i nuovi articoli che devono essere inviati, ma un collegamento di riferimento incrociato nella scheda **NAR/Reso** della pagina **Parametri servizio clienti** collega l'ordine di sostituzione, l'autorizzazione per la restituzione dei materiali e l'ordine cliente di reso.

Quando vengono elaborati i pagamenti su un ordine di sostituzione, le organizzazioni hanno due opzioni:

- Rimborsare al cliente l'ordine di reso, in base al metodo di pagamento originale, quindi riscuotere un pagamento separato per l'ordine di sostituzione. Non è richiesta alcuna configurazione aggiuntiva per utilizzare questa opzione.
- Impostare l'opzione **Applica credito** su **Sì** nella scheda **NAR/Reso** della pagina **Parametri servizio clienti**. In questo caso, un metodo di pagamento del cliente viene applicato sistematicamente sia all'ordine di reso che all'ordine di sostituzione. Questa opzione può aiutare a impedire l'emissione di un pagamento di rimborso esterno. Aiuta anche a prevenire qualsiasi elaborazione di pagamento sulla transazione. Può essere utile in situazioni in cui viene elaborato uno scambio alla pari e l'organizzazione preferisce utilizzare il giustificativo di credito generato quando l'ordine di reso viene fatturato per pagare la fattura generata dall'ordine di sostituzione. Quando l'opzione **Applica credito** è impostata su **Sì**, l'organizzazione deve liquidare manualmente la nota di credito con la fattura dell'ordine di sostituzione dopo che entrambi i documenti finanziari sono stati generati.

L'impostazione **Sì** per l'opzione **Applica credito** è applicabile solo quando l'ordine di reso è collegato a un ordine di sostituzione. In questo caso, il metodo di pagamento del cliente che verrà utilizzato per pagare sistematicamente il reso e l'ordine di scambio è definito dal campo **Applica il metodo di pagamento crediti** nella scheda **NAR/Reso** della pagina **Parametri servizio clienti**. Solo un pagamento di tipo **Cliente** può essere selezionato in questo campo.

> [!NOTE]
> Per un ordine di reso che non ha un ordine di sostituzione collegato, un'impostazione di **Sì** per l'opzione **Applica credito** non avrà alcun effetto sulla logica di pagamento dell'ordine di reso, poiché questa impostazione si applica solo agli ordini di sostituzione.

![Campo Applica il metodo di pagamento crediti nella scheda NAR/Reso della pagina Parametri del servizio clienti](media/callcenterrefundparameters1.png)

> [!IMPORTANT]
> Se gli utenti che creano ordini di sostituzione prevedono di utilizzare l'opzione **Applica credito** non devono eseguire la funzione **Completa** nell'ordine di reso prima di impostare l'opzione **Applica credito** su **Sì**. Dopo che la funzione **Completa** viene eseguita, il pagamento del rimborso viene calcolato e applicato all'ordine di reso cliente. Qualsiasi tentativo di impostare l'opzione **Applica credito** su **Sì** dopo che un pagamento di rimborso è già stato calcolato e applicato non attiverà un ricalcolo del pagamento di rimborso e il metodo di pagamento selezionato nel campo **Applica metodo di pagamento crediti** non verrà applicato. Se l'opzione **Applica credito** deve essere utilizzata in questo contesto, l'utente deve eliminare l'ordine di sostituzione e l'autorizzazione per la restituzione dei materiali, quindi ricominciare e creare una nuova Autorizzazione per la restituzione dei materiali. Questa volta, l'utente deve assicurarsi che l'opzione **Applica credito** sia impostata su **Sì** prima di eseguire la funzione **Completa**.

## <a name="payment-overrides-for-call-center-returns"></a>Sostituzioni pagamenti per i resi del servizio clienti

Sebbene la logica del servizio clienti determini sistematicamente il metodo di pagamento del rimborso nel modo descritto in precedenza in questo argomento, gli utenti a volte potrebbero voler sostituire tali pagamenti. Ad esempio, un utente potrebbe modificare o rimuovere righe di pagamento di rimborso esistenti e applicare nuove righe di pagamento. I pagamenti dei rimborsi calcolati dal sistema possono essere modificati solo dagli utenti che dispongono delle autorizzazioni di sostituzione corrette. Queste autorizzazioni possono essere configurate nella pagina **Autorizzazioni di sostituzione** in Retail e Commerce. Per eseguire una sostituzione del pagamento con rimborso, l'utente deve essere collegato a un ruolo di sicurezza in cui l'opzione **Consenti pagamento alternativo** è impostata su **Sì** nella pagina **Autorizzazioni di sostituzione**.

![Consenti opzione di pagamento alternativo nella pagina Autorizzazioni di sostituzione](media/overridepermissions.png)

In alternativa, un'organizzazione può impostare l'opzione **Consenti sostituzione pagamento** su **Sì** nella scheda **NAR/Reso** della pagina **Parametri servizio clienti**. In questo caso, è necessario selezionare un codice di sostituzione di sicurezza nel campo **Codice di sostituzione sicurezza**. Il codice di sostituzione di sicurezza è un codice alfanumerico che deve essere gestito esternamente, poiché gli utenti non possono visualizzarlo in Commerce headquarters dopo che è stato impostato. Il codice di sostituzione della sicurezza deve essere conosciuto solo da poche persone chiave e fidate in un'organizzazione. Quando l'opzione **Consenti sostituzione pagamento** è impostata su **Sì**, se gli utenti che non dispongono delle autorizzazioni di ruolo corrette tentano di modificare il metodo di pagamento in un ordine di reso, avranno la possibilità di inserire il codice di sostituzione di sicurezza. Se non lo sanno o se un responsabile o un supervisore non può inserirlo nella pagina, non potranno sostituire il metodo di pagamento del reso.

> [!NOTE]
> Se il codice di sostituzione di sicurezza viene perso o dimenticato, l'organizzazione dovrà ripristinarlo definendo un nuovo codice di sostituzione di sicurezza nel campo **Codice di sostituzione di sicurezza** nella scheda **NAR/Reso** della pagina **Parametri servizio clienti**.

![Parametri di sostituzione pagamento nella scheda NAR/Reso della pagina Parametri servizio clienti](media/overridepaymentparameter.png)

> [!IMPORTANT]
> Prima che le organizzazioni provino a sostituire i pagamenti con rimborso che utilizzano i tipi di pagamento con carta di credito, devono verificare che il loro sistema di elaborazione delle carte di credito consenta resi non collegati. Molti sistemi di elaborazione delle carte di credito richiedono che i rimborsi vengano riportati sulla carta originale. Qualsiasi tentativo di emettere un rimborso su una carta che non ha acquisizioni precedenti potrebbe causare errori di registrazione con il sistema di elaborazione delle carte di credito.

## <a name="additional-resources"></a>Risorse aggiuntive

[Metodi di pagamento nei servizi clienti](work-with-payments.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]