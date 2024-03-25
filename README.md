
# Excluir repositórios do GitHub de maneira automatizada

Faaaaaaaaaaaaala galera, tudo bem com vocês? Espero que sim!  
  
Venho aqui compartilhar com vocês um projeto que eu fiz recentemente, com o intuito de automatizar a exclusão de repositórios no GitHub! Quem costuma criar e deletar muitos repositórios no GitHub, sabe o quão repetitivo e chatinho é esse processo, e foi com o objetivo de acelerar esse processo que eu criei esse projeto! 😊

### Construção do projeto

De início, foram realizadas as importações para duas bibliotecas:
- `pyautogui`
- `pyperclip`  
Dessas bibliotecas, a `pyautogui` é a responsável por simular os movimentos de mouse e realizar os clicks nos botões. Eu diria que 90% do projeto só foi possível graças a essa biblioteca.  
  
Após as importações, foi utilizado a função `pyautogui.position()` para retornar a posição exata que o mouse está. "Mas a onde eu irei utilizar a posição do mouse?" Simples! Como citado anteriormente, iremos SIMULAR os movimentos e clicks do mouse nos botões, para assim deletar o repositório.  

("Seria possível fazer esse mesmo processo, mas sem usar a posição do mouse?" SIM! Se você utilizar o comando `pyautogui.hotkey("tab")`, ele iria se movimentar pela página utilizando o Tab, mas seria um processo bem mais demorado.)  
  
O próximo passo é armazenar em uma variável o nome do usuário e o nome do repositório que será excluido. Vamos armazenar na variável `user_repository`.

Após isso, basta criar uma nova aba utilizando o comando `pyautogui.hotkey("ctrl", "t")`, e essa mesma lógica será aplicada em todo o restante do código!

Nessa nova aba, para digitar o endereço exato do repositório, iremos utilizar as duas bibliotecas importadas. Primeiro digitamos `pyperclip.copy(f"www.github.com/{user_repository}")`. Esse código irá copiar o endereço exato do seu repositório, e após isso, digitamos `pyautogui.hotkey("ctrl", "v")` e `pyautogui.hotkey("enter")`.  

Feito isso, você já estará na página do seu repositório, e após isso, basta utilizar o comando `pyautogui.click()` e passar as coordenadas do mouse dentro dos parenteses.

Após isso, utilize o comando `pyautogui.scroll(-4096)` para rolar até o final da página.

Por fim, basta aplicar a mesma lógica em todo o restante do procedimento, e você conseguirá excluir o seu repositório! O código do projeto está totalmente comentado, indicando cada passo do projeto! 🚀  
