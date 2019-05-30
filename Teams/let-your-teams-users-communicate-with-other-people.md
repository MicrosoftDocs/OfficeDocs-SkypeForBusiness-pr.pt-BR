---
title: Comunicar-se com os usuários do Teams em outra organização
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: Veja como configurar o Microsoft Teams para permitir que os usuários se comuniquem com os usuários de outra organização.
ms.openlocfilehash: e9e2a60c7f1f93df56408976a92e4aa47f3e486e
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494686"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permitir que os usuários do seu Team conversem e se comuniquem com usuários em outra organização de equipes

Siga as etapas descritas neste artigo quando:
  
- Você tem usuários em domínios diferentes na sua empresa. Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.
    
- Você quer que as pessoas em sua organização usem o Teams para entrar em contato com pessoas em empresas específicas fora da sua organização.
    
- Você quer que qualquer outro usuário do mundo que use o Microsoft Teams possa encontrá-lo e contatá-lo usando seu endereço de e-mail. Se você e outro usuário habilitarem o acesso externo e permitirem os domínios uns dos outros, isso funcionará. Se não funcionar, o outro usuário deve verificar se a configuração dele não está bloqueando o seu domínio.

Isso permitirá que os usuários localizem, liguem e enviem mensagens instantâneas, além de configurar reuniões com você. Se você quiser que os usuários externos tenham acesso a equipes e canais, o acesso de convidado pode ser uma melhor maneira de começar. Siga as etapas deste artigo e certifique-se de [ativar o acesso de convidado](set-up-guests.md) para que os usuários possam se comunicar.

> [!IMPORTANT]
> Para federar-se atualmente no cliente do Microsoft Teams para um usuário externo fora de sua organização que não seja um convidado do seu AAD/locatário, você deve ser configurado corretamente para o Hybrid e movido para o Skype for Business online. A partir de 2/25/2019, as equipes ainda não dão suporte à Federação nativa sem que o usuário do perfil SIP seja hospedado no Skype for Business online. Para saber mais sobre como configurar sua conta para Hybrid e depois movê-la para o Microsoft Teams, consulte [atualizar a implantação híbrida do Skype for Business para](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)o Microsoft Teams.

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permitir que os usuários do seu Team conversem e se comuniquem com usuários em outra organização de equipes

Siga estas etapas.

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>Etapa 1: Certifique-se de configurar as portas e URLs que são necessárias.

**O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>Etapa 2-habilitar sua organização a se comunicar com outra organização de equipes

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**

   1. No painel de navegação esquerdo, vá para >  **configurações de toda a organização****acesso externo**. 

   2. Na parte superior da página de **acesso externo** , clique em **acesso externo** para **ativado**. 

   3. Se você quiser permitir que todas as organizações de equipe se comuniquem com os usuários da sua organização, pule para a etapa 5. 
   
   4. Se quiser limitar quais organizações podem se comunicar com os usuários em sua organização, você pode permitir todos, mas alguns domínios, ou somente permitir organizações específicas. Para permitir todos, mas alguns domínios, adicione os domínios que você deseja bloquear clicando em **Adicionar domínio**. No painel **Adicionar um domínio** , insira o nome do domínio, clique em **bloqueado** e em **concluído**. Para limitar as comunicações a organizatioins específicas, adicione esses domínios à lista com um status de **permitido**. Depois que você adicionar qualquer domínio à lista de permissões, as comunicações com outras organizações serão limitadas apenas às organizações cujos domínios estiverem na lista de permissões. 
   
   5. Clique em **Salvar**. 

   6. Em seguida, verifique se o administrador na organização outras equipes executa essas mesmas etapas. Por exemplo, na lista de **domínios permitidos** , o administrador precisará inserir o domínio para sua empresa se eles limitarem quais organizações podem se comunicar com seus usuários. 

### <a name="step-3---test-it"></a>Etapa 3-testar
Para testar a configuração, você precisará de um usuário do teams que não esteja atrás do seu firewall.
  
   1. Depois que você e o administrador da organização tiverem alterado as configurações de **acesso externo** , você deverá ir bem.
    
   2. No aplicativo Teams, procure a pessoa por endereço de e-mail e envie uma solicitação para conversar.
    
   3. Peça ao contato do teams para lhe enviar uma solicitação para conversar. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).
    
   4. Outra maneira de testar se o problema é o seu firewall é acessar um local WiFi que não está atrás do seu firewall, como uma lanchonete, e usar o Microsoft Teams para enviar uma solicitação ao seu contato para conversar. Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Comunicar-se com usuários em uma organização do Skype for Business Online

Se você estiver configurando para permitir que seus usuários do teams localizem e entrem em contato com usuários que estão em uma organização do Skype for Business que limitam quem pode contatar seus usuários, você solicitará que o administrador dessa organização siga estas etapas.

![Um ícone mostrando o logotipo](media/sfb-logo-30x30.png) do Skype for Business usando o **centro de administração do Skype for Business** 

Faça as seguintes etapas para o administrador da organização:
    
1. No centro de administração do Office 365, vá para **Centro** > de administração do **& portal do Skype** > **Legacy**.
  
2. No **Centro de administração do Skype for Business**, escolha **Organização** > **Comunicações externas**.
    
3. Para configurar a comunicação com uma empresa específica ou com usuários em outro domínio, na caixa suspensa, escolha **ativado somente para os domínios permitidos**.
    
    OU, se quiserem habilitar a comunicação com todos os participantes do mundo que tenham as políticas do Skype for Business abertas, escolha **ativado exceto para os domínios bloqueados**. Esta é a configuração padrão.
    
4. Em **domínios bloqueados ou permitidos**, **+** escolha e adicione o nome do domínio que você deseja permitir. Certifique-se de que o administrador da outra organização faça as mesmas etapas. Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.
    
### <a name="related-topics"></a>Tópicos relacionados

[Entrar](sign-in-teams.md)
no[treinamento do usuário final do](enduser-training.md) Microsoft Teams para equipes

