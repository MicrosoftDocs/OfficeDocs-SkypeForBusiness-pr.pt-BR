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
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: Consulte como configurar equipes para permitir que os usuários se comuniquem com usuários de outra organização.
ms.openlocfilehash: c3faf65dd3f36c193a75e74e73d90bf5e9be11df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222367"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permitir que o bate-papo de usuários equipes e se comunicar com usuários de outra organização de equipes

Siga as etapas descritas neste artigo quando:
  
- Você possui usuários em domínios diferentes em sua empresa. Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.
    
- Você deseja as pessoas na sua organização usar equipes para contatar pessoas na empresas específicas fora da sua organização.
    
- Deseja que qualquer pessoa no mundo que usa as equipes possam encontrar e contatá-lo, usando seu endereço de email. Se você e outro usuário habilitar o acesso externo e permitem uns dos outros domínios, isso funcionará. Se ela não funcionar, o outro usuário verifique se seu ou sua configuração não está bloqueando o seu domínio.

Isso permitirá que os usuários a localizar, chamar e lhe enviar mensagens instantâneas, bem como configurar reuniões com você. Se desejar que os usuários externos tenham acesso às equipes e canais, acesso de convidado pode ser uma melhor maneira de ir. Siga as etapas neste artigo e certifique-se para [Ativar o acesso de convidado](set-up-guests.md) para que os usuários podem se comunicar.

> [!IMPORTANT]
> Para federar atualmente no cliente Microsoft Teams a um usuário externo fora da sua organização que não está sendo convidado de seu locatário do AAD /, você deve ser corretamente configurado para o híbrido e movida para Skype para Business Online. A partir de 25/2/2019, equipes ainda não oferece suporte nativa federação sem que o usuário do SIP perfil sendo hospedado no Skype para negócios Online. Para obter mais informações sobre a configuração de backup de sua conta para o híbrido e depois movido para equipes, consulte [Atualizar Skype para implantação híbrida do Business às equipes](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permitir que o bate-papo de usuários equipes e se comunicar com usuários de outra organização de equipes

Siga estas etapas.

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>Etapa 1 - certificar-se de configurar as portas e URLs que são necessários.

**O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>Etapa 2 - habilitar a sua organização se comuniquem com outra organização de equipes

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**

   1. No painel de navegação esquerdo, vá para **configurações de toda a organização** > **acesso externo**. 

   2. Na parte superior da página de **acesso externo** , clique em **acesso externo** para **ativado**. 

   3. Se você deseja permitir todas as organizações de equipes para se comunicar com usuários em sua organização, pule para a etapa 5. 
   
   4. Se você deseja limitar quais organizações podem se comunicar com usuários em sua organização você pode permitir que todos os mas alguns domínios ou permitir apenas organizações específicas. Para permitir que todos os mas alguns domínios, adicione os domínios que você deseja bloquear, clicando em **Adicionar domínio**. No painel de **Adicionar um domínio** , coloque o nome de domínio, clique em **bloqueado** e **feito**. Para limitar as comunicações para organizatioins específicos, adicione os domínios à lista com um status de **Alowed**. Assim que você tiver adicionado qualquer domínio à lista de permissões, as comunicações para outras organizações será limitadas apenas às organizações cujos domínios estão na lista de permissões. 
   
   5. Clique em **Salvar**. 

   6. Verifique se que o administrador na organização do equipes segue essas etapas mesmas. Por exemplo, em sua lista de **domínios permitidos** , seu administrador precisa insira o domínio para sua empresa se eles limitam o que as organizações podem se comunicar com seus usuários. 

### <a name="step-3---test-it"></a>Etapa 3 - testá-lo
Para testar sua configuração, você precisa de um usuário de equipes que não está atrás do firewall.
  
   1. Depois que o administrador da organização e você tem alterado as configurações de **acesso externo** , você deve estar pronto.
    
   2. No aplicativo de equipes, procurar a pessoa pelo endereço de email e enviar uma solicitação para o bate-papo.
    
   3. Peça ao seu contato de equipes lhe enviar uma solicitação para o bate-papo. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).
    
   4. Outra maneira para testar se o problema é seu firewall deve ir para um local de wifi não atrás do seu firewall, como um café e use equipes para enviar uma solicitação ao seu contato para o bate-papo. Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Se comunicar com usuários em um Skype para a organização Business Online

Se você estiver configurando-lo para permitir que sua localização de usuários de equipes e visita os usuários que estão em um Skype para organização de negócios que limita quem pode contatar seus usuários, você pedirá que o administrador na organização que devem seguir estas etapas.

![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **Usando Skype para centro de administração de negócios** 

Ter o administrador em que a organização siga estas etapas:
    
1. No Centro de administração do Office 365, vá para **Centros de Admin** > **& equipes Skype** > **portal herdada**.
  
2. No **Centro de administração do Skype for Business**, escolha **Organização** > **Comunicações externas**.
    
3. Para configurar a comunicação com um negócio específicos ou com usuários em outro domínio, na caixa suspensa, escolha **em somente para domínios permitidos**.
    
    OU, se deseja habilitar a comunicação com todas as outras pessoas no mundo que tenha aberto Skype para políticas de negócios, escolha **no, com exceção de domínios bloqueados**. Esta é a configuração padrão.
    
4. Em **bloqueado ou domínios permitidos**, escolha **+** e adicione o nome do domínio que você deseja permitir. Certificar-se de que o administrador na organização do segue essas etapas mesmas. Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.
    
### <a name="related-topics"></a>Tópicos relacionados

[Entrar no Microsoft Teams](sign-in-teams.md)
[para equipes de treinamento do usuário final](enduser-training.md)

