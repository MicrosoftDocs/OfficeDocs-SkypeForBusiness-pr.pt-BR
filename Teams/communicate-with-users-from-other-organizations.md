---
title: Use o acesso para convidado e o acesso externo para colaborar com pessoas de fora da sua organização
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
description: Aprenda como fazer uma chamada, bater papo, encontrar e adicionar usuários de fora da organização no Microsoft Teams usando o acesso externo e o acesso para convidado.
ms.openlocfilehash: 829f763c77578fdc9e17a29386ebad30e52f4986
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023984"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a>Use o acesso para convidado e o acesso externo para colaborar com pessoas de fora da sua organização

Este artigo descreve duas das opções para colaborar com pessoas de fora da sua organização:

- **Acesso externo** - Um tipo de federação que permite aos usuários encontrar, fazer chamadas e conversar com pessoas de outras organizações. Estas pessoas não podem ser adicionadas a uma equipe a menos que sejam chamadas como convidadas.
- **Acesso de convidado** - O acesso ao convidado permite que você convide pessoas de fora da sua organização para se juntar a uma equipe. Pessoas convidadas recebem uma conta de convidado no Azure Active Directory.

Para obter uma visão geral completa da colaboração externa no Microsoft 365, consulte [Visão geral das opções de colaboração externa no Microsoft 365](/microsoft-365/enterprise/external-guest-access).

## <a name="external-access-external-chat-and-meetings"></a>Acesso externo (chat externo e reuniões)

Configure o acesso externo se precisar localizar, fazer uma chamada, bater um papo e marcar reuniões com pessoas de fora da sua organização que usam o Teams, Skype for Business (online ou local) ou o Skype. 

Por padrão, o acesso externo é habilitado para todos os domínios. Você pode restringir o acesso externo permitindo ou bloqueando domínios específicos, ou desligando-o.

![Captura de tela das configurações de acesso externo.](media/external-access-federation-settings.png)

O acesso externo está disponível para os seguintes locatários:

- No e entre Comercial, GCC e GCC High
- Somente entre DOD

Para configurar o acesso externo, consulte [Gerenciar acesso externo](manage-external-access.md). 

>[!NOTE]
> As licenças gratuitas do [Microsoft Teams Gratuito (clássico)](https://support.microsoft.com/office/welcome-to-microsoft-teams-free-classic-6d79a648-6913-4696-9237-ed13de64ae3c) não oferecem suporte a acesso externo.

## <a name="guest-access"></a>Acesso de convidados

Utilize o acesso de convidado para adicionar uma pessoa de fora da sua organização a uma equipe, onde ela pode bater papo, fazer uma chamada, se encontrar e colaborar em arquivos. Um convidado pode receber quase todos os mesmos recursos do Teams que um membro nativo da equipe. Para obter mais informações, consulte [Experiência de convidado no Teams](guest-experience.md).

Os convidados são adicionados ao Azure Active Directory da sua organização como usuários B2B e devem se conectar ao Teams usando sua conta de convidado. Isso significa que eles podem precisar sair da própria organização para entrar na sua.

O acesso de convidado está disponível para os seguintes locatários:

- No e entre Comercial e GCC
- Somente entre GCC High
- Somente entre DOD

Para configurar o acesso de convidado para o Teams, consulte [Colaborar com convidados em uma equipe ](/microsoft-365/solutions/collaborate-as-team).

## <a name="compare-external-and-guest-access"></a>Comparar o acesso externo e de convidados

As tabelas a seguir mostram as diferenças entre o uso de acesso externo (federação) e convidados. Em ambos os casos, pessoas de fora da sua organização são identificadas para os seus usuários como sendo externas.

### <a name="things-your-users-can-do"></a>Coisas que seus usuários podem fazer

| Os usuários podem | Usuários de acesso externo | Convidados |
|---------|-----------------------|--------------------|
| Converse com alguém em outra organização | Sim | Sim |
| Faça uma chamada para alguém em outra organização | Sim | Sim |
| Veja se alguém de outra organização está disponível para uma chamada ou bate-papo | Sim | Sim<sup>1</sup> |
| Procurar por pessoas em outras organizações | Sim<sup>2</sup> | Não |
| Compartilhe arquivos | Não | Sim |
| Veja a mensagem de ausência do escritório de alguém em outra organização | Não | Sim |
| Bloquear alguém em outra organização  | Não | Sim |
| Usar @menções | Sim<sup>3</sup> | Sim |

### <a name="things-people-outside-your-organization-can-do"></a>Coisas que podem ser feitas por pessoas de fora da sua organização

| Pessoas fora da sua organização podem | Usuários de acesso externo | Convidados |
|---------|-----------------------|--------------------|
| Recursos de acesso do Teams | Não | Sim |
| Seja adicionado a um bate-papo em grupo | Sim | Sim |
| Seja convidado para uma reunião | Sim | Sim |
| Fazer chamadas privadas | Sim | Sim<sup>5</sup> |
| Exibir o número de telefone dos participantes da reunião discada | Não<sup>4</sup> | Sim |
| Utilizar vídeo IP | Sim | Sim<sup>5</sup> |
| Utilizar o compartilhamento de tela | Sim<sup>3</sup> | Sim<sup>5</sup> |
| Utilize o reunir agora | Não | Sim<sup>5</sup> |
| Editar mensagens enviadas | Sim<sup>3</sup> | Sim<sup>5</sup> |
| Apagar mensagens enviadas | Sim<sup>3</sup> | Sim<sup>5</sup> |
| Usar Giphy em conversas | Sim<sup>3</sup> | Sim<sup>5</sup> |
| Usar memes em conversas | Sim<sup>3</sup> | Sim<sup>5</sup> |
| Usar figurinhas em conversas | Sim<sup>3</sup> | Sim<sup>5</sup> |
| A presença é exibida | Sim | Sim |
| Usar @menções | Sim<sup>3</sup> | Sim |

<br>

<sup>1</sup> Desde que o usuário tenha sido adicionado como convidado e esteja conectado com a conta de convidado.<br>
<sup>2</sup> Apenas por endereço de email ou de protocolo SIP.<br>
<sup>3</sup> Suporte para bate-papo 1:1 Somente usuários do Teams para o Teams a partir de duas organizações diferentes. <br>
<sup>4</sup> Por padrão, os participantes externos não podem visualizar os números de telefone dos participantes discados. Se você quiser manter a privacidade desses números de telefone, selecione **Tons** para **Tipo de anúncio de entrada/saída** (isso impede que os números sejam lidos pelo Microsoft Teams). Para saber mais, consulte [Ativar ou desativar anúncios de entrada e saída de reuniões no Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md). <br>
<sup>5</sup> Permitido por padrão, mas pode ser desativado pela administração do Teams

## <a name="related-topics"></a>Tópicos relacionados

[Acesso externo ao Teams](manage-external-access.md)

[Acesso de convidados ao Teams](guest-access.md)
