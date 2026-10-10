# Disner Finances — Organizador de Dados para Declaração do Imposto de Renda

> Projeto desenvolvido no desafio **Santander 2026 — DIO**, utilizando Microsoft Excel para reunir, organizar e facilitar o preenchimento de informações que podem ser necessárias na preparação da declaração do Imposto de Renda.

![Excel](https://img.shields.io/badge/Microsoft%20Excel-365-217346?logo=microsoftexcel&logoColor=white)
![Projeto](https://img.shields.io/badge/Projeto-Desafio%20DIO-EC1C24)
![Status](https://img.shields.io/badge/Status-Acadêmico%20%7C%20Em%20desenvolvimento-blue)

## Visão geral

O **Disner Finances — Organizador de Dados para Declaração do Imposto de Renda** é uma ferramenta construída no Excel com foco em centralizar informações pessoais, informes bancários e registros de rendimentos em uma interface organizada e de navegação simples.

A proposta é reduzir a dispersão de informações que costumam ser consultadas durante a preparação da declaração anual, permitindo que o usuário registre os dados em áreas específicas da pasta de trabalho. A interface utiliza botões de navegação, listas de opções e uma identidade visual própria.

O projeto é um **organizador de informações**: não substitui o programa oficial da Receita Federal, não transmite declarações e não determina, por si só, quais valores são tributáveis ou dedutíveis.

## Objetivos do projeto

- Aplicar conhecimentos de Excel em uma solução prática.
- Centralizar informações pessoais e dados financeiros em uma única pasta de trabalho.
- Estruturar campos para facilitar o preenchimento e a consulta.
- Usar validação de dados para padronizar determinadas entradas.
- Criar uma navegação visual entre as seções da planilha.
- Documentar o projeto de maneira clara e reproduzível no GitHub.
- Demonstrar organização, atenção à experiência de uso e aplicação prática dos conteúdos estudados.

## Funcionalidades identificadas

| Área | Finalidade | Recursos observados |
|---|---|---|
| **Titular** | Reunir dados cadastrais da pessoa física | Campos de identificação e contato; opções de SIM/NÃO para determinadas perguntas; link de e-mail; botão de navegação |
| **Informes** | Registrar informações de rendimentos bancários | Três blocos de bancos, campo de valor atual, campo para referência de anexo e cálculo do total |
| **Notas** | Registrar entradas de rendimentos mês a mês | Tabela com data, categoria e valor; categorias predefinidas; espaço para vários lançamentos |
| **Tabela de apoio** | Apoiar a seleção de instituições financeiras | Lista de bancos utilizada como referência para opções de preenchimento |

A pasta de trabalho contém quatro planilhas: `TÍTULAR`, `INFORMES`, `NOTAS` e `Tbl_Apoio`. A planilha `Tbl_Apoio` está oculta na configuração examinada e contém uma lista de instituições financeiras.

## Como a planilha está organizada

### 1. Titular

Esta seção concentra os dados cadastrais informados pelo usuário.

| Campo | Para que serve |
|---|---|
| Nome | Identifica o titular dos dados |
| CPF | Registra o Cadastro de Pessoas Físicas |
| Nascimento | Registra a data de nascimento |
| Título de eleitor | Campo destinado ao número do título eleitoral |
| Cônjuge | Registra a resposta indicada pelo usuário sobre cônjuge |
| Rua | Armazena o endereço informado |
| Rua abreviada | Permite guardar uma forma abreviada do endereço |
| CEP | Registra o código postal |
| Telefone e celular | Reúnem contatos telefônicos |
| E-mail | Armazena o e-mail e permite acionar um link de mensagem quando configurado |
| Houve alterações da entrega anterior | Campo de resposta SIM/NÃO |
| Dependente cônjuge | Campo de resposta SIM/NÃO, conforme o rótulo existente na planilha |
| Residente do exterior | Campo de resposta SIM/NÃO |

**Validação observada:** os campos de resposta nas células `D16:D18` utilizam uma lista com as opções `SIM` e `NÃO`. Isso reduz variações de digitação nesses campos, mas não verifica se a resposta informada está correta do ponto de vista fiscal.

A planilha também apresenta um botão visual de avanço para a próxima seção e um link para o perfil do autor no LinkedIn.

### 2. Informes de rendimentos bancários

Esta seção permite registrar informações de até três instituições financeiras. Cada bloco contém:

- **Banco:** instituição relacionada ao informe.
- **Valor atual:** valor informado pelo usuário para aquela instituição.
- **Anexo:** campo destinado a indicar ou referenciar um documento de apoio.

O campo **Total** consolida os três valores registrados. Na versão analisada, a célula `D5` utiliza:

```excel
=SUM(D9,D14,D19)
```

A fórmula soma os valores das células correspondentes aos três blocos bancários. Em instalações do Excel configuradas em português, o nome da função e o separador de argumentos podem aparecer localizados, conforme o idioma e as configurações do aplicativo.

**Importante:** o total representa a soma dos valores preenchidos nesses campos. Ele não deve ser interpretado automaticamente como saldo tributável, patrimônio fiscal declarado ou valor final de imposto.

Os campos de banco apresentam opções relacionadas a instituições financeiras. A pasta de trabalho também possui uma planilha de apoio com nomes de bancos. Como listas e controles visuais podem depender de recursos específicos do Excel, recomenda-se testar a interação no aplicativo utilizado para editar o arquivo.

### 3. Notas bancárias ou extratos de holerites

Esta área foi organizada para registrar entradas de rendimentos mês a mês. A tabela apresenta três colunas:

- **Data:** dia relacionado ao recebimento ou lançamento.
- **Categoria:** tipo de entrada registrado.
- **Valor:** quantia correspondente ao lançamento.

A tabela do Excel identificada como `tbl_Entradas` ocupa a área de registros e possui espaço preparado para vários lançamentos. A validação de dados aplicada à coluna de categoria oferece as opções:

- `HOLERITE`
- `CNPJ`
- `FREELANCE`
- `OUTRO(A)`

A lista ajuda a manter categorias consistentes. Ela não classifica automaticamente a natureza tributária do rendimento nem substitui a conferência dos documentos originais.

### 4. Tabela de apoio

A planilha `Tbl_Apoio` está oculta e contém uma relação de instituições financeiras. Esse tipo de área auxiliar pode servir de origem para listas suspensas e ajuda a manter as opções centralizadas.

A lista identificada inclui instituições como Banco do Brasil, Caixa Econômica Federal, Banco Santander, Itaú Unibanco, Nubank, Banco Inter e outras. A presença de uma instituição nessa lista não confirma que todos os seus códigos ou nomes estejam atualizados; recomenda-se validar a lista antes de usar o arquivo em um processo real.

## Navegação e experiência de uso

A interface apresenta uma barra lateral com a identidade visual **Disner Finances** e botões para acessar as áreas **Titular**, **Informes** e **Notas**. Também há botões visuais de navegação, como **Próximo** e **Anterior**, que procuram tornar o fluxo de preenchimento semelhante ao de um formulário multipágina.

A navegação e os elementos visuais foram observados nas capturas de tela fornecidas. A inspeção programática do arquivo confirma os rótulos e os links associados às células, mas bibliotecas de leitura de arquivos Excel podem não expor integralmente todos os objetos gráficos e controles interativos. Por isso, o funcionamento de cada botão deve ser validado diretamente no Excel antes da publicação como funcionalidade garantida.

## Recursos técnicos utilizados

- **Microsoft Excel:** estrutura principal da ferramenta.
- **Formatação de células:** separação visual de títulos, rótulos, campos e áreas de preenchimento.
- **Validação de dados:** listas predefinidas para respostas e categorias.
- **Tabela do Excel:** organização dos lançamentos de rendimentos na área `NOTAS`.
- **Fórmula de soma:** consolidação dos valores registrados nos três blocos bancários.
- **Links:** acesso por e-mail e link para o perfil do autor no LinkedIn.
- **Planilha auxiliar oculta:** armazenamento de uma lista de instituições financeiras.
- **Navegação visual:** botões e elementos de interface entre seções, conforme apresentado nas capturas fornecidas.

A documentação não pressupõe o uso de VBA, macros, Power Query, conexões externas ou automações por código, pois esses recursos não foram confirmados na análise realizada.

## Como utilizar

1. Baixe o arquivo Excel do repositório.
2. Abra-o no Microsoft Excel e habilite a edição, caso seja solicitado.
3. Revise a seção **Titular** e substitua os dados de exemplo por informações próprias.
4. Preencha os valores e as referências de documentos na seção **Informes**.
5. Registre os recebimentos na seção **Notas**, informando data, categoria e valor.
6. Confira os totais calculados e compare os registros com os documentos de origem.
7. Salve uma cópia privada e mantenha os comprovantes originais organizados.
8. Antes de utilizar os dados para preparar uma declaração real, confira as regras e orientações oficiais aplicáveis ao ano-calendário correspondente.

Os nomes de campos refletem a estrutura atual da planilha. A necessidade de cada informação deve ser confirmada de acordo com as instruções oficiais vigentes da Receita Federal.

## Privacidade e segurança dos dados

Este projeto pode conter dados pessoais e financeiros. **Não publique uma versão preenchida com informações reais em um repositório público.**

Antes de enviar o arquivo ao GitHub:

- Substitua ou remova CPF, endereço, data de nascimento, telefones, e-mail e outros dados pessoais.
- Remova valores financeiros reais e referências a documentos privados.
- Verifique também as capturas de tela: elas podem revelar informações mesmo quando o arquivo Excel foi sanitizado.
- Não inclua comprovantes, informes bancários, holerites ou anexos com dados pessoais.
- Mantenha uma cópia privada e protegida para uso próprio.

Os dados visíveis na versão examinada parecem incluir valores de demonstração e dados de teste, mas isso não garante que todas as informações sejam fictícias. Faça uma revisão manual antes de compartilhar.

## Limitações e considerações

- A ferramenta organiza dados; não constitui uma declaração oficial de Imposto de Renda.
- Não foi identificado cálculo automático do imposto devido, classificação fiscal completa de rendimentos ou transmissão de dados à Receita Federal.
- Os campos e categorias disponíveis podem não abranger todos os documentos e tipos de rendimento de uma pessoa.
- A soma dos valores bancários não determina, por si só, como esses valores devem ser declarados.
- As listas suspensas padronizam entradas, mas não validam a exatidão nem a pertinência fiscal das informações.
- A aparência e a navegação devem ser testadas na versão do Excel utilizada pelo usuário.
- A documentação não substitui a conferência dos informes originais, das regras oficiais ou a orientação de profissional habilitado quando necessária.

## Possíveis melhorias futuras

As sugestões abaixo não devem ser entendidas como funcionalidades já implementadas:

- Expandir a área de informes para permitir mais instituições sem duplicar blocos manualmente.
- Incluir campos de referência para o ano-calendário e a data de atualização dos dados.
- Adicionar verificações de preenchimento e avisos para campos obrigatórios, se definidos pelo escopo.
- Criar uma área de conferência que identifique campos vazios e possíveis duplicidades.
- Melhorar a rastreabilidade dos documentos por meio de identificadores ou referências locais seguras.
- Incluir instruções de uso dentro da própria pasta de trabalho.
- Criar uma versão de demonstração com dados inteiramente fictícios.
- Testar formalmente os botões e controles em diferentes versões do Excel.

## Estrutura sugerida do repositório

```text
disner-finances-organizador-ir/
├── README.md
├── Desafio do Santander 2026 - DIO - Pt 2.xlsx
└── images/
    ├── titular.png
    ├── informes-bancarios.png
    └── notas-e-holerites.png
```

Adicione a pasta `images/` somente depois de revisar e sanitizar cada captura. Use imagens que demonstrem a interface sem expor informações pessoais ou financeiras. Os nomes acima são sugestões de organização.

## Contexto do desafio

O projeto foi elaborado no contexto do **Desafio Santander 2026 — DIO**, cuja proposta é aplicar os conhecimentos do treinamento em uma ferramenta Excel, documentar o processo e compartilhar a documentação técnica em um repositório público no GitHub.

A entrega do README também demonstra práticas de organização de projeto, comunicação técnica e uso do Markdown para documentar uma solução.

## Referências

- [Desafio Santander 2026 — DIO](https://web.dio.me/)
- [Documentação oficial do GitHub](https://docs.github.com/)
- [Sintaxe básica de formatação Markdown no GitHub](https://docs.github.com/pt/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [Receita Federal — Meu Imposto de Renda](https://www.gov.br/receitafederal/pt-br/assuntos/meu-imposto-de-renda)

Consulte sempre as orientações oficiais referentes ao exercício e ao ano-calendário aplicáveis. Regras fiscais podem mudar.

## Autor

**Carlos Eduardo Moreira Disner**

Projeto desenvolvido para fins de aprendizado e portfólio no contexto do treinamento Santander 2026 — DIO.

- [LinkedIn](https://www.linkedin.com/in/carlos-eduardo-moreira-disner-79077b2a6/)

---

> **Aviso:** este arquivo tem finalidade organizacional e educacional. Não constitui aconselhamento contábil, jurídico ou tributário e não garante que os dados reunidos sejam suficientes ou corretos para uma declaração fiscal.
