# WORKSHOP AI4GEN: GitHub Copilot Advanced

Welcome to this workshop on the different features of GitHub Copilot. It will show you how Copilot can assist you in your daily life as a developer.<br>You will discover various methods, shortcuts, and tips.<br>Ready? Let's go!  
<br><br>

## Prerequisites  
- GitHub Copilot installed and ready in your IDE.  
<br>  
**Warning:** If another AI tool is installed in your IDE, it might block some of Copilot's shortcuts/options. If so, you can temporarily disable the other tools to work with this workshop. If you prefer not to disable them, use Copilot Chat instead of the shortcuts we provide.  
<br><br>

## GitHub Copilot

### New Project  
Create a new project in your IDE for this workshop.<br>Ask Copilot Chat to generate a new project in the programming language of your choice.<br>
Copilot might prompt you to create a new workspace automatically. Alternatively, you can copy and paste the generated code into a new file.  

<details>  
    <summary>Click to reveal the solution</summary>  
    Generate a project in [Your-programming-language]  
</details>  

**Note:** You can remove the default "Hello, World!" code that has been generated.  
<br><br>

### Code Generation  

1) In the main file of your project, use inline Copilot Chat (`Ctrl + I`) to create a variable (`input1`) that prompts the user to enter an integer.  

<details>  
    <summary>Click to reveal the solution</summary>  
    Write in [Your-programming-language] a code snippet that takes an integer from the user and stores it in `input1`.  
</details>  
<br><br>

2) Right below the newly created instruction, start typing `input2` and observe what happens.  
Copilot will suggest an auto-completion in gray. It should generate another integer input request. If the suggestion is correct, press **Tab** to accept it.  
<br><br>

3) Now that we have two inputs, let's display a message summarizing the inputs to the user.  
Write a comment in natural language instructing the AI to summarize the inputs.  

<details>  
    <summary>Click to reveal the solution</summary>  
    [your-programming-language-comment-shortcut (// or # or others)] your message  
    **Examples:**  
    - In Java, JavaScript, C#:  
      ```  
      // Write a message that summarizes the two user inputs  
      ```  
    - In Python:  
      ```  
      # Write a message that summarizes the two user inputs  
      ```  
</details>  

**Note:** To keep the code cleaner, you can remove any previous generated messages if necessary.  
<br><br>

4) Open a new Copilot Chat and copy-paste the following text in French into the chat.  
(Replace `[your-programming-language]` with the language you are using.)  

<details>  
    <summary>French text to copy and paste</summary>  
    Créer une fonction en [your-programming-language] qui se nommera "etrangeFonction" et qui calculera le plus grand diviseur commun entre deux variables passées en paramètres, puis retournera la valeur. Dans cette fonction, n’écris aucun commentaire et utilise uniquement des noms de variables abstraits. Je veux seulement cette fonction, sans aucun autre code autour.  
</details>  
<br><br>

5) Now, use AI to translate the following code into your language.  
Add the AI-generated result to your code.  

```python  
def secondFonction(a, b):  
    iCalcul = etrangeFonction(a, b) - 1  
    return 10 / iCalcul  
```  

**Note:** If you're using Python, convert this code into another language you know. The goal here is to demonstrate that AI can understand and translate code between languages.  

<details>  
    <summary>Click to reveal the solution</summary>  
    Rewrite this code from Python to [your-programming-language]:  
    ```python  
    def secondFonction(a, b):  
        iCalcul = etrangeFonction(a, b) - 1  
        return 10 / iCalcul  
    ```  
</details>  
<br><br>

6) Now, go back to the end of your `main` function and insert a few blank lines.  
Copilot should suggest another comment.  
If it suggests calling `secondFonction` and printing the result, press **Tab** to accept it.  
If not, start writing a comment instructing the use of `secondFonction` until Copilot understands and completes it for you.  

**Example in Python:**  

<details>  
    <summary>Click to reveal the solution</summary>  
    ```python  
    # Call the second function with the two inputs as parameters  
    # and print the result  
    ```  
</details>  

After that, insert another blank line and wait for Copilot to suggest the code. If the suggested code matches the expected comment, press **Tab** to accept it.  
<br><br>

7) Run the generated code and test these values:  

```
input1 = 22  
input2 = 33  
Expected result = 1  
```

```
input1 = 5  
input2 = 6  
Expected result = Error: division by zero  
```

If the results are incorrect, specify it to the AI.  
<br><br>

### Maintainability  

1) Hmm... Strange. Why do we get an error in that test?  
The issue might come from the function `etrangeFonction`. But what exactly does it do?  

Highlight the entire `etrangeFonction` function.  
Then, open Copilot Chat.  

You should see an indication in the text box:  

```
[name-of-your-file]:[highlighted-lines] *Current file* [and an eye]
```

This means that Copilot will automatically use the selected code as context.  
Now, ask Copilot: **"What does this code do?"**  

<details>  
    <summary>Click to reveal the solution</summary>  
    The function `etrangeFonction` calculates the greatest common divisor (GCD) of two numbers.  
</details>  

**Note:** If you don’t want Copilot to use the current file as context, click on the eye icon to disable it.  
<br><br>

2) The function `etrangeFonction` looks fine, so the issue is likely in `secondFonction`.  
We should add some protection against division by zero.  

Highlight the entire `secondFonction`.  
Right-click on it, go to **Copilot**, and select **Fix**.  
Copilot will explain the issue and suggest a fix in green.  
If the suggested fix looks good, click **Accept**. Otherwise, click **Discard**.  
<br><br>

3) Now, the code works, but it looks messy. Let's refactor it.  

Unselect all code in your file.  
Then, ask Copilot to **Refactor** the entire file.  

**Note:** If your file is large, it’s better to refactor only specific sections by highlighting them before asking Copilot.  
<br><br>

4) Now that we have a cleaner code, let’s check if it follows good programming practices.  

Highlight the entire code.  
Right-click, go to **Copilot**, and select **Review and Comment**.  
Copilot will suggest modifications to improve code consistency.  
You can either accept or discard these changes.  
<br><br>

5) After all that, we might need to test our code, that would be great

Highlight a section of code you want to document.  
Right-click, go to **Copilot**, and select **Generate tests**.  
If the generated documentation looks good, click **Accept**, otherwise, click **Discard**.  
<br><br>

6) Copilot will make a general test of your code, if you want to do a specific test, you'll have to ask to Copilot chat

Highlight the entire `etrangeFonction` and `secondFonction`.  
Open new Copilot chat and ask to have a test on secondFonction that will be an error message.  
If the generated documentation looks good, add it to your test file  
<details>  
    <summary>Click to reveal the solution</summary>  
    Generate test on secondFonction where the result is an error
</details>  
<br><br>

7) Great! Now let’s document the code.  

Highlight a section of code you want to document.  
Right-click, go to **Copilot**, and select **Generate Docs**.  
If the generated documentation looks good, click **Accept**, otherwise, click **Discard**.  
<br><br>

8) If you need to understand a function, highlight it, right-click, go to **Copilot**, and select **Explain**.  
Copilot Chat will generate an explanation of what the function does.  
<br><br>
