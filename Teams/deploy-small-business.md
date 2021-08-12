---
title: Configurar o Microsoft Teams em sua pequena empresa
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Configurar o Teams em sua pequena empresa para permitir que os usuários colaborem usando chat e compartilhamento de arquivos, configurar e participar de reuniões pequenas e grandes e conversar por meio de vídeo e voz.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 92bd4ef4d53cbae8902719da3ce55a5b88a270c4b18d43bfe75ab89578fe204a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322693"
---
# <a name="set-up-microsoft-teams-in-your-small-business"></a>Configurar o Microsoft Teams em sua pequena empresa

Há várias maneiras de personalizar o Teams. As seções a seguir mostram como configurar cada carga de trabalho do Teams: **chats, equipes e canais**; **reuniões e conferências**; e **voz na nuvem**. A ordem em que você configura cada carga de trabalho é com você. Embora seja recomendável configurar primeiro os chats, equipes e canais de carga de trabalho, você pode começar com reuniões, conferências ou até mesmo a voz na nuvem. A escolha é sua!

> [!NOTE]
> Se você ainda não fez isso, sugerimos que você inicie a implantação do Teams com um piloto. Um piloto permitirá que você e alguns dos primeiros adotantes se familiarizem com o Teams e suas características antes do seu planejamento e eventual lançamento. Para obter mais informações sobre como iniciar seu piloto, consulte [Começar a usar o Microsoft Teams](get-started-with-teams-quick-start.md).

Antes de lançar o Teams de forma abrangente, certifique-se de que sua organização está pronta, revendo os itens em [Certifique-se de que você está pronto](get-started-with-teams-quick-start.md#make-sure-youre-ready).

Pule para a seção em que você está interessado:

- [Cargas de trabalho](#workloads)
  - [Chat, equipes e canais](#chat-teams-and-channels)
  - [Reuniões e conferências](#meetings-and-conferencing)
  - [Business Voice](#business-voice)
- [Implantar clientes](#deploy-clients)
- [Treinamento](#training)

## <a name="workloads"></a>Cargas de trabalho
### <a name="chat-teams-and-channels"></a>Chat, equipes e canais

Chat, equipes e canais são a base do Teams. O **Chat** permite que um ou mais usuários conversem uns com os outros, compartilhem arquivos e se reúnam em privado. O **Teams**, que pode ser visível para todos na sua organização ou apenas para os membros da equipe, deixa as pessoas certas colaborarem em qualquer tarefa ou ocasião, seja um projeto a longo prazo ou planejar uma festa de aniversário. Os **Canais** dentro das equipes podem segmentar tópicos, projetos, departamentos ou qualquer outra coisa que faça sentido para a sua equipe. Para obter mais detalhes sobre chat, equipes e canais, consulte [Visão geral de equipes e canais](teams-channels-overview.md).

> [!TIP]
> Veja como você pode gerenciar as funções, acesso e políticas de mensagens da equipe completando o módulo [Gerenciar o Microsoft Teams](/learn/modules/m365-teams-collab-manage-teams/) no Microsoft Learn.

Ao pensar na distribuição de equipes e canais, você precisa decidir quem deve ser capaz de criá-los, se os convidados de fora da sua organização podem acessá-los e assim por diante. O artigo [Chat, equipes, canais e aplicativos no Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) tem muitas informações sobre como planejar chat, equipes e canais. No entanto, aqui estão algumas coisas importantes desse artigo que você deve pensar. Selecione uma decisão se quiser saber mais sobre ela.

| Decisão | Descrição |
|--|--|
| [Quem deveria ser os administradores do Teams?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-administrators) | As funções de administrador podem ser usadas para conceder permissões específicas às pessoas que você quer administrar no Teams. Talvez as pequenas empresas não precisem dessas funções extras porque a mesma pessoa pode ser responsável por todos os aspectos do Teams. Você poderá adicionar ou remover administradores posteriormente.<br><br>[Usar as funções de administrador do Microsoft Teams para gerenciar o Teams](using-admin-roles.md) |
| [Quem deveria ser os proprietários e membros do Teams?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-owners-and-members) | Os proprietários do Teams controlam quem pode acessar uma equipe e seus canais. Eles podem decidir se uma equipe ou canal é público (para a organização) ou privado e podem estabelecer políticas, por exemplo, se um canal deve ser moderado. Os membros podem acessar a equipe e seus canais (a menos que um canal seja privado e eles não sejam membros desse canal) e podem ser designados como moderadores.<br><br>[Atribuir proprietários de equipe e membros no Microsoft Teams](assign-roles-permissions.md) |
| [O acesso de convidados deve estar habilitado?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#guest-access) |O acesso de convidado permite que as pessoas da sua organização convidem pessoas de fora da sua organização para acessarem suas equipes e canais. O acesso de convidado é usado com frequência para colaborar com pessoas de fora da sua organização que não têm uma relação formal com a sua empresa. Por exemplo, você pode convidar um planejador de projeto para trabalhar temporariamente em um projeto.<br>O acesso de convidado é diferente do acesso externo. O acesso de convidado convida indivíduos específicos para interagir com pessoas em sua organização.  <br>O acesso de convidado está **Desativado** por padrão. <br><br>[Ativar ou desativar o acesso de convidado ao Microsoft Teams](set-up-guests.md)  |

Não é necessário fazer mais nada para que os usuários comecem a usar chat, equipes e canais. No entanto, há muitas opções para controlar como o Teams é usado. Você pode mudar agora ou esperar para ver como as pessoas estão usando o Teams. Para saber mais, confira os seguintes artigos:

- [Gerenciar políticas de mensagens no Teams](messaging-policies-in-teams.md)
- [Configurações do Teams](enable-features-office-365.md#teams-settings)

### <a name="meetings-and-conferencing"></a>Reuniões e conferências

Reuniões e conferências permitem que as pessoas em sua organização se encontrem entre si e com as pessoas de fora da sua organização. Qualquer pessoa com um cliente do Teams ou do Skype for Business pode participar de **reuniões** para as quais tenha sido convidada. Usar o microfone, a câmera e a tela de seu dispositivo permite que os participantes ingressem na conversa, sem a necessidade de um telefone. Os participantes podem conversar, fazer chamadas de voz e compartilhar vídeos e aplicativos com outros participantes usando um computador ou dispositivo móvel.

A **Audioconferência** permite que os participantes ingressem em reuniões por meio de um telefone comum ligando para um número de telefone em conferência e inserindo uma ID de reunião. A audioconferência é útil quando um participante não tem uma boa conexão à Internet, a reunião for apenas de voz, ou alguma outra circunstância não permitir que ele participe através do cliente do Teams.

> [!TIP]
> Familiarize-se mais com reuniões e eventos ao completar o módulo [Gerenciar reuniões, conferências e eventos com o Microsoft Teams](/learn/modules/m365-teams-collab-manage-meetings) no Microsoft Learn.

As reuniões são habilitadas por padrão no Teams. No entanto, você pode controlar a experiência da reunião para organizadores e participantes. Você também pode definir políticas para o que as pessoas têm ou não permissão de fazer antes e durante as reuniões. Para saber mais, confira os seguintes artigos:

- [Início rápido do administrador – Reuniões e eventos ao vivo no Microsoft Teams](quick-start-meetings-live-events.md)
- [Configurar Audioconferência para pequenas e médias empresas](audio-conferencing-smb.md)

### <a name="business-voice"></a>Business Voice

[O Microsoft 365 Business Voice](business-voice/whats-business-voice.md) é uma ótima solução para empresas com menos de 300 usuários que oferece todos os recursos de um sistema de telefone comercial. O Business Voice inclui caixa postal, ID do chamador, menus do sistema de telefone, números de chamada gratuita e muito mais, sem a necessidade de gerenciar um sistema telefônico complexo e de alto custo no local.

Com base no Sistema de Telefonia do Microsoft 365, o Business Voice simplifica a adição de voz à sua organização, agregando complementos e recursos do Sistema Telefônico e fornecendo um assistente fácil de acompanhar para ajudá-lo a configurar seu sistema telefônico. Se sua organização estiver localizada em um [país ou região com suporte para Business Voice](business-voice/country-region-availability.md), você poderá transferir seus números de telefone para o Microsoft 365 e nos permitir gerenciar seu sistema telefônico para você.

Com o Microsoft 365 como seu sistema telefônico, você pode transformar qualquer dispositivo em um telefone instalando o cliente do Teams nele. Ou, se você preferir ter um telefone de mesa tradicional ou um telefone de conferência, há muitos dispositivos certificados do Teams para escolher. De qualquer forma, as chamadas são sempre roteada para onde você está e as chamadas que você faz sempre têm seu número de telefone do escritório.

Se você tiver interesse em usar o Business Voice, confira [O que preciso comprar para usar o Microsoft 365 Business Voice?](business-voice/what-to-buy.md).

## <a name="deploy-clients"></a>Implantar clientes

Quando você estiver pronto para que seus usuários comecem a usar o Teams, eles podem instalar o cliente do Teams nos computadores Windows, Mac ou Linux, ou no seu dispositivo Android ou iOS. Os usuários podem baixar o cliente do Teams diretamente do <https://teams.microsoft.com/downloads>.

Certifique-se de que todos que usarão o Teams tenham uma licença do Teams. Para obter mais informações de como atribuir uma licença do Teams, consulte [Gerenciar o acesso do usuário ao Teams](user-access.md#using-the-microsoft-365-admin-center).

> [!TIP]
> Obtenha recomendações de como planejar a implantação do cliente do Teams preenchendo o módulo [Implantar clientes do Microsoft Teams](/learn/modules/m365-teams-collab-deploy-clients/) no Microsoft Learn.

Se sua organização usa o Microsoft Endpoint Configuration Manager, Política de Grupo ou um mecanismo de distribuição de terceiros para implantar um software nos computadores dos seus usuários, consulte [Instalar o Microsoft Teams usando o Microsoft Endpoint Configuration Manager](msi-deployment.md).

Se você quiser informações detalhadas sobre como implantar os clientes do Teams, consulte [Obter clientes para o Microsoft Teams](get-clients.md).

## <a name="training"></a>Treinamento

Para obter mais informações de como treinar seus usuários para usarem o Teams, consulte [Treinamento do Microsoft Teams](training-microsoft-teams-landing-page.md).