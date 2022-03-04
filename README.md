# CSS only Rubik's Cube

# Wat ga ik maken?

Ik heb gekozen om een 3D Rubrik's kubus te maken met CSS, zonder JavaScript of pre- en post-processors. Ook mogen er geen classes of id's gebruikt worden (met uitzondering van het gebruik om de :target selector te triggeren en om labels te koppelen aan inputs).

## Uitdaging

De uitdaging voor mij wordt echt om de grenzen van CSS op te zoeken. Ik heb een redelijke basis met CSS, maar ik heb nog nooit met 3D gewerkt hierin. Daarom lijkt het mij interessant om te kijken of het lukt om die kubus echt werkend te krijgen.

## Week 1

In week 2 ben ik begonnen aan de kubus. Allereest heb ik een 3d vierkant gemaakt met CSS. Vervolgens heb ik de vlakken hiervan een kleur gegeven en heb ik 26 keer deze kubus gekopiërd. Nu was het een kwestie van deze bokken goed positioneren.

## Week 2

In week 2 ben ik gaan kijken naar het transformeren van de kubus. Hierbij wilde ik eerst kijken hoe ik 1 kant kan roteren. Dit ging ik doen met `transform(rotate())`. Hierbij liep ik echter tegen problemen aan, namelijk dat de blokjes individueel van elkaar tranformeerde (en dus niet als een hele zijde van de kubus), en dat elke individueel blokje overal dezelfde kleuren heeft. Hierdoor zie je bijvoorbeeld wanneer je de kant met rode blokjes draait dat er achter ook allemaal rode blokjes zitten. Dit is bij een echte rubiks kubus niet zo en dit ziet er ook verwarrend uit.

### Nieuwe versie

Hierdoor koos ik ervoor om deels opnieuw te beginnen. Ik ging elk blokje individueel de juiste kleuren geven, en de vlakken die je niet ziet zwart maken. Dit was nogal een klus maar het resultaat is een stuk beter. Hierna heb ik het roteer probleem opgelost door alle blokje van te voren een roteer property mee te geven die op 0 staat.

## Week 3

Ik week 3 kreeg ik corona en kon ik minder doen dan verwacht helaas. Wat ik wel heb gedaan is allereerst de code efficienter maken. Door middel van custom properties met een fallback value heb ik alle transforms op elke blokje met een stuk minder code kunnen schrijven. Ook heb ik de code voor het kleuren van de juistje vlakjes anders geschreven. Door wat complexere selectoren te gebruiken was een stuk minder code vereist. Hier zie je een voorbeeld:

```css
/* Yellow side */
ul:nth-child(3n + 14) li:nth-child(2),
ul:nth-child(-3n + 12) li:nth-child(2) {
    --color: var(--yellow);
}
```

Verder heb ik een toggle voor het camera menutje gemaakt. Zo kan je hem weergeven en verbergen wanneer je wil, wat vooral op mobiel wel handig kan zijn.
