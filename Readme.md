# O Papel do _Data Science_ na Educação Moderna

Rodrigo Saito, Professor dos cursos de Tecnologia do UNIANCHIETA – [rodrigo.ksaito@gmail](mailto:rodrigo.ksaito@gmail)

# Resumo

O capítulo apresenta os fundamentos de _Data Science_ e de dados que sustentam a análise de dados educacionais. Partindo da definição de _Data Science_ como um campo multidisciplinar que combina ciência da computação, estatística e matemática, o capítulo orienta a configuração do ambiente de trabalho em _Python_ no _Windows_ por meio da distribuição _Anaconda_, detalhando o passo a passo da instalação e o uso do _Jupyter Notebook_. A parte aplicada apresenta um estudo de caso sobre a previsão de evasão em um Ambiente Virtual de Aprendizagem, com um _dataset_ realista de aproximadamente 20 mil estudantes e 17 atributos comportamentais, e desenvolve a primeira etapa prática: o diagnóstico e a visualização dos dados, incluindo o tratamento de valores ausentes, duplicatas e _outliers_, a engenharia de atributos e a análise de correlações.

**Palavras-chave:** _Data Science_; Ciência de Dados Educacionais; Aprendizado de Máquina; _Python_; _Anaconda_; _Jupyter Notebook_; Ambiente Virtual de Aprendizagem; Evasão Escolar; _Learning Analytics_; Análise de Dados.

# Introdução

Vivemos um momento em que a produção de dados cresce em ritmo acelerado. Como observa Pierson (2019), o que antes eram lagos e poças de informação se transformou em verdadeiras inundações de dados estruturados, semiestruturados e não estruturados, gerados por quase toda atividade humana nos mundos digital e físico. No campo educacional, essa realidade não é diferente: ambientes virtuais de aprendizagem registram cada interação dos estudantes, cada acesso e cada atividade entregue, e esse rastro digital permanece, na maioria das vezes, subutilizado. É nesse contexto que o _Data Science_ se apresenta como resposta. Trata-se de um campo multidisciplinar que combina ciência da computação, estatística e matemática para transformar volumes massivos de dados em conhecimento acionável. Quando aplicado à educação, esse conhecimento permite compreender o fenômeno educacional em profundidade, identificar padrões de comportamento e, sobretudo, agir antes que os problemas se consolidem, como ocorre no caso da evasão escolar.

Este capítulo tem três objetivos. O primeiro é estabelecer os fundamentos conceituais do _Data Science_ e da Ciência de Dados Educacionais. O segundo é capacitar o estudante a configurar seu próprio ambiente de trabalho, com a instalação do _Anaconda_ e do _Jupyter Notebook_ em _Python_. O terceiro é analisar os dados de um estudo sobre evasão em um Ambiente Virtual de Aprendizagem.

# Introdução à _Data Science_

De acordo com Pierson (2019, p. 17), embora a imersão em dados não seja nova, é notável que o fenômeno esteja se acelerando. Lagos, poças e rios de informação transformaram-se em inundações e verdadeiros tsunamis de dados estruturados, semiestruturados e não estruturados, que jorram de quase toda atividade ocorrida nos mundos digital e físico. Especialistas conhecidos como engenheiros de dados encontram constantemente maneiras inovadoras e poderosas de capturar, combinar e condensar volumes enormes de dados de modos inimagináveis; outros especialistas, conhecidos como cientistas de dados, extraem informações úteis e valiosas desses dados.

_Data Science_ é um campo multidisciplinar que combina ciência da computação – mais especificamente os campos de engenharia de _software_ e _Machine Learning_ (ML), ou Aprendizado de Máquina –, estatística e matemática para analisar quantidades massivas de dados e deles extrair conhecimento. (FILATRO, 2020, p. 14)

|     |     |
| --- | --- |
| Etapas | Objetivos |
| Definição do problema | Entender o que, como e por que o processo de _Data Science_ será realizado, e ter uma visão clara sobre o propósito e o contexto do problema, os recursos a serem utilizados, a maneira como a análise será realizada e a lista de entregas dispostas em uma linha do tempo. |
| Coleta de dados | Ter acesso aos dados (em vários formatos), seja consultando bancos de dados internos ou adquirindo conjuntos de dados externos. |
| Preparação dos dados | Transformar os dados brutos em um formato diretamente utilizável, além de identificar e corrigir eventuais erros (valores ausentes, duplicados, inválidos), e, se necessário, mesclar dados de fontes diferentes. |
| Exploração dos dados | Usar técnicas visuais e descritivas para realizar a análise exploratória, buscando correlações e padrões que permitam obter _insights_ e compreensão dos dados. |
| Modelagem dos dados | Construir um modelo1 que, utilizando abordagens descritivas, preditivas ou prescritivas, permita responder às perguntas levantadas na 1ª etapa. |
| Comunicação dos resultados | Apresentar os resultados da modelagem de dados em diferentes formatos, variando desde relatórios detalhados de consulta até apresentações em painéis de controle (_Dashboards_), passando por gráficos, estatísticas e mapas de calor (_heatmaps_). |
| Automatização da análise | Quando necessário, se o processo tiver de ser replicado várias vezes, tornar a análise automática para economizar tempo. |
| Fonte: adaptado de CIELEN et al., 2016 apud BALDASSARRE, 2016. |     |

Para usar _Data Science_ de forma prática, no verdadeiro sentido do termo, é preciso ter conhecimentos analíticos de matemática e estatística, habilidades de programação para trabalhar com os dados e um mínimo de especialização no assunto. Sem essa combinação, pode-se ser apenas matemático ou estatístico. Da mesma forma, um programador de _software_ sem especialização no assunto e sem prática analítica pode ser considerado engenheiro de _software_ ou desenvolvedor, mas não cientista de dados (PIERSON, 2019, p. 17).

Filatro (2020, p. 15) defende que o processo de _Data Science_ raramente é linear. Em cada etapa, pode ser necessário retornar às etapas anteriores antes de chegar ao final do processo, revisitando métodos e técnicas ou mesmo reconsiderando se o problema originalmente identificado era adequado. Ao chegar a um resultado, é bastante provável que as respostas encontradas simplesmente gerem novas perguntas, reiniciando o processo.

Quando aplicado especificamente ao campo educacional, o _Data Science_ reúne ciência da computação, educação, estatística e outras ciências sociais para examinar e compreender o fenômeno educacional. Assim, **_Educational Data Science_** **(EDS)**, ou Ciência de Dados Educacionais, pode ser definida como um campo orientado por dados, sistêmico, transdisciplinar e dinâmico, que combina habilidades técnicas e sociais com uma compreensão profunda da prática educacional em diferentes ambientes de aprendizagem (FILATRO, 2020, p. 16).

O EDS utiliza procedimentos e técnicas para reunir, organizar, tratar e interpretar fontes de dados educacionais volumosas e diversificadas, assegurando a consistência desses conjuntos e criando visualizações para auxiliar na compreensão de dados complexos. Além disso, modelos matemáticos são construídos para comunicar _insights_/descobertas a educadores, gestores, _designers_ instrucionais, alunos e outras partes interessadas.

Para os objetivos deste livro, o EDS pode ser explicado como a intersecção entre _Educational Data_ _Mining, Learning Analytics_ e Inteligência Artificial na Educação.

Figura 1 - Áreas que compõem o Data Science na Educação

# Configuração do Ambiente de Trabalho com a linguagem _Python_ no _Windows_

Como diz o autor NETTO (2021, p. 16), _Python_ é uma das linguagens de programação mais populares na atualidade e é uma das mais utilizadas para Análise de Dados e, em particular, para _Machine Learning_. Entre suas características marcantes, podemos destacar:

É uma linguagem de alto nível — escrever um programa nesse tipo de linguagem é mais fácil, pois sua sintaxe é mais parecida com a linguagem humana. Nesse sentido, Python é extremamente enxuta e facilita demais o desenvolvimento de programas ricos em recursos com poucas linhas de código.

É fortemente tipada, ou seja, os tipos de dados são verificados em todas as operações para garantir que sejam compatíveis.

É dinamicamente tipada — esse conceito costuma ser confundido por iniciantes. Basicamente, dizer que Python é uma linguagem dinamicamente tipada significa que os tipos de dados de suas variáveis são inferidos automaticamente, a partir do valor armazenado nelas. É permitido até mesmo alterar o tipo de dado de uma variável em tempo de execução (embora essa seja considerada uma prática ruim).

É multiparadigma, podendo ser classificada ao mesmo tempo como linguagem imperativa, funcional e, no paradigma imperativo, como orientada a objetos e procedural. (NETTO, 2021, p. 16)

Considerando que você esteja utilizando o sistema operacional _Windows_, será necessário instalar uma suíte para _Data Science_. Trata-se de uma ferramenta poderosa, amplamente utilizada no mercado e disponível gratuitamente para fins de estudo.

Como menciona o _site_ do _Anaconda_ (2015), é uma distribuição que reúne pacotes essenciais do _Python_, ferramentas como _Jupyter_ e _RStudio_ e um gerenciador de pacotes chamado _Conda_. Isso simplifica o gerenciamento de pacotes e a implantação de projetos nas áreas de ciência de dados, aprendizado de máquina e computação científica. Embora o foco principal do _Anaconda_ seja tornar a ciência de dados acessível, a plataforma também oferece soluções que reforçam a segurança e dão suporte ao desenvolvimento impulsionado por IA. Além disso, o _Anaconda_ disponibiliza soluções de nível empresarial que ampliam as capacidades de código aberto do _Python_ com recursos como colaboração em equipe, segurança e escalabilidade. Essas soluções são projetadas para atender grandes organizações que utilizam _Python_ em ciência de dados, IA e aprendizado de máquina.

Para fazer download para Windows, entre no endereço: https://www.anaconda.com/download

Clique em \[_Free Download_\] e, caso não queira se registrar, clique em \[_Skip Registration_\].

Clique em Download para Windows:

O download será iniciado. Após a conclusão, o arquivo dessa versão terá quase 1 GB. Dê um duplo clique no arquivo do _Anaconda_.

|     |     |
| --- | --- |
|     |     |
| Para iniciar a instalação do Anaconda, clique em \[Next\] | Clique em \[_Next_\] para acessar a licença de uso do _Anaconda_. |

|     |     |
| --- | --- |
|     |     |
| Clique em \[_Next_\] para realizar a instalação somente para você. | Escolha o local de instalação e clique em \[Next\] |

Mantenha as opções padrão de personalização e clique em \[_Install_\].

**Observação: para executar o comando _python_ de qualquer local no _Prompt_ de Comando, marque a opção "_Add Anaconda3 to my PATH environment variable_". Embora essa opção apareça como não recomendada, ela é necessária para que o _Anaconda_ configure automaticamente as variáveis de ambiente no _Windows_.**

|     |     |
| --- | --- |
|     |     |
| A instalação irá prosseguir, conforme as escolhas feitas | Ao final da instalação, serão baixadas as bibliotecas mais recentes do _Anaconda_. Esse processo pode levar alguns minutos; aguarde. Em seguida, clique em \[_Next_\] para continuar. |

|     |     |
| --- | --- |
|     |     |
| Na tela seguinte, será mostrada a versão do Anaconda. Clique em \[Next\] | Clique em \[Finish\] para completar a instalação. |

Para abrir o programa, clique no menu \[Iniciar\] do _Windows_, procure por "_Anaconda_" na barra de pesquisa e clique em \[_Anaconda Navigator_\].

|     |     |
| --- | --- |
|     |     |
| Ao abrir o _Anaconda_, será apresentada uma tela para atualização do _software_. Clique em \[_Yes_\]. | Depois de atualizado, clique em \[Launch Navigator\] |

Será aberta uma tela de registro. Caso não queira se registrar, clique no botão Fechar.

A tela do Anaconda será aberta:

|     |     |
| --- | --- |
|     |     |
| Clique em \[_Launch_\] no _JupyterLab_. | Escolha o navegador de sua preferência e clique em \[Sempre\] |

O _Jupyter Notebook_ será aberto. Clique em \[_Python 3 (ipykernel)_\].

O _Jupyter Notebook_ abrirá um novo caderno para que você possa executar comandos em _Python_.

# Manipulação de Dados Educacionais (AVA)

## Estudo de _Data Science_: Previsão de Evasão em um Ambiente Virtual de Aprendizagem

### Contexto do problema

Um Ambiente Virtual de Aprendizagem (AVA), como o _Moodle_, _Canvas_ e outros existentes no mercado, registra toda a interação dos estudantes com o conteúdo: acessos, tempo de permanência, participação em fóruns, visualização de vídeos, realização de _quizzes_ e entrega de atividades. Esses registros formam um rastro digital valioso. O objetivo deste estudo é transformar esse rastro em conhecimento: entender quais comportamentos levam um estudante a abandonar o curso e construir modelos capazes de prever, com antecedência, quem está em risco de evasão. A evasão é o "_churn_" do mundo acadêmico. Em um curso presencial, o professor percebe o problema tarde demais. Com dados, é possível agir antes: identificar o estudante em risco, oferecer apoio e reduzir a taxa de abandono.

### O _dataset_

Cada linha representa um estudante, com 17 atributos que resumem seu comportamento no AVA ao longo do período letivo.

|     |     |
| --- | --- |
| **Coluna** | **Descrição** |
| _student_id_ | Identificador único do estudante |
| course | Disciplina (Matemática Discreta, Programação I, Banco de Dados, Redes de Computadores, Estatística) |
| total_accesses | Número total de acessos ao AVA |
| total_time_minutes | Tempo total de permanência, em minutos |
| avg_time_per_access | Tempo médio por acesso (minutos) |
| days_active | Quantidade de dias distintos com pelo menos um acesso |
| modules_accessed | Quantidade de módulos do curso acessados (1 a 10) |
| activities_completed | Atividades concluídas |
| quizzes_taken | Quizzes realizados (0 a 12) |
| avg_quiz_score | Nota média nos quizzes, de 0 a 10 (NaN quando nenhum quiz foi feito) |
| forum_posts | Mensagens publicadas em fóruns (NaN em 2% dos casos) |
| forum_reads | Leituras de mensagens em fóruns |
| videos_watched | Vídeos assistidos |
| assignments_submitted | Trabalhos entregues (0 a 8) |
| weekend_access_ratio | Proporção de acessos feitos no fim de semana |
| regularity_index | Coeficiente de variação dos acessos semanais (quanto menor, mais regular o estudante) |
| dropout | **Variável alvo**: 1 = evadiu, 0 = permaneceu |

O _dataset_ foi construído de forma realista: estudantes engajados (muitos acessos, alta regularidade, boas notas) tendem a permanecer; estudantes com baixo engajamento tendem a evadir. Há valores ausentes e outliers de propósito, para que o processo de limpeza seja exercitado de verdade.

As quatro partes desse _dataset_ e o código do _Jupyter Notebook_ podem ser baixados em:  
https://github.com/datalibtec/livroPythonERParaDataScience

### Algumas das questões que podem ser respondidas

Com o _dataset_ disponível, há inúmeras questões que podem ser respondidas por meio de consultas simples no _Excel_ ou de ferramentas mais adequadas à manipulação de grandes volumes de dados. Neste contexto, resolveremos algumas das questões apresentadas a seguir. Para outras, poderão ser utilizados algoritmos de aprendizado de máquina, tema que não será abordado neste momento.

1.  Quais fatores de uso do AVA estão mais associados à evasão?
2.  É possível prever, com base no comportamento de acesso, se um estudante está em risco de evasão?
3.  Estudantes com acesso mais regular (menor regularity_index) evadem menos?
4.  O desempenho médio em quizzes é um preditor relevante de evasão?

### Parte 1: Diagnóstico e Visualização

Nesta parte fazemos a **mineração dos dados**: carregamento, exploração inicial, detecção de problemas (valores ausentes, duplicatas, outliers) e visualização de padrões. O objetivo é conhecer o dado antes de modelar.

Reunimos todas as dependências em uma única célula. O _pandas_ e o _numpy_ são a base da análise; _matplotlib_ e _seaborn_ geram os gráficos; o _scikit-learn_ fornece os algoritmos e as métricas; o _scipy_ fornece os testes estatísticos.

Todos os arquivos estão no mesmo formato (CSV), então a mesma função de leitura é aplicada aos quatro. O _read_csv_ lê arquivos de texto separados por vírgula e converte cada linha em um registro do _DataFrame_.

A concatenação junta as 4 partes em um único _DataFrame_, permitindo analisar os 20.000 estudantes como um todo. A verificação de duplicatas garante que as partes não se sobrepõem, confirmando a integridade da divisão.

O resultado será um erro ao executar esse último trecho de código, com aproximadamente este problema:

Ao verificar a quantidade de colunas, observe que há apenas uma, na qual todos os dados estão sendo concatenados.

Criaremos uma função para realizar a separação das colunas por meio de comparações padronizadas.

Ao realizar novamente a leitura das colunas, obteremos o seguinte resultado:

O dicionário de dados documenta o significado de cada coluna, o tipo e as particularidades (valores ausentes, outliers). É a referência conceitual que orienta todas as decisões de tratamento e modelagem.

Teremos o seguinte resultado ou algo aproximado como:

O _info()_ mostra o tipo de cada coluna e quantos valores não nulos existem. Colunas com contagem menor que 20.000 indicam a presença de dados ausentes, como _avg_quiz_score_ e _forum_posts_.

Teremos o seguinte resultado ou algo aproximado como:

O _describe()_ calcula média, desvio padrão, mínimo, quartis e máximo de cada coluna numérica. Compare o máximo de _total_time_minutes_ com o terceiro quartil: se houver grande diferença, há indício de _outliers_.

Teremos o seguinte resultado ou algo aproximado como:

Antes de modelar, precisamos saber onde estão os dados ausentes, pois a maioria dos algoritmos de _machine learning_ não os aceita. O tratamento é obrigatório.

Teremos o seguinte resultado ou algo aproximado como:

Duplicatas podem inflar padrões e viciar o modelo. Como cada linha é um estudante único, qualquer duplicata seria um erro de extração a remover.

O resultado será: Linhas duplicadas: 0

A variável alvo é o coração do problema. A proporção de evasão indica se o problema é relevante e se há desbalanceamento, o que justifica o uso de estratificação na divisão treino/teste.

Teremos o seguinte resultado ou algo aproximado como:

Existem três estratégias para valores ausentes: remover linhas, remover colunas ou preencher (imputar). Remover 12% das linhas desperdiçaria dados valiosos. A imputação pela mediana é a escolha mais segura, pois não é influenciada por outliers. Para avg_quiz_score, a mediana representa a nota típica, uma estimativa razoável para quem não fez quizzes.

Teremos o seguinte resultado ou algo aproximado como:

_Outliers_ extremos podem distorcer a média, o escalonamento e o treinamento dos modelos. A regra do IQR considera _outliers_ os valores abaixo de Q1 - 1,5 × IQR ou acima de Q3 + 1,5 × IQR. Em vez de descartar as linhas, aplicamos a winsorização: os valores extremos são limitados aos limites calculados, preservando o registro, mas neutralizando o efeito do valor extremo.

Teremos o seguinte resultado ou algo aproximado como:

Algoritmos de _machine learning_ trabalham apenas com números. A coluna _course_ é textual, então precisamos convertê-la. O _LabelEncoder_ atribui um número inteiro a cada disciplina. Para variáveis nominais sem ordem natural, o _One-Hot Encoding_ seria mais indicado (ver Parte Avançada); aqui usamos o _LabelEncoder_ por simplicidade didática.

Teremos o seguinte resultado ou algo aproximado como:

A engenharia de atributos cria novas variáveis a partir das existentes, capturando conceitos que nenhuma coluna isolada representa. O _engagement_index_ sintetiza quatro indicadores de engajamento em um único _score_ entre 0 e 1. Cada componente é normalizado pela sua escala máxima e ponderado por sua importância presumida.

Teremos o seguinte resultado ou algo aproximado como:

A correlação mede a força e a direção da relação linear entre duas variáveis, variando de -1 (inversa) a +1 (direta). A linha da coluna _dropout_ é a mais importante: valores negativos indicam que, quanto maior a variável, menor a chance de evasão. Isso responde parcialmente à questão 1.

Teremos o seguinte resultado ou algo aproximado como:

O _boxplot_ resume a distribuição com quartis e _outliers_ visíveis. Comparar as duas caixas mostra visualmente se quem evadiu realmente passou menos tempo no ambiente. É uma análise descritiva que antecipa o teste estatístico.

Teremos o seguinte resultado ou algo aproximado como:

Histogramas revelam a forma da distribuição: simétrica, assimétrica, concentrada ou espalhada. Isso ajuda a decidir se a média é uma boa medida de tendência central e se o escalonamento será necessário.

Teremos o seguinte resultado ou algo aproximado como:

Este gráfico verifica se a evasão é uniforme entre as disciplinas ou se alguma concentra mais abandono. Se houver diferença, a disciplina pode ser uma variável preditiva relevante, o que será confirmado pelo teste qui-quadrado.

Teremos o seguinte resultado ou algo aproximado como:

# Considerações Finais

Ao longo deste capítulo, o leitor percorreu um caminho que vai do conceito à prática. Compreendeu que _Data Science_ não é apenas uma coleção de técnicas, mas um processo cíclico e multidisciplinar, no qual cada etapa pode exigir o retorno às anteriores, e que a Ciência de Dados Educacionais traduz esse processo para o contexto específico da aprendizagem, unindo mineração de dados educacionais, _learning analytics_ e inteligência artificial. Também aprendeu a preparar o ambiente para a análise: a instalação do _Anaconda_, a abertura do _Jupyter Notebook_ e a leitura crítica de um _dataset_ realista, com seus valores ausentes, duplicatas e _outliers_ propositais.

A mensagem central é que os dados, sejam educacionais ou de outra natureza, só geram valor quando são transformados em decisões. O estudo de caso sobre evasão ilustra exatamente esse ponto: identificar com antecedência o estudante em risco permite que a instituição ofereça apoio antes que o abandono ocorra, algo que a percepção isolada do professor em sala de aula dificilmente alcança a tempo.

Como recomendação prática, sugere-se que o estudante execute cada etapa do capítulo em seu próprio ambiente, reproduzindo os comandos e, principalmente, explorando os dados por conta própria: altere visualizações, teste diferentes tratamentos para os valores ausentes e formule novas perguntas sobre o _dataset_. É na experimentação autônoma que os fundamentos apresentados aqui se consolidam, preparando para as próximas etapas, em que os algoritmos de _machine learning_ entrarão em cena para responder às perguntas levantadas neste capítulo.

Referências Bibliográficas:

ANACONDA, Anaconda vs. Python: What’s the Difference? Disponível em: https://www.anaconda.com/topics/choosing-between-anaconda-vs-python. Acesso em: 21 set. 2026.

FILATRO, Andrea C. Data Science da educação. Rio de Janeiro: Saraiva Uni, 2020. E-book. ISBN 9786587958446. Disponível em: https://integrada.minhabiblioteca.com.br/reader/books/9786587958446/. Acesso em: 21 set. 2026.

NETTO, Amilcar; MACIEL, Francisco. Python para Data Science e Machine Learning Descomplicado. Rio de Janeiro: Editora Alta Books, 2021. E-book. ISBN 9786555203172. Disponível em: https://integrada.minhabiblioteca.com.br/reader/books/9786555203172/. Acesso em: 21 set. 2026.

PIERSON, Lillian. Data Science para Leigos. Rio de Janeiro: Editora Alta Books, 2019. E-book. ISBN 9788550813080. Disponível em: https://integrada.minhabiblioteca.com.br/reader/books/9788550813080/. Acesso em: 21 set. 2026.

# _Learning Analytics_ e Análise de Engajamento de Alunos em plataforma AVA

Rodrigo Saito, Professor dos cursos de Tecnologia do UNIANCHIETA – rodrigo.ksaito@gmail.com

# Resumo

Este capítulo apresenta o uso de _Learning Analytics_ e aprendizado de máquina para a análise de engajamento e a predição de sucesso acadêmico de estudantes em Ambientes Virtuais de Aprendizagem (AVAs). A partir de um _dataset_ sintético de 20.000 registros de alunos de cursos de computação, dividido em quatro partes concatenáveis de 5.000 registros cada, o texto documenta um _pipeline_ completo de ciência de dados executado em _Jupyter Notebook_. O conjunto reúne 26 variáveis comportamentais, demográficas, textuais e acadêmicas, entre elas métricas de acesso, tempo de permanência, participação em fóruns, desempenho em _quizzes_ e indicadores de regularidade, além de duas variáveis alvo: a nota final (regressão) e o _status_ acadêmico de Aprovado, Reprovado ou Evadido (classificação). O trabalho percorre as etapas de carga e concatenação dos dados, verificação de valores ausentes e duplicatas, imputação pela mediana, tratamento de _outliers_ por winsorização, engenharia de atributos com a criação de um índice de engajamento e análise de correlações. Em seguida, treina modelos supervisionados de classificação (Regressão Logística e _Random Forest_) e de regressão (Linear e _Random Forest_), avaliados por acurácia, precisão, _recall_, _F1-score_, _AUC-ROC_, _MAE_, _RMSE_ e R². Por fim, aplica técnicas de mineração de textos sobre as interações em fóruns, com _TF-IDF_ e análise de sentimento, demonstrando que o comportamento textual complementa os dados numéricos como sinal precoce de risco de evasão.

**Palavras-chave:** _Learning Analytics_; Aprendizado de Máquina; Engajamento Discente; Evasão Escolar; Mineração de Textos; Ambientes Virtuais de Aprendizagem.

# Introdução

Conforme explica o _blog_ ARVORE, _Learning Analytics_ é um termo em inglês utilizado para definir o processo de obtenção e análise de dados de _performance_ dos estudantes visando melhorar a eficiência da aprendizagem e, consequentemente, seu desempenho. 

A utilização de dados na educação faz parte de uma crescente ampliação do [acesso às tecnologias nas instituições de ensino](https://www.arvore.com.br/blog/tendencias-do-mercado-educacional). Principalmente se pensarmos o período da pandemia, em que se intensificou o uso de Ambientes Virtuais de Aprendizagem (AVAs) para garantir a continuidade do processo de ensino e aprendizagem nas escolas. 

Em uma plataforma digital, a coleta de dados de navegação como acesso, cliques, tempo de permanência, resultados, entre outros, viabiliza o uso dessas informações para posteriores análises dentro do próprio _software_ ou em uma combinação integrada de sistemas. 

Assim, abre-se um leque de possibilidades em relação a esses dados, seja na elaboração de hipóteses ou na interpretação de resultados que vão fortalecer as tomadas de decisão pelos educadores.

De acordo com CAFÉ, é preciso possibilitar um desenvolvimento personalizado e baseado em competências que realmente impactem o negócio, transformando dados em _insights_ que impulsionam decisões estratégicas e resultados concretos.

Para que o _learning analytics_ seja realmente eficaz, é fundamental acompanhar as métricas certas. Trata-se de quantificar acessos ou conclusões de cursos, mas também de entender profundamente como o conhecimento está sendo absorvido e aplicado. Entre as principais métricas que devem ser monitoradas, destacam-se:

– Taxa de engajamento: vai além da simples presença, pois mede o quanto os colaboradores estão realmente interagindo com o conteúdo;

– Tempo de conclusão: não apenas quanto tempo levou para finalizar um treinamento, mas como esse tempo foi distribuído entre os módulos;

– Padrões de navegação: entender como os colaboradores exploram o conteúdo pode revelar intuições valiosas sobre suas preferências de aprendizado;

– Retenção de conhecimento: avaliações estrategicamente posicionadas podem mostrar não apenas se o conteúdo foi compreendido, mas por quanto tempo esse conhecimento permanece ativo;

– Aplicação prática: talvez a [métrica](https://www.senior.com.br/blog/hris-e-indicadores-de-rh-confira-como-otimizar-os-resultados-do-setor) mais valiosa — como o conhecimento adquirido está sendo transportado para o dia a dia de trabalho.

Esses indicadores de _performance_ individual, quando analisados em conjunto, formam um mapa detalhado do processo de aprendizagem, permitindo intervenções precisas e eficazes tanto de forma coletiva quanto individual.

# _Machine Learning_

Para NETTO (2021, p. 117), a era da informação trouxe consigo uma avalanche nunca vista na criação de informação digital. Um estudo de 2012 da consultoria EMC previu que entre 2005 e 2020 a quantidade de dados produzidos eletronicamente aumentaria de 130 _exabytes_ para 40 mil _exabytes_, ou 40 trilhões de _gigabytes_. O acesso e a interpretação desses dados tornaram-se um diferencial estratégico para empresas e para governos. Em 2015, o presidente Barack Obama criou o cargo de _Chief Data Scientist_, Cientista-Chefe de Dados do governo norte-americano, especificamente com a função de analisar as mais de 138 mil bases de dados do governo federal dos EUA. Perceba que essa quantidade de dados pode dar suporte a estudos de várias áreas do conhecimento, como Economia e Política, passando pelas Ciências Sociais. É nesse contexto que as ferramentas necessárias para o tratamento desses dados foram desenvolvidas, de forma a retornar conhecimento relevante a partir desse volume imenso de informações.

Aprendizado de máquina é um termo cunhado por volta de 1960, composto por duas palavras — _machine_, que corresponde a um computador, robô ou outro dispositivo, e _learning_, que se refere a uma atividade destinada a adquirir ou descobrir padrões de eventos, algo em que nós, humanos, somos bons. Exemplos interessantes incluem reconhecimento facial, tradução de idiomas, resposta a _e-mails_, tomada de decisões de negócio orientadas por dados e criação de vários tipos de conteúdo. (LIU, 2026, p. 2)

Ainda segundo o mesmo autor, máquinas aprendizes são mais adequadas do que os humanos para tarefas rotineiras, repetitivas ou tediosas. Além disso, a automação por aprendizado de máquina pode mitigar riscos causados por fadiga ou desatenção. Carros autônomos são um ótimo exemplo: um veículo é capaz de navegar ao perceber seu ambiente e tomar decisões sem intervenção humana. Outro exemplo é o uso de braços robóticos em linhas de produção, que são capazes de causar uma redução significativa em lesões e custos.

No decorrer deste capítulo, utilizaremos aprendizado de máquina em alguns de nossos códigos aplicados ao _dataset_.

# Conteúdo dos dados de um Ambiente Virtual de Aprendizagem (AVA)

O _dataset_ completo possui 20.000 registros, com os quais você pode trabalhar de forma integral ou parcial, fazendo as adaptações necessárias para realizar a leitura e o carregamento dos dados. Cada arquivo possui registros de estudantes matriculados em cursos da área de computação ministrados em um Ambiente Virtual de Aprendizagem (AVA). O dicionário documenta o significado semântico de cada coluna do conjunto de dados, seu tipo estrutural no ecossistema _Python_ e _Pandas_, o domínio de valores aceitos, as particularidades de engenharia de dados, como padrões de ausência intencional e _outliers_ comportamentais, bem como o papel analítico designado a cada variável, dividindo-as entre variáveis preditoras e variáveis-alvo de tarefas supervisionadas. A compreensão aprofundada desta documentação orienta todas as decisões metodológicas de pré-processamento, imputação, transformação de atributos e validação empírica de algoritmos preditivos de regressão e classificação no ambiente _Jupyter Notebook_.

## Tabela Principal do Dicionário de Dados

A matriz analítica do _dataset_ é estruturada em exatamente 26 variáveis comportamentais, demográficas, textuais e acadêmicas, descritas na íntegra a seguir:

|     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- |
| **Nome da Coluna** | **Tipo** | **Descrição** | **Domínio / Faixa** | **Valores Ausentes** | **Papel** |
| _student_id_ | Texto (string) | Identificador único do estudante no AVA | Formato STU0001 a STU20000 | Sem ausentes | Identificação |
| _course_ | Categórico (string) | Disciplina em que o estudante está matriculado | Matemática Discreta, Programação I, Banco de Dados, Redes de Computadores, Estatística | Sem ausentes | Preditora |
| age | Inteiro | Idade do estudante | 17 a 45 anos | Sem ausentes | Preditora |
| gender | Categórico (string) | Gênero informado pelo estudante | Feminino, Masculino, Outro | Sem ausentes | Preditora |
| total_accesses | Inteiro | Número total de acessos (logins) ao AVA no período letivo | 5 a 250 acessos (com presenças de outliers altos) | Sem ausentes | Preditora |
| total_time_minutes | Float | Tempo total acumulado de permanência no AVA em minutos | 60.0 a 9000.0 (outliers até aproximadamente 15000.0) | Sem ausentes | Preditora |
| avg_time_per_access | Float | Tempo médio despendido em cada acesso ao sistema em minutos | 3.0 a 60.0 minutos | Sem ausentes | Preditora |
| days_active | Inteiro | Quantidade de dias distintos com pelo menos um acesso registrado | 1 a 120 dias | Sem ausentes | Preditora |
| modules_accessed | Inteiro | Quantidade de módulos do curso abertos pelo estudante | 1 a 10 módulos | Sem ausentes | Preditora |
| lessons_completed | Inteiro | Aulas instrucionais marcadas como concluídas | 0 a 40 aulas | Sem ausentes | Preditora |
| videos_watched | Inteiro | Total de conteúdos em vídeo assistidos no ambiente | 0 a 60 vídeos | Sem ausentes | Preditora |
| video_completion_rate | Float | Percentual médio de reprodução dos vídeos até o encerramento | 0.0 a 100.0 % | Sem ausentes | Preditora |
| quizzes_taken | Inteiro | Quantidade de testes rápidos de avaliação realizados | 0 a 12 quizzes | Sem ausentes | Preditora |
| avg_quiz_score | Float | Nota média obtida nos quizzes realizados | 0.0 a 10.0 pontos | Ausentes em cerca de 15% dos casos (estudantes sem quiz realizado) | Preditora |
| assignments_submitted | Inteiro | Trabalhos práticos e tarefas formais entregues | 0 a 8 tarefas | Sem ausentes | Preditora |
| forum_posts | Inteiro | Mensagens textuais autorais publicadas nos fóruns | 0 a 30 postagens | Sem ausentes | Preditora |
| forum_reads | Inteiro | Total de visualizações e leituras de mensagens no fórum | 0 a 400 leituras | Sem ausentes | Preditora |
| threads_started | Inteiro | Novos tópicos de discussão inaugurados pelo estudante | 0 a 10 tópicos | Sem ausentes | Preditora |
| replies_received | Inteiro | Respostas de colegas e docentes recebidas nas postagens do aluno | 0 a 25 respostas | Sem ausentes | Preditora |
| avg_post_length | Float | Média de caracteres por postagem autoral redigida | 50.0 a 800.0 caracteres | Ausentes quando forum_posts for igual a 0 | Preditora (mineração de textos) |
| sentiment_score | Float | Polaridade média de sentimento das mensagens publicadas | \-1.00 (altamente negativo) a +1.00 (altamente positivo) | Ausentes quando forum_posts for igual a 0 | Preditora (mineração de textos) |
| help_seeking_posts | Inteiro | Postagens caracterizadas semanticamente como solicitação de ajuda | 0 a 10 postagens | Sem ausentes (fixado em 0 quando forum_posts for 0) | Preditora (mineração de textos) |
| weekend_access_ratio | Float | Proporção de acessos ao ambiente executados em finais de semana | 0.00 a 1.00 | Sem ausentes | Preditora |
| regularity_index | Float | Coeficiente de variação dos acessos semanais ao longo do semestre | 0.10 a 2.50 (valores menores denotam maior regularidade) | Sem ausentes | Preditora |
| final_grade | Float | Nota final consolidada obtida no encerramento da disciplina | 0.0 a 10.0 pontos | Sem ausentes | VARIÁVEL ALVO (regressão) |
| status | Categórico (string) | Desfecho acadêmico final consolidado na disciplina | Aprovado, Reprovado, Evadido | Sem ausentes | VARIÁVEL ALVO (classificação) |

## Notas sobre a Construção do _Dataset_

O conjunto de dados, totalizando 20.000 registros, foi sintetizado computacionalmente por meio de modelos estocásticos com o propósito de espelhar com elevado grau de verossimilhança os padrões comportamentais observados em ambientes virtuais de aprendizagem de nível superior. Para garantir a consistência das relações multivariadas, foi implementada uma variável latente de engajamento acadêmico. Esse construto teórico não observado governa probabilisticamente as variáveis de interação direta na plataforma, assegurando que métricas como volume de acessos, tempo de tela, taxa de conclusão instrucional, entrega de atividades e assiduidade em fóruns compartilhem correlações críveis e clinicamente significativas com o rendimento e a permanência discente.

O _dataset_ completo foi estruturado e dividido em 4 partes de 5.000 registros cada, geradas a partir de sementes pseudoaleatórias distintas (_seeds_ 42, 2026, 3030 e 4040), de modo que cada partição represente uma amostra empiricamente distinta, porém plenamente coerente com as demais. As quatro partes são diretamente concatenáveis por compartilharem com absoluto rigor a mesma arquitetura de 26 colunas, bem como os mesmos padrões de distribuição estatística, taxas de valores ausentes e injeção controlada de _outliers_.

A distribuição populacional da variável dependente categórica _status_ foi calibrada de modo a refletir a realidade empírica observada em ofertas de disciplinas na modalidade a distância em cursos de tecnologia. O _dataset_ consolida uma proporção aproximada de 58% de estudantes classificados como Aprovado, 22% de discentes categorizados como Reprovado e 20% registrados como Evadido. Essa estratificação preserva o desbalanceamento moderado característico de problemas educacionais reais, viabilizando o estudo crítico de métricas de avaliação que superem a acurácia global, como sensibilidade, precisão, _F1-score_ e área sob a curva _ROC_.

As dimensões de mineração de texto refletidas no atributo _sentiment_score_ foram projetadas para capturar tonalidades afetivas e disposicionais em fóruns de discussão. Estudantes que concluem o semestre com êxito (_status_ Aprovado) exibem um escore de sentimento predominantemente positivo, com média estimada em +0.3 pontos, associado a interações colaborativas e posturas proativas. Em contrapartida, discentes em rota de abandono (_status_ Evadido) manifestam sentimentos médios tendendo à negatividade, com valor médio próximo a -0.2 pontos, refletindo frustrações precoces, desorientação instrucional e pedidos reiterados de suporte registrados em _help_seeking_posts_.

Os arquivos do dataset e o código do Jupyter notebook podem ser baixados em:  
https://github.com/datalibtec/livroPythonERParaDataScience

## Questões que podem ser respondidas com o _Dataset_

1.  Quais fatores de uso e navegação no AVA estão mais fortemente associados ao risco de evasão discente?
2.  É possível prever precocemente, com base no comportamento de acesso das primeiras semanas, se um estudante se encontra em trajetória de abandono?
3.  Estudantes que mantêm uma rotina de acesso mais homogênea e regular (menor valor de _regularity_index_) apresentam taxas de evasão significativamente menores do que estudantes esporádicos?
4.  O aproveitamento formativo médio demonstrado nas baterias de _quizzes_ (_avg_quiz_score_) constitui um preditor estatisticamente relevante do desempenho acadêmico final?
5.  Qual família de algoritmos de aprendizado de máquina supervisionado apresenta o melhor equilíbrio entre acurácia, _recall_ da classe minoritária e métrica _AUC-ROC_ na classificação do _status_ acadêmico?
6.  Quais modelos de regressão linear, regularizada ou baseada em árvores estimam com menor erro (_MAE_, _RMSE_ e maior R²) a nota final consolidada dos matriculados?
7.  O escore de polaridade de sentimento e o volume de solicitações de ajuda nos fóruns de discussão guardam correlação estatisticamente significante com o rendimento final e com o desfecho de evasão?
8.  A disciplina curricular em que o aluno se encontra matriculado exerce influência moderadora sobre as taxas de aprovação, reprovação e evasão escolar na área de computação?

# Análise de Engajamento de Alunos em plataforma AVA

Para fazer as análises dos dados, iremos utilizar o _Jupyter Notebook_ visto em capítulos anteriores;

Aqui carregamos todas as bibliotecas que serão usadas no _notebook_. Cada uma tem um papel específico no _pipeline_ de ciência de dados.

## Métricas de avaliação

A seguir, serão utilizadas as seguintes métricas de avaliação.

_accuracy_score_: proporção de acertos na classificação.

_classification_report_: relatório com precisão, _recall_ e F1 por classe.

_confusion_matrix_: matriz de confusão (acertos e erros por classe).

_roc_auc_score_: área sob a curva _ROC_, mede a capacidade de separar classes.

_mean_absolute_error_, _mean_squared_error_, _r2_score_: métricas de regressão.

## Carga e concatenação das quatro partes do dataset

O _dataset_ completo foi dividido em 4 arquivos _CSV_ de 5.000 registros cada. Carregamos cada parte e as unimos em um único _DataFrame_ com _pd.concat_. Todos os arquivos têm o mesmo formato (mesmas 26 colunas), então a mesma função de leitura é aplicada aos quatro.

IMPORTANTE: os arquivos foram salvos com separador _TAB_ (\\t).

Por isso usamos _sep='\\t'_ na leitura. Sem isso, o _pandas_ leria cada linha inteira como uma única coluna.

Teremos o seguinte resultado ou algo aproximado como:

Verificamos se a concatenação não criou duplicatas. Como cada linha é um estudante único (STU0001 a STU20000), qualquer duplicata indicaria sobreposição entre as partes.

Teremos o seguinte resultado ou algo aproximado como:

Contamos quantos registros vieram de cada parte, usando o prefixo do student_id para identificar a origem. Exemplo: STU0001-STU5000 = parte 1, STU5001-STU10000 = parte 2, etc.

Teremos o seguinte resultado ou algo aproximado como:

## Análise de Engajamento nos Sistemas EaD

O engajamento é o envolvimento comportamental, cognitivo e emocional do estudante, observável pelo rastro digital de interações no AVA. Antes de modelar, precisamos **conhecer os dados**: tipos, distribuições, valores ausentes e outliers.

Teremos o seguinte resultado ou algo aproximado como:

Cria um _DataFrame_ com a descrição de cada coluna, para consulta rápida no estudo. O dicionário de dados documenta o significado de cada coluna, o tipo e as particularidades (valores ausentes, _outliers_). É a referência conceitual que orienta todas as decisões de tratamento e modelagem.

Teremos o seguinte resultado ou algo aproximado como:

_df.describe()_ calcula estatísticas descritivas das colunas numéricas: média, desvio padrão, mínimo, quartis (25%, 50%, 75%) e máximo. O _.T_ transpõe o resultado (linhas viram colunas) para facilitar a leitura.

Teremos o seguinte resultado ou algo aproximado como:

## Verificação de valores ausentes e duplicatas

Teremos o seguinte resultado ou algo aproximado como:

## Tratamento de valores ausentes (imputação pela mediana)

Teremos o seguinte resultado ou algo aproximado como:

## Tratamento de outliers (winsorização pela regra do IQR)

## Engenharia de atributos (índice de engajamento)

Teremos o seguinte resultado ou algo aproximado como:

## Matriz de correlação com as variáveis alvo

Teremos o seguinte resultado ou algo aproximado como:

## Visualizações do engajamento por status

Teremos o seguinte resultado ou algo aproximado como:

Comentário de interpretação

Aprovados tendem a ter mais acessos, mais tempo no ambiente e menor _regularity_index_ (acesso regular e disciplinado). Evadidos concentram baixo engajamento e afastamento precoce das rotinas do AVA. A correlação confirma que o engajamento é o principal motor do desempenho.

## Modelos Preditivos de Desempenho

Aprendizado supervisionado: treinamos modelos com dados rotulados para prever resultados. Aqui fazemos **classificação** (prever o _status_: Aprovado/Reprovado/Evadido) e **regressão** (prever a _final_grade_: nota de 0 a 10).

## Classificação do _status_ (Regressão Logística e _Random Forest_)

Teremos o seguinte resultado ou algo aproximado como:

Teremos o seguinte resultado ou algo aproximado como:

## Regressão da nota final (Linear e _Random Forest_)

Teremos o seguinte resultado ou algo aproximado como:

## Importância de atributos (_Random Forest_)

Teremos o seguinte resultado ou algo aproximado como:

### Comentário de interpretação

O _Random Forest_ tende a superar a Regressão Logística na classificação, com maior _recall_ da classe Evadido, essencial para intervenção precoce. Na regressão, o _Random Forest_ também erra menos (menor _MAE_/_RMSE_) e explica mais a variância (maior R²). O engajamento e as entregas práticas dominam a importância de atributos.

## Mineração de Textos em Fóruns e Atividades

Extraímos sinais do comportamento textual dos estudantes: comprimento das postagens, sentimento e pedidos de ajuda. O texto dos fóruns é uma fonte rica de sinais precoces de risco.

Teremos o seguinte resultado ou algo aproximado como:

## Construção de um corpus sintético de postagens

O _dataset_ não traz o texto bruto das postagens, apenas resumos numéricos (comprimento, sentimento, pedidos de ajuda). Para demonstrar as técnicas de mineração de texto, criamos um _corpus_ sintético: uma função que gera uma postagem representativa para cada estudante, com base no seu perfil.

Teremos o seguinte resultado ou algo aproximado como:

## _TF-IDF_ (transformando texto em números)

Teremos o seguinte resultado ou algo aproximado como:

## Termos mais frequentes por grupo

Teremos o seguinte resultado ou algo aproximado como:

## Sentimento como sinal de risco

Teremos o seguinte resultado ou algo aproximado como:

### Comentário de Interpretação

O sentimento das postagens se correlaciona com o desempenho e diferencia os grupos: aprovados escrevem mensagens mais longas e positivas, evadidos postam pouco e com sentimento negativo. O texto dos fóruns é uma fonte rica de sinais precoces e complementa os dados numéricos de engajamento.

# Considerações Finais

A análise conduzida ao longo do capítulo evidencia que o rastro digital deixado pelos estudantes em um ambiente AVA constitui uma base sólida para compreender e antecipar o desempenho acadêmico. Os indicadores de engajamento, como volume de acessos, tempo de permanência, conclusão de aulas e participação em fóruns, mostraram-se os principais itens do rendimento, enquanto o índice de regularidade revelou que a disciplina de acesso distingue aprovados de evadidos com mais clareza do que qualquer medida isolada de presença. Entre os modelos testados, o _Random Forest_ tendeu a superar a Regressão Logística na classificação do _status_, sobretudo pelo maior _recall_ da classe Evadido, resultado essencial quando o objetivo institucional é permitir intervenção precoce. Na regressão da nota final, o mesmo algoritmo apresentou menores erros e melhor explicação da variância, com engajamento e entregas práticas dominando a importância dos atributos.

A mineração de textos acrescentou uma dimensão complementar e valiosa à análise. O sentimento das postagens correlacionou-se com o desempenho e diferenciou os grupos: aprovados escreveram mensagens mais longas e positivas, enquanto evadidos postaram pouco e com tonalidade negativa, frequentemente marcada por pedidos de ajuda. Esse achado reforça que os fóruns são fonte rica de sinais precoces de risco, capazes de antecipar o abandono antes que ele se materialize nos dados numéricos de acesso.

Do ponto de vista pedagógico, o capítulo demonstra que _Learning Analytics_ não se resume a quantificar acessos, mas a transformar dados em _insights_ acionáveis para educadores. A combinação de métricas comportamentais, modelos preditivos e análise de sentimento forma um mapa detalhado do processo de aprendizagem, viabilizando intervenções precisas tanto no nível coletivo quanto no individual. Como limitações e caminhos futuros, destacam-se a natureza sintética do _dataset_, que embora calibrada com uma variável latente de engajamento não substitui a complexidade dos dados reais, e a possibilidade de ampliar o estudo com técnicas mais avançadas de processamento de linguagem natural e validação cruzada mais rigorosa.

Referências Bibliográficas:

ARVORE, Learning analytics: entenda o que é e quais as vantagens: https://www.arvore.com.br/blog/learning-analytics. Acesso em: 23 set. 2026.

CAFÉ, André. Educação Corporativa, Gestão de Pessoas, HCM. https://www.senior.com.br/blog/learning-analytics. Acesso em: 23 set. 2026.

LIU, Yuxi. Machine learning com Python na prática. São Paulo: Editora Blucher, 2026. E-book. ISBN 9788521227625. Disponível em: https://integrada.minhabiblioteca.com.br/reader/books/9788521227625/. Acesso em: 24 set. 2026.

NETTO, Amilcar; MACIEL, Francisco. Python para Data Science e Machine Learning Descomplicado. Rio de Janeiro: Editora Alta Books, 2021. E-book. p. 121. ISBN 9786555203172. Disponível em: https://integrada.minhabiblioteca.com.br/reader/books/9786555203172/. Acesso em: 20 set. 2026.