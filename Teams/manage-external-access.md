---
title: Gerenciar o acesso externo (federação) no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/12/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.externalaccess.overview
description: O administrador de TI pode configurar o acesso externo para outros domínios (federação) para permitir que os usuários desses domínios participem do Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: f39760eb971a333373191b444abbb72395f13737
ms.sourcegitcommit: 1721acdd507591d16a4e766b390b997979d985e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37305756"
---
<a name="manage-external-access-in-microsoft-teams"></a>Gerenciar o acesso externo no Microsoft Teams
======================================================

Com o acesso externo do Microsoft Teams, os usuários do Teams de outros domínios podem participar de chats e chamadas. Também é possível permitir a participação de outros usuários externos que ainda estejam usando o Skype for Business Online, o Skype for Business local ou até mesmo o Skype.

Use as etapas presentes neste artigo quando:
  
- Você tiver usuários em diferentes domínios na sua empresa, como carlos@contoso.com e ana@northwindtraders.com.

- Você desejar que as pessoas em sua organização usem o Teams para entrar em contato com pessoas em empresas específicas de fora de sua organização.

- Você desejar que todas as pessoas que usam o Teams sejam capazes de localizar e entrar em contato com você usando seu endereço de email. Isso funcionará se você e outro usuário habilitarem o acesso externo e permitirem domínios um do outro. Se não funcionar, o outro usuário deve verificar se a configuração que ele está usando está bloqueando o seu domínio.

O acesso externo permite aos usuários externos localizar você, telefonar e enviar mensagens instantâneas, além de marcar reuniões. No entanto, se você desejar que usuários externos tenham acesso a equipes e canais, o acesso de convidados deve ser a melhor opção. Para obter mais informações sobre as diferenças entre o acesso externo e o acesso de convidado, confira [Acesso externo versus acesso de convidado](#external-access-vs-guest-access) abaixo. Para ativar o acesso de convidado, confira [Ativar ou desativar o acesso de convidado ao Microsoft Teams](set-up-guests.md) para que os usuários possam se comunicar.

> [!IMPORTANT]
> Atualmente, para executar a federação dentro do aplicativo Microsoft Teams a um usuário externo à sua organização que não seja um convidado do Azure AD (Azure Active Directory) ou locatário, a sua configuração como híbrido deve estar correta e você deve ter migrado para o Skype for Business Online. A partir de 25/02/2019, o Teams não terá mais suporte à federação nativa sem o usuário do perfil SIP estar hospedado no Skype for Business Online. Para saber mais sobre como configurar sua conta como híbrida e depois migrar o Teams, confira [Atualizar de uma implantação híbrida do Skype for Business para o Teams](https://docs.microsoft.com/pt-BR/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

> [!IMPORTANT]
> Os usuários convidados seguem as configurações de toda a organização para o modo de coexistência. Isso não pode ser alterado.

## <a name="external-access-vs-guest-access"></a>Acesso externo versus acesso de convidado

O acesso externo (federação) e o acesso de convidado são diferentes:

- O acesso de convidado concede acesso a uma pessoa. O acesso externo concede acesso a um domínio todo.

- O acesso de convidado, depois de concedido por um proprietário de equipe, permite que o convidado [acesse recursos](guest-experience.md), como discussões e arquivos de canal de uma equipe específica, além de conversar com outros usuários da equipe para a qual foi convidado. Com o acesso externo (chat federado), os participantes do chat externo não têm acesso às equipes ou aos recursos das equipes da organização que o convidou. Eles só podem participar de um chat federado entre duas pessoas. Os administradores de locatários podem escolher entre as duas opções de comunicação, dependendo do nível de colaboração desejável com o participante externo. Os administradores podem escolher uma ou ambas as abordagens, dependendo das suas necessidades organizacionais, mas é recomendável permitir o acesso de convidado para obter uma experiência mais abrangente e colaborativa do Teams. 

Confira a tabela a seguir para obter uma comparação de recursos de acesso externo e de convidado.

| Recurso | Usuários de acesso externo | Usuários de acesso de convidado |
|---------|-----------------------|--------------------|
| O usuário pode conversar com alguém de outra empresa | Sim |Sim |
| O usuário pode fazer chamadas para alguém de outra empresa | Sim | Sim |
| Os usuários podem ver se alguém de outra empresa está disponível para uma chamada ou um chat | Sim | Sim<sup>1</sup> |
| O usuário pode pesquisar usuários em locatários externos | Sim<sup>2</sup> | Não |
| O usuário pode compartilhar arquivos | Não | Sim |
| O usuário pode acessar os recursos do Teams | Não | Sim |
| O usuário pode ser adicionado a um chat de grupo | Não | Sim |
| O usuário pode ser adicionado a uma reunião | Sim | Sim |
| É possível adicionar outros usuários a um chat com um usuário externo | Não<sup>3</sup> | N/D |
| O usuário é identificado como um participante externo | Sim | Sim |
| A presença é exibida | Sim | Sim |
| A mensagem de ausência temporária é exibida | Não | Sim |
| É possível bloquear um usuário individual | Não | Não |
| Há suporte para @menções | Não | Sim |
| Fazer chamadas privadas | Sim | Sim |
| Permitir vídeo IP | Sim | Sim |
| Modo de compartilhamento de tela | Não | Sim |
| Permitir Reunir Agora
 | Não | Sim |
| Editar mensagens enviadas | Não | Sim |
| É possível excluir mensagens enviadas | Não | Sim |
| Usar Giphy em conversas | Não | Sim |
| Usar memes em conversas | Não | Sim |
| Usar figurinhas em conversas | Não | Sim |
||||

<sup>1</sup> Desde que o usuário tenha sido adicionado como um convidado e esteja conectado também como convidado ao locatário de convidado.<br>
<sup>2</sup> Apenas por endereço de email ou de protocolo SIP.<br>
<sup>3</sup> O chat externo (federado) funciona apenas no modo 1:1.

Para obter mais informações sobre os recursos e a experiência de convidado, confira [Ativar ou desativar o acesso de convidado ao Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) e [Como é a experiência do convidado](https://docs.microsoft.com/microsoftteams/guest-experience).

Para saber mais sobre a versão gratuita do Teams e como ela funciona com os recursos encontrados no acesso externo, confira [Diferenças entre o Microsoft Teams e o Microsoft Teams gratuito](https://support.office.com/article/differences-between-microsoft-teams-and-microsoft-teams-free-0b69cf39-eb52-49af-b255-60d46fdf8a9c?ui=en-US&rs=en-US&ad=US).

## <a name="quick-steps-for-scenarios"></a>Etapas rápidas para cenários

|**Você deseja...**  |**Etapas rápidas**  |
|---------|-----------------------|
|Você deseja permitir que **usuários do Teams** da sua organização se comuniquem com **usuários do Teams** de outra organização (externa).|No Acesso externo, adicione o domínio externo à lista permitida ou use a federação aberta. <p>Depois, o administrador da outra organização do Teams deve fazer o mesmo.      |
|Você deseja permitir que **usuários do Teams** da sua organização se comuniquem com **usuários do Skype for Business Online** da mesma organização.  |Habilite o modo de Coexistência ou escolha o modo de Atualização das ilhas para oferecer suporte aos usuários do Skype for Business em sua organização.   |
|Você deseja permitir que **usuários do Teams** da sua organização se comuniquem com **usuários do Skype for Business Online** de outra organização (externa).      |No Acesso externo, adicione o domínio externo à lista permitida ou use a federação aberta.  <p>Ative a configuração **Os usuários podem se comunicar com usuários do Skype for Business e do Teams** no Acesso externo. <p>Depois, o administrador da outra organização do Teams deve fazer o mesmo. <p>**OBSERVAÇÃO**: o domínio externo com usuários do Skype for Business deve habilitar o modo de Coexistência ou escolher o modo de Atualização das ilhas para oferecer suporte aos usuários do Skype for Business na organização.|
|Você deseja permitir que **usuários do Teams** da sua organização se comuniquem com usuários do **Skype** de dentro ou fora da organização.   | Não há suporte para esse cenário atualmente. <p>**IMPORTANTE**: os usuários do Teams não serão capazes de se comunicar com os usuários do Skype, mas os usuários do Skype for Business em sua organização poderão se comunicar com usuários do Skype de dentro ou fora da sua organização se estes dois requisitos forem atendidos: <p>1)  Ative as configurações **Os usuários podem se comunicar com usuários do Skype for Business e do Teams** e **Os usuários do Skype for Business podem se comunicar com usuários do Skype** no Acesso externo. <p> 2) Sua organização está sendo executada no modo de Coexistência.  |
|Você deseja permitir que seus **usuários do Teams** se comuniquem com os **usuários do Skype for Business Online** de uma organização local e com **usuários do Skype**.   |No Acesso externo, adicione o domínio externo à lista permitida ou use a federação aberta. . <p>Ative a configuração **Os usuários podem se comunicar com usuários do Skype for Business e do Teams** no Acesso externo. <p>Ative a configuração **Os usuários do Skype for Business podem se comunicar com usuários do Skype** no Acesso externo. <p> Depois, o administrador da organização local deve fazer o mesmo.<p>**IMPORTANTE**: nesse cenário, os usuários do Teams não conseguirão se comunicar com usuários do Skype, mas os usuários do Skype for Business em sua organização poderão se comunicar com os usuários do Skype de dentro ou de fora da sua organização se você ativar as configurações **Os usuários podem se comunicar com usuários do Skype for Business e do Teams** e **Os usuários do Skype for Business podem se comunicar com usuários do Skype** no Acesso externo.|
|Você deseja permitir que **usuários do Skype for Business Online** se comuniquem com **usuários do Teams** em outra organização com o Office 365.|Habilite o modo de Coexistência ou escolha o modo de Atualização das ilhas para oferecer suporte aos usuários do Skype for Business em sua organização. <p>No Acesso externo, adicione o domínio externo à lista permitida ou use a federação aberta.  <p> Ative a configuração **Os usuários podem se comunicar com usuários do Skype for Business e do Teams** no Acesso externo. <p>Depois, o administrador da outra organização do Teams deve fazer o mesmo. |
|Você deseja permitir que **usuários do Skype for Business Online** se comuniquem com **usuários do Skype for Business Online** em outra organização com o Office 365.    | Habilite o modo de Coexistência ou escolha o modo de Atualização das ilhas para oferecer suporte aos usuários do Skype for Business em sua organização. <p>No Acesso externo, adicione o domínio externo à lista permitida ou use a federação aberta. <p> Ative a configuração **Os usuários podem se comunicar com usuários do Skype for Business e do Teams** no Acesso externo.<p>Depois, o administrador da outra organização do Teams deve fazer o mesmo. |
|Você deseja permitir que **usuários do Skype for Business Online** se comuniquem com **usuários do Skype for Business Online** em outra organização local.     |Habilite o modo de Coexistência ou escolha o modo de Atualização das ilhas para oferecer suporte aos usuários do Skype for Business em sua organização. <p>No Acesso externo, adicione o domínio externo à lista permitida ou use a federação aberta.  <p>Ative a configuração **Os usuários podem se comunicar com usuários do Skype for Business e do Teams** no Acesso externo.  <p> Depois, o administrador da organização local deve fazer o mesmo. |
|Você deseja permitir que **usuários do Skype for Business Online** se comuniquem com **usuários do Skype** (de dentro ou de fora da sua organização).   |Habilite o modo de Coexistência ou escolha o modo de Atualização das ilhas para oferecer suporte aos usuários do Skype for Business em sua organização. <p>Ative a configuração **Os usuários do Skype for Business podem se comunicar com usuários do Skype** no Acesso externo.         |
|Você deseja permitir que **usuários do Skype for Business Online** se comuniquem com **usuários do Skype for Business Online** de outra organização e com **usuários do Skype** de dentro ou de fora da sua organização.    |Habilite o modo de Coexistência ou escolha o modo de Atualização das ilhas para oferecer suporte aos usuários do Skype for Business em sua organização. <p>No Acesso externo, adicione o domínio externo à lista permitida ou use a federação aberta.  <p> Ative as configurações **Os usuários podem se comunicar com usuários do Skype for Business e do Teams** e **Os usuários do Skype for Business podem se comunicar com usuários do Skype** no Acesso externo. <p>Depois, o administrador da outra organização do Teams deve fazer o mesmo.       <p> **OBSERVAÇÃO**: o administrador do outro domínio externo não precisa ativar a configuração **Os usuários do Skype for Business podem se comunicar com usuários do Skype** no Acesso externo.|

> [!IMPORTANT]
> Você não precisa adicionar nenhum **“domínio do Skype”** como domínio permitido para permitir que os usuários do Teams ou do Skype for Business Online se comuniquem com usuários do Skype de dentro ou de fora da sua organização. Todos os **domínios Skype** estão na lista de permissões, o que significa que todos esses domínios são considerados PERMITIDOS.

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-organization"></a>Permitir que os usuários do Teams conversem e se comuniquem com usuários em outra organização

O Acesso externo permite que os usuários do Teams e do Skype for Business se comuniquem com usuários de fora da organização. Por padrão, sua organização pode se comunicar com todos os domínios externos. Se você adicionar domínios bloqueados, todos os outros domínios serão permitidos; mas se você adicionar domínios permitidos, todos os outros domínios serão bloqueados. Você pode configurar facilmente o acesso externo à sua organização. Há três cenários para fazer essa configuração:

- **Cenário 1**: você pode usar a **FEDERAÇÃO ABERTA**. Essa é a configuração padrão, a qual permite que as pessoas em sua organização localizem, façam chamadas e enviem mensagens instantâneas/façam chats, além de configurar reuniões com pessoas de fora da sua organização.

    Quando você usa essa configuração, os usuários podem se comunicar com TODOS os domínios externos que estejam executando o Teams ou o Skype for Business E estejam usando a Federação Aberta ou tenham adicionado seu domínio à lista de permissões.

- **Cenário 2**: você pode adicionar um ou mais domínios à lista de **PERMISSÕES**. Para isso, clique em **Adicionar um domínio**, adicione o nome do domínio, clique em **Ação a ser executada neste domínio** e depois selecione **Permitido**. É importante saber que, se você fizer isso, todos os outros domínios serão **BLOQUEADOS**.

- **Cenário 3**: você pode adicionar um ou mais domínios à lista de **BLOQUEIOS**. Para isso, clique em **Adicionar um domínio**, adicione o nome do domínio, clique em **Ação a ser executada neste domínio** e depois selecione **Bloqueado**. É importante saber que, se você fizer isso, todos os outros domínios serão **PERMITIDOS**.

Siga estas etapas para permitir ou bloquear domínios.

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

4. Outra maneira de testar se o problema está no seu firewall é acessando um local com WiFi não protegido pelo seu firewall, como uma cafeteria, e usar o Teams para enviar uma solicitação de chat ao seu contato. Se você conseguir enviar a mensagem usando o WiFi do local e não conseguir fazer o mesmo no seu trabalho, isso quer dizer que o problema está no seu firewall.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Comunicar-se com usuários em uma organização do Skype for Business Online

Se você estiver configurando o acesso externo para permitir que os usuários do Teams localizem e entrem em contato com os usuários que estão em uma organização do Skype for Business que limitam quem pode entrar em contato com seus usuários, siga as etapas para configurar o acesso externo do seu domínio para o domínio da outra organização. Depois, peça ao administrador da outra organização para seguir as etapas abaixo para configurar o acesso externo ao Skype for Business Online.

![Um ícone mostrando o logotipo do Skype for Business](media/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

Solicite que o administrador da organização siga estas etapas:

1. No centro de administração Microsoft 365, acesse **Centros de administração** > **Teams e Skype** > **Portal herdado**.
  
2. No **Centro de administração Skype for Business**, escolha **Organização** > **Comunicações externas**.

3. Para configurar a comunicação com uma empresa específica ou com usuários em outro domínio, na caixa suspensa, escolha **Ativado somente para os domínios permitidos**.

    OU, se o administrador desejar habilitar a comunicação com todos que tiverem as políticas do Skype for Business, escolha **Ativado exceto para domínios bloqueados**. Esta é a configuração padrão.

4. Em **Domínios bloqueados ou permitidos**, escolha **+** e adicione o nome do domínio que você deseja permitir.

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre o acesso de convidados no Microsoft Teams, confira [Gerenciar o acesso de convidado no Microsoft Teams](manage-guests.md).
