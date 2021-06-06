---
title: Gerenciar acesso externo (federação)
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
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
localization_priority: Priority
ms.openlocfilehash: 5f472ef2a009a3a0b9b87222d951ef34b65da15a
ms.sourcegitcommit: f5b6a0fe055e42e06eee21ce311813b5127474ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52741070"
---
# <a name="manage-external-access-in-microsoft-teams"></a>Gerenciar o acesso externo no Microsoft Teams

O acesso externo é uma maneira de os usuários do Teams de um domínio externo inteiro encontrarem, ligarem, baterem papo e marcarem reuniões com você no Teams. Você também pode usar o acesso externo para se comunicar com pessoas de outras organizações que ainda usam o Skype for Business (online e local) e o Skype (em versão prévia).

Se você deseja que pessoas de outras organizações tenham acesso a equipes e canais, o acesso de convidado pode ser a melhor opção. Para obter mais informações sobre as diferenças entre o acesso externo e o acesso para convidado, confira [Comparar o acesso externo e o acesso para convidado](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Usar o acesso externo quando:
  
- Você tem usuários em diferentes domínios que precisam trabalhar juntos. Por exemplo, pedro@contoso.com e eduarda@northwindtraders.com estão trabalhando em um projeto junto com outros nos domínios contoso.com e northwindtraders.com.

- Você desejar que as pessoas em sua organização usem o Teams para entrar em contato com pessoas em empresas específicas de fora de sua organização.

- Você desejar que todas as pessoas que usam o Teams sejam capazes de localizar e entrar em contato com você usando seu endereço de email. 

> [!IMPORTANT]
> Para usar o cliente Teams para se comunicar com um usuário externo (se esse usuário estiver usando Teams ou Skype for Business), o usuário Teams deve estar hospedado no Skype for Business Online.

## <a name="plan-for-external-access"></a>Planejar o acesso externo

O acesso externo é ativado por padrão no Teams, o que significa que sua organização pode se comunicar com todos os domínios externos. Se adicionar domínios bloqueados, todos os outros domínios serão permitidos; mas se adicionar domínios permitidos, todos os outros domínios serão bloqueados. A exceção a esta regra é se participantes anônimos são permitidos nas reuniões. Existem três cenários para configurar o acesso externo no centro de administração do Teams (**Configurações gerais de organização** > **Acesso externo**):

> [!NOTE]
> Os usuários do Teams podem adicionar aplicativos ao hospedar reuniões ou chats com pessoas de outras organizações. Eles também podem usar aplicativos compartilhados por pessoas de outras organizações quando ingressarem em reuniões ou chats hospedados por essas organizações. As políticas de dados da organização do usuário de hospedagem, assim como as práticas de compartilhamento de dados de qualquer aplicativo de terceiros compartilhado pela organização desse usuário, serão aplicadas.

> [!NOTE]
> Se você desabilitar o acesso externo em sua organização, os usuários externos ainda poderão ingressar em reuniões por meio de ingresso anônimo. Para saber mais, veja [Gerenciar configurações de reunião no Teams](./meeting-settings-in-teams.md).

- **Federação aberta**: essa é a configuração padrão no Teams. Ela permite que as pessoas em sua organização localizem, façam chamadas e enviem mensagens instantâneas, conversem e configurem reuniões com pessoas de fora da sua organização, em qualquer domínio.

    Neste caso, os usuários podem se comunicar com todos os domínios externos que estejam executando o Teams ou o Skype for Business e estejam usando a Federação Aberta ou tenham adicionado seu domínio à lista de permissões.

- **Permitir domínios específicos**: ao adicionar domínios a uma lista de **permissões**, você limita o acesso externo somente aos domínios permitidos. Depois de configurar uma lista de domínios permitidos, todos os outros domínios serão bloqueados. Para permitir domínios específicos, clique em **Adicionar um domínio**, adicione o nome do domínio, clique em **Ação a ser executada neste domínio** e depois selecione **Permitido**.

- **Bloquear domínios específicos**: ao adicionar domínios a uma lista de **bloqueados**, você pode se comunicar com todos os domínios externos, *exceto* os bloqueados. Para bloquear domínios específicos, clique em **Adicionar um domínio**, adicione o nome do domínio, clique em **Ação a ser executada neste domínio** e depois selecione **Bloqueado**. Depois de configurar uma lista de domínios bloqueados, todos os outros domínios serão bloqueados.

> [!NOTE]
> Os domínios permitidos ou bloqueados só se aplicam às reuniões se o acesso anônimo às reuniões estiver "desabilitado".

## <a name="allow-or-block-domains"></a>Permitir ou bloquear domínios

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a>Etapa 1 - Habilitar que sua organização se comunique com outras equipes ou organizações do Skype for Business

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

3. Peça ao seu contato do Teams para enviar a você uma solicitação de chat. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).

4. Outra maneira de testar se o problema é o firewall, basta usar o WiFi de um lugar que não tenha firewall, como uma cafeteria, e usar o Teams para enviar uma solicitação de chat para um contato. Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.

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

As seções a seguir descrevem como habilitar a federação para cenários de acesso externo comuns e como a Política de atualização do Teams determina a entrega de chats e chamadas de entrada.

### <a name="enable-federation"></a>Habilitar a federação:

Para habilitar que os usuários em sua organização se comuniquem com usuários em outra organização, ambas as organizações devem habilitar a federação. As etapas para habilitar a federação para uma determinada organização dependem se a organização é puramente online, híbrida ou puramente local.

| Se sua organização for | Habilitar a federação da seguinte forma |
|:---------|:-----------------------|
|Online sem Skype for Business no local. Isso inclui organizações que têm usuários TeamsOnly e/ou usuários do Skype for Business Online.| Se estiver usando o Centro de Administração Teams: <br>-   Certifique-se de que **Os usuários podem se comunicar com outros usuários do Skype for Business e Teams** configuração está habilitada em Acesso Externo.<br>- Se você não estiver usando a federação aberta (que permite a federação com qualquer outro domínio), adicione o domínio externo à lista Permitido.<br><br>Se estiver usando PowerShell:<br>- Certifique-se de que o locatário esteja habilitado para federação: `Get-CsTenantFederationConfiguration` deve mostrar `AllowFederatedUsers=true` <br>- Garanta o valor efetivo do usuário de `CsExternalAccessPolicy` tem `EnableFederationAccess=true`.<br>- Se você não estiver usando federação aberta, certifique-se de que o domínio de destino esteja listado em `AllowedDomains` de `CsTenantFederationConfiguration`. |
|Puro no local | Em ferramentas locais: <br>- Certifique-se de que a federação está habilitada em `CsAccessEdgeConfiguration`.<br>- Certifique-se de que a federação para o usuário está habilitada por meio de `ExternalAccessPolicy` (seja por meio da política global, política do site ou política atribuída pelo usuário). <br> - Se você não estiver usando federação aberta, certifique-se de que o domínio de destino esteja listado em `AllowedDomains`. |
|Híbrido com alguns usuários online (no Skype for Business ou Teams) e alguns usuários no local. | Siga as etapas acima para organizações online e locais. |

### <a name="delivery-of-incoming-chats-and-calls"></a>Entrega de chats e chamadas recebidas 

Os chats e chamadas de entrada de uma organização da federação vão parar no Teams do usuário ou no cliente Skype for Business, dependendo do modo do usuário destinatário na Política de atualização de equipes.

| Se você quiser | Faça o seguinte: |
|:---------|:-----------------------|
| Garanta que os chats e chamadas federados de entrada cheguem ao cliente Teams do usuário: | Configure seus usuários para serem TeamsOnly.
| Garanta que os chats e chamadas federados de entrada cheguem ao cliente Skype for Business do usuário | Configure seus usuários para estarem em qualquer modo diferente de TeamsOnly. |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>Habilite a federação entre usuários em sua organização e usuários consumidores do Skype

Para habilitar a federação entre usuários em sua organização e usuários consumidores do Skype:

| Se sua organização for | Habilitar a federação do consumidor da seguinte forma |
|:---------|:-----------------------|
| Puro online, sem Skype for Business local.  Isso inclui organizações que têm usuários TeamsOnly e/ou usuários do Skype for Business Online. | Se estiver usando o Centro de Administração Teams: <br>No Acesso Externo, ative a configuração **Os usuários podem se comunicar com usuários do Skype**.<br><br>Se estiver usando PowerShell: <br>- Certifique-se de que o locatário está habilitado para federação: `Get-CsTenantFederationConfiguration` deve mostrar `AllowPublicUsers=true`. <br> - Garanta o valor efetivo do usuário de `CsExternalAccessPolicy` tem `EnablePublicCloudAccess=true`. |
| Puro no local | Em ferramentas locais: <br> - Certifique-se de que o Skype está habilitado como parceiro federado. <br> - Garantir `EnablePublicCloudAccess=true` para o usuário por meio de `ExternalAccessPolicy` (por meio de política global, política do site ou política atribuída pelo usuário).|
| Híbrido com alguns usuários online (no Skype for Business ou Teams) e alguns usuários no local.| Siga as etapas acima para organizações online e locais.


> [!IMPORTANT]
> Não é necessário adicionar nenhum **domínio do Skype** como domínio permitido para permitir que os usuários do Teams ou do Skype for Business Online se comuniquem com usuários do Skype de dentro ou de fora da sua organização. Todo **Domínios Skype** são autorizadas.

## <a name="how-does-external-access-compare-with-guest-access"></a>Como o acesso externo se compara ao acesso para convidado?

Para saber mais sobre a diferença entre o acesso externo e o acesso para convidado, confira[Comunicar-se com usuários de outras organizações](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Experiência de chat nativo para usuários externos (federados)](native-chat-for-external-users.md)
