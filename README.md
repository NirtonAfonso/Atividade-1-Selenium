# 🎯 Atividade Prática: Automação de Login com Selenium

## 📖 Apresentação da Atividade

Bem-vindo(a) à sua primeira atividade prática de automação de testes com Selenium e Java! 

Nesta atividade, você irá aplicar todo o conhecimento adquirido em aula para criar testes automatizados de um formulário de login simples. O objetivo é praticar os conceitos básicos de localização de elementos, interação com formulários e validação de resultados.

**Diferenciais desta atividade:**
- ✅ Você terá uma página web real para testar
- ✅ Aprenderá a documentar seus testes com screenshots
- ✅ Praticará diferentes cenários de teste
- ✅ Desenvolverá código organizado e comentado

---

## 🎓 Objetivos de Aprendizagem

Ao completar esta atividade, você será capaz de:

1. **Localizar elementos** na página usando IDs
2. **Preencher campos** de texto e senha
3. **Trabalhar com dropdowns** (elementos select)
4. **Clicar em botões** e acionar ações
5. **Verificar mensagens** exibidas na página
6. **Capturar screenshots** para documentar os testes
7. **Organizar código** com comentários claros

---

## 📋 Pré-requisitos

Antes de começar, certifique-se de que você tem:

- ✅ Java JDK 8 ou superior instalado
- ✅ Eclipse IDE configurado
- ✅ Projeto Maven criado conforme visto em aula
- ✅ Dependências do Selenium e WebDriverManager no pom.xml
- ✅ Página HTML fornecida salva em seu computador

---

## 🌐 Sobre a Página de Testes

Você receberá um arquivo HTML chamado `site-teste-simples.html` que simula um sistema de login básico. Esta página contém:

- **Campo de usuário** (id: `username`)
- **Campo de senha** (id: `password`)
- **Dropdown de perfil** (id: `perfil`) com 3 opções:
  - Administrador
  - Cliente
  - Convidado
- **Botão "Entrar"** (id: `btnLogin`)
- **Mensagem de sucesso** (id: `msgSuccess`)
- **Mensagem de erro** (id: `msgError`)

### 🔐 Credenciais de Teste

Para login bem-sucedido, use:
- **Usuário:** `admin`
- **Senha:** `123`
- **Perfil:** qualquer opção (menos "Selecione um perfil")

Qualquer outra combinação deve resultar em erro.

---

## 📁 Preparando o Ambiente

### Passo 1: Criar a pasta de trabalho

Crie uma pasta para organizar seus arquivos:
- **Windows:** `C:\selenium-atividade\`
- **Mac/Linux:** `/home/seu-usuario/selenium-atividade/`

### Passo 2: Salvar a página HTML

Salve o arquivo `site-teste-simples.html` (fornecido separadamente) dentro da pasta criada.

### Passo 3: Testar manualmente

Antes de automatizar, abra o arquivo HTML no navegador e teste manualmente:
1. Tente fazer login com `admin` e `123`
2. Tente com dados incorretos
3. Observe as mensagens que aparecem

### Passo 4: Criar estrutura no Eclipse

Ao criar seu projeto Maven adicione as seguintes informaçãoes do `groupoId`, `artifactId` e `version`:

```
<groupId>com.aula.selenium</groupId>
<artifactId>atividade1-selenium</artifactId>
<version>1.0-SNAPSHOT</version>
```

No seu projeto Maven, crie o pacote:
```
src/main/java/com/atividade/selenium/
```

Dentro deste pacote você criará suas classes de teste.

### Passo 5: Adicione as dependências no arquivo pom.xml do seu projeto Maven

No seu arquivo pom.xml adicione as seguintes dependencias antes de fechar a tag `<\project>`:
```
 <!-- Definindo versão do Java -->
    <properties>
        <maven.compiler.source>11</maven.compiler.source>
        <maven.compiler.target>11</maven.compiler.target>
    </properties>
    
    <!-- Bibliotecas necessárias -->
    <dependencies>
        <!-- Selenium WebDriver - biblioteca principal -->
        <dependency>
            <groupId>org.seleniumhq.selenium</groupId>
            <artifactId>selenium-java</artifactId>
            <version>4.14.0</version>
        </dependency>
        
        <!-- WebDriverManager - facilita configuração dos drivers -->
        <dependency>
            <groupId>io.github.bonigarcia</groupId>
            <artifactId>webdrivermanager</artifactId>
            <version>5.5.3</version>
        </dependency>
    </dependencies>
```


---

## 🎯 Desafios da Atividade

### ✅ Desafio 1: Login com Dados Válidos

**Objetivo:** Automatizar um login bem-sucedido e documentar com screenshot.

**O que você deve fazer:**

1. Criar a classe `Desafio1LoginValido.java`
2. Implementar um teste que:
   - Abre o navegador Chrome
   - Navega para a página `site-teste-simples.html`
   - Preenche o campo usuário com: `admin`
   - Preenche o campo senha com: `123`
   - Seleciona qualquer perfil no dropdown
   - Clica no botão "Entrar"
   - Verifica se a mensagem de sucesso aparece
   - Captura um screenshot
   - Imprime no console todas as ações realizadas

**Entrega esperada:**
- Arquivo: `Desafio1LoginValido.java`
- Screenshot: `desafio1-sucesso.png`

---

### ✅ Desafio 2: Login com Dados Inválidos

**Objetivo:** Testar que o sistema rejeita credenciais incorretas.

**O que você deve fazer:**

1. Criar a classe `Desafio2LoginInvalido.java`
2. Implementar um teste que:
   - Abre o navegador
   - Navega para a página
   - Preenche o campo usuário com dados incorretos (ex: `usuario_errado`)
   - Preenche o campo senha com dados incorretos (ex: `senha_errada`)
   - Seleciona um perfil qualquer
   - Clica no botão "Entrar"
   - Verifica se a mensagem de ERRO aparece
   - Captura screenshot do erro
   - Imprime no console o texto da mensagem de erro

**Entrega esperada:**
- Arquivo: `Desafio2LoginInvalido.java`
- Screenshot: `desafio2-erro.png`

---

### ✅ Desafio 3: Validação de Campos Vazios

**Objetivo:** Verificar que o sistema não permite login sem preencher os campos.

**O que você deve fazer:**

1. Criar a classe `Desafio3CamposVazios.java`
2. Implementar um teste que:
   - Abre o navegador
   - Navega para a página
   - **NÃO preenche nenhum campo**
   - Clica diretamente no botão "Entrar"
   - Verifica se a mensagem de erro aparece
   - Captura screenshot
   - Imprime no console que a validação funcionou

**Entrega esperada:**
- Arquivo: `Desafio3CamposVazios.java`
- Screenshot: `desafio3-campos-vazios.png`

---

### ✅ Desafio 4: Login Sem Selecionar Perfil

**Objetivo:** Testar validação quando o perfil não é selecionado.

**O que você deve fazer:**

1. Criar a classe `Desafio4SemPerfil.java`
2. Implementar um teste que:
   - Abre o navegador
   - Navega para a página
   - Preenche usuário: `admin`
   - Preenche senha: `123`
   - **NÃO seleciona nenhum perfil** (deixa no valor padrão)
   - Clica em "Entrar"
   - Verifica que o sistema exibe erro
   - Captura screenshot
   - Imprime confirmação no console

**Entrega esperada:**
- Arquivo: `Desafio4SemPerfil.java`
- Screenshot: `desafio4-sem-perfil.png`

---

## 🏆 Desafio BÔNUS

**Objetivo:** Criar uma bateria completa de testes com relatório.

**O que você deve fazer:**

1. Criar a classe `DesafioBonusRelatorio.java`
2. Implementar um programa que:
   - Executa automaticamente os 4 testes anteriores em sequência
   - Captura screenshot de cada teste
   - Conta quantos testes passaram e quantos falharam
   - Gera um relatório no console com estatísticas
   - Salva screenshots com timestamp para organização

**Entrega esperada:**
- Arquivo: `DesafioBonusRelatorio.java`
- Screenshots: 4 arquivos com timestamp

---

## 📚 Recursos e Dicas

### 🔍 Localizando elementos

Lembre-se da sintaxe básica:

```java
// Por ID (recomendado)
WebElement campo = driver.findElement(By.id("nome-do-id"));
```

### ⌨️ Preenchendo campos

```java
campo.clear();           // Limpa o campo
campo.sendKeys("texto"); // Digita o texto
```

### 🎯 Trabalhando com dropdowns

```java
import org.openqa.selenium.support.ui.Select;

WebElement dropdown = driver.findElement(By.id("perfil"));
Select select = new Select(dropdown);
select.selectByValue("admin");  // Por valor
// ou
select.selectByVisibleText("Administrador"); // Por texto visível
```

### 🖱️ Clicando em elementos

```java
elemento.click();
```

### ✅ Verificando se elemento está visível

```java
boolean estaVisivel = elemento.isDisplayed();
if (estaVisivel) {
    System.out.println("Elemento encontrado!");
}
```

### 📸 Capturando screenshot

```java
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.OutputType;
import java.io.File;
import java.nio.file.Files;
import java.nio.file.Paths;

TakesScreenshot screenshot = (TakesScreenshot) driver;
File arquivo = screenshot.getScreenshotAs(OutputType.FILE);
Files.copy(arquivo.toPath(), Paths.get("caminho/screenshot.png"));
```

### ⏱️ Aguardando (quando necessário)

```java
Thread.sleep(1000); // Aguarda 1 segundo (1000 milissegundos)
```

### 🧹 Sempre limpar recursos

```java
try {
    // Seu código aqui
} catch (Exception e) {
    System.out.println("Erro: " + e.getMessage());
} finally {
    driver.quit(); // SEMPRE fechar o navegador
}
```

---

## 📦 O que Entregar

### Estrutura de pastas esperada:

```
C:\selenium-atividade\
├── site-teste-simples.html
├── Desafio1LoginValido.java
├── Desafio2LoginInvalido.java
├── Desafio3CamposVazios.java
├── Desafio4SemPerfil.java
├── DesafioBonusRelatorio.java (se fez o bônus)
├── desafio1-sucesso.png
├── desafio2-erro.png
├── desafio3-campos-vazios.png
├── desafio4-sem-perfil.png
└── bonus-[testes com timestamp].png (se fez o bônus)
```

### Enviar via:
- Arquivo ZIP com todos os arquivos .java e screenshots
- Ou: Repositório Git com todo o código

---

## ✅ Checklist Final

Antes de entregar, verifique:

- [ ] Todos os 4 desafios obrigatórios foram concluídos
- [ ] Cada classe Java executa sem erros
- [ ] Todos os screenshots foram capturados
- [ ] Código está comentado explicando cada passo
- [ ] Imports necessários estão presentes
- [ ] Caminho do arquivo HTML está correto no código
- [ ] Try-catch-finally está implementado
- [ ] Console imprime mensagens informativas
- [ ] Screenshots salvos na pasta correta
- [ ] (Bônus) Bateria de testes e relatório funcionam

---

## ❓ Problemas Comuns e Soluções

### Problema: "NoSuchElementException"
**Causa:** ID do elemento está errado ou página não carregou  
**Solução:** Verifique os IDs no HTML e adicione um `Thread.sleep(1000)` após carregar a página

### Problema: Screenshot não salva
**Causa:** Pasta não existe ou caminho errado  
**Solução:** Certifique-se de que a pasta `C:\selenium-atividade\` existe

### Problema: Página não abre no navegador
**Causa:** Caminho do arquivo HTML incorreto  
**Solução:** Use caminho absoluto começando com `file:///`  
Exemplo Windows: `file:///C:/selenium-atividade/site-teste-simples.html`

### Problema: Dropdown não funciona
**Causa:** Esqueceu de usar a classe `Select`  
**Solução:** Importe `org.openqa.selenium.support.ui.Select` e use conforme exemplos

### Problema: Navegador não fecha
**Causa:** Código tem erro e não chega no `driver.quit()`  
**Solução:** Use bloco `finally` para garantir que sempre execute

---

## 🎯 Dicas para Obter Nota Máxima

1. **Organize seu código:** Use comentários explicando cada passo
2. **Nomeie variáveis claramente:** `campoUsuario` é melhor que `campo1`
3. **Valide sempre:** Verifique se elementos estão visíveis antes de interagir
4. **Documente com prints:** Use `System.out.println()` para explicar o que está acontecendo
5. **Capture screenshots:** São sua evidência de que o teste funcionou
6. **Teste antes de entregar:** Execute cada desafio pelo menos 2 vezes
7. **Faça o bônus:** Mostra que você dominou o conteúdo

---

## 📅 Prazo de Entrega

**Data limite:** [A ser definida pelo professor]

**Forma de entrega:** [A ser definida pelo professor]

---

## 💬 Dúvidas?

Se tiver dúvidas durante a atividade:
1. Revise o material da aula teórica
2. Consulte os exemplos práticos fornecidos
3. Teste sua página HTML manualmente primeiro
4. Procure o professor durante o horário de atendimento

---

## 🎓 Palavras Finais

Esta atividade é sua oportunidade de praticar o que aprendeu e construir confiança na automação de testes. Não tenha medo de errar - cada erro é uma oportunidade de aprendizado!

**Lembre-se:**
- Comece pelo mais simples (Desafio 1)
- Teste cada código antes de passar para o próximo
- Use os exemplos da aula como referência
- Organize seu código com comentários
- Capture screenshots de cada etapa

**Boa sorte e bons testes!** 🚀

---

## 📖 Referências Úteis

- Documentação oficial do Selenium: https://selenium.dev/documentation/
- Material da aula (PDF fornecido)
- Exemplos práticos da aula (arquivo .md fornecido)

---

*Atividade elaborada para a disciplina de Automação de Testes com Selenium e Java*
