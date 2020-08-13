---
title: Gerenciar o aplicativo elogio no centro de administração do teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Saiba mais sobre as configurações de administrador no aplicativo elogios no centro de administração do Microsoft Teams
ms.openlocfilehash: 2fa2f7e92646dafe3d8bf1cc39325a682c823686
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656302"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Gerenciar o aplicativo elogios no centro de administração do Microsoft Teams

O aplicativo elogios no Microsoft Teams ajuda os usuários a mostrarem reconhecimento de seus membros da organização ou da sala de aula. Com uma seleção de conjuntos de emblemas para escolher e a opção para criar seus próprios selos, elogios é projetado para ajudar a reconhecer o esforço que entra na ampla gama de trabalho que os usuários do teams fazem, dos educadores até a primeira linha de funcionários.

Os administradores podem controlar quais selos estão disponíveis para sua organização a partir do centro de administração do teams. No painel de navegação esquerdo, selecione **aplicativos do teams > gerenciar aplicativos**. Abra elogios no [Catálogo de aplicativos do locatário](https://docs.microsoft.com/microsoftteams/manage-apps#view-apps-in-your-tenant-app-catalog)e vá para **configurações**.

## <a name="use-built-in-badge-sets"></a>Usar conjuntos de emblemas internos

Conjuntos internos são conjuntos de selos projetados pela Microsoft para o aplicativo elogio. Esses conjuntos não são editáveis por administradores. O conjunto de emblemas padrão já está habilitado e disponível no aplicativo elogio. Para alterar a disponibilidade do conjunto padrão ou de qualquer conjunto de selos, alterne o botão de alternância correspondente para ativado ou desativado. 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>Emblemas padrão

O conjunto de emblemas padrão foi projetado para ajudar os usuários do teams a reconhecerem seus colegas de trabalho para ultrapassarem o seu trabalho.

![Visualização do conjunto de emblemas padrão](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>Selos de aprendizagem sociais e emocional para educação

Educadores podem reconhecer alunos individuais para conquistas e comportamentos sociais e de aprendizagem emocional (SEL) com emblemas que ilustram esses conceitos.

![Visualização dos selos de aprendizagem sociais e emocional para educação](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>Criar seus próprios selos

Alterne o botão de alternância de **notificações personalizadas** para ativado e selecione **criar um selo personalizado**. A partir daí, você pode criar um emblema personalizado no painel lateral. Você pode criar até 25 selos personalizados. 

1. Digite o nome do selo. Esse é o nome que aparecerá no selo quando os usuários enviarem elogios.

2. Defina as cores do selo. Para definir as cores de texto e de plano de fundo do selo, você precisa inserir as cores como valores hexadecimais (Hex).

   > [!TIP]
   > Se você não tem experiência com valores hexa, este artigo inclui uma [rápida introdução](#hex-colors-intro) para mostrar como usá-los.

3. Carregar uma imagem de selo. O tipo de arquivo aceito é. Formato. O arquivo de imagem deve ter menos de 40 KB com dimensões máximas de 216 X 216 pixels.
![Selo com campos de plano de fundo, texto e imagem rotulados](media/praise-app-badge-fields.png)

4. Localize o nome do seu selo: em **nomes de selo localizados**, selecione **Adicionar**. Selecione o local desejado na lista suspensa. Em seguida, digite o nome do selo no idioma designado.

5. Exclua seu selo de localidades específicas: em **excluir selo destas localidades**, selecione **Adicionar**. Selecione as localidades que você deseja excluir na lista suspensa.

6. Selecione **aplicar**. Seu novo emblema aparecerá na tabela de selos personalizados.

> [!NOTE]
> Se as etapas 4 e 5 forem ignoradas, o selo estará no idioma padrão para todos os locais.
>
> Quando terminar de fazer alterações na seleção do selo, selecione **Enviar**. Pode levar algumas horas para que as alterações sejam disponibilizadas para a sua organização.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>Especificar cores com valores hexadecimais

Os valores de cor hexa são cadeias de seis dígitos hexadecimais que representam a intensidade de vermelho (RR), verde (GG) e azul (BB) em uma cor específica em uma escala de 00 até FF. Quando você coloca os valores de todas as três cores juntas, obtém um valor hex: #RRGGBB

Por exemplo, o valor hex para a cor vermelho é #FF0000 porque o vermelho está definido no valor mais alto possível, FF e verde e azul são definidos no valor mais baixo possível, 00.

Para explorar diferentes cores e seus valores hexadecimais, confira o [seletor de cores do Bing](https://www.bing.com/search?q=color+picker).

Veja a seguir uma lista de cores de exemplo para ajudá-lo a começar:

|Cor  |Valor hex|
|-------|---------|
|![#FF6666 de cores hexa](media/hexColor1.png)|  #FF6666   |
|![#7FFFD4 de cores hexa](media/hexColor2.png)|  #7FFFD4   |
|![#FF75F0 de cores hexa](media/hexColor3.png)|  #FF75F0   |
|![#00BFFF de cores hexa](media/hexColor4.png)|  #00BFFF   |
|![#800080 de cores hexa](media/hexColor5.png)|  #800080   |
|![#000000 de cores hexa](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>Práticas recomendadas para a criação de selos personalizados

**Envie todos os seus selos ao mesmo tempo.** Como demora um tempo para que novos selos sejam processados, é melhor adicionar todos os seus selos personalizados à tabela antes de enviá-los.

**Ao escolher as cores, mantenha a acessibilidade em mente.** Algumas cores se unem melhor do que outras.  Crie contraste entre as cores do texto e do plano de fundo para facilitar a leitura do nome do selo. Por exemplo, se você tiver escolhido uma cor de fundo escura, escolha uma cor de texto claro.

**Ao selecionar uma imagem, mantenha as dimensões do selo em mente.** Para obter a melhor qualidade, recomendamos carregar um arquivo de imagem que seja 216 x 216 pixels (que são as dimensões máximas). Evite redimensionar ou distorcer a imagem para ajustá-las a essas dimensões.

**Se a sua imagem do selo não for retangular, torne a imagem transparente.** Você precisará fazer isso antes de carregar o arquivo de imagem para elogios.

![Esquerda: selo com imagem não transparente, direita: selo com imagem transparente](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>Ativos do conjunto de notificações

Os conjuntos de emblemas internos não podem ser modificados, portanto, quando um conjunto interno está habilitado, todos os selos do conjunto são adicionados ao aplicativo elogio. Se você quiser adicionar notificações específicas de um conjunto interno e deixar os outros, crie novamente os selos que deseja usar como crachás personalizados. Você pode baixar a imagem do selo e localizar as cores do texto e do plano de fundo dos emblemas de conjuntos internos nas tabelas abaixo.

### <a name="default-badges-assets"></a>Ativos de emblema padrão

</br>

|Nome do selo     |Arquivo de imagem  |Cor do texto | Cor da tela de fundo |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|Awesome        |[PNG incrível](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png>Awesome.PNG)</a>|#8283B2    |#D1EFF2|
|Executiva          |[O PNG do treinador](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Impedir        |[PNG recomendável](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Financiamento       |[PNG criativo](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|Incluindo      |[PNG inclusivo](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Tipo de coração     |[Tipo de coração PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|Liderança     |[PNG de liderança](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership.pn)|#419098    |#D2EAEC|
|Melhoridade       |[PNG de melhoridade](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|Solucionador de problemas |[Resoluções de problemas PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|Reprodutor de equipe    |[PNG do Team Player](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|Obrigado      |[Agradecimento PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>Selos de aprendizagem sociais e emocional para ativos de educação

</br>

|Nome do selo        |Arquivo de imagem  |Cor do texto | Cor da tela de fundo |
|------------------|------------|---------- |--------|
|Telecomunicações     |[PNG de comunicação](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|Raciocínio crítico |[PNG de raciocínio crítico](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Curiosidade         |[PNG da curiosidade](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Empathy           |[Empathy PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|Acompanhamento de metas      |[PNG de acompanhamento de metas](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|Motivação        |[PNG de motivação](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|Persistência       |[PNG de persistência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|À           |[Respeitar o PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|Responsabiliza    |[PNG de responsabilidade](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|Auto-reconhecimento    |[PNG de auto-reconhecimento](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|Gerenciamento automático   |[PNG de gerenciamento automático](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Consideração    |[PNG de consideração](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
