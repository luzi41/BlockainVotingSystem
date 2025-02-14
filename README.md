# BlockchainVotingSystem

## Anforderungen

Zu den Anforderungen im Hinblick auf die Integrität einer Online-Wahl gehört, dass das Wahlergebnis abschließend überprüft werden muss. Die notwendige Vertraulichkeit einer politischen Wahl erschwert jedoch die Entwicklung eines Verfahrens, das einerseits für Wählerinnen und Wahlbeobachter einfach zu handhaben ist und andererseits die Überprüfung einzelner Stimmen und des Wahlergebnisses als Ganzes gewährleistet. Diese Anforderung wird End-To-End Verifiability (E2E-V) genannt.

Die Ziele einer Verifizierung einer Wahl lauten: 
- Auswahl wie vorgesehen;
- registriert wie gewählt und
- gezählt wie registriert.” 

Das bedeutet, dass überprüfbar sein muss:
1. Wurde der beabsichtigte Kandidat gewählt? Wenn beispielsweise die Kandidaten auf den Listen vertauscht würden, könnte ein Wähler unbeabsichtigt die falsche Wahl treffen.
2. Wurde die Stimme so übermittelt und gespeichert, wie gewählt? Durch Manipulationen bei der Übermittlung oder Speicherung können bei einem Online-Wahlsystem Stimmen verloren gehen, oder doppelt gespeichert werden.
3. wurde die Stimme auch so gewertet wie gespeichert?

### Authentifizierung und Anonymität
Für eine demokratische Wahl muss auch gewährleistet werden, dass nur berechtigte Wählerinnen ihre Stimme abgeben können und dass jeder die gleiche Anzahl von Stimmen hat. Gleichzeitig muss die Anonymität der abgegebenen Stimmen gewahrt bleiben. Bei einem Peer-To-Peer-Netzwerk auf Basis des Bitcoin-Protokolls ist eine Authentifizierung nicht vorgesehen, jeder kann Teilnehmer in dem Netzwerk werden und alle Transaktionen beobachten. 

### Geheimhaltung und Mechanismus gegen Erpressungen
Ein Online-Wahlsystem muss eine geheime Wahl garantieren. Da eine Online-Wahl unter „unkontrollierten“ Bedingungen stattfindet (nicht im Wahllokal sondern zuhause auf unsicheren Endgeräten), muss außerdem sichergestellt werden, dass kein massenhafter Stimmenkauf, Erpressung etc. technisch ermöglicht wird, ohne dass dies entdeckt wird. Das bedeutet, dass das System beispielsweise nicht offenbaren darf, wie ein bestimmter Wähler gewählt hat. Eine Umsetzung dieser Anforderung bedarf letztendlich eines Identitäts-Managements, das jedoch getrennt werden muss von der Stimmenabgabe (wie die Wahlkabine in einem Wahllokal bei einer konventionellen Wahl)
- Entweder muss die Schreiberechtigung in einer Blockchain von der Prüfung der Wahlberechtigung abhängen;
- oder es müssen spezielle Token/Assets/ColoredCoins für die Wahlen verwendet werden;
- oder die Ausführung eines Smart Contracts muss von einer Identitätsprüfung und Wahlberechtigung abhängig gemacht werden.

Das Problem der potentiellen Erpressbarkeit erweitert die Anforderung der bloßen Geheimhaltung: Die Gefahr, dass Stimmen gekauft oder erpresst werden, lässt sich nur verhindern, wenn eine Wählerin nicht die Möglichkeit hat, zu beweisen, wie sie gewählt
hat. Wäre sie dazu in der Lage, könnte ein Erpresser diesen Beleg fordern und sie wäre erpressbar. Eine Anforderung, die deswegen an elektronische Wahlsysteme gestellt wird, wird in der Literatur als „Coercion resistance“ - zu Deutsch etwa „Widerstandsfähigkeit gegen Erpressung“ bezeichnet. Ein möglicher Erpresser darf außerdem auch ohne Kooperation der Wählerin keine Möglichkeit haben, eine Verbindung zwischen der Wählerin und ihrer Wahlentscheidung herstellen können dürfen. Um die Anforderungen betreffs der Geheimhaltung und Widerstandsfähigkeit zu erfüllen, ist es notwendig, die Wahlentscheidungen bei der Übertragung in die Blockchain so zu verschlüsseln, dass ein Erpresser keine Möglichkeit hat, vom Opfer oder dem Computer des Opfers einen Schlüssel zur Entschlüsselung der Daten zu bekommen, um Kenntnis über die tatsächliche Wahlentscheidung der Wählerin zu erlangen – sei es mit oder ohne Kooperation der Wählerin.

### Untersuchung verschiedener Arten von Blockchain-Netzwerken auf ihre Eignung
Welche Features muss eine geeignete Blockchainlösung bieten, um alle Anforderungen für eine politische Wahl zu erfüllen:
- Assets bzw. Colored Coins?
- Smart Contract (SC)
- Anonymisierung

#### Vergleich Blockchaineigenschaften

|              |  Bitcoin  | Ethereum | Multichain   | Secret | Avalanche |
|--------------|-----------|----------|--------------|--------|-----------|
| Anonymität   |     -     |    -     | -            |  ja    |   -       |
| SC           |     -     |   ja     | Smart Filter |  ja    |  ja       |

## Entwicklung von Prototypen

Für das BVS werden verschiedene Applikationen benötigt, die jeweils die Funktionalitäten für die jeweiligen Rollen bei einer Wahl abdecken. Als erster Prototyp (V1) wird ein Web3-basiertes Frontend entwickelt, mit der die Funktionalitäten für die Rolle Wähler/-in getestet werden kann. Als Basis dient dabei eine Node.js (Javascript) Laufzeit-Umgebung und als Backend das Testnet von SUI, einem Blockchain-Projekt, das wie Ethereum dApps (Verteilte Anwendungen) und SmartContracts unterstützt.

## Installation der Wahl-Applikation für Wählerinnen

### Prerequitsites
- NodeJS >= 10.16 and npm >= 5.6 installed.
- sui wALLET extension added to the browser.

#### Nodejs
#### SUI Wallet
