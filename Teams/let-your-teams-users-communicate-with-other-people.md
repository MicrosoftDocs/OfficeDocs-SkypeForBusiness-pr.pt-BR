---
title: Se comunicar com usuários de equipes em outra organização
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Strat_MT_TeamsAdmin
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Consulte como configurar equipes para permitir que os usuários se comuniquem com usuários de outra organização.
ms.openlocfilehash: 39be4ddb1a9f42382de30c04d3e81a990aad3547
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23863101"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permitir que o bate-papo de usuários equipes e se comunicar com usuários de outra organização de equipes

Siga as etapas descritas neste artigo quando:
  
- Você possui usuários em domínios diferentes em sua empresa. Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.
    
- Você deseja as pessoas na sua organização usar equipes para contatar pessoas na empresas específicas fora da sua organização.
    
- Deseja que qualquer pessoa no mundo que usa as equipes possam encontrar e contatá-lo, usando seu endereço de email. Se você e outro usuário habilitar o acesso externo e permitem uns dos outros domínios, isso funcionará. Se ela não funcionar, o outro usuário verifique se seu ou sua configuração não está bloqueando o seu domínio.

Siga estas etapas:

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Permitir que o bate-papo de usuários equipes e se comunicar com usuários de outra organização de equipes

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>Etapa 1 - certificar-se de configurar as portas e URLs que são necessários.

**O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>Etapa 2 - habilitar a sua organização se comuniquem com outra organização de equipes

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

   1. No painel de navegação esquerdo, vá para **configurações de toda a organização** > **acesso externo**. 

   2. Na parte superior da página de **acesso externo** , clique em **acesso externo** para **ativado**. 

   3. Adicione domínio da outra organização à lista de permissões, clicando em **Adicionar domínio**. No painel de **Adicionar um domínio** , preparado o clique de nome de domínio **permitido** e **feito**.

   4. Clique em **Salvar**. 

   5. Verifique se que o administrador na organização do equipes segue essas etapas mesmas. Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.

### <a name="step-3---test-it"></a>Etapa 3 - testá-lo
Para testar sua configuração, você precisa de um usuário de equipes que não está atrás do firewall.
  
   1. Depois que o administrador da organização e você tem alterado as configurações de **acesso externo** , você deve estar pronto.
    
   2. No aplicativo de equipes, procurar a pessoa pelo endereço de email e enviar uma solicitação para o bate-papo.
    
   3. Peça ao seu contato de equipes lhe enviar uma solicitação para o bate-papo. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).
    
   4. Outra maneira para testar se o problema é seu firewall deve ir para um local de wifi não atrás do seu firewall, como um café e use equipes para enviar uma solicitação ao seu contato para o bate-papo. Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Se comunicar com usuários em um Skype para a organização Business Online

Se você estiver definindo-la até permitir que os usuários de equipes localizar e contatar os usuários que estão em um Skype para organização de negócios, você será o administrador na organização que devem seguir estas etapas.

![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **Usando Skype para centro de administração de negócios** 

Ter o administrador em que a organização siga estas etapas:
    
1. No Centro de administração do Office 365, vá para **Centros de Administração** > **Skype for Business**.
  
2. No **Centro de administração do Skype for Business**, escolha **Organização** > **Comunicações externas**.
    
3. Para configurar a comunicação com um negócio específicos ou com usuários em outro domínio, na caixa suspensa, escolha **em somente para domínios permitidos**.
    
    OU, se quiser habilitar a comunicação com todos que tiverem as políticas do Skype for Business, escolha **Ativado exceto para domínios bloqueados**. Esta é a configuração padrão.
    
4. Em **bloqueado ou domínios permitidos**, escolha **+** e adicione o nome do domínio que você deseja permitir. Certificar-se de que o administrador na organização do segue essas etapas mesmas. Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.
    
### <a name="related-topics"></a>Tópicos relacionados

[Inscreva-se em equipes](sign-in-teams.md)
[para equipes de treinamento do usuário final](enduser-training.md)

