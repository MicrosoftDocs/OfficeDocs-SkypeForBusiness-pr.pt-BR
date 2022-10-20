---
title: Guia de acessibilidade para administradores do Microsoft Teams
ms.author: meghan
author: meganrmhan
ms.reviewer: eljones
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Melhore a acessibilidade no Microsoft Teams ativando legendas e transcrição, dando acesso à reunião para interpretadores de idiomas de sinal e legendas CART, reduzindo distrações, melhorando a participação e compartilhando recursos.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- M365-collaboration
ms.openlocfilehash: 7b089785695e9bef985107b5f1db8e5659c48c33
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614688"
---
# <a name="accessibility-guide-for-microsoft-teams-admins"></a>Guia de acessibilidade para administradores do Microsoft Teams

Como administrador do Microsoft Teams para sua organização, você pode ajudar a tornar seu ambiente do Teams o mais inclusivo e acessível possível para todos os usuários. Siga os guias e recursos abaixo para configurar o Microsoft Teams para acessibilidade ideal.

> [!NOTE]
> Muitas das opções de acessibilidade estão ativadas por padrão, mas você pode verificar se elas não foram desativadas seguindo as etapas neste guia.

## <a name="turn-on-captions-and-transcription-for-meetings-and-calls"></a>Ativar legendas e transcrição para reuniões e chamadas

Crie reuniões inclusivas e chamadas para usuários com deficiências para que todos possam participar e contribuir.

### <a name="turn-on-live-captions-for-meetings"></a>Ativar legendas ao vivo para reuniões

Legendas ao vivo são texto gerado automaticamente em tempo real do que é dito em uma reunião. Eles aparecem algumas linhas por vez para um usuário que as ativou e não foram salvas.

Para ativar legendas ao vivo para usuários:

1. No centro de administração do Microsoft Teams, vá **para Reuniões** e selecione as políticas de **reunião suspensas**.

2. Selecione a política que você deseja modificar.

3. Vá para **a seção Participantes & convidados** .

4. **Alterne as legendas ao vivo** **para Não habilitado, mas o usuário pode substituir**.

5. Selecione **Salvar**.

> [!TIP]
> Compartilhe o link a seguir para que os usuários possam aprender [a ativar legendas ao vivo durante as reuniões](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop).

> [!NOTE]
> Legendas ao vivo estão disponíveis para reuniões realizadas em Organizações comerciais e da GCC (Nuvem da Comunidade Governamental) dos EUA.

### <a name="turn-on-transcription-for-calls"></a>Ativar a transcrição para chamadas

A transcrição é gerada automaticamente, com texto gravado do que foi dito em uma chamada. Quando ativada, a transcrição fica disponível para os usuários revisarem após o fim de uma chamada.

Para ativar a transcrição para usuários:

1. No centro de administração do Microsoft Teams, vá para **o Voice** e selecione as políticas de **chamada suspensas**.

2. Selecione a política que você deseja modificar.

3. **Ative a** **Transcrição** e selecione **Salvar**.

### <a name="why-captions-and-transcripts-are-important"></a>Por que legendas e transcrições são importantes

Legendas e transcrições são versões de texto das palavras que alguém está falando. Elas dão às pessoas a opção de ver o texto além de, ou em vez de, somente áudio. As legendas também beneficiam pessoas com deficiência auditiva ou com deficiência auditiva, fornecendo informações adicionais sobre o que alguns usuários recebem do interpretador de linguagem de sinais ou do legenda CART com o qual eles podem trabalhar.

Legendas e transcrição são úteis em uma ampla variedade de situações, mas podem ser especialmente úteis para:

- Pessoas que são surdos ou difíceis de ouvir

- Pessoas com deficiências de aprendizado

- Pessoas que estão em um ambiente barulhento ou confuso e precisam revisar as informações compartilhadas após o fim de uma reunião

Para obter mais informações, consulte os seguintes links:

- [Configurações de política de reunião para gravação e transcrição](/Microsoftteams/meetings-policies-recording-and-transcription)

- [WCAG (Diretrizes de Acessibilidade de Conteúdo da Web) 1.2.4.: Legendas (ao vivo)](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

## <a name="give-meeting-access-to-sign-language-interpreters-and-cart-communication-access-real-time-translation-captioners"></a>Fornecer acesso de reunião a interpretadores de idioma de sinal e legendas cart (Tradução em tempo real do Acesso à Comunicação)

Conceda aos intérpretes de linguagem de sinais e aos legendas cart (tradução em tempo real de acesso de comunicação) acesso às reuniões do Microsoft Teams para que eles possam trabalhar com mais eficiência junto com usuários surdos ou com deficiência auditiva.

### <a name="admit-sign-language-interpreters-and-cart-captioners-to-meetings"></a>Admitir interpretadores de linguagem de sinais e legendas CART em reuniões

Interpretadores de linguagem de sinais e legendas cart provavelmente não funcionam para sua organização, mas você pode convidá-los para reuniões do Microsoft Teams fornecendo a eles [acesso de convidado](/MicrosoftTeams/guest-access).

Depois que o acesso de convidado tiver sido fornecido, para admitir interpretadores de linguagem de sinais e legendas cart para reuniões:

1. No centro de administração do Microsoft Teams, vá **para Reuniões** e selecione as políticas de **reunião suspensas**.

2. Selecione a política que você deseja modificar.

3. Vá para **a seção Participantes & convidados** .

4. Escolha a opção em **Admitir automaticamente as pessoas** que melhor se ajustam aos requisitos de conformidade e segurança da sua organização. Você pode selecionar uma das seguintes opções:

   - Todos (não recomendado)

   - Pessoas em minha organização e convidados (recomendado)

   - Pessoas da minha organização e organizações confiáveis

   - Pessoas da minha organização

   - Organizador somente

   - Somente usuários convidados

5. Selecione **Salvar**.

> [!NOTE]
> A **configuração Admitir automaticamente que** as pessoas não se aplicam a usuários de discagem.

### <a name="turn-on-ip-video-feed-for-your-users"></a>Ativar o feed de vídeo IP para seus usuários

Dê aos interpretadores de linguagem de sinais a capacidade de compartilhar feed de vídeo IP durante reuniões do Microsoft Teams para que eles possam se comunicar com usuários surdos ou com deficiência auditiva.

Para verificar se o feed de vídeo IP está ativado:

1. No centro de administração do Microsoft Teams, vá **para Reuniões** e selecione as políticas de **reunião suspensas**.

2. Selecione a política que você deseja modificar.

3. Vá para a **seção áudio & vídeo** .

4. Verifique se **o vídeo IP** está **ativado e** selecione **Salvar**.

> [!TIP]
> Compartilhe os links a seguir com os usuários para que eles possam ajustar como usam o Teams para maximizar a capacidade de participar, se concentrar e colaborar em reuniões:
> - [Personalizar o modo de exibição de reunião](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)
> - [Usar legendas CART](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

### <a name="why-its-important-to-include-sign-language-interpreters-and-cart-captioners"></a>Por que é importante incluir interpretadores de linguagem de sinais e legendas cart

Alguns usuários podem preferir usar legendas CART porque podem ser mais precisos para jargões, acentos e muito mais específicos do que legendas geradas automaticamente.

Os usuários cujo principal método de comunicação é a linguagem de sinais exigem interpretação de linguagem de sinais, o que exige que um interpretador humano esteja presente.

Para obter mais informações, consulte o WCAG (Guia de Acessibilidade de Conteúdo da [Web) 1.2.6.: Interpretação da linguagem de sinal](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded).

## <a name="reduce-distractions-in-meetings"></a>Reduzir distrações em reuniões

Incentive a participação do usuário ativando filtros de vídeo para reduzir distrações em reuniões do Teams.

### <a name="turn-on-video-filters"></a>Ativar filtros de vídeo

Os filtros de vídeo ajudam a reduzir as distrações durante as reuniões.

Para ativar filtros de vídeo:

1. No centro de administração do Microsoft Teams, vá **para Reuniões** e selecione as políticas de **reunião suspensas**.

2. Selecione a política que você deseja modificar.

3. Vá para a **seção Compartilhamento de** conteúdo.

4. Escolha a opção em **Selecionar filtros de vídeo** que melhor atendam aos requisitos de conformidade e segurança da sua organização. Selecione uma das seguintes opções:

   - Somente desfoque de plano de fundo

   - Desfoque de plano de fundo e imagens padrão

   - Todos os filtros

5. Selecione **Salvar**.

> [!TIP]
> Compartilhe os links a seguir para que os usuários possam ajustar suas preferências de reunião do Teams para reduzir as distrações:
> - [Alterar efeitos de plano de fundo em reuniões do Teams](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)
> - [Reduzir o ruído de fundo em reuniões do Teams](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

### <a name="why-its-helpful-to-reduce-distractions"></a>Por que é útil reduzir distrações

Algumas pessoas em sua organização podem achar difícil se concentrar durante reuniões em vídeo e chamadas devido ao movimento, luz e outras distrações nos planos de fundo dos participantes. O uso de filtros de vídeo ajuda os usuários a controlar distrações e participar totalmente.

*Os efeitos de* tela de fundo podem ajudar as pessoas a se concentrarem no alto-falante em vez de na tela de fundo do locutor. O Microsoft Teams tem uma biblioteca de telas de fundo e os usuários também podem carregar suas próprias.

*O desfoque* de plano de fundo ajuda a melhorar a visibilidade e o foco em reuniões ou chamadas porque reduz distrações em segundo plano, mas mantém os usuários em foco.

Os filtros de vídeo são úteis em uma ampla variedade de situações, mas podem ser especialmente úteis para:

- Pessoas que são neurodiverso

- Pessoas que são surdos ou difíceis de ouvir

Para obter mais informações, consulte WCAG (Diretriz de Acessibilidade de Conteúdo da [Web) 1.4.8.: Apresentação Visual](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html).

## <a name="improve-participation-in-microsoft-teams-meetings"></a>Melhorar a participação em reuniões do Microsoft Teams

Incentive a participação do usuário com mais opções de controle e flexibilidade ativando o **Chat** em reuniões e políticas de mensagens, como edição de **chat, Leitura Avançada** e emojis.

### <a name="turn-on-chat-in-meetings"></a>Ativar o chat em reuniões

O chat facilita para muitos usuários fazer perguntas ou adicionar informações em reuniões do Teams.

Para verificar se o chat na reunião está ativado:

1. No centro de administração do Microsoft Teams, vá **para Reuniões** e selecione as políticas de **reunião suspensas**.

2. Selecione a política que você deseja modificar.

3. Vá para **a seção Participantes & convidados** .

4. Escolha a opção em **Chat em reuniões que** melhor atendam aos requisitos de conformidade e segurança da sua organização. Você pode selecionar uma das seguintes opções:

   - Ativá-lo para todos (recomendado)

   - Desativá-lo para todos (não recomendado)

   - Ativá-lo para todos, exceto usuários anônimos

5. Selecione **Salvar**.

### <a name="use-messaging-policies-for-increased-flexibility-and-control"></a>Usar políticas de mensagens para aumentar a flexibilidade e o controle

As opções de chat flexíveis facilitam para muitos usuários entenderem as mensagens dos outros, revisarem suas próprias mensagens e se expressarem.

Para verificar se essas opções de chat flexíveis estão ativadas:

No centro **de administração do Microsoft Teams**:

1. No centro de administração do Microsoft Teams, acesse **políticas de mensagens**.

2. Selecione a política que você deseja modificar.

3. Verifique se os seguintes itens estão **ativados**:

   - **Excluir mensagens enviadas**

   - **Editar mensagens enviadas**

   - **Chat**

   - **Giphys em conversas**

   - **Memes em conversas**

   - **Adesivos em conversas**

   - **Visualizações de URL**

   - **Traduzir mensagens**

   - **Leitura avançada para mensagens**

4. Selecione **Salvar**.

> [!TIP]
> Compartilhe o link [de como escrever texto Alt efetivo](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2) com sua organização para ajudar os usuários a entender mensagens que não são de texto compartilhadas no chat.

### <a name="why-alternate-participation-options-matter"></a>Por que as opções de participação alternativas importam

As opções de chat flexíveis oferecem às pessoas maior flexibilidade em como elas usam conteúdo de chat na reunião e mais controle sobre como participam de uma reunião com chat.

*O chat na reunião* oferece às pessoas outra maneira de participar da discussão da reunião. Para algumas pessoas com deficiências, o chat pode ser preferível à linguagem de voz ou de sinais como uma maneira de contribuir para discussões de reunião.

*Leitura Avançada*, uma ferramenta projetada para pessoas com dislexia e disgrafia, ajuda a facilitar a compreensão do texto. Ele também inclui a tradução em linha para pessoas que preferem se comunicar em um idioma diferente. Alguns dos principais recursos do Leitura Avançada são:

- Adicionando a opção para que o conteúdo seja lido em voz alta

- Alterando o tamanho do texto e a cor da tela de fundo

- Dividir palavras em sílabas

- Aumentar o espaço entre letras

- Realçando uma ou mais linhas de texto

- Realçar partes da fala

As opções de chat flexíveis são úteis em uma ampla variedade de situações, mas podem ser especialmente úteis para:

- Pessoas que são cegos ou têm baixa visão

- Pessoas que são neurodiversas (ou seja, têm dislexia ou disgrafia)

Para obter mais informações, consulte WCAG (Diretrizes de Acessibilidade de Conteúdo da [Web) 1.1.1.: Alternativas de texto](https://www.w3.org/TR/WCAG21/#text-alternatives).

## <a name="share-resources-with-users-to-further-accessibility-awareness"></a>Compartilhar recursos com usuários para aumentar o reconhecimento de acessibilidade

Há etapas adicionais que os usuários podem seguir para melhorar sua experiência em acessibilidade. Compartilhe os links abaixo com sua organização e usuários convidados.

### <a name="reference-links"></a>Links de referências

O Answer Desk de Deficiências da Microsoft tem guias do usuário final para personalizar sua experiência para atender às suas necessidades de acessibilidade:

- [Ativar legendas ao vivo durante reuniões](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop)

- [Personalizar o modo de exibição de reunião](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)

- [Usar legendas CART](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

- [Alterar efeitos de plano de fundo em reuniões do Teams](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)

- [Reduzir o ruído de fundo em reuniões do Teams](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

- [Escrever texto Alt efetivo](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2)

- [Ferramentas de acessibilidade para o Microsoft Teams](https://support.microsoft.com/office/accessibility-tools-for-microsoft-teams-2d4009e7-1300-4766-87e8-7a217496c3d5?ui=en-us&rs=en-us&ad=us)

### <a name="reference-web-content-accessibility-guidelines-wcag"></a>Diretrizes de acessibilidade de conteúdo da Web de referência (WCAG)

O WCAG é uma série de padrões internacionais projetados para melhorar a acessibilidade da Web. O critério de sucesso referenciado neste guia inclui:

- [WCAG 1.2.4.: Legendas (ao vivo)](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

- [WCAG 1.2.6.: Interpretação da linguagem de sinal](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded)

- [WCAG 1.4.8.: Apresentação Visual](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html)

- [WCAG 1.1.1.: Alternativas de Texto](https://www.w3.org/TR/WCAG21/#text-alternatives)
