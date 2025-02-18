# 🚀 WORKSHOP AI4GEN : GitHub Copilot avancé

Bienvenue dans cette formation basée sur l'enseignement des différentes possibilités de GitHub Copilot. Elle vous montrera comment Copilot peut vous assister dans votre vie quotidienne en tant que programmeur.  
Nous verrons plusieurs méthodes, raccourcis et astuces.

Prêt ? C'est parti ! 🎉

## Prérequis
- Copilot installé dans votre IDE ⚙️

**Attention** : Si d'autres outils IA sont installés dans votre IDE, cela peut potentiellement bloquer des raccourcis/options de Copilot. Si cela est le cas, vous pouvez les désactiver temporairement pour travailler sur cette formation. Si vous ne le pouvez pas, utilisez la fonctionnalité chat de Copilot à la place des options.

## GitHub Copilot

### 🗂 Nouveau projet
1. Créez un nouveau projet dans votre IDE pour cette formation.  
2. Demandez à votre chat Copilot de générer un nouveau projet dans le langage de programmation que vous voulez.  
3. Ajoutez le code dans un nouveau fichier, ou, si cela est proposé, laissez Copilot créer un nouveau workspace pour vous.

<details>
  <summary>Cliquez ici pour voir la solution</summary>
    <pre>Génère un nouveau projet en [Langage-de-programmation-voulu]</pre>
</details>

### ⚛️ Générateur de code
1. Dans le `main` de votre projet, utilisez le inline Copilot chat (`Ctrl + I`') pour créer une variable `iInput1` qui contiendra un entier venant de l'utilisateur.

      <details>
        <summary>Cliquez ici pour voir la solution</summary>
   
        Écrit en [Langage-de-programmation-voulu] un code qui va récupérer un entier de l'utilisateur, et le placera dans `iInput1`.
      </details>
      <br>

2. Juste sous la nouvelle instruction créée, commencez à taper `iInput2` et observez. En gris, Copilot vous proposera un code dont il pense être la continuité de votre code. Il devrait écrire un code qui va récupérer un second entier à l'utilisateur. Si c'est le cas, appuyez sur `Tab` pour valider la suggestion.

3. Maintenant que nous avons 2 variables, nous voulons écrire un message à l'utilisateur qui résume ces inputs. Écrivez un message en commentaires qui demandera en langage naturel de résumer les entrées effectuées.

    <details>
        <summary>Click to reveal the solution</summary>

        [Raccourcis-Commentaire-de-votre-langage-de-programmation (// ou # ou autre)] Votre message
        exemples : 
        En java, javascript, C# : 
        // Ecrit un message qui va print les deux inputs fait par l'utilisateur
        En python : 
        # Ecrit un message qui va print les deux inputs fait par l'utilisateur

    </details>

    <br>
4. Lancez une nouvelle conversation Copilot et copiez-collez ce texte en langue étrangère dans le chat. (Dans le texte, modifiez le texte [Langage-de-programmation-voulu] par le langage que vous utilisez). Ajoutez le résultat de l'IA dans votre code (Nous verrons plus tard ce que fait le code).

    <details>
      <summary>Texte à copier</summary>

        Erstellen Sie eine Funktion in [Langage-de-programmation-voulu], die "etrangeFonction" genannt wird und den größten gemeinsamen Teiler zwischen zwei gegebenen Parametern berechnet und den Wert zurückgibt. Schreiben Sie in dieser Funktion keine Kommentare und verwenden Sie nur abstrakte Variablennamen. Ich möchte nur diese Funktion und keinen weiteren Code darum herum.
    </details>
    <br>
5. Maintenant, utilisez l'IA pour transformer le code en Python que je vais vous donner en un code dans votre langage de programmation. Ajoutez le résultat de votre IA à votre code.

    ```python
    def secondFonction(a, b):
        iCalcul = etrangeFonction(a, b) - 1
        return (10 / iCalcul)
    ```

    **Note** : Si vous utilisez du Python pour cette formation, changez le code vers un autre langage que vous connaissez. Le but ici est de vous montrer que l'IA a la capacité de comprendre votre code et de le modifier vers un autre.

    <details>
        <summary>Cliquez ici pour voir la solution</summary>
        
       Ecrit ce code en [Langage-de-programmation-voulu] :
       def secondFonction(a, b):
           iCalcul = etrangeFonction(a, b) - 1
           return (10 / iCalcul)
    </details>
  <br>

6. Vous pouvez retourner à la fin de votre fonction `main` et sauter des lignes. Vous devriez voir une nouvelle suggestion de code en commentaire. S'il vous propose d'utiliser la fonction `secondFonction` et d'afficher le résultat, appuyez sur `Tab` pour valider. Si ce n'est pas le cas, commencez à écrire un commentaire pour utiliser `secondFonction` jusqu'à ce que Copilot comprenne et complète pour vous.

    <details>
      <summary>Cliquez ici pour voir la solution</summary>
        
       Un exemple en Python :
       # Appelle la fonction secondFunction avec les deux inputs en tant que paramètre
       # Et affichez le résultat
    </details>
    <br>

    Suite à cela, faites de nouveau un saut de ligne et attendez que Copilot vous suggère un code. Si le code correspond à ce qu'on voulait en commentaire, appuyez sur `Tab` pour valider.
<br>

7. Exécutez le code donné et testez ces valeurs :  
   - `input1 = 22`  
     `input2 = 33`  
     Devrait donner le résultat = 1

   - `input1 = 5`  
     `input2 = 6`  
     Devrait donner le résultat = error division by 0  

   Si ce n'est pas le cas, appelez l'admin.

### 🛠️ Maintenabilité
1. Hmm... Étrange, pourquoi avons-nous une erreur avec ce test ? Ça doit être la fonction `etrangeFonction` que je vous ai donnée mais... Que fait-elle ? Voyons voir (en supposant que vous ne savez pas ce que fait cette fonction).  
   
    Sélectionnez toute la fonction `etrangeFonction`. Puis ouvrez votre chat Copilot. Dans la zone de texte, vous devriez voir une petite indication disant `[nom-de-votre-fichier]:[lignes-sélectionnées] *current file* [et un œil]`. Cela indique que la demande que vous enverrez à votre IA attachera des informations du fichier que vous avez ouvert, et plus précisément les lignes sélectionnées dans le fichier (ici, les lignes sélectionnées sont la fonction que vous venez de surligner) => Cela ajoute une référence utilisée comme "contexte".  
   Demandez à votre IA, que fait ce code. Vous verrez que vous n'avez pas besoin de copier-coller la fonction que vous avez surlignée, elle est automatiquement ajoutée au contexte du chat Copilot. Alors, que fait ce code ?

    <details>
      <summary>Cliquez ici pour voir la solution</summary>
      
        La fonction `etrangeFonction` calcule le plus grand diviseur commun (PGCD) de deux nombres.
      </details>
      <br>

    **Note** : Si vous ne voulez pas que Copilot ajoute le fichier actuel comme contexte, cliquez sur l'œil pour le désactiver.

2. Il semble que ce code soit bon et assez simple, donc c'est la fonction `secondFonction` qui a un problème causant cette division par 0. Nous devrions ajouter une protection autour de cela. Sélectionnez toute la fonction `secondFonction`. Cette fois, faites un clic droit dessus et trouvez l'option "Copilot". Et comme nous voulons la corriger, cliquez sur "fix". Copilot expliquera ce qu'il pense ne pas fonctionner et vous proposera du code en vert. Ce code ne sera pas appliqué tant que vous ne l'aurez pas vérifié et cliqué sur "accept". Si le code proposé ne correspond pas à ce que vous voulez, vous pouvez cliquer sur "discard".

3. Maintenant, cela devrait être mieux... Mais avec autant de modifications, nous avons un gros code spaghetti, peut-être devrions-nous refactoriser ce fichier. Désélectionnez tout code de votre fichier. Vous devriez voir cette fois dans votre chat Copilot `[nom-de-votre-fichier]:~~[lignes-sélectionnées]~~ *Fichier actuel* [et un œil]`. Il n'y a maintenant plus aucune ligne indiquée, donc cela ajoutera TOUT le fichier dans le contexte du prompt. Demandez à votre IA de refactoriser le code.  

    **Note** : Vous pouvez le faire comme ça parce que c'est un petit fichier avec peu de lignes de code. Si votre fichier est beaucoup plus grand ou si vous voulez refactoriser seulement une partie de votre code (ce qui est une meilleure méthode), surlignez la partie du code puis demandez à votre IA. Si le code vous semble correct, vous pouvez maintenant copier-coller le code généré et remplacer le vôtre ou, en haut à droite du code suggéré, vous pouvez cliquer sur "apply in editor" et "accept changes".


4. Maintenant que nous avons un code qui est quelque peu correct, vérifions s'il suit les bonnes pratiques de programmation selon ce que Copilot sait des revues de code.<br>Sélectionnez tout votre code<br>
Faites un clic droit dessus et trouvez l'option "Copilot"<br>
Et comme nous voulons le revoir, cliquez sur "review and comment"<br>
Selon ce que Copilot sait des revues de code, il vous suggérera des modifications pour avoir une bonne cohérence dans votre code<br>
Vous pouvez soit Accepter soit Rejeter en fonction de vos best practices<br>
**Note** : Vous pouvez le faire comme ça parce que c'est un petit fichier avec peu de lignes de code, si votre fichier est beaucoup plus grand ou si vous voulez revoir seulement une partie de votre code (ce qui est une meilleure méthode), sélectionnez la partie du code puis demandez à votre IA
    <br><br>
    
5. Nous devrions tester notre code, ce serait une bonne idée<br>
Sélectionnez toute la fonction `etrangeFonction`<br>
Faites un clic droit dessus et trouvez l'option `Copilot`<br>
Et comme nous voulons la tester, cliquez sur `Generate tests`<br>
Selon le langage que vous utilisez, Copilot pourrait vous demander s'il peut créer un nouveau fichier pour vous<br>
Si les tests vous semblent bons, vous pouvez valider en cliquant sur `accept` ou refuser en cliquant sur `discard`
    <br><br>
    
6. Copilot testera principalement votre code en général<br>si vous voulez tester un aspect spécifique du code, vous devrez le demander dans le chat<br>Sélectionnez cette fois tout le code de `etrangeFonction` et `secondFonction`<br>Allez dans votre chat Copilot et demandez un test spécifique<br>ex : essayer d'obtenir le message d'erreur<br>Si les tests vous semblent bons, vous pouvez valider en cliquant sur `accept` ou refuser en cliquant sur `discard`
    <details>
        <summary>Click to reveal the solution</summary>
        
        Génère un test sur secondFonction où le résultat est un message d'erreur
    </details>
    <br>

7. Super, ce nouveau code devrait être correct maintenant, nous devrions écrire de la documentation sur certaines parties de ce code<br>Sélectionnez une partie du code pour laquelle vous voulez de la documentation<br>Faites un clic droit dessus et trouvez l'option `Copilot`<br>Et comme nous voulons de la documentation, cliquez sur `Generate docs`<br>Si la documentation générée vous semble bonne, vous pouvez valider en cliquant sur `accept` ou refuser en cliquant sur `discard`
<br><br>

8. Si vous avez oublié d'écrire de la documentation pour une fonction et que vous essayez de comprendre ce que fait le code<br>Sélectionnez la partie de la fonction que vous voulez comprendre<br>Faites un clic droit dessus et trouvez l'option `Copilot`<br>
Cliquez sur `Explain`<br>
Vous verrez, dans le chat Copilot, une explication de ce que fait le code
<br><br>
