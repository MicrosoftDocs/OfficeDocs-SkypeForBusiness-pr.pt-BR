---
title: Gerenciar o acesso externo (federação) no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/19/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: Seu administrador de ti pode configurar o acesso externo para outros domínios (Federação) para permitir que os usuários desses domínios participem da equipe.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43e4153959a4d444a81f4769daf69976af018c4d
ms.sourcegitcommit: 2af4c9e3a8374d9a6995e36604d8b0b8eff23b34
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2019
ms.locfileid: "35133919"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a>Gerenciar o acesso externo (federação) no Microsoft Teams
======================================================

Com o acesso externo ao Microsoft Teams, os usuários de outros domínios podem participar de chats e chamadas. Você também pode permitir que usuários externos que ainda estejam usando o Skype for Business online ou o Skype for Business no local para participar.

Siga as etapas descritas neste artigo quando:
  
- Você tem usuários em domínios diferentes na sua empresa: por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.

- Você quer que as pessoas em sua organização usem o Teams para entrar em contato com pessoas em empresas específicas fora da sua organização.

- Você quer que qualquer outro usuário do mundo que use o Microsoft Teams possa encontrá-lo e contatá-lo usando seu endereço de e-mail. Se você e outro usuário habilitarem o acesso externo e permitirem os domínios uns dos outros, isso funcionará. Se não funcionar, o outro usuário deve verificar se a configuração dele não está bloqueando o seu domínio.

O acesso externo permite que os usuários externos encontrem, liguem e enviem mensagens de chat, além de configurar reuniões com você. No entanto, se você quiser que os usuários externos tenham acesso a equipes e canais, o acesso de convidado pode ser uma melhor maneira de começar. Para obter mais informações sobre as diferenças entre acesso externo e acesso de convidado, consulte acesso [externo versus acesso de convidado](#external-access-vs-guest-access)) abaixo. Para ativar o acesso de convidado, consulte [ativar o acesso de convidado](set-up-guests.md) para que os usuários possam se comunicar.

> [!IMPORTANT]
> Atualmente, para federar-se no cliente do Microsoft Teams a um usuário externo fora de sua organização, que não seja um convidado do seu Azure Active Directory (Azure AD) ou locatário, você deve estar corretamente configurado para o Hybrid e movido para o Skype for Business online. A partir de 2/25/2019, o Teams não oferece suporte à Federação nativa sem que o usuário do perfil SIP seja hospedado no Skype for Business online. Para saber mais sobre como configurar sua conta para híbrido e, em seguida, migrar para o Microsoft Teams, consulte [atualizar a implantação híbrida do Skype for Business para](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)o Teams.

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
| Modo de compartilhamento de tela | Sim | Sim |
| Permitir reunião agora | Não | Sim |
| Editar mensagens enviadas | Sim | Sim |
| Pode excluir mensagens enviadas | Sim | Sim |
| Usar o Giphy em conversa | Sim | Sim |
| Usar o memes em conversa | Sim | Sim |
| Usar adesivos em conversa | Sim | Sim |
||||

<sup>1</sup> desde que o usuário tenha sido adicionado como um convidado e esteja conectado como convidado ao locatário de convidado.<br>
<sup>2</sup> somente por endereço de email ou protocolo de iniciação de sessão (SIP).<br>
<sup>3</sup> o chat externo (federado) só é o 1:1.

> [!NOTE]
> Para obter mais informações sobre os recursos convidados e sobre a experiência de convidado, consulte [Ativar ou desativar o acesso de convidado ao Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) e o [que a experiência de convidado é curtir](https://docs.microsoft.com/microsoftteams/guest-experience).

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-organization"></a>Permitir que os usuários do Microsoft Teams conversem e se comuniquem com usuários em outra organização

O acesso externo permite que suas equipes e usuários do Skype for Business se comuniquem com outros usuários que estão fora da sua organização. Por padrão, a sua organização pode se comunicar com todos os domínios externos. Se você adicionar domínios bloqueados, todos os outros domínios serão permitidos, mas se você adicionar domínios permitidos, todos os outros domínios serão bloqueados. Você pode facilmente configurar o acesso externo à sua organização. Há três cenários para configurá-lo:

- **Cenário 1** – você pode usar a **Federação aberta**. Esta é a configuração padrão e permite que as pessoas em sua organização encontrem, liguem e enviem mensagens instantâneas, além de configurar reuniões com pessoas externas à sua organização.

    Quando você usa essa configuração, os usuários podem se comunicar com todos os domínios externos que estão executando o Teams, mas configurar o domínio/organização para permitir o seu domínio.

- **Cenário 2** -você pode adicionar um domínio ou domínios à lista de **permissões** . Para fazer isso, clique em **Adicionar um domínio**, adicione o nome de domínio, clique em **ação para assumir o domínio**e selecione **permitido**. É importante saber que, se você fizer isso, todos os **** outros domínios serão bloqueados.

- **Cenário 3** – você pode adicionar um domínio ou domínios à lista **** de bloqueios. Para fazer isso, clique em **Adicionar um domínio**, adicione o nome de domínio, clique em **ação para assumir o domínio**e selecione **bloqueado**. É importante saber que, se você fizer isso, isso **permitirá** que todos os outros domínios.

Siga estas etapas para permitir ou bloquear domínios.

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>Etapa 1-habilitar sua organização a se comunicar com outra organização de equipes

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**

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

## <a name="more-information"></a>Mais informações

Para obter informações sobre o acesso de convidado no Microsoft Teams, consulte [gerenciar o acesso de convidados no Microsoft Teams](manage-guests.md).
