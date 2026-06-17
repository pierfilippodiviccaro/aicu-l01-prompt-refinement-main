# Prompt Refinement L01

## Prompt Di Partenza

Incolla qui il prompt scelto.

```txt
Aggiungi un messaggio carino quando non ci sono ticket aperti
...
```

## Diagnosi Operativa

- Informazioni mancanti: non vi è una specificazione dettagliata dell'effetto grafico che si vuole avere quando viene fatto il display del messaggio 
- Ambiguita': non sa se vi è backend o anche cosa deve dire 
- Rischio di scope troppo largo: può andare a creare backend oppure fare altre assunzioni che non abbiamo specificato 
- Output non verificabile: 
- Strategia iniziale: zero-shot 
- Servono esempi?  No, perchè ovviamente questa è una cosa che dovremmo specificare noi all'LLM come vogliamo che questa determinata cosa venga fatta

## Prompt Usato Per Migliorare

```txt
voglio che mi aiuti a migliorare questo prompt. non serve che tu svolga il task ma vorrei capire cosa ci sta di sbagliato in questo prompt per agire meglio di conseguenza. la chain of thought non deve essere estesa e non mi servono degli esempi, quindi deve essere zero-shot
```

## Strategia Del Prompt Finale

- Zero-shot o few-shot: zero-shot 
- Motivo della scelta: Ha scomposto il prompt nelle componenti che di solito determinano se un'AI produce codice utile al primo colpo: posizione esatta (file/blocco), stato preesistente (sostituire vs aggiungere, per evitare duplicati), e criteri concreti al posto di aggettivi vaghi come "carino" (tono, lunghezza, coerenza stilistica). Senza questi tre elementi, il modello deve indovinare, e indovina spesso male o in modo generico.
- Se few-shot, cosa dimostrano gli esempi:
- Evidenze richieste all'AI: l'intelligenza artificale non ha richiesto nessuna evidenza ma ha detto cosa mancava e lo ha spiegato in tutti i modi 

## Prompt Migliorato

```txt
Nella vista resources/views/admin/tickets/index.blade.php, nel blocco @empty del @forelse che itera i ticket, sostituisci il messaggio attuale con un messaggio amichevole e breve (1 riga) che comunichi positivamente l'assenza di ticket aperti (es. tono leggero, niente di formale/burocratico). Mantieni lo stile coerente con il resto della UI (stessi font/colori già in uso). (mi è stato scritto in laravel, perchè io uso principlamente quello)
...
```

## Controllo Qualita'

- Contesto presente: il blocco empty del forelse che itera 
- Confini espliciti: tocca solamente una parte specifica del codice e non tutto 
- Output atteso: sostituzione di messaggio attuale con un messaggio amichevole 
- Prova di controllo:
- Cosa chiede all'AI di non fare:
- Esempi necessari e proporzionati: l'esempio è dato nel tono, ho chiesto personalmente di non fare esempi 
- Evita chain-of-thought estesa: fatto 
- E' piu' specifico perche': non mi dice una cosa vaga ma va diretto al punto 
- Limita meglio il lavoro perche': è semplice da capire e non vi sono punti troppo pesanti 
- Produce un output piu' verificabile perche':  si ritrova in una porzione molto stretta e ben lavorabile 
- Lo classificherei come: Utilizzabile 
