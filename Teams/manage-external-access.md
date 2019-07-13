---
title: Gerenciar o acesso externo (federação) no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/12/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.externalaccess.overview
description: Seu administrador de ti pode configurar o acesso externo para outros domínios (Federação) para permitir que os usuários desses domínios participem da equipe.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 706e4641824808cfea493f87a4d0c4b859a43369
ms.sourcegitcommit: baa425d7a07429e6fe84b4f27c76243cf755c1a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643144"
---
<a name="manage-external-access-in-microsoft-teams"></a>Gerenciar o acesso externo no Microsoft Teams
======================================================

Com o acesso externo ao Microsoft Teams, os usuários do Microsoft Teams de outros domínios podem participar de chats e chamadas. Você também pode permitir que usuários externos do othe que ainda estejam usando o Skype for Business Online, o Skype for Business local ou até o Skype possam participar.

Siga as etapas descritas neste artigo quando:
  
- Você tem usuários em domínios diferentes na sua empresa: por exemplo, Rob@contoso.com e Ann@northwindtraders.com.

- Você quer que as pessoas em sua organização usem o Teams para entrar em contato com pessoas em empresas específicas fora da sua organização.

- Você quer que qualquer outro usuário do mundo que use o Microsoft Teams possa encontrá-lo e contatá-lo usando seu endereço de e-mail. Se você e outro usuário habilitarem o acesso externo e permitirem os domínios uns dos outros, isso funcionará. Se não funcionar, o outro usuário deve verificar se a configuração dele não está bloqueando o seu domínio.

O acesso externo permite que os usuários externos encontrem, liguem e enviem mensagens de chat, além de configurar reuniões com você. No entanto, se você quiser que os usuários externos tenham acesso a equipes e canais, o acesso de convidado pode ser uma melhor maneira de começar. Para obter mais informações sobre as diferenças entre acesso externo e acesso de convidado, consulte acesso [externo versus acesso de convidado](#external-access-vs-guest-access)) abaixo. Para ativar o acesso de convidado, consulte [ativar o acesso de convidado](set-up-guests.md) para que os usuários possam se comunicar.

> [!IMPORTANT]
> Atualmente, para federar-se no aplicativo Microsoft Teams a um usuário externo fora de sua organização, mas que não seja um convidado do seu Azure Active Directory (Azure AD) ou locatário, você deve estar corretamente configurado para o Hybrid e movido para o Skype for Business online. A partir de 2/25/2019, o Teams não oferece suporte à Federação nativa sem que o usuário do perfil SIP seja hospedado no Skype for Business online. Para saber mais sobre como configurar sua conta para híbrido e, em seguida, migrar para o Microsoft Teams, consulte [atualizar a implantação híbrida do Skype for Business para](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)o Teams.

## <a name="external-access-vs-guest-access"></a>Acesso externo versus acesso de convidado

O acesso externo (Federação) e o acesso de convidado são diferentes:

- O acesso de convidado concede permissão de acesso a um indivíduo. O acesso externo oferece permissão de acesso a um domínio inteiro.

- O acesso de convidado, uma vez concedido por um proprietário de equipe, permite que um convidado [acesse recursos](guest-experience.md), como discussões e arquivos de canal, para uma equipe específica e converse com outros usuários na equipe em que foram convidados. Com o acesso externo (chat federado), os participantes do chat externo não têm acesso às equipes ou aos recursos da equipe que convida a organização. Eles podem participar apenas de um chat federado único. Os administradores de locatários podem escolher entre as duas opções de comunicação, dependendo do nível de colaboração que é desejável na parte externa. Os administradores podem escolher abordagens ou ambos, dependendo de suas necessidades organizacionais, mas recomendamos habilitar o acesso de convidado para obter uma experiência de equipes mais abrangente e colaborativa. 

Consulte a tabela a seguir para obter uma comparação de recursos de acesso externo e de convidado.

| Recurso | Usuários de acesso externo | Usuários de acesso de convidado |
|---------|-----------------------|--------------------|
| O usuário pode conversar com alguém em outra empresa | Sim |Sim |
| O usuário pode fazer uma chamada para alguém em outra empresa | Sim | Sim |
| O usuário pode ver se alguém de outra empresa está disponível para chamada ou chat | Sim | Sim<sup>1</sup> |
| O usuário pode pesquisar usuários em locatários externos | Sim<sup>2</sup> | Não |
| O usuário pode compartilhar arquivos | Não | Sim |
| O usuário pode acessar os recursos da equipe | Não | Sim |
| O usuário pode ser adicionado a um chat em grupo | Não | Sim |
| O usuário pode ser adicionado a uma reunião | Sim | Sim |
| Outros usuários podem ser adicionados a um chat com um usuário externo | Não<sup>3</sup> | N/D |
| O usuário é identificado como uma festa externa | Sim | Sim |
| A presença será exibida | Sim | Sim |
| Mensagem de ausência temporária é mostrada | Não | Sim |
| O usuário individual pode ser bloqueado | Não | Sim |
| @mentions têm suporte | Não | Sim |
| Fazer chamadas privadas | Sim | Sim |
| Permitir vídeo IP | Sim | Sim |
| Modo de compartilhamento de tela | Não | Sim |
| Permitir reunião agora | Não | Sim |
| Editar mensagens enviadas | Não | Sim |
| Pode excluir mensagens enviadas | Não | Sim |
| Usar o Giphy em conversa | Não | Sim |
| Usar o memes em conversa | Não | Sim |
| Usar adesivos em conversa | Não | Sim |
||||

<sup>1</sup> desde que o usuário tenha sido adicionado como um convidado e esteja conectado como convidado ao locatário de convidado.<br>
<sup>2</sup> somente por endereço de email ou protocolo de iniciação de sessão (SIP).<br>
<sup>3</sup> o chat externo (federado) só é o 1:1.

Para obter mais informações sobre os recursos convidados e sobre a experiência de convidado, consulte [Ativar ou desativar o acesso de convidado ao Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) e o [que a experiência de convidado é curtir](https://docs.microsoft.com/microsoftteams/guest-experience).

Para obter mais informações sobre a versão gratuita do Teams e como ela funciona com recursos encontrados em acesso externo, consulte [diferenças entre o Microsoft Teams e o Microsoft Teams gratuito](https://support.office.com/article/differences-between-microsoft-teams-and-microsoft-teams-free-0b69cf39-eb52-49af-b255-60d46fdf8a9c?ui=en-US&rs=en-US&ad=US).

## <a name="quick-steps-for-scenarios"></a>Etapas rápidas para cenários

|**Você deseja...**  |**Etapas rápidas**  |
|---------|-----------------------|
|Você deseja permitir que **os usuários** do teams na sua organização se comuniquem com **usuários** do teams em outra organização (externa).|Em acesso externo, adicione o domínio externo à lista de permitidos ou use a Federação aberta. <p>Em seguida, faça com que o administrador na outra organização de equipes faça a mesma coisa.      |
|Você deseja permitir que **os usuários** do teams na sua organização se comuniquem com **usuários do Skype for Business online** na mesma organização.  |Habilite o modo de coexistência ou escolha o modo de atualização de ilhas para dar suporte aos usuários do Skype for Business em sua organização.   |
|Você deseja permitir que **os usuários** do teams na sua organização se comuniquem com **usuários do Skype for Business online** em outra organização (externa).      |Em acesso externo, adicione o domínio externo à lista de permitidos ou use a Federação aberta.  <p>Ativar **os usuários pode se comunicar com a configuração do Skype for Business e dos usuários** do teams no acesso externo. <p>Em seguida, faça com que o administrador na outra organização de equipes faça a mesma coisa. <p>**Observação**: o domínio externo com usuários do Skype for Business deve habilitar o modo de coexistência ou escolher o modo de atualização de ilhas para dar suporte aos usuários do Skype for Business nessa organização.|
|Você deseja permitir que **os usuários** do teams na sua organização se comuniquem com usuários do **Skype** de dentro ou de fora da sua organização.   | Não é um cenário com suporte no momento. <p>**Importante**: os usuários do Microsoft Teams não poderão se comunicar com usuários do Skype, mas os usuários do Skype for Business em sua organização poderão se comunicar com usuários do Skype dentro ou fora da sua organização se estes dois requisitos forem atendidos: <p>1) ativar **os usuários pode se comunicar com os usuários do Skype for Business e** do Teams e **os usuários do Skype for Business podem se comunicar com** as configurações de usuários do Skype no acesso externo. <p> 2) a sua organização está em execução no modo de coexistência. |
|Você deseja permitir que os **usuários** do seu Team se comuniquem com **usuários do Skype for Business online** de uma organização local e com **usuários do Skype**.   |Em acesso externo, adicione o domínio externo à lista de permitidos ou use a Federação aberta. . <p>Ativar **os usuários pode se comunicar com a configuração do Skype for Business e dos usuários** do teams no acesso externo. <p>Habilite **os usuários do Skype for Business para se comunicar com** as configurações de usuários do Skype no acesso externo. <p> Então, o administrador da organização local faz a mesma coisa.<p>**Importante** Nesse cenário, os usuários do Microsoft Teams não poderão se comunicar com usuários do Skype, mas os usuários do Skype for Business em sua organização poderão se comunicar com usuários do Skype dentro ou fora de sua organização se você ativar **os usuários podem se comunicar com o Skype for Business os usuários** do Teams e **do Skype for Business podem se comunicar com** as configurações de usuários do Skype no acesso externo.|
|Você deseja permitir que seus **usuários do Skype for Business online** se comuniquem com **usuários** do teams em outra organização do Office 365.|Habilite o modo de coexistência ou escolha o modo de atualização de ilhas para dar suporte aos usuários do Skype for Business em sua organização. <p>Em acesso externo, adicione o domínio externo à lista de permitidos ou use a Federação aberta.  <p> Ativar **os usuários pode se comunicar com a configuração do Skype for Business e dos usuários** do teams no acesso externo. <p>Em seguida, faça com que o administrador na outra organização de equipes faça as mesmas coisas. |
|Você deseja permitir que seus **usuários do Skype for Business online** se comuniquem com os **usuários do Skype for Business online** a partir de outra organização do Office 365.    | Habilite o modo de coexistência ou escolha o modo de atualização de ilhas para dar suporte aos usuários do Skype for Business em sua organização. <p>Em acesso externo, adicione o domínio externo à lista de permitidos ou use a Federação aberta. <p> Ativar **os usuários pode se comunicar com a configuração do Skype for Business e dos usuários** do teams no acesso externo.<p>Em seguida, faça com que o administrador na outra organização de equipes realize todas as mesmas coisas. |
|Você deseja permitir que seus **usuários do Skype for Business online** se comuniquem com os **usuários do Skype for Business online** a partir de uma organização local.     |Habilite o modo de coexistência ou escolha o modo de atualização de ilhas para dar suporte aos usuários do Skype for Business em sua organização. <p>Em acesso externo, adicione o domínio externo à lista de permitidos ou use a Federação aberta.  <p>Ativar **os usuários pode se comunicar com a configuração do Skype for Business e dos usuários** do teams no acesso externo.  <p> Então, o administrador da organização local faz as mesmas coisas. |
|Você deseja permitir que seus **usuários do Skype for Business online** se comuniquem com **usuários do Skype** (dentro ou fora da sua organização).   |Habilite o modo de coexistência ou escolha o modo de atualização de ilhas para dar suporte aos usuários do Skype for Business em sua organização. <p>Ative os **usuários do Skype for Business para se comunicar com** as configurações de usuários do Skype no acesso externo.         |
|Você deseja permitir que seus **usuários do Skype for Business online** se comuniquem com **usuários do Skype for Business online** em outra organização e **usuários do Skype** de dentro ou de fora da sua organização.    |Habilite o modo de coexistência ou escolha o modo de atualização de ilhas para dar suporte aos usuários do Skype for Business em sua organização. <p>Em acesso externo, adicione o domínio externo à lista de permitidos ou use a Federação aberta.  <p> Ativar **os usuários pode se comunicar com os usuários do Skype for Business e** do Teams e os **usuários do Skype for Business podem se comunicar com** as configurações de usuários do Skype no acesso externo. <p>Em seguida, faça com que o administrador na outra organização de equipes faça as mesmas coisas.       <p> **Observação**: o administrador do outro domínio externo não precisa ativar **os usuários do Skype for Business para se comunicar com** as configurações de usuários do Skype no acesso externo.|

> [!IMPORTANT]
> Você não precisa adicionar nenhum **"domínio do Skype"** como domínios permitidos para permitir que equipes ou usuários do Skype for Business online se comuniquem com usuários do Skype dentro ou fora de sua organização. Todos os **domínios do Skype** são whitelists, o que significa que todos esses domínios são considerados permitidos.

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-organization"></a>Permitir que os usuários do Microsoft Teams conversem e se comuniquem com usuários em outra organização

O acesso externo permite que suas equipes e usuários do Skype for Business se comuniquem com outros usuários que estão fora da sua organização. Por padrão, a sua organização pode se comunicar com todos os domínios externos. Se você adicionar domínios bloqueados, todos os outros domínios serão permitidos, mas se você adicionar domínios permitidos, todos os outros domínios serão bloqueados. Você pode facilmente configurar o acesso externo à sua organização. Há três cenários para configurá-lo:

- **Cenário 1** – você pode usar a **Federação aberta**. Esta é a configuração padrão e permite que as pessoas em sua organização encontrem, liguem e enviem mensagens instantâneas, além de configurar reuniões com pessoas externas à sua organização.

    Quando você usa essa configuração, os usuários podem se comunicar com todos os domínios externos que estão executando o Teams, mas configurar o domínio/organização para permitir o seu domínio.

- **Cenário 2** -você pode adicionar um domínio ou domínios à lista de **permissões** . Para fazer isso, clique em **Adicionar um domínio**, adicione o nome de domínio, clique em **ação para assumir o domínio**e selecione **permitido**. É importante saber que, se você fizer isso, todos os **** outros domínios serão bloqueados.

- **Cenário 3** – você pode adicionar um domínio ou domínios à lista **** de bloqueios. Para fazer isso, clique em **Adicionar um domínio**, adicione o nome de domínio, clique em **ação para assumir o domínio**e selecione **bloqueado**. É importante saber que, se você fizer isso, isso **permitirá** que todos os outros domínios.

Siga estas etapas para permitir ou bloquear domínios.

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>Etapa 1-habilitar sua organização a se comunicar com outra organização de equipes

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png)do Microsoft Teams**usando o centro de administração do Microsoft Teams**  

1. No painel de navegação esquerdo, vá para >  **configurações de toda a organização****acesso externo**.

2. Alternar os **usuários podem se comunicar com o Skype for Business e os usuários** do teams mudarão para **ativado**.

     ![Captura de tela da opção de acesso externo ativada](media/manage-external-access-2.png).

3. Se você quiser permitir que todas as organizações de equipe se comuniquem com os usuários da sua organização, pule para a etapa 5.

4. Se desejar limitar as organizações que podem se comunicar com os usuários em sua organização, você poderá permitir todos exceto alguns domínios, ou só poderá permitir domínios específicos. 

    - Para permitir todos exceto alguns domínios, adicione os domínios que você deseja bloquear clicando em **Adicionar domínio**. No painel **Adicionar um domínio** , digite o nome do domínio, clique em **bloqueado**e, em seguida, clik **concluído**. 
    - Para limitar as comunicações a organizações específicas, adicione esses domínios à lista com um status de **permitido**. Depois que você adicionar qualquer domínio à lista de permissões, as comunicações com outras organizações serão limitadas apenas às organizações cujos domínios estiverem na lista de permissões. 

5. Clique em **Salvar**.

6. Certifique-se de que o administrador na organização outras equipes conclua as mesmas etapas. Por exemplo, na lista de **domínios permitidos** , o administrador precisará inserir o domínio para a sua empresa se limitar as organizações que podem se comunicar com seus usuários.

### <a name="step-2---test-it"></a>Etapa 2-testá-lo

Para testar a configuração, você precisará de um usuário do teams que não esteja atrás do seu firewall.
  
1. Depois que você e o administrador da organização tiverem alterado as configurações de **acesso externo** , você deverá ir bem.

2. No aplicativo Teams, procure a pessoa por endereço de e-mail e envie uma solicitação para conversar.

3. Peça ao contato do teams para lhe enviar uma solicitação para conversar. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).

4. Outra maneira de testar se o problema é o seu firewall é acessar um local WiFi que não está protegido pelo firewall. como uma lanchonete e usar o Microsoft Teams para enviar uma solicitação ao seu contato para conversar. Se a mensagem passar pelo local WiFi, mas não quando você estiver no trabalho, você saberá que o problema é seu firewall.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Comunicar-se com usuários em uma organização do Skype for Business Online

Se você estiver configurando o acesso externo para permitir que os usuários do Microsoft Teams localizem e entrem em contato com os usuários que estão em uma organização do Skype for Business que limitam quem pode contatar seus usuários, siga as etapas para configurar o acesso externo do seu domínio para o domínio da outra organização. Em seguida, peça ao administrador da outra organização para seguir as etapas abaixo para configurar o acesso externo para o Skype for Business online.

![Um ícone mostrando o logotipo](media/sfb-logo-30x30.png) do Skype for Business **usando o centro de administração do Skype for Business**

Faça as seguintes etapas para o administrador da organização:

1. No centro de administração do Microsoft 365, acesse **centros** > de administração de administração **& portal do Skype** > **Legacy**.
  
2. No **Centro de administração do Skype for Business**, escolha **Organização** > **Comunicações externas**.

3. Para configurar a comunicação com uma empresa específica ou com usuários em outro domínio, na caixa suspensa, escolha **ativado somente para os domínios permitidos**.

    OU, se quiserem habilitar a comunicação com todos os participantes do mundo que tenham as políticas do Skype for Business abertas, escolha **ativado exceto para os domínios bloqueados**. Esta é a configuração padrão.

4. Em **domínios bloqueados ou permitidos**, **+** escolha e, em seguida, adicione o nome do domínio que você deseja permitir.

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre o acesso de convidado no Microsoft Teams, consulte [gerenciar o acesso de convidados no Microsoft Teams](manage-guests.md).
