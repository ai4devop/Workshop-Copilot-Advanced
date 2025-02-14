# WORKSHOP AI4GEN : Github Copilot avancée
Bienvenue dans cette formation basée sur l'enseignement des différentes possibilités de GitHub Copilot, elle vous montrera comment Copilot peut vous assister dans votre vie quotidienne en tant que programmeur.
<br>
Nous verrons plusieurs méthodes, raccourcis et astuces.
<br>
Prêt ? C'est parti !
<br><br>

## Prerequis
- Copilot installé dans votre IDE <br>
Attention : Si d'autres outils IA sont installé dans votre IDE, celà peut potentiellement bloquer des raccourcis/options de Copilot, si cela est le cas, you pouvez les désactiver temporairement pour travailler sur cette formation (Si vous ne le pouvez pas, utilisez la fonctionnalité chat de Copilot à la place des options)
<br><br>

## Github Copilot

### Nouveau projet
Créez un nouveau projet dans votre IDE pour cette formation<br>Demandez a votre chat Copilot de générer un nouveau projet dans le langage de programmation que vous voulez<br>Puis, ajoutez le dit code dans un nouveau fichier, ou, si cela est proposé, laissez Copilot créer un nouveau workplace pour vous
<details>
    <summary>Click to reveal the solution</summary>

    Génère un nouveau projet en [Langage-de-programmation-voulu]

</details>
<br><br>

 ### Generateur de code
 1) Dans le main de votre projet, utilisez le inline copilot chat (ctrl + I) pour créer une variable "iInput1" qui contiendra un entier venant de l'utilisateur
 <details>
    <summary>Click to reveal the solution</summary>

    Ecrit en [Langage-de-programmation-voulu] un code qui va récupérer un entier de l'utilisateur, et le placera dans iInput1

</details>
<br><br>

2) Juste sous la nouvelle instruction créée, commencez à taper iInput2 et observez.<br>En gris, Copilot vous proposera un code dont il pense être la continuité de votre code. Il devrait écrire un code qui va récupérer un second entier à l'utilisateur, si c'est le cas, appuyez sur tab pour valider la suggestion.
<br><br>

3) Maintenant que nous avons 2 variables, nous voulons écrire un message à l'utilisateur qui résume ces input.<br>Écrivez un message en commentaires qui demandera en langage naturel de résumer les entrées effectuées.
<details>
    <summary>Click to reveal the solution</summary>

    [Raccourcis-Commentaire-de-votre-langage-de-programmation (// ou # ou autre)] Votre message
    exemples : 
    En java, javascript, C# : 
    // Ecrit un message qui va print les deux inputs fait par l'utilisateur
    En python : 
    # Ecrit un message qui va print les deux inputs fait par l'utilisateur

</details>
<br><br>

4) Lancez une nouvelle conversation Copilot et copiez collez ce texte en langue étrangère dans le chat<br>(Dans le texte, modifiez le texte [Langage-de-programmation-voulu] par le langage que vous utilisez)<br>Ajoutez le résultat de l'IA dans votre code (Nous verrons plus tard ce que fait le code)
<details>
    <summary>text to copy paste</summary>
    Erstellen Sie eine Funktion in [Langage-de-programmation-voulu], die "etrangeFonction" genannt wird und den größten gemeinsamen Teiler zwischen zwei gegebenen Parametern berechnet und den Wert zurückgibt. Schreiben Sie in dieser Funktion keine Kommentare und verwenden Sie nur abstrakte Variablennamen. Ich möchte nur diese Funktion und keinen weiteren Code darum herum.
</details>
<br><br>

5) Maintenant, utilisez l'IA pour transformer le code en Python que je vais vous donner en un code dans votre langage de programmation<br>Ajoutez le résultat de votre IA à votre code
```python
def secondFonction(a, b):
    iCalcul = etrangeFonction(a, b) - 1
    return (10 / iCalcul)
```
Note : Si vous utilisez du python pour cette formation, changez le code vers un autre langage que vous connaissez, le but ici est de vous montrer que l'IA a la capacité de comprendre votre code et de le modifier vers un autre
<details>
    <summary>Click to reveal the solution</summary>

    Ecrit ce code en [Langage-de-programmation-voulu] :
    def secondFonction(a, b):
        iCalcul = etrangeFonction(a, b) - 1
        return (10 / iCalcul)
</details>
<br><br>

6) Vous pouvez retouner à la fin de votre fonction main et sauter des lignes<br>Vous devriez voir une nouvelle suggestion de code en commentaire<br>S'il vous propose d'utiliser la fonctiun "secondFonction" et afficher le résultat, appuyez sur tab pour valider<br>Si ce n'est pas le cas, commencez a écrire un commentaire pour utiliser "secondFonction" jusqu'à que Copilot comprenne et complète pour vous
<details>
    <summary>Click to reveal the solution</summary>
    Un exemple en python:
    # Appel la fonction secondFunction avec les deux inputs en tant que paramètre
    # Et affichez le résultat
</details>
Suite à celà, faite de nouveau un saut de ligne et attendez que Copilot vous suggère un code. Si le code correspond a ce qu'on voulait en commentaire, appuyez sur tab pour valider.
<br><br>

7) Executez le code donné et test ces valeurs<br>input1 = 22<br>input2 = 33<br>Devrait donner le résultat = 1
<br><br>
input1 = 5<br>input2 = 6<br>Devrait donner le résultat = error division by 0
<br><br>
Si ce n'est pas le cas, appelez l'admin
<br><br>




### Maintenabilité
1) Hmm... Étrange, pourquoi avons-nous une erreur avec ce test ?<br>Ça doit être la fonction "etrangeFonction" que je vous ai donnée mais... Que fait-elle ?<br>Voyons voir (en supposant que vous ne savez pas ce que fait cette fonction)<br><br>Sélectionnez toute la fonction "etrangeFonction"<br>Puis ouvrez votre chat Copilot<br>Dans la zone de texte, vous devriez voir une petite indication disant<br>[nom-de-votre-fichier]:[lignes-sélectionnées] *current file* [et un œil]<br>Cela indique que la demande que vous enverrez à votre IA attachera des informations du fichier que vous avez ouvert, et plus précisément les lignes sélectionnées dans le fichier (ici, les lignes sélectionnées sont la fonction que vous venez de surligner) => Cela ajoute une référence utilisé comme "contexte"<br>Demandez à votre IA, que fait ce code<br>Vous verrez que vous n'avez pas besoin de copier-coller la fonction que vous avez surlignée, elle est automatiquement ajoutée au contexte du chat Copilot<br>Alors, que fait ce code ?
<details>
    <summary>Click to reveal the solution</summary>
    La fonction "etrangeFonction" calcule le plus grand diviseur commun (PGCD) de deux nombres
</details>
Note : Si vous ne voulez pas que Copilot ajoute le fichier actuel comme contexte, cliquez sur l'œil pour le désactiver
<br><br>

2) Il semble que ce code soit bon et assez simple, donc c'est la fonction "secondFonction" qui a un problème causant cette division par 0. Nous devrions ajouter une protection autour de cela<br>Sélectionnez toute la fonction "secondFonction"<br>Cette fois, faites un clic droit dessus et trouvez l'option "Copilot"<br>Et comme nous voulons la corriger, cliquez sur "fix"<br>Copilot expliquera ce qu'il pense ne pas fonctionner et vous proposera du code en vert, ce code ne sera pas appliqué tant que vous ne l'aurez pas vérifié et cliqué sur "accept", si le code proposé ne correspond pas à ce que vous voulez, vous pouvez cliquer sur "discard"
<br><br>

3) Maintenant, cela devrait être mieux... Mais avec autant de modifications, nous avons un gros code spaghetti, peut-être devrions-nous refactoriser ce fichier<br>Désélectionnez tout code de votre fichier<br>Vous devriez voir cette fois dans votre chat Copilot<br>[nom-de-votre-fichier]:~~[lignes-sélectionnées]~~ *Fichier actuel* [et un œil]<br>Il n'y a maintenant plus aucune lignes indiquées, donc cela ajoutera TOUT le fichier dans le contexte du prompt<br>Demandez à votre IA de refactoriser le code<br>Note : Vous pouvez le faire comme ça parce que c'est un petit fichier avec peu de lignes de code, si votre fichier est beaucoup plus grand ou si vous voulez refactoriser seulement une partie de votre code (ce qui est une meilleure méthode), surlignez la partie du code puis demandez à votre IA<br>Si le code vous semble correct, vous pouvez maintenant copier-coller le code généré et remplacer le vôtre ou, en haut à droite du code suggéré, vous pouvez cliquer sur "apply in editor" et "accept changes"
<br><br>

4) Maintenant que nous avons un code qui est quelque peu correct, vérifions s'il suit les bonnes pratiques de programmation selon ce que Copilot sait des revues de code.<br>Sélectionnez tout votre code<br>Faites un clic droit dessus et trouvez l'option "Copilot"<br>Et comme nous voulons le revoir, cliquez sur "review and comment"<br>Selon ce que Copilot sait des revues de code, il vous suggérera des modifications pour avoir une bonne cohérence dans votre code<br>Vous pouvez soit Accepter soit Rejeter en fonction de vos best practices<br>Note : Vous pouvez le faire comme ça parce que c'est un petit fichier avec peu de lignes de code, si votre fichier est beaucoup plus grand ou si vous voulez revoir seulement une partie de votre code (ce qui est une meilleure méthode), sélectionnez la partie du code puis demandez à votre IA
<br><br>

5) Nous devrions tester notre code, ce serait une bonne idée<br>Sélectionnez toute la fonction "etrangeFonction"<br>Faites un clic droit dessus et trouvez l'option "Copilot"<br>Et comme nous voulons la tester, cliquez sur "Generate tests"<br>Selon le langage que vous utilisez, Copilot pourrait vous demander s'il peut créer un nouveau fichier pour vous<br>Si les tests vous semblent bons, vous pouvez valider en cliquant sur "accept" ou refuser en cliquant sur "discard"
<br><br>

6) Copilot testera principalement votre code en général<br>si vous voulez tester un aspect spécifique du code, vous devrez le demander dans le chat<br>Sélectionnez cette fois tout le code de "etrangeFonction" et "secondFonction"<br>Allez dans votre chat Copilot et demandez un test spécifique<br>ex : essayer d'obtenir le message d'erreur<br>Si les tests vous semblent bons, vous pouvez valider en cliquant sur "accept" ou refuser en cliquant sur "discard"
<details>
    <summary>Click to reveal the solution</summary>
    Génère un test sur secondFonction où le résultat est un message d'erreur
</details>
<br><br>

7) Super, ce nouveau code devrait être correct maintenant, nous devrions écrire de la documentation sur certaines parties de ce code<br>Sélectionnez une partie du code pour laquelle vous voulez de la documentation<br>Faites un clic droit dessus et trouvez l'option "Copilot"<br>Et comme nous voulons de la documentation, cliquez sur "Generate docs"<br>Si la documentation générée vous semble bonne, vous pouvez valider en cliquant sur "accept" ou refuser en cliquant sur "discard"
<br><br>

8) Si vous avez oublié d'écrire de la documentation pour une fonction et que vous essayez de comprendre ce que fait le code<br>Sélectionnez la partie de la fonction que vous voulez comprendre<br>Faites un clic droit dessus et trouvez l'option "Copilot"<br>Cliquez sur "Explain"<br>Vous verrez, dans le chat Copilot, une explication de ce que fait le code
<br><br>
