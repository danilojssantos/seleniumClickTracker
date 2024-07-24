# seleniumClickTracker


Este projeto demonstra o uso do Selenium para automatizar a interação com um elemento de uma página web. O script abre uma página específica, clica em um link várias vezes, e exibe o texto de um elemento `<p>` após cada clique.

## Pré-requisitos

- Python 3.x
- Selenium
- Webdriver para o navegador que você deseja utilizar (neste exemplo, estamos usando o Chrome)

## Instalação

1. Clone o repositório:
    ```bash
    git clone https://github.com/seu-usuario/selenium-click-tracker.git
    cd selenium-click-tracker
    ```

2. Instale os pacotes necessários:
    ```bash
    pip install selenium
    ```

3. Baixe e instale o WebDriver para o navegador desejado (Chrome, neste exemplo). Adicione o WebDriver ao seu PATH.

## Uso

1. Abra o navegador e navegue para a URL especificada.
2. O script clicará no link 10 vezes e exibirá o texto do último elemento `<p>` após cada clique.
3. Verifique os valores no console para confirmar se o texto do `<p>` corresponde ao número do clique.

### Exemplo de Uso

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from time import sleep

url = 'https://curso-python-selenium.netlify.app/aula_03.html'

# Abre o navegador
navegador = webdriver.Chrome()

# Abre a URL
navegador.get(url)
#trava o projeto por 3s
sleep(3)

# Busca o elemento no HTML
a = navegador.find_element(By.TAG_NAME, 'a')

for click in range(1, 11):
  a.click()  
  ps = navegador.find_elements(By.TAG_NAME,'p') 
  print(f'Valor do ultimo p: {ps[click].text} valor do click: {click}')
  print(f'Os valors são iguais {ps[click].text == str(click)}')

# Fecha o navegador
navegador.quit()
```

## Contribuição
Se você quiser contribuir com este projeto, sinta-se à vontade para abrir um pull request ou relatar problemas na seção de Issues.


## Licença
Este projeto está licenciado sob a licença MIT. Veja o arquivo LICENSE para mais
