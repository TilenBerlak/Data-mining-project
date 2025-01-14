{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Zaključno poročilo"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "---"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Predstavitev množice podatkov"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Naša množica podatkov zajema meritve porabe električne energije po namembnosti in električnem viru v Sloveniji. Podatke smo prenesli s spletne strani https://podatki.gov.si/."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Meritve so zajete od leta 2000 do 2020. Za vsako leto smo primerjali energetske vire (premog, lesna goriva, električna energija, zemeljski plin, itd.) in namene v slovenskih gospodinjstvih za katere se uporabljajo (ogrevanje prostorov, kuhanje, razsvetljava, itd.). Merska enota za energijo je teradžul (TJ). Iz tega lahko na primer pridemo do ugotovitve, kako se skozi leta spreminja poraba energije pridobljene iz premoga."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Podatkovno množico smo iz PX formata pretvorili v dve CSV datoteki. V spodnji tabeli so podrobno predstavljeni atributi iz množice podatkov."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "| Atribut         | Opis        | Podatkovni tip |\n",
    "| -----------     | ----------- | -------------- |\n",
    "|   Leto          | Meritve so za vsako leto od 2000 do 2020            |       string         |\n",
    "| Energetski vir  | Ekstra lahko kurilno olje, zemeljski plin, lesna goriva, utekočinjeni naftni plin, elektrika, premog, daljinsko ogrevanje, sončna energija, toplota okolice          |    string            |\n",
    "|  Namen uporabe  |  Ogrevanje prostorov, ogrevanje vode, kuhanje, osvetljava, hladilniki, zmrzovalniki, pralni in sušilni stroji, pomivalni stroji, osebni računalniki, televizije in ostali porabniki          |    string         |\n",
    "| Poraba energije |   Merska enota električne energije je v TJ (Terajoules)                    | float |"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Odgovorjena vprašanja"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "* Kateri so največji porabniki?\n",
    "* Ali se je v zadnjih letih povečal delež električne energije pridobljene iz obnovljivih virov?\n",
    "* Kateri so vodilni energetski viri?\n",
    "* Ali se je uporaba kakšnega vira opazno spremenila skozi leta?\n",
    "* Koliko se je povečala ali zmanjšala raba virov skozi leta?"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Analiza podatkov in ugotovitve"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Najprej smo ugotovili kateri porabniki v slovenskih gospodinjstvih porabijo največ energije. Izkazalo se je, da gre daleč največ energije za ogrevanje gospodinjskih prostorov. Sledi ogrevanje vode in ostali porabniki, ki imajo manjši delež porabe.\n",
    "\n",
    "![Vizualizacija1](Projekt/graph1.png)\n",
    "\n",
    "Od leta 2000 do 2020 smo preverili, kako se spreminja poraba energije za dva največja porabnika (ogrevanje prostorov in vode). Poraba energije za ogrevanje vode skozi 20 let ostane konstantna. Poraba za ogrevanje prostorov pa z leti pada. Razlog za padec porabe je lahko boljša izolacija v novejših gradnjah gospodinstev.\n",
    "\n",
    "![Vizualizacija2](Projekt/graph2.png)\n",
    "\n"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Kateri energetski vir se skozi leta najbolj uporablja?\n",
    "\n",
    "Za vsako leto posebaj smo preverili, kateri energetski vir ima največjo skupno porabo namembnosti. Povedano drugače, če seštejemo porabo vseh porabnikov v gospodinjstvu, iz katerega vira pride največ energije za te porabnike. Iz grafa lahko razberemo, da so se v celotnem obdobju 20-ih let vedno največ uporabljala lesna goriva. Ker je ogrevanje prostorov največji porabnik, lahko sklepamo, da se veliko gospodinjstev ogreva na lesene pelete in drva.\n",
    "\n",
    "![Vizualizacija3](Projekt/graph3.png)\n"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Naslednja analiza je bila primerjanje uporabe energetskih virov v zadnjih dveh desetletjih. Poiskali smo odstotke rasti in padcev za vsak energetski vir za obdobje 10 let. Za boljšo preglednost poročila so v tabeli prikazane le najbolj zanimive spremembe. Vsi ostali odstotki so izpisani v projektu. Od vseh energetskih virov najbolj odstopata premog in sončna energija. V zadnjem desetletju se je premog nehal uporabljati, raba sončne energije pa se je povišala. Raba električne energije se je v zadnjih desetletjih povečala za 40%, sklepamo, da je vzrok za rast večje število in raba elektrnoskih naprav v gospodinjstvih."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "| Energetski vir | Obdobje | Odstotek spremembe |\n",
    "| -------------- | ------- | ------------------ | \n",
    "| Extra light fuel oil: |  2000-2020: | -68.61%  |\n",
    "| Wood fuels: | 2000-2020: | -16.60%  |\n",
    "| Coal: | 2000-2010: | -88.21% | \n",
    "| Coal: | 2010-2020: | -100.00% |\n",
    "| Solar energy: | 2000-2010: | 75.38% |\n",
    "| Solar energy: | 2010-2020: | 25.73% |\n",
    "| Electricity:  | 2000-2020: | 39.72% |"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "![Vizualizacija4](Projekt/graph4.png)\n",
    "\n",
    "![Vizualizacija5](Projekt/graph5.png)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Na koncu smo želeli podrobno ugotoviti kako se spreminja poraba energije pridobljene iz obnovljivih in neobnovljivih virov. Spoznali smo, da raba neobnovljivih energetskih virov skozi leta postopoma upada. Raba obnovljivih virov kot je npr. sončna energija pa iz leta v leto raste (vedno več gospodinstev  ). Če primerjamo ekstra kurilno olje in zemeljske pline vidimo, da je bila raba kurilnega olja leta 2000 večja za več kot 500% kot zemeljski plini. Danes pa imajo zemeljski plini večjo porabo."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "![Vizualizacija6](Projekt/graph6.png)\n",
    "![Vizualizacija7](Projekt/graph7.png)\n",
    "![Vizualizacija8](Projekt/graph8.png)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Zaključne misli"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.10.2"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 4
}
