# Objetivos desta guia
Criar uma apresentação simples e prática sobre o formato ePub3 as suas vantagens.

**Importante:** O texto abaixo está defasado e requer ajustes para adequar ao ePub 3.1.

# Atualizações deste documento
- Criação do documento baseando-se em um texto de 2016
- versão 0.1 do documento
- Data atualização: 8 junho de 2017

# O que é o ePub3
Depois de muitos meses de trabalho o IDPF terminou de preparar as especificações do ePub3. Trata-se de uma revisão das especificações anteriores, sobretudo em vista de conteúdo multimídia. O ePub3 acrescenta elementos novos como a possibilidade de inserir facilmente vídeo e áudio e de acrescentar alguns elementos interativos. Isto graças à adoção do html5 como base para o conteúdo. Além disto, a adoção de elementos do CSS3 permite um design mais elaborado, até mesmo animações feitas diretamente com CSS.

Além disto, e ePub 3 procura integrar de forma mais completa elementos já presentes e utilizáveis no ePub, como o SVG, o Math ML e recursos de sincronização de áudio e com a leitura do texto.

Estas especificações já estão aprovadas e disponíveis no site do IDPF, mas o grande problema é a ausência de um verdadeiro leitor de ePub3. Até o presente momento nenhuma software house disponibilizou estes recursos. É uma questão de tempo, pois com a chegada de mais tablets no mercado com recursos avançados aumentam o espaço e a necessidade de um conteúdo que desfrute estas funcionalidade.

# As especificações do ePub3
Internamente, o ePub mudou quase por completo, em especial sua estrutura e organização dos arquivos.  A lista de tecnologias que envolve o ePub cresceu, e agora inclui, entre outras: xhtml5, SVG, css3, WOFF e Javascript. Uma boa definição para o ePub3 seria o de container que transforma estas tecnologias em uma nova experiência de leitura. As especificações intimidam pelo tamanho e quantidade de hyperlinks e referências. Segue aqui um resumo sobre as novas especificações do ePub:
ePub Publications 3.0

Arquivo xml utilizado no pacote de informações sobre o ePub: metadata (titulo, autor, idioma), listas dos elementos contidos no ePub, ordem de leitura, entre outros. Trata-se do antigo Content.opf com novas opções.

## ePub Content Documents 3.0
Esta especificação substitui a antiga Open Publication Structure 2.0.1 na tarefa de descrever o perfil das principais tecnologias contidas no ePub – xhtml5, SVG 1.1 e css 3 – e utilizadas para formatar e estruturar o conteúdo. Nesta revisão, a navegação pela tag NAV, foi incluída no Content Documents em substituição ao NCX da antiga OPF – Open Publication Format. Contudo, o ePub3 continua a oferecer pleno suporte ao NCX, assegurando a navegação de ebooks em dispositivos compatíveis apenas com ePub2.

## ePub Media Overlays 3.0
Este é o “irmão” mais novo das especificações do formato ePub. Sua sintaxe é baseada na especificação SMIL – Synchronized Multimedia Integration Language, e através de suas tags é possível associar texto e áudio na sequência de leitura.
ePub Open Container Format (OCF) 3.0
E por fim, o Open Container Format é responsável pelo empacotamento de todos as arquivos acima mencionados em um grande ZIP, chamado ePub. Essa especificação não sofreu significativas mudanças.
Características práticas do ePub3

## HTML5
Para esclarecer, html5 é a linguagem base do ePub 3 (com alguns pequenos ajustes para permitir a paginação e outros comportamentos de leitura). Uma vez que o conteúdo do ePub 3 é escrito em html5,  ele irá desfrutar de todas as características implementadas do html5.
Os sistemas de leituras do ePub 3 devem ser capazes de processar arquivos xhtml escritos em html5. Isso não significa que os navegadores web serão capaz de exibir arquivos ePub, a menos que sejam capazes de processar as informações de navegação adicionais contidas no arquivo ePub. Já existem alguns sistemas de leitura que são implementados dentro de um ambiente de navegador (como o complemento para Firefox ePubReader).

## CSS
A nova base para as folhas de estilo é o css2.1 com alguns complementos do css3 inclusos. Isto fornece um layout muito mais completo, incluindo visualização em múltiplas colunas, melhor suporte a fonte e impressão direcionada, para citar alguns. Não é necessário que os sistemas de leitura suportem o css, mas quase todos eles fazem isso. Uma das principais causas de frustração é a diferença de suporte ao css entre os sistemas de leitura.
No ambiente atual do ePub, muitos sistemas de leitura não permitem que as folhas de estilo dentro de um arquivo ePub substituam as configurações padrão do sistema. O ePub 3 não faz nada para aliviar esta situação e, de fato, podem até piorar um pouco devido aos recursos adicionais que serão possíveis com ele. Sistemas de leitura também têm a capacidade de implementar suas próprias extensões de css, que são ignoradas por outros sistemas de leitura.

## Áudio
O áudio pode ser inserido em arquivos do ebook usando a tag <audio> do html5. Isso é o que a Apple, Barnes & Noble e Amazon têm utilizado para inserir áudio nos enhanced ebooks (ebooks melhorados, com algum "extra"). Agora, é simplesmente parte das especificações do ePub 3. Não é necessário que os sistemas de leitura suportem áudio, embora quase todos eles façam isso. Se um sistema de leitura suporta áudio, ele deve oferecer suporte a MP3. Além disso, o suporte aos formatos MP4 e AAC (explicado mais adiante) é opcional.

## Vídeo
O vídeo pode ser inserido em arquivos de ebook usando a tag <video> do html5. Novamente, isso é o que já vem ocorrendo. E, novamente, não é necessário que os sistemas de leitura suportem vídeo. Na verdade, a maioria dos dispositivos de e-Ink não são capazes de mostrar o vídeo de forma satisfatória.

Um dos principais pontos de discordância com as especificações do ePub 3 é que não existe um formato especificado que deva ser suportado. Se um sistema de leitura suporta vídeo, a especificação recomenda o apoio de pelo menos um ou ambos os H.264 (também conhecidos como MPEG-4 AVC) ou os formatos de compressão de vídeo VP8, mas isso também não é obrigatório. Infelizmente, a especificação também não diz se algum formato não é permitido. Essencialmente, não há nada que impeça um desenvolvedor de sistemas de leituras de implementar algum outro formato de vídeo (como o Flash). O que acontecerá ainda veremos, mas há uma abertura disponível.

Nesse meio tempo, os editores precisarão preparar vídeos em ambos os formatos para apoiar a mais vasta gama de sistemas de leitura. Como já foi discutido no passado, isso poderia levar a grandes arquivos de ePub 3, ou diferentes versões que serão direcionadas a sistemas de leitura específicos (um para o iPad, um para webkit, etc.).

## Sobreposições de mídia
A funcionalidade da sobreposição foi adicionada à especificação para permitir que o texto e mídia possam ser apresentados de forma combinada. Por exemplo, realçar o texto enquanto ele é lido em voz alta pelo computador, ou como parte de uma trilha sonora. Para empregar essas sobreposições, será necessário criar arquivos especiais Synchronized Multimedia Integration Language (SMIL).

Sistemas de leitura não são obrigados a fornecer essa funcionalidade, mas se fizerem isso, devem permitir que os leitores ignorem ou pulem essas sobreposições. Sobreposições também podem ser usadas para disponibilizar a função text-to-speech, que lê o texto em voz alta A especificação do ePub 3 menciona a Especificação Lexicon de Pronúncia (PLS) e o Speech Synthesis Markup Language (SSML) para dar suporte na geração de voz sintética, mas não requer que os sistemas de leitura usem essa informação.

## SVG
Os arquivos Scalable Vector Graphic (SVG) já são permitidos dentro de arquivos ePub há algum tempo. No entanto, seu uso era limitado, em grande parte devido à falta de suporte pelo sistema de leitura. O ePub 3 agora obriga que os sistemas de leitura sejam capazes de processar o SVG dentro do ebook, inclusive permitindo que os usuários selecionem texto e pesquisa dentro do conteúdo desse formato. A única parte do SVG que não é permitida é a capacidade de animação.

## MathML
O MathML é parte do html5 e, portanto, é parte do ePub 3. Os sistemas de leitura devem ser capazes de processar a forma de apresentação do MathML, mas também podem suportar a forma de conteúdo do MathML. Não vamos entrar em muitos detalhes aqui. Mas as editoras que lidam com conteúdo matemático e científico podem estar interessadas, uma vez que essas mudanças irão permitir que fórmulas possam ser incluídas como parte da marcação xhtml em vez de serem inseridas como imagens. Isso significa que o conteúdo será redimensionável, entre outras coisas. Ainda é recomendado que as imagens das fórmulas sejam incluídas como fallbacks.

## Recursos externos
Os recursos externos são “pedaços de conteúdo” não necessariamente aceitos pela especificação do ePub. Por exemplo, pdfs podem ser considerados recursos estrangeiros. Podem existir casos onde arquivos pdf são incorporados em arquivos ePub. Quando isso é feito, pelo menos um fallback (talvez um equivalente de texto simples) deve ser incluído para permitir que sistemas de leitura que não suportam esse recurso possam funcionar normalmente.

## Scripts
Scripts e interatividade são outros dos recursos mais esperados do ePub 3. Mais uma vez o ePub 3 recebe esta funcionalidade através do html5. Geralmente isso significa JavaScript, mas esta não é a única opção. Enquanto os scripts podem deixar tênues a linha entre ebooks e aplicativos, deve ser notado que os sistemas de leitura não precisam suportar esse recurso. Além disso, sistemas de leitura têm a capacidade de colocar limitações adicionais sobre os recursos fornecidos para scripts por uma variedade de razões, incluindo segurança e capacidade de processamento. Dito isto, os editores devem já pensar em maneiras possíveis para que o conteúdo possa ser mais interativo e começar a planear a criação dessas melhorias. Como sempre, eles também devem se certificar de que a experiência de leitura não será afetada se um leitor decidir desligar os scrips, ou se um sistema de leitura não tiver suporte a eles.

## Links
O ePub3 criou uma especificação Canonical Fragment Identifier (EPUBCFI) para criar e acessar vários locais dentro do conteúdo. Isto permite um refinado acesso ao conteúdo, mesmo ao nível de uma palavra ou frase. O uso desta especificação poderia permitir aos índices o link para uma exata palavra dentro do conteúdo. É também a base da especificação de uma futura interligação entre documentos.

## Acessibilidade
Na verdade, o ePub 2.0.1 consiste em dois esquemas — ePub e DTBook. O DTBook tinha a intenção de fornecer conteúdo aos sistemas de apoio para pessoas com deficiência visual através de leitores de Braille e outras tecnologias. Por causa das características de acessibilidade já inclusas no html5, foi decidido que o DTBook seria descontinuado e suas funcionalidade poderiam ser inseridas no ePub. Então, tecnicamente, os arquivos ePub 3 são acessíveis a partir "do design".
Os editores devem fazer tudo dentro da razão para garantir que todos os itens dentro de seu conteúdo são acessíveis. Isto inclui as descrições de todas as imagens e textos alternativos para o MathML e scripts.

## Prospectivas práticas para o editor
A chegada do ePub3 trás consigo nosas prospectivas para a editoria digital e também novos desafios. A evolução do formato ePub como vimos, permitirá a presença de elementos multimídia que desfrutem a capacidade dos aparelhos leitores mais modernos já presentes no mercado ou que em breve chegarão, mas aumenta a necessidade de pensar o conteúdo para uma nova plataforma com o acréscimo de elementos bem diferentes e mais complexos do que o simples texto, requerendo assim  a figura de novos profissionais.

A grande vantagem é a facilidade técnica de acrescentar recursos como áudio e vídeo que o html5 oferecer, por outro lado será necessário preparar e editar este material audiovisual de modo coerente com o resto do texto. Este será o desafio maior para os editores, conseguir produzir ou escolher qual material é mais adapto a um determinado conteúdo. Isto aumenta ainda mais a importância do editor pois perante a facilitação que o formato oferece em acrescentar elementos interativos será necessário uma capacidade maior de discernimento profissional para a criação de um produto de alta qualidade onde a interatividade não seja mero enfeite mas traga algo de novo ao conteúdo.

Sem dúvidas para o setor do livro infantil o ePub3 oferece a possibilidade de aumentar a produção de livros interativos ou animados sem os custos que a produção de um aplicativo contém. O fato do ePub3 poder funcionar em várias plataformas permanece a grande vantagem do formato respeito a outras soluções não multiplataforma.