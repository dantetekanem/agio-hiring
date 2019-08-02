# Teste Ágio - Desenvolvedor Junior Ruby/Ruby on Rails

## O que deverá ser feito?
Neste diretório você irá encontrar dois arquivos no diretório `support/`: `livro.csv` e `notas.txt`.
Você deverá atualizar o arquivo `processor.rb`, para que suporte consultar o `livro.csv` e `notas.txt`, e possa gerar um arquivo final chamado `resultado.txt`, contendo o `notas.txt` atualizado.

## Como funcionará a atualização dos dados?
O `Processor` irá iniciar consultando o arquivo notas.txt, e deverá executar as seguintes tarefas:
- Procurar quais linhas tem a primeira coluna como AB3, caso encontre, deverá capturar a chave fiscal (terceira coluna) da linha `AB1` antecedendo a linha AB3
- Com a chave fiscal, verificar no `livro.csv` a linha correta de acordo com a nota fiscal e capturar os dados dessa linha no livro.
- Gerar uma nova linha após o AB3, chamada AB5 com os dados atualizados no **formato AB5** proveniente dos dados capturados no `livro.csv` e da própria linha AB3.

### Formato AB5
- O formato AB5 vai constituir de 4 colunas, no formato `|COLUNA 1|COLUNA 2|COLUNA 3|COLUNA 4|COLUNA 5|`.
- Os dados devem estar formatados corretamente para:
1. Coluna 1: AB5
2. Coluna 2: Data do livro (baseada na chave nfe)
3. Coluna 3: Valor corrigido do livro (baseado na chave nfe), com duas casas decimais, ex: (8000 vira 8000.00)
4. Coluna 4: Quantidade relacionada (baseada na linha AB3, terceira coluna)
5. Coluna 5: Valor final (valor corrigido multiplicado pela quantidade), com duas casas decimais, ex: (8000 vira 8000.00)

### Detalhes
- Pode haver mais de um AB3 para cada bloco, o AB5 deverá vir após o AB3, se houver mais de um, deverá vir sempre após seu AB3 relativo.
- O arquivo final tem que ser válido e salvo no diretório `teste/` com o nome resultado.txt.
- Você deverá adicionar os testes (usando RSpec) testando o aplicativo como um todo.
- Para gerar o arquivo, o comando esperado será `ruby processor.rb`
- (opcional) Para gerar o arquivo, o comando esperado será `ruby processor.rb livro.csv notas.txt resultado.txt` (ou um formato parecido), passando na ordem o primeiro parâmetro como o livro, segundo como as notas e terceiro o arquivo que será salvo.
- Um arquivo chamado `resultado_esperado.txt` em `support/` possui o resultado final que deve ser gerado pelo aplicativo, utilize o como referência ou para comparar durante os testes.
- É permitido utilizar qualquer biblioteca (gem) disponível, incluindo banco de dados. De preferência, utilize o SQLite, mas pode usar PostgreSQL também (inclua detalhes de como instalar).
- O formato das datas no arquivo `resultado.txt` deve ser YYYY-MM-DD (ou em pt-br, AAAA-MM-DD, ex.: 2019-08-01).
- Quanto mais testes, melhor. O que aconteceria se não tivesse a data no livro.csv? Você ainda pode adicionar mais colunas nos arquivos de teste para melhorar o conteúdo.

### Como participar
- Você deverá fazer um fork deste repositório e trabalhar localmente.
- Dê preferência para os commits na ordem que for fazendo, bons commits e descritivos são ideais.
- Altere o arquivo `README.md` com detalhes de como rodar os testes e como gerar o arquivo, de acordo com o que você criou.
- Envie o seu repositório (público) para `fbrum@agiobr.com`, com o título `Desenvolvedor Ruby`, anexe no e-mail o seu currículo e não esqueça de enviar o link do seu repositório com o teste feito e funcional.