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
description: Seu administrador do Teams ou de TI pode configurar o acesso externo de outros domínios (federação) para permitir que os usuários desses domínios encontrem, liguem, conversem e configurem reuniões com seus usuários.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: ee2492038ac05f54d1846703851846bef95893eb
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634920"
---
# <a name="manage-external-access-in-microsoft-teams"></a>Gerenciar o acesso externo no Microsoft Teams

O acesso externo é uma maneira de os usuários do Teams de um domínio externo inteiro encontrarem, ligarem, conversarem e marcarem reuniões com você no Teams. Você também pode usar o acesso externo para se comunicar com pessoas de outras organizações que ainda usam o Skype for Business (online e local) e o Skype (em versão prévia).

Se você quer que pessoas de outras organizações tenham acesso às equipes e canais, o acesso de convidado pode ser a melhor opção. Para obter mais informações sobre as diferenças entre o acesso externo e o acesso para convidado, confira [Comparar o acesso externo e o acesso para convidado](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Usar o acesso externo quando:
  
- Você possui usuários em domínios externos que precisam trabalhar juntos. Por exemplo, Rob@contoso.com e Ann@northwindtraders.com estão trabalhando em um projeto junto com outros nos domínios contoso.com e northwindtraders.com.

- Você desejar que as pessoas em sua organização usem o Teams para entrar em contato com pessoas em empresas específicas de fora de sua organização.

- Você desejar que todas as pessoas que usam o Teams sejam capazes de localizar e entrar em contato com você usando seu endereço de email. 

## <a name="plan-for-external-access"></a>Planejar o acesso externo

O acesso externo é ativado por padrão no Teams, o que significa que sua organização pode se comunicar com todos os domínios externos. Se adicionar domínios bloqueados, todos os outros domínios serão permitidos; mas se adicionar domínios permitidos, todos os outros domínios serão bloqueados. A exceção a esta regra é se participantes anônimos são permitidos nas reuniões. Há três cenários para configurar o acesso externo no Centro de administração do Teams (**Usuários** > **Acesso externo**):

> [!NOTE]
> Os usuários do Teams podem adicionar aplicativos ao hospedar reuniões ou chats com pessoas de outras organizações. Eles também podem usar aplicativos compartilhados por pessoas de outras organizações quando ingressarem em reuniões ou chats hospedados por essas organizações. As políticas de dados da organização do usuário de hospedagem, assim como as práticas de compartilhamento de dados de qualquer aplicativo de terceiros compartilhado pela organização desse usuário, serão aplicadas.

> [!NOTE]
> Se você desabilitar o acesso externo em sua organização, os usuários externos ainda poderão ingressar em reuniões por meio de ingresso anônimo. Para saber mais, veja [Gerenciar configurações de reunião no Teams](meeting-settings-in-teams.md).

- **Permitir todos os domínios externos**: essa é a configuração padrão no Teams e permite que as pessoas na sua organização localizem, liguem, conversem e configurem reuniões com pessoas externas à sua organização em qualquer domínio.

    Nesse cenário, seus usuários podem se comunicar com todos os domínios externos que estiverem executando o Teams ou Skype for Business ou que permitam todos os domínios externos ou que tenham adicionado seu domínio à sua lista de permissões.

- **Permitir apenas domínios externos específicos**: ao adicionar domínios a uma lista **Permitir**, você limita o acesso externo apenas aos domínios permitidos. Depois de configurar uma lista de domínios permitidos, todos os outros domínios serão bloqueados. Para permitir domínios específicos, clique em **Adicionar um domínio**, adicione o nome do domínio, clique em **Ação a ser executada neste domínio** e depois selecione **Permitido**.

- **Bloquear domínios específicos**: ao adicionar domínios a uma lista de **bloqueados**, você pode se comunicar com todos os domínios externos, *exceto* os bloqueados. Para bloquear domínios específicos, clique em **Adicionar um domínio**, adicione o nome do domínio, clique em **Ação a ser executada neste domínio** e depois selecione **Bloqueado**. Depois de configurar uma lista de domínios bloqueados, todos os outros domínios serão bloqueados.

- **Bloquear todos os domínios externos** - Impede que as pessoas na sua organização localizem, chamem, conversem e configurem reuniões com pessoas externas à sua organização em qualquer domínio.

> [!NOTE]
> Os domínios permitidos ou bloqueados só se aplicam às reuniões se o acesso anônimo às reuniões estiver "desabilitado".

## <a name="allow-or-block-domains"></a>Permitir ou bloquear domínios

  **Usando o centro de administração do Microsoft Teams**

Para permitir domínios específicos

1. No Centro de administração do Teams, acesse **Usuários**  >  **Acesso externo**.

2. Em **Escolher quais domínios seus usuários possuem acesso**, escolha **Permitir apenas domínios externos específicos**.

3. Selecione **Permitir domínios**.

4. Na caixa **Domínio**, digite o domínio que você quer permitir e clique em **Feito**.

5. Se você quiser permitir outro domínio, clique em **Adicionar um domínio**.

6. Clique em **Salvar**.

Para bloquear domínios específicos

1. No Centro de administração do Teams, acesse **Usuários**  >  **Acesso externo**.

2. Em **Escolher quais domínios seus usuários possuem acesso**, escolha **Bloquear apenas domínios externos específicos**.

3. Selecione **Bloquear domínios**.

4. Na caixa **Domínio**, digite o domínio que você quer permitir e clique em **Feito**.

5. Se você quiser bloquear outro domínio, clique em **Adicionar um domínio**.

6. Clique em **Salvar**.

Certifique-se de que o administrador na outra organização do Teams conclua essas mesmas etapas. Por exemplo, na sua lista de **domínios permitidos**, o administrador precisará inserir o domínio da sua empresa caso ele limite as organizações que podem se comunicar com seus usuários.

## <a name="communicate-with-skype-users-preview"></a>Comunicação com usuários do Skype (visualização)

Siga estas etapas para permitir que os usuários do Teams em sua organização conversem com usuários do Skype. Os usuários do Teams podem pesquisar e iniciar uma conversa de somente texto ou uma chamada de áudio/vídeo com usuários do Skype e vice-versa.

  **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, acesse **Usuários** > **Acesso externo**.

2. Ative a configuração **Permitir que os usuários da minha organização se comuniquem com os usuários do Skype**.

Para saber mais sobre as formas pelas quais os usuários do Teams e do Skype podem se comunicar, incluindo as limitações que se aplicam, confira [Teams e a interoperabilidade do Skype](teams-skype-interop.md).

## <a name="block-unsolicited-contact-with-external-unmanaged-teams-users"></a>Bloquear o contato não solicitado com usuários externos não Teams

Siga essas etapas para impedir usuários do Teams em sua organização de contato não solicitado com usuários externos do Teams cujas contas não são gerenciadas por uma organização.

  **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, acesse **Usuários** > **Acesso externo**.

2. Siga uma dessas etapas:

    - Para impedir que usuários Teams em sua organização se comuniquem com usuários externos do Teams cujas contas não são gerenciadas por uma organização, desative a configuração **Pessoas em minha organização podem se comunicar com usuários do Teams cujas contas não são gerenciadas por uma organização** e desmarque a caixa de seleção **Usuários externos com contas do Teams não gerenciadas por uma organização podem entrar em contato com usuários em minha organização**.

    - Para permitir que os usuários Teams em sua organização se comuniquem com usuários externos do Teams cujas contas não são gerenciadas por uma organização se seus usuários do Teams iniciarem o contato, habilite a configuração **Pessoas em minha organização podem se comunicar com usuários Teams cujas contas não são gerenciadas por uma organização** e desmarque a caixa de seleção **Usuários externos com contas do Teams não gerenciadas por uma organização pode entrar em contato com usuários na minha organização**.

    - Para permitir que os usuários Teams em sua organização se comuniquem com usuários externos do Teams cujas contas não são gerenciadas por uma organização e recebam solicitações para se comunicar com esses usuários externos do Teams, habilite a opção **Pessoas em minha organização podem se comunicar com usuários do Teams cujas contas não são gerenciadas por uma organização** e selecionar a caixa **Usuários externos com contas Teams não gerenciadas por uma organização podem entrar em contato com usuários na minha organização**.

## <a name="test-access"></a>Testar o acesso

Para testar sua configuração, você precisa de um usuário do Teams que não seja protegido pelo seu firewall.
  
1. Depois de você e o administrador da organização terem alterado as configurações de **Acesso externo**, tudo deve estar pronto.

2. No aplicativo do Teams, pesquise um endereço de email e envie uma solicitação de chat.

3. Peça ao seu contato do Teams para enviar a você uma solicitação de chat. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).

4. Outra maneira de testar se o problema é o firewall, basta usar o WiFi de um lugar que não tenha firewall, como uma cafeteria, e usar o Teams para enviar uma solicitação de chat para um contato. Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.

> [!NOTE]
> Isso funcionará se você e outro usuário habilitarem o acesso externo e permitirem domínios um do outro. Se não funcionar, o outro usuário deve verificar se a configuração que ele está usando está bloqueando o seu domínio.

## <a name="common-external-access-scenarios"></a>Casos comuns de acesso externo

As seções a seguir descrevem como habilitar a federação para cenários de acesso externo comuns e como a Política de atualização do Teams determina a entrega de chats e chamadas de entrada.

### <a name="enable-federation"></a>Habilitar a federação:

Para habilitar que os usuários em sua organização se comuniquem com usuários em outra organização, ambas as organizações devem habilitar a federação. As etapas para habilitar a federação para uma determinada organização dependem se a organização é puramente online, híbrida ou puramente local.

| Se sua organização for | Habilitar a federação da seguinte forma |
|:---------|:-----------------------|
|Online sem Skype for Business no local. Isso inclui organizações que têm usuários TeamsOnly e/ou usuários do Skype for Business Online.| Se estiver usando o Centro de Administração Teams: <br>- Certifique-se de que os domínios com os quais você quer se comunicar sejam permitidos no Acesso Externo.<br><br>Se estiver usando PowerShell:<br>- Certifique-se de que o locatário esteja habilitado para federação: `Get-CsTenantFederationConfiguration` deve mostrar `AllowFederatedUsers=true` <br>- Garanta o valor efetivo do usuário de `CsExternalAccessPolicy` tem `EnableFederationAccess=true`.<br>- Se você não estiver usando federação aberta, certifique-se de que o domínio de destino esteja listado em `AllowedDomains` de `CsTenantFederationConfiguration`. |
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
| Puro online, sem Skype for Business local.  Isso inclui organizações que têm usuários TeamsOnly e/ou usuários do Skype for Business Online. | Se estiver usando o Centro de Administração Teams: <br>-Certifique-se de que **Permitir que os usuários da minha organização se comuniquem com os usuários do Skype** esteja habilitado no Acesso Externo.<br><br>Se estiver usando PowerShell: <br>- Certifique-se de que o locatário está habilitado para federação: `Get-CsTenantFederationConfiguration` deve mostrar `AllowPublicUsers=true`. <br> - Garanta o valor efetivo do usuário de `CsExternalAccessPolicy` tem `EnablePublicCloudAccess=true`. |
| Puro no local | Em ferramentas locais: <br> - Certifique-se de que o Skype está habilitado como parceiro federado. <br> - Garantir `EnablePublicCloudAccess=true` para o usuário por meio de `ExternalAccessPolicy` (por meio de política global, política do site ou política atribuída pelo usuário).|
| Híbrido com alguns usuários online (no Skype for Business ou Teams) e alguns usuários no local.| Siga as etapas acima para organizações online e locais.


> [!IMPORTANT]
> Você não precisa adicionar **domínios do Skype** como domínios permitidos para permitir que os usuários do Teams ou do Skype for Business Online se comuniquem com usuários do Skype dentro ou fora da sua organização. Todos os **domínios do Skype** são permitidos.

## <a name="federation-diagnostic-tool"></a>Ferramenta de Diagnóstico de Federação

Se você for um administrador, poderá usar a seguinte ferramenta de diagnóstico para validar se um usuário do Teams pode se comunicar com um usuário federado do Teams:

1. Selecione **Executar testes** abaixo, o que preencherá o diagnóstico no Centro de Administração do Microsoft 365. 

   > [!div class="nextstepaction"]
   > [Executar testes: Federação do Teams](https://aka.ms/TeamsFederationDiag)

2. No painel "Executar diagnóstico", insira o **Endereço do protocolo SIP** e o **Nome de domínio do locatário federado**, e selecione **Executar Testes**.

3. Os testes retornarão as melhores próximas etapas para resolver quaisquer configurações de locatário ou de política que estejam impedindo a comunicação com o usuário federado.


## <a name="related-topics"></a>Tópicos relacionados

- [Experiência de chat nativo para usuários externos (federados)](native-chat-for-external-users.md)
