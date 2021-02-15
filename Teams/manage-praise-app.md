---
title: Gerenciar o aplicativo Elogiar no Centro de administração do Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: adotey
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Saiba mais sobre as configurações de administração no aplicativo Elogiar no Centro de administração do Microsoft Teams
ms.openlocfilehash: acb9d000aeec61daa35421c5ded389888032873f
ms.sourcegitcommit: d2e67f2eed7b817c2c5f76015ec11582d0e0cb9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2021
ms.locfileid: "50037847"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Gerenciar o aplicativo Elogiar no Centro de administração do Microsoft Teams

> [!NOTE]
> Os administradores devem ter uma licença do Teams para acessar esse recurso. Se você tentar acessar esse recurso sem uma licença do Teams, você verá uma mensagem de erro.

O aplicativo Elogiar no Microsoft Teams ajuda os usuários a mostrar reconhecimento aos membros de sua organização ou sala de aula. Com uma seleção de conjuntos de selos para escolher e a opção de criar seus próprios selos, o Elogio foi projetado para ajudar a reconhecer o esforço que vai para a ampla gama de trabalho que os usuários do Teams fazem, de educadores a Trabalhadores de Linha de Frente. Para saber mais, confira [Enviar Elogios às pessoas.](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)

Os administradores podem controlar quais selos estão disponíveis para sua organização no Centro de administração do Microsoft Teams. No painel de navegação esquerdo, vá para **aplicativos do Teams > Gerenciar aplicativos.** Na lista de aplicativos, **clique** em Elogiar e selecione **Configurações.**  A partir daqui, você pode optar por habilitar conjuntos de selos padrão e integrados e criar selos personalizados.

![Captura de tela da guia Configurações do aplicativo Elogiar](media/manage-praise-app-settings.png)

> [!NOTE]
> O recurso de aplicativo Elogiar não está disponível para nuvens do governo dos EUA.

## <a name="use-built-in-badge-sets"></a>Usar conjuntos de selos integrados

Conjuntos integrados são conjuntos de selos projetados pela Microsoft para o aplicativo Elogiar. Esses conjuntos não são editáveis por administradores. O conjunto de selos padrão já está habilitado e disponível no aplicativo Elogiar. Para alterar a disponibilidade do conjunto padrão ou de qualquer conjunto de selos, alterne o botão de alternância correspondente para Ligar ou Desligar. 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>Selos padrão

O conjunto de selos padrão foi projetado para ajudar os usuários do Teams a reconhecer seus colegas para ir além e acima com seu trabalho.

![Visualização do conjunto de selos padrão](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>Selos de aprendizagem social e emocional para educação

Os educadores podem reconhecer alunos individuais para conquistas e comportamentos de aprendizagem social e emocional (SEL) com selos que ilustram esses conceitos.

![Visualização dos selos de aprendizagem social e emocional para educação](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>Criar seus próprios selos

Selecione **Criar um selo personalizado.** A partir daqui, você pode criar um selo personalizado no painel lateral. Você pode criar até 25 selos personalizados. 

![Captura de tela do painel Criar um selo personalizado](media/manage-praise-app-create-custom-badge.png)

1. Insira um nome de selo. Esse é o nome que aparecerá no selo quando os usuários enviarem elogios.

2. De definir as cores do selo. Para definir as cores de texto e plano de fundo do selo, você precisa inserir as cores como valores hexadecimais (hex).

   > [!TIP]
   > Se você é novo em valores hexaxas, este artigo inclui uma [introdução](#hex-colors-intro) rápida para mostrar como usá-los.

3. Carregar uma imagem de selo. O tipo de arquivo aceito é . Png. O arquivo de imagem deve ter menos de 40 KB com dimensões máximas de 216 X 216 pixels.
![Selo com campos de plano de fundo, texto e imagem rotulados](media/praise-app-badge-fields.png)

4. Localize o nome do selo: Em **Nomes de selo localizados,** selecione **Adicionar.** Selecione a localidade desejada na lista lista listada. Em seguida, insira o nome do selo no idioma designado.

5. Exclua seu selo de localidades específicas: em **Excluir selo dessas localidades,** selecione **Adicionar.** Selecione as localidades que você deseja excluir da lista lista listada.

6. Selecione **Aplicar.** Seu novo selo agora aparecerá na tabela de selos personalizados.

> [!NOTE]
> Se as etapas 4 e 5 foram ignoradas, o selo estará no idioma padrão para todas as localidades.
>
> Quando terminar de fazer alterações na seleção do selo, selecione **Enviar.** Pode levar até algumas horas até que essas alterações sejam disponibilizadas para sua organização.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>Especificar cores com valores hexaxa

Os valores de cores hexadecimais são cadeias de caracteres de seis dígitos hexadecimais que representam a intensidade de vermelho (RR), verde (GG) e azul (BB) em uma cor específica em uma escala de 00 a FF. Quando você coloca os valores de todas as três cores juntas, você tem um valor hexaxa: #RRGGBB

Por exemplo, o valor hexaxa para a cor vermelha é #FF0000 porque vermelho é definido no valor mais alto possível, FF e verde e azul são cada um definido no menor valor possível, 00.

Para explorar cores diferentes e seus valores hexadados, confira o selador de cores [do Bing.](https://www.bing.com/search?q=color+picker)

Veja a seguir uma lista de cores de exemplo para você começar:

|Cor  |Valor hexaxa|
|-------|---------|
|![cor hex #FF6666](media/hexColor1.png)|  #FF6666   |
|![hex color #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![cor hex #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![cor hex #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![cor hex #800080](media/hexColor5.png)|  #800080   |
|![cor hex #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>Práticas recomendadas para a criação de selos personalizados

**Envie todos os seus selos ao mesmo tempo.** Como leva algum tempo para que novos selos sejam processados, é melhor adicionar todos os selos personalizados à tabela antes de enviar.

**Ao escolher cores, lembre-se da acessibilidade.** Algumas cores são melhores juntas do que outras.  Crie contraste entre as cores do texto e do plano de fundo para facilitar a leitura do nome do selo. Por exemplo, se você escolher uma cor de plano de fundo escura, escolha uma cor de texto clara.

**Ao selecionar uma imagem, lembre-se das dimensões do selo.** Para ter a melhor qualidade, é recomendável carregar um arquivo de imagem de 216 x 216 pixels (que são as dimensões máximas). Evite alongar ou distorcer a imagem para se ajustar a essas dimensões.

**Se sua imagem de selo não for retangular, tornar a imagem transparente.** Você precisará fazer isso antes de carregar o arquivo de imagem para Elogio.

![Esquerda: selo com imagem não transparente, direita: selo com imagem transparente](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>Ativos de conjunto de selos

Conjuntos de selos integrados não podem ser modificados, portanto, quando um conjunto integrado está habilitado, todos os selos no conjunto são adicionados ao aplicativo Elogiar. Se você quiser adicionar selos específicos de um conjunto integrado e deixar outras pessoas de fora, crie os selos que deseja usar como selos personalizados. Você pode baixar a imagem do selo e encontrar as cores de texto e plano de fundo de selos de conjuntos integrados nas tabelas abaixo.

### <a name="default-badges-assets"></a>Ativos de selos padrão

</br>

|Nome do selo     |Arquivo de imagem  |Cor do texto | Cor da tela de fundo |
|---------------|------------|---------- |--------|
|Empreendedor       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|Incrível        |[PNG incrível](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|Treinador          |[Treinador PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Coragem        |[PNG Desanimo](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Criativo       |[Creative PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|Inclusive      |[PNG inclusivo](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Kind Heart     |[Kind Heart PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|Liderança     |[PNG de liderança](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|Otimismo       |[PNG Desvamo](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|Solucionador de problemas |[PNG do solucionador de problemas](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|Jogador da equipe    |[Team player PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|Obrigado      |[Obrigado PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>Selos de aprendizagem social e emocional para ativos de educação

</br>

|Nome do selo        |Arquivo de imagem  |Cor do texto | Cor da tela de fundo |
|------------------|------------|---------- |--------|
|Comunicação     |[PNG de comunicação](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|Pensamento crítico |[PNG de pensamento crítico](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Curiosidade         |[PNG de PNG Desving](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Empatia           |[PNG de empática](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|Busca de meta      |[Busca de meta PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|Motivação        |[Motivação PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|Persistência       |[PNG persistente](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|Respeito           |[Respeitar PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|Responsabilidade    |[Responsabilidade PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|Autoconhecimento    |[Autoconhecimento PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|Autocontrole   |[PNG de auto-gerenciamento](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Thoughtfulness    |[PNG de consideração](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
