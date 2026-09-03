# Modelos de Licenças de Software

## MIT, Apache 2.0, GNU GPL e BSD

Neste material, nós vamos conhecer alguns dos modelos de licenças de software mais utilizados em projetos de desenvolvimento.

A proposta é apresentar cada licença de forma simples, mostrando:

1. O nome da licença.
2. Quando ela costuma ser utilizada.
3. Como preencher os campos principais.
4. O texto em inglês.
5. A tradução em português logo após o texto original.
6. Alguns cuidados importantes ao publicar a licença no GitHub.

> **Importante**
>
> As traduções apresentadas neste material possuem finalidade didática. Em um projeto real, principalmente quando houver necessidade jurídica ou comercial, devemos manter no arquivo `LICENSE` o texto oficial da licença escolhida.

---

# 1. Licença MIT

## 1.1 O que é a Licença MIT?

A Licença MIT é uma licença de software livre bastante permissiva.

Ela permite que outras pessoas possam usar, copiar, modificar, distribuir, publicar, sublicenciar e até vender cópias do software.

A principal exigência é manter o aviso de direitos autorais e o texto da licença.

É bastante utilizada em projetos de código aberto, bibliotecas, frameworks, projetos acadêmicos e projetos publicados no GitHub.

## 1.2 O que devemos alterar?

No modelo abaixo, devemos substituir:

```text
<YEAR>
```

pelo ano da publicação.

Exemplo:

```text
2026
```

Também devemos substituir:

```text
<COPYRIGHT HOLDER>
```

pelo nome da pessoa, empresa ou organização responsável pelos direitos autorais.

Exemplo:

```text
Éder Silva
```

## 1.3 Texto original em inglês

```text
MIT License

Copyright <YEAR> <COPYRIGHT HOLDER>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```

## 1.4 Tradução para o português

```text
Licença MIT

Copyright <ANO> <DETENTOR DOS DIREITOS AUTORAIS>

É concedida, por meio deste documento, permissão gratuita a qualquer pessoa
que obtenha uma cópia deste software e dos arquivos de documentação associados,
denominados neste texto como "Software", para utilizar o Software sem restrições,
incluindo, sem limitação, os direitos de usar, copiar, modificar, fundir,
publicar, distribuir, sublicenciar e/ou vender cópias do Software, bem como
permitir que as pessoas a quem o Software for fornecido façam o mesmo, sujeito
às seguintes condições:

O aviso de direitos autorais acima e este aviso de permissão devem ser incluídos
em todas as cópias ou partes substanciais do Software.

O SOFTWARE É FORNECIDO "NO ESTADO EM QUE SE ENCONTRA", SEM GARANTIA DE QUALQUER
TIPO, EXPRESSA OU IMPLÍCITA, INCLUINDO, MAS NÃO SE LIMITANDO, ÀS GARANTIAS DE
COMERCIABILIDADE, ADEQUAÇÃO A UMA FINALIDADE ESPECÍFICA E NÃO VIOLAÇÃO.

EM NENHUMA HIPÓTESE OS AUTORES OU DETENTORES DOS DIREITOS AUTORAIS SERÃO
RESPONSÁVEIS POR QUALQUER REIVINDICAÇÃO, DANOS OU OUTRA RESPONSABILIDADE,
SEJA EM UMA AÇÃO CONTRATUAL, EXTRACONTRATUAL OU DE OUTRA NATUREZA, DECORRENTE
DE, RELACIONADA A OU EM CONEXÃO COM O SOFTWARE, COM O USO DO SOFTWARE OU COM
OUTRAS OPERAÇÕES ENVOLVENDO O SOFTWARE.
```

## 1.5 Exemplo preenchido

```text
MIT License

Copyright 2026 Éder Silva
```

O restante do texto permanece igual.

---

# 2. Licença Apache 2.0

## 2.1 O que é a Licença Apache 2.0?

A Apache License 2.0 também é uma licença permissiva.

Ela permite o uso, modificação e distribuição do software, inclusive em projetos comerciais.

Uma característica importante é que ela possui disposições relacionadas a patentes, o que pode ser relevante em projetos empresariais e projetos de maior porte.

O texto mostrado a seguir corresponde ao aviso padrão normalmente colocado nos arquivos de código de um projeto Apache 2.0.

O arquivo `LICENSE` do projeto deve conter o texto oficial completo da Apache License 2.0.

## 2.2 O que devemos alterar?

Devemos substituir:

```text
[yyyy]
```

pelo ano.

Também devemos substituir:

```text
[name of copyright owner]
```

pelo nome do responsável pelos direitos autorais.

Exemplo:

```text
Copyright 2026 Éder Silva
```

## 2.3 Texto original em inglês

```text
Copyright [yyyy] [name of copyright owner]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

## 2.4 Tradução para o português

```text
Copyright [aaaa] [nome do titular dos direitos autorais]

Licenciado sob a Licença Apache, Versão 2.0, denominada neste texto como
"Licença".

Você não pode utilizar este arquivo exceto em conformidade com a Licença.

Você pode obter uma cópia da Licença em:

http://www.apache.org/licenses/LICENSE-2.0

Salvo quando exigido pela legislação aplicável ou acordado por escrito, o
software distribuído sob esta Licença é fornecido "NO ESTADO EM QUE SE
ENCONTRA", SEM GARANTIAS OU CONDIÇÕES DE QUALQUER TIPO, sejam expressas ou
implícitas.

Consulte a Licença para conhecer as disposições específicas que regem as
permissões e limitações estabelecidas por ela.
```

## 2.5 Exemplo preenchido

```text
Copyright 2026 Éder Silva
```

---

# 3. GNU General Public License

## 3.1 O que é a GNU GPL?

A GNU General Public License, conhecida como GNU GPL, é uma licença de software livre baseada no princípio de copyleft.

Isso significa que podemos utilizar, estudar, modificar e redistribuir o software.

Entretanto, quando distribuímos uma versão modificada ou derivada do programa sob as condições da GPL, devemos respeitar as obrigações estabelecidas pela própria licença.

O trecho abaixo é um aviso recomendado para programas licenciados sob a GNU GPL.

Ele não substitui o texto completo da licença.

## 3.2 O que devemos alterar?

Devemos substituir:

```text
<one line to give the program's name and a brief idea of what it does.>
```

por uma linha contendo o nome do programa e uma pequena descrição.

Exemplo:

```text
SistemaEscola is a desktop application for managing students and classes.
```

Também devemos substituir:

```text
<year>
```

pelo ano.

E:

```text
<name of author>
```

pelo nome do autor.

## 3.3 Texto original em inglês

```text
<one line to give the program's name and a brief idea of what it does.>

Copyright (C) <year> <name of author>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <https://www.gnu.org/licenses/>.
```

## 3.4 Tradução para o português

```text
<uma linha para indicar o nome do programa e uma breve descrição de sua função.>

Copyright (C) <ano> <nome do autor>

Este programa é um software livre: você pode redistribuí-lo e/ou modificá-lo
sob os termos da Licença Pública Geral GNU, conforme publicada pela
Free Software Foundation, seja a versão 3 da Licença ou, a seu critério,
qualquer versão posterior.

Este programa é distribuído na esperança de que seja útil, mas SEM QUALQUER
GARANTIA, inclusive sem a garantia implícita de COMERCIABILIDADE ou ADEQUAÇÃO
A UM PROPÓSITO ESPECÍFICO.

Consulte a Licença Pública Geral GNU para obter mais detalhes.

Você deve ter recebido uma cópia da Licença Pública Geral GNU juntamente com
este programa. Caso contrário, consulte <https://www.gnu.org/licenses/>.
```

## 3.5 Exemplo preenchido

```text
SistemaEscola is a desktop application for managing students and classes.

Copyright (C) 2026 Éder Silva
```

---

# 4. Licença BSD de 3 Cláusulas

## 4.1 O que é a Licença BSD?

BSD significa Berkeley Software Distribution.

A Licença BSD possui diferentes versões. O modelo apresentado neste material corresponde à BSD de 3 Cláusulas.

Ela é uma licença permissiva e permite utilizar, modificar e redistribuir o código fonte e também versões compiladas.

Uma das principais condições é que o nome do autor ou dos colaboradores não seja utilizado para promover produtos derivados sem autorização prévia.

## 4.2 O que devemos alterar?

O modelo deve informar corretamente o ano e o detentor dos direitos autorais.

Em vez de utilizar:

```text
Copyright © belongs to the uploader
```

é recomendável utilizar uma identificação concreta.

Exemplo:

```text
Copyright (c) 2026 Éder Silva
All rights reserved.
```

## 4.3 Texto em inglês

```text
BSD 3-Clause License

Copyright (c) <YEAR>, <COPYRIGHT HOLDER>
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice,
   this list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its contributors
   may be used to endorse or promote products derived from this software
   without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
ARE DISCLAIMED.

IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY
DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES,
INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION, HOWEVER CAUSED AND
ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT,
INCLUDING NEGLIGENCE OR OTHERWISE, ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

## 4.4 Tradução para o português

```text
Licença BSD de 3 Cláusulas

Copyright (c) <ANO>, <DETENTOR DOS DIREITOS AUTORAIS>
Todos os direitos reservados.

A redistribuição e o uso nas formas de código fonte e binário, com ou sem
modificação, são permitidos desde que as seguintes condições sejam atendidas:

1. As redistribuições do código fonte devem manter o aviso de direitos autorais
   acima, esta lista de condições e a seguinte isenção de responsabilidade.

2. As redistribuições em formato binário devem reproduzir o aviso de direitos
   autorais acima, esta lista de condições e a seguinte isenção de
   responsabilidade na documentação e/ou em outros materiais fornecidos com
   a distribuição.

3. Nem o nome do detentor dos direitos autorais nem os nomes de seus
   colaboradores podem ser utilizados para endossar ou promover produtos
   derivados deste software sem autorização específica e prévia por escrito.

ESTE SOFTWARE É FORNECIDO PELOS DETENTORES DOS DIREITOS AUTORAIS E
COLABORADORES "NO ESTADO EM QUE SE ENCONTRA", SENDO EXCLUÍDAS QUAISQUER
GARANTIAS EXPRESSAS OU IMPLÍCITAS, INCLUINDO, MAS NÃO SE LIMITANDO, ÀS
GARANTIAS IMPLÍCITAS DE COMERCIABILIDADE E ADEQUAÇÃO A UMA FINALIDADE
ESPECÍFICA.

EM NENHUMA HIPÓTESE O DETENTOR DOS DIREITOS AUTORAIS OU OS COLABORADORES
SERÃO RESPONSÁVEIS POR DANOS DIRETOS, INDIRETOS, INCIDENTAIS, ESPECIAIS,
EXEMPLARES OU CONSEQUENCIAIS, INCLUINDO, MAS NÃO SE LIMITANDO, À AQUISIÇÃO
DE BENS OU SERVIÇOS SUBSTITUTOS, PERDA DE USO, DADOS OU LUCROS, OU
INTERRUPÇÃO DE NEGÓCIOS, INDEPENDENTEMENTE DA CAUSA E DA TEORIA DE
RESPONSABILIDADE APLICADA, SEJA CONTRATUAL, RESPONSABILIDADE OBJETIVA OU
EXTRACONTRATUAL, INCLUINDO NEGLIGÊNCIA OU OUTRA, DECORRENTE DE QUALQUER
FORMA DO USO DESTE SOFTWARE, MESMO QUE TENHA SIDO AVISADO DA POSSIBILIDADE
DE TAIS DANOS.
```

## 4.5 Exemplo preenchido

```text
BSD 3-Clause License

Copyright (c) 2026 Éder Silva
All rights reserved.
```

---

# 5. Onde colocar a licença no projeto?

Normalmente, nós criamos um arquivo chamado:

```text
LICENSE
```

na pasta principal do repositório.

Exemplo de estrutura:

```text
MeuProjeto/
│
├── src/
├── docs/
├── README.md
├── LICENSE
└── .gitignore
```

No GitHub, o arquivo `LICENSE` normalmente aparece na página principal do repositório quando a plataforma reconhece a licença utilizada.

---

# 6. Devemos colocar inglês e português no arquivo LICENSE?

Para projetos reais, a recomendação mais segura é manter no arquivo `LICENSE` o texto oficial da licença escolhida, normalmente em inglês.

A tradução pode ser colocada em um arquivo complementar com finalidade educacional.

Por exemplo:

```text
LICENSE
LICENSE_PT_BR.md
```

Outra possibilidade para nossos projetos de aula é utilizar:

```text
docs/
└── LICENCAS_EXPLICADAS.md
```

Assim nós preservamos o texto oficial da licença e mantemos uma explicação em português para os alunos.

---

# 7. Exemplo de organização no GitHub

```text
ProjetoJava/
│
├── src/
│   └── ...
│
├── docs/
│   └── LICENCAS_EXPLICADAS.md
│
├── README.md
├── CONTRIBUTING.md
├── CHANGELOG.md
├── LICENSE
└── .gitignore
```

---

# 8. Qual licença escolher?

A escolha depende dos objetivos do projeto.

| Licença | Característica principal | Pode usar comercialmente? | Exige disponibilizar o código derivado? |
|---|---|---:|---:|
| MIT | Muito permissiva | Sim | Não |
| Apache 2.0 | Permissiva e possui disposições sobre patentes | Sim | Não |
| GNU GPL | Copyleft | Sim | Em determinadas formas de distribuição, deve respeitar as obrigações da GPL |
| BSD 3 Cláusulas | Permissiva | Sim | Não |

---

# 9. Observação importante 

Uma licença de software não serve apenas para colocar um arquivo bonito dentro do repositório.

Ela informa juridicamente o que outras pessoas podem ou não podem fazer com aquele código.

Quando publicamos um projeto sem uma licença definida, isso não significa automaticamente que qualquer pessoa pode copiar, modificar ou redistribuir o código livremente.

Por isso, antes de publicar um projeto, devemos analisar:

1. Quem poderá utilizar o código.
2. Se alterações poderão ser distribuídas.
3. Se o software poderá ser utilizado comercialmente.
4. Se queremos exigir que versões derivadas mantenham determinadas liberdades.
5. Se queremos apenas permitir o uso mantendo os créditos e avisos legais.

---

# 10. Resumo

Podemos lembrar das quatro licenças desta forma:

**MIT**

Simples, permissiva e muito utilizada em projetos de código aberto.

**Apache 2.0**

Permissiva, semelhante à MIT em vários aspectos, mas com disposições adicionais, principalmente relacionadas a patentes.

**GNU GPL**

Licença baseada em copyleft, criada para preservar determinadas liberdades do software também em versões modificadas e redistribuídas.

**BSD de 3 Cláusulas**

Licença permissiva que permite ampla utilização do código, desde que sejam respeitadas suas condições e avisos.

---

# 11. Atividade sugerida

Escolha um projeto que você já publicou ou pretende publicar no GitHub.

Depois responda:

1. Qual licença você escolheria?
2. Por que escolheu essa licença?
3. Seu projeto poderá ser utilizado comercialmente?
4. Outra pessoa poderá modificar seu código?
5. Essa pessoa precisará publicar as modificações?
6. Quais informações devem ser alteradas no modelo da licença antes da publicação?

Depois disso, crie o arquivo `LICENSE` na raiz do projeto e preencha corretamente os campos necessários.

---

## Conclusão

Entender licenças faz parte da documentação profissional de um projeto.

Quando nós publicamos um código no GitHub, não estamos apenas mostrando nossa programação. Também estamos definindo quais direitos e responsabilidades acompanham aquele software.

Escolher e documentar corretamente uma licença torna o repositório mais organizado, facilita a colaboração e deixa explícitas as condições de uso do código.
