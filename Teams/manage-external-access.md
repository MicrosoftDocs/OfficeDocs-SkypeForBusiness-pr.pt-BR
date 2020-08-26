---
title: Gerenciar o acesso externo (Federação)
author: SerdarSoysal
ms.author: serdars
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
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: O administrador do Teams ou de TI pode configurar o acesso externo para outros domínios (federação) para permitir que os usuários desses domínios participem do Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: b3d6eafe5f2ab5989e5b21a060901dc317332127
ms.sourcegitcommit: c1aaf1f81c07c0956095b5bd4cb241b1de67b189
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46897821"
---
<a name="manage-external-access-in-microsoft-teams"></a>Gerenciar o acesso externo no Microsoft Teams
======================================================

O acesso externo é uma maneira para os usuários do teams de um domínio externo inteiro para localizar, chamar, bater papo e configurar reuniões com você no Teams. Você também pode usar o acesso externo para se comunicar com usuários externos que ainda estão usando o Skype for Business (online e local) e o Skype (na versão prévia).

Se desejar que usuários externos tenham acesso a equipes e canais, o acesso para convidado será a melhor opção. Para obter mais informações sobre as diferenças entre o acesso externo e o acesso para convidado, confira [Comparar o acesso externo e o acesso para convidado](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Usar o acesso externo quando:
  
- Você tem usuários em domínios diferentes que precisam colaborar. Por exemplo, pedro@contoso.com e eduarda@northwindtraders.com estão trabalhando em um projeto junto com outros nos domínios contoso.com e northwindtraders.com.

- Você desejar que as pessoas em sua organização usem o Teams para entrar em contato com pessoas em empresas específicas de fora de sua organização.

- Você desejar que todas as pessoas que usam o Teams sejam capazes de localizar e entrar em contato com você usando seu endereço de email. 

> [!IMPORTANT]
> Atualmente, para executar a federação dentro do aplicativo Microsoft Teams a um usuário externo à sua organização que não seja um convidado do Azure AD (Azure Active Directory) ou locatário, a sua configuração como híbrido deve estar correta e você deve ter migrado para o Skype for Business Online. A partir de 25 de fevereiro de 2019, o Teams não é compatível com a Federação **nativa** sem que o usuário do perfil SIP seja hospedado no Skype for Business online. Para saber mais sobre como configurar sua conta como híbrida e depois migrar o Teams, confira [Atualizar de uma implantação híbrida do Skype for Business para o Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

## <a name="plan-for-external-access"></a>Planejar o acesso externo

O acesso externo é ativado por padrão no Teams, o que significa que sua organização pode se comunicar com todos os domínios externos. Se adicionar domínios bloqueados, todos os outros domínios serão permitidos; mas se adicionar domínios permitidos, todos os outros domínios serão bloqueados. Há três casos para configurar o acesso externo no centro de administração do Teams (**Configurações de toda a organização** > **Acesso externo**):

- **Federação aberta**: essa é a configuração padrão no Teams. Ela permite que as pessoas em sua organização localizem, façam chamadas e enviem mensagens instantâneas, conversem e configurem reuniões com pessoas de fora da sua organização, em qualquer domínio.

    Neste caso, os usuários podem se comunicar com todos os domínios externos que estejam executando o Teams ou o Skype for Business e estejam usando a Federação Aberta ou tenham adicionado seu domínio à lista de permissões.

- **Permitir domínios específicos**: ao adicionar domínios a uma lista de **permissões**, você limita o acesso externo somente aos domínios permitidos. Depois de configurar uma lista de domínios permitidos, todos os outros domínios serão bloqueados. Para permitir domínios específicos, clique em **Adicionar um domínio**, adicione o nome do domínio, clique em **Ação a ser executada neste domínio** e depois selecione **Permitido**.

- **Bloquear domínios específicos**: ao adicionar domínios a uma lista de **bloqueados**, você pode se comunicar com todos os domínios externos, *exceto* os bloqueados. Para bloquear domínios específicos, clique em **Adicionar um domínio**, adicione o nome do domínio, clique em **Ação a ser executada neste domínio** e depois selecione **Bloqueado**. Depois de configurar uma lista de domínios bloqueados, todos os outros domínios serão bloqueados.

## <a name="allow-or-block-domains"></a>Permitir ou bloquear domínios

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a>Etapa 1-permitir que sua organização se comunique com outras equipes ou organizações do Skype for Business

![Um ícone mostrado o logotipo do Microsoft Teams](media/teams-logo-30x30.png)  **Usando centro de administração Microsoft Teams**

1. Na navegação à esquerda, acesse **Configurações em toda a organização** > **Acesso externo**.

2. Ative a configuração **Os usuários podem se comunicar com usuários do Skype for Business e do Teams**.

     ![Captura de tela da configuração Os usuários podem se comunicar com usuários do Skype for Business e do Teams habilitada.](media/manage-external-access-2.png).

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

4. Outra maneira de testar se o problema está no seu firewall é acessar um local com WiFi não protegido pelo seu firewall, como uma cafeteria, e usar o Teams para enviar uma solicitação de chat ao seu contato. Se conseguir enviar a mensagem usando o WiFi do local e não conseguir fazer o mesmo no seu trabalho, isso quer dizer que o problema está no seu firewall.

> [!NOTE]
> Isso funcionará se você e outro usuário habilitarem o acesso externo e permitirem domínios um do outro. Se não funcionar, o outro usuário deve verificar se a configuração que ele está usando está bloqueando o seu domínio.


## <a name="communicate-with-skype-users-in-preview"></a>Comunicação com usuários do Skype (na visualização)

Siga estas etapas para permitir que os usuários do Teams em sua organização conversem com usuários do Skype. Os usuários do Teams podem pesquisar e iniciar uma conversa de somente texto ou uma chamada de áudio/vídeo com usuários do Skype e vice-versa.

![Um ícone mostrado o logotipo do Microsoft Teams](media/teams-logo-30x30.png)  **Usando centro de administração Microsoft Teams**

1. Na navegação à esquerda, acesse **Configurações em toda a organização** > **Acesso externo**.

2. Ative a configuração **Os usuários podem se comunicar com os usuários do Skype**.

    ![Captura de tela da configuração Os usuários podem se comunicar com o Skype ativada](media/manage-external-access-5.png).

Para saber mais sobre as formas pelas quais os usuários do Teams e do Skype podem se comunicar, incluindo as limitações que se aplicam, confira [Teams e a interoperabilidade do Skype](teams-skype-interop.md).

## <a name="common-external-access-scenarios"></a>Casos comuns de acesso externo

|**Se você quiser...**  |**Faça isto**  |
|---------|-----------------------|
|Permita que **usuários do Teams** da sua organização se comuniquem com **usuários do Teams** de outra organização (externa).|No Acesso externo, adicione o domínio externo à lista permitida ou use a federação aberta. Depois, o administrador da outra organização do Teams deve fazer o mesmo.      |
|Permita que **usuários do Teams** da sua organização se comuniquem com **usuários do Skype for Business Online** da mesma organização.  |Habilite o modo de Coexistência ou escolha o modo de Atualização das ilhas para oferecer suporte aos usuários do Skype for Business em sua organização.   |
|Permita que **usuários do Teams** da sua organização se comuniquem com **usuários do Skype for Business Online** de outra organização (externa).      |No Acesso externo, adicione o domínio externo à lista de permissões ou use a federação aberta. <br><br>No Acesso Externo, ative a configuração **Os usuários podem se comunicar com usuários do Skype for Business e do Teams**. Depois, o administrador da outra organização do Teams deve fazer o mesmo. <br><br>**OBSERVAÇÃO**: o domínio externo com usuários do Skype for Business deve habilitar o modo de Coexistência ou escolher o modo de Atualização das ilhas para oferecer suporte aos usuários do Skype for Business na organização.|
|Permita que **os usuários do teams** na sua organização se comuniquem com **usuários locais do Skype for Business** em outra organização (externa).      |No Acesso externo, adicione o domínio externo à lista de permissões ou use a federação aberta. <br><br>No Acesso Externo, ative a configuração **Os usuários podem se comunicar com usuários do Skype for Business e do Teams**. Em seguida, faça com que o administrador da outra organização configure o servidor do Skype for Business no local para permitir a Federação com o seu domínio.|
|Permita que **usuários do Teams** em sua organização se comuniquem com usuários do **Skype**.<br>  |No Acesso Externo, ative a configuração **Os usuários podem se comunicar com usuários do Skype**. |
|Permita que seus **usuários do Skype for Business online** se comuniquem com **usuários do teams** em outro 365 ou o Office 365.| Os usuários do Skype for Business Online podem se comunicar com usuários do Teams em outra organização se os usuários estiverem em um dos seguintes modos de atualização: Ilhas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings, e se os usuários do Teams de outra organização estiverem no modo TeamsOnly. <br><br>No Acesso Externo, ative a configuração **Os usuários podem se comunicar com outros usuários do Skype for Business e do Teams**. Depois, o administrador de outra organização com o Teams deve fazer o mesmo.|
|Permita que seus **usuários do Skype for Business online** se comuniquem com **usuários do Skype for Business online** de outro Microsoft 365 ou do Office 365.    | Os usuários do Skype for Business Online podem se comunicar com usuários do Skype for Business Online em outra organização se os usuários estiverem em um dos seguintes modos de atualização: Ilhas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; e se os usuários do Skype for Business Online de outra organização estiverem nos seguintes modos de atualização: Ilhas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>No Acesso Externo, ative a configuração **Os usuários podem se comunicar com outros usuários do Skype for Business e do Teams**. Depois, o administrador de outra organização com o Teams deve fazer o mesmo.|
|Permita que **usuários do Skype for Business Online** se comuniquem com **usuários do Skype for Business Online** de outra organização local.     |Seus usuários do Skype for Business online poderão se comunicar com usuários do Skype for Business a partir de uma organização local se os usuários estiverem em um dos seguintes modos de atualização: Ilhas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings. <br><br> No Acesso Externo, ative a configuração **Os usuários podem se comunicar com outros usuários do Skype for Business e do Teams**. Em seguida, faça com que o administrador da outra organização configure o servidor do Skype for Business no local para permitir a Federação com o seu domínio.|
|Permita que **usuários do Skype for Business Online** se comuniquem com **usuários do Skype** (de dentro ou de fora da sua organização).   |No Acesso Externo, ative a configuração **Os usuários podem se comunicar com usuários do Skype**.|

> [!IMPORTANT]
> Não é necessário adicionar nenhum **domínio do Skype** como domínio permitido para permitir que os usuários do Teams ou do Skype for Business Online se comuniquem com usuários do Skype de dentro ou de fora da sua organização. Todos os **domínios Skype** estão na lista de permissões, o que significa que todos esses domínios são considerados PERMITIDOS.

## <a name="how-does-external-access-compare-with-guest-access"></a>Como o acesso externo se compara ao acesso para convidado?

Para saber mais sobre a diferença entre o acesso externo e o acesso para convidado, confira[Comunicar-se com usuários de outras organizações](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Experiência de chat nativo para usuários externos (federados)](native-chat-for-external-users.md)
