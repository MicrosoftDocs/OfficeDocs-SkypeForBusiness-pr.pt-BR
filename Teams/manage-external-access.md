---
title: Gerenciar o acesso externo (federação) no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- ms.teamsadmincenter.externalaccess.overview
description: Suas equipes ou administradores de ti podem configurar o acesso externo para outros domínios (Federação) para permitir que os usuários desses domínios participem do teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: a04a5547e13b8b93864b1b23dc598b08877c745a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707286"
---
<a name="manage-external-access-in-microsoft-teams"></a>Gerenciar o acesso externo no Microsoft Teams
======================================================

O acesso externo é uma maneira de os usuários de equipes externas terem um domínio inteiro para localizar, chamar, bater papo e configurar reuniões com você no Teams. Você também pode usar o acesso externo para se comunicar com usuários externos que ainda estejam usando o Skype for Business (online e local) e o Skype (chegando no início do 2020).

Se você desejar que usuários externos tenham acesso a equipes e canais, o acesso de convidados poderá ser a melhor opção. Para obter mais informações sobre as diferenças entre acesso externo e acesso de convidado, consulte [comparar o acesso externo e de convidado](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Use o acesso externo quando:
  
- Você tem usuários em domínios diferentes que precisam colaborar. Por exemplo, Rob@contoso.com e Ann@northwindtraders.com estão trabalhando em um projeto juntamente com alguns outros nos domínios contoso.com e northwindtraders.com.

- Você desejar que as pessoas em sua organização usem o Teams para entrar em contato com pessoas em empresas específicas de fora de sua organização.

- Você desejar que todas as pessoas que usam o Teams sejam capazes de localizar e entrar em contato com você usando seu endereço de email. 




> [!IMPORTANT]
> Atualmente, para executar a federação dentro do aplicativo Microsoft Teams a um usuário externo à sua organização que não seja um convidado do Azure AD (Azure Active Directory) ou locatário, a sua configuração como híbrido deve estar correta e você deve ter migrado para o Skype for Business Online. A partir de 25 de fevereiro de 2019, o Teams não é compatível com a Federação nativa sem que o usuário do perfil SIP seja hospedado no Skype for Business online. Para saber mais sobre como configurar sua conta como híbrida e depois migrar o Teams, confira [Atualizar de uma implantação híbrida do Skype for Business para o Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).






## <a name="plan-for-external-access"></a>Plano para acesso externo

Por padrão, o acesso externo está ativado no Microsoft Teams, o que significa que sua organização pode se comunicar com todos os domínios externos. Se você adicionar domínios bloqueados, todos os outros domínios serão permitidos; e, se você adicionar domínios permitidos, todos os outros domínios serão bloqueados. Há três cenários para configurar o acesso externo no centro de administração do Teams ( > **acesso externo**às**configurações de toda a organização**):

- **Abrir Federação**: essa é a configuração padrão no Teams e permite que as pessoas em sua organização localizem, chamem, enviem mensagens de chat e configurem reuniões com pessoas externas à sua organização em qualquer domínio.

    Nesse cenário, os usuários podem se comunicar com todos os domínios externos que executam o Microsoft Teams ou o Skype for Business e estão usando a Federação aberta ou adicionaram seu domínio à lista de permissões.

- **Permitir domínios específicos**: ao adicionar domínios a uma lista de **permissões** , você limita o acesso externo somente aos domínios permitidos. Depois de configurar uma lista de domínios permitidos, todos os outros domínios serão bloqueados. Para permitir domínios específicos, clique em **Adicionar um domínio**, adicione o nome de domínio, clique em **ação para assumir o domínio**e selecione **permitido**.

- **Bloquear domínios específicos** – adicionando domínios a uma lista de **blocos** , você pode se comunicar com todos os domínios externos, *exceto* aqueles que você bloqueou. Para bloquear domínios específicos, clique em **Adicionar um domínio**, adicione o nome de domínio, clique em **ação para assumir o domínio**e selecione **bloqueado**. Depois de configurar uma lista de domínios bloqueados, todos os outros domínios serão permitidos.

## <a name="allow-or-block-domains"></a>Permitir ou bloquear domínios

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>Etapa 1: habilitar sua organização a se comunicar com outras organizações do Teams

![Um ícone mostrado o logotipo do Microsoft Teams](media/teams-logo-30x30.png)  **Usando centro de administração Microsoft Teams**

1. Na navegação à esquerda, acesse **Configurações em toda a organização** > **Acesso externo**.

2. Passe **Os usuários podem se comunicar com usuários do Skype for Business e do Teams** para **Ativo** no Acesso externo.

     ![Captura de tela com o acesso externo ativado](media/manage-external-access-2.png).

3. Se você deseja permitir que todas as organizações do Teams se comuniquem com os usuários em sua organização, pule para a Etapa 5.

4. Se você deseja limitar as organizações que podem se comunicar com os usuários em sua organização, é possível dar permissão a todos os domínios com exceção de alguns ou permitir apenas domínios específicos. 

    - Para permitir todos os domínios com exceção de alguns, clique em **Adicionar domínio** para adicionar os domínios que deseja bloquear. No painel **Adicionar um domínio**, digite o nome do domínio, clique em **Bloqueado** e depois em **Concluído**. 
    - Para limitar as comunicações a organizações específicas, adicione esses domínios à lista com um status de **Permitido**. Depois de ter adicionado um domínio à lista de Permissões, as comunicações com outras organizações estarão limitadas apenas às organizações cujos domínios estiverem na lista de Permissões. 

5. Clique em **Salvar**.

6. Verifique se o administrador do Teams da outra organização concluiu as mesmas etapas. Por exemplo, na lista de **domínios permitidos**, o administrador precisará inserir o domínio da sua empresa caso ele limite as organizações que podem se comunicar com seus usuários.

### <a name="step-2---test-it"></a>Etapa 2: testar

Para testar sua configuração, você precisa de um usuário do Teams que não seja protegido pelo seu firewall.
  
1. Depois de você e o administrador da organização terem alterado as configurações de **Acesso externo**, tudo deve estar pronto.

2. No aplicativo do Teams, pesquise um endereço de email e envie uma solicitação de chat.

3. Peça ao seu contato do Teams para lhe enviar uma solicitação de chat. Se você não receber a solicitação, é porque o problema está nas suas configurações de firewall (pressupondo que seu contato já confirmou que as configurações de firewall dele estão corretas).

4. Outra maneira de testar se o problema é o seu firewall é acessar um local WiFi que não está protegido pelo firewall. como uma cafeteria, e usar o Teams para enviar uma solicitação de chat ao seu contato. Se a mensagem passar pelo local WiFi, mas não quando você estiver no trabalho, você saberá que o problema é seu firewall.

> [!NOTE]
> Se você e outro usuário ativarem o acesso externo e permitirem um dos outros domínios, isso funcionará. Se isso não funcionar, o outro usuário deve verificar se a configuração não está bloqueando o seu domínio.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Comunicar-se com usuários em uma organização do Skype for Business Online

Se você estiver configurando o acesso externo para permitir que os usuários do seu Team localizem e entrem em contato com usuários em uma organização do Skype for Business que limitam quem pode contatar seus usuários, siga as etapas para configurar o acesso externo do seu domínio para o domínio da outra organização. Depois, peça ao administrador da outra organização para seguir as etapas abaixo para configurar o acesso externo ao Skype for Business Online. 

Para obter orientação específica sobre os cenários comuns do Skype for Business Online, consulte [cenários de acesso externo comuns](#common-external-access-scenarios) abaixo.

![Um ícone mostrando o logotipo do Skype for Business](media/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

Solicite que o administrador da organização siga estas etapas:

1. No centro de administração Microsoft 365, acesse **Centros de administração** > **Teams e Skype** > **Portal herdado**.
  
2. No **Centro de administração Skype for Business**, escolha **Organização** > **Comunicações externas**.

3. Para configurar a comunicação com uma empresa específica ou com usuários em outro domínio, na caixa suspensa, escolha **Ativado somente para os domínios permitidos**.

    OU, se o administrador desejar habilitar a comunicação com todos que tiverem as políticas do Skype for Business, escolha **Ativado exceto para domínios bloqueados**. Esta é a configuração padrão.

4. Em **Domínios bloqueados ou permitidos**, escolha **+** e adicione o nome do domínio que você deseja permitir.

## <a name="common-external-access-scenarios"></a>Cenários comuns de acesso externo

|**Se quiser...**  |**Fazer isso**  |
|---------|-----------------------|
|Permita que **os usuários do teams** na sua organização se comuniquem com **usuários do teams** em outra organização (externa).|No Acesso externo, adicione o domínio externo à lista permitida ou use a federação aberta. Depois, o administrador da outra organização do Teams deve fazer o mesmo.      |
|Permita que **os usuários do teams** na sua organização se comuniquem com **usuários do Skype for Business online** na mesma organização.  |Habilite o modo de Coexistência ou escolha o modo de Atualização das ilhas para oferecer suporte aos usuários do Skype for Business em sua organização.   |
|Permita que **os usuários do teams** na sua organização se comuniquem com **usuários do Skype for Business online** em outra organização (externa).      |No Acesso externo, adicione o domínio externo à lista permitida ou use a federação aberta. <br><br>Ative a configuração **Os usuários podem se comunicar com usuários do Skype for Business e do Teams** no Acesso externo. Depois, o administrador da outra organização do Teams deve fazer o mesmo. <br><br>**OBSERVAÇÃO**: o domínio externo com usuários do Skype for Business deve habilitar o modo de Coexistência ou escolher o modo de Atualização das ilhas para oferecer suporte aos usuários do Skype for Business na organização.|
|Permita que **os usuários do teams** na sua organização se comuniquem com usuários do **Skype** de dentro ou de fora da sua organização.   | Este cenário estará disponível em breve. <br><br>**Importante**: seus usuários do Microsoft Teams ainda não conseguem se comunicar com usuários do Skype, mas seus usuários do Skype for Business podem continuar a se comunicar com usuários do Skype dentro ou fora de sua organização. Ativar os **usuários podem se comunicar com os usuários do Skype for Business e do teams** e **os usuários do Skype for Business podem se comunicar com** as configurações de usuários do Skype no acesso externo. |
|Permita que seus **usuários do Skype for Business online** se comuniquem com **usuários do teams** em outra organização do Office 365.| Seus usuários do Skype for Business Online podem se comunicar com usuários do teams em outra organização se seus usuários estiverem em um dos seguintes modos de atualização: Ilhas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; e os usuários de equipes de outras organizações estão no modo TeamsOnly. <br><br>Habilite os **usuários que podem se comunicar com as configurações do Skype for Business e do teams Users** no acesso externo. Depois, o administrador da outra organização do Teams deve fazer o mesmo.|
|Permita que seus **usuários do Skype for Business online** se comuniquem com **usuários do Skype for Business online** de outra organização do Office 365.    | Seus usuários do Skype for Business Online podem se comunicar com usuários do Skype for Business online em outra organização se seus usuários estiverem em um dos seguintes modos de atualização: Ilhas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; os usuários do Skype for Business online da outra organização estão em um dos seguintes modos de atualização: Ilhas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>Habilite os **usuários que podem se comunicar com as configurações do Skype for Business e do teams Users** no acesso externo. Depois, o administrador da outra organização do Teams deve fazer o mesmo.|
|Permita que seus **usuários do Skype for Business online** se comuniquem com **usuários do Skype for Business** a partir de uma organização local.     |Seus usuários do Skype for Business online poderão se comunicar com usuários do Skype for Business a partir de uma organização local se os usuários estiverem em um dos seguintes modos de atualização: Ilhas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; os usuários do Skype for Business online da outra organização estão em um dos seguintes modos de atualização: Ilhas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>Habilite os **usuários que podem se comunicar com as configurações do Skype for Business e do teams Users** no acesso externo. Depois, o administrador da outra organização do Teams deve fazer o mesmo.|
|Permita que seus **usuários do Skype for Business online** se comuniquem com **usuários do Skype** (dentro ou fora da sua organização).   |Ative a configuração **Os usuários do Skype for Business podem se comunicar com usuários do Skype** no Acesso externo.|

> [!IMPORTANT]
> Você não precisa adicionar nenhum **domínio do Skype** como domínios permitidos para permitir que os usuários do teams ou do Skype for Business online se comuniquem com usuários do Skype dentro ou fora de sua organização. Todos os **domínios do Skype** são whitelists, o que significa que todos esses domínios são considerados permitidos.



## <a name="how-does-external-access-compare-with-guest-access"></a>Como o acesso externo se compara ao acesso de convidado?

Para saber mais sobre a diferença entre acesso externo e acesso de convidado, leia [comunicar-se com usuários de outras organizações](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Tópicos relacionados

[Experiência de chat nativo para usuários externos (federados)](native-chat-for-external-users.md)
