---
title: Ligar e conversar com usuários de outras organizações
author: serdars
ms.author: serdars
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
- NOCSH
description: Aprenda a ligar, usar o chat, encontrar e adicionar usuários de fora da organização no Microsoft Teams usando acesso externo (federação) e acesso de convidado.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 401b63aad667d355516486deb6f056e0995dbe26
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031807"
---
<a name="call-and-chat-with-users-from-other-organizations-in-microsoft-teams"></a>Ligar e conversar com os usuários de outras organizações no Microsoft Teams
======================================================

Quando você precisa se comunicar e colaborar com pessoas fora do sua organização, o Microsoft Teams lhe oferece duas formas diferentes de fazer isso acontecer. A primeira – **acesso externo** (federação) – permite encontrar, ligar e conversar com usuários em outros domínios (por exemplo, contoso.com). A segunda – **acesso de convidados** – permite adicionar indivíduos às suas equipes, como convidados, usando seu endereço de e-mail. Você pode colaborar com os convidados como colaboraria com qualquer outro usuário da sua organização.

Você pode usar o acesso externo e o acesso para convidados, se desejar - isso não impede a outra pessoa.

Em um nível alto, veja aqui como escolher (para uma comparação detalhada, vá para [Comparar acesso externo e de convidados](#compare-external-and-guest-access)):

## <a name="external-access"></a>Acesso externo

Use **acesso externo** (federação) quando você precisa de uma solução que permita que usuários externos em outros domínios encontrem, liguem, conversem e marquem reuniões com você. Os usuários externos não possuem acesso às equipes da sua organização ou aos recursos de equipe. Escolha o acesso externo quando quiser se comunicar com usuários de fora da sua organização que ainda estejam no Skype for Business ( on-line ou nas instalações) ou no Skype (a partir do início de 2020). 

O acesso externo é ativado por padrão no Teams, significando que sua organização pode se comunicar com todos os domínios externos. O administrador do Teams pode desativá-lo ou especificar quais domínios devem ser incluídos (ou excluídos). Para obter mais informações, leia [Gerencie o acesso externo](manage-external-access.md). 

Se você desejar que usuários externos tenham acesso a equipes e canais, o [acesso de convidados](#guest-access) poderá ser a melhor opção. 


## <a name="guest-access"></a>Acesso de convidados

Use **acesso de convidados** para adicionar um usuário individual (independentemente do domínio) a uma equipe, onde ele pode conversar, ligar, reunir e colaborar em arquivos da organização (armazenados no SharePoint ou OneDrive for Business), usando aplicativos Microsoft 365 ou Office 365, como Word, Excel ou PowerPoint. Um usuário convidado pode receber quase todos os mesmos recursos do Teams que um membro nativo da equipe. Para obter mais informações, leia [Acesso de convidados no Teams](guest-access.md).

- Os convidados são adicionados ao Active Directory da sua organização.
- Para se comunicar com um convidado, o convidado tem que estar conectado ao Teams usando sua conta de convidado. Isso significa que um convidado pode ter que sair da sua própria conta do Teams para entrar na sua conta do Teams, ou mudar de organização se for a mesma conta.
- Os usuários convidados têm acesso a mais recursos no Teams - como arquivos, equipes e canais - do que os usuários de acesso externo (federado).
- A administração do Teams controla tudo o que um convidado pode (ou não) fazer no Centro de administração do Teams. Para obter mais informações, leia [Gerenciar o acesso de convidados](manage-guests.md).

Se estiver pronto para ativar o acesso de convidados em sua organização, comece com o [Colaborar com convidados em uma equipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).


## <a name="compare-external-and-guest-access"></a>Comparar o acesso externo e de convidados

| Recurso | Usuários de acesso externo | Usuários de acesso de convidado |
|---------|-----------------------|--------------------|
| O usuário pode conversar com alguém de outra empresa | Sim |Sim |
| O usuário pode fazer chamadas para alguém de outra empresa | Sim | Sim |
| Os usuários podem ver se alguém de outra empresa está disponível para uma chamada ou um chat | Sim | Sim<sup>1</sup> |
| O usuário pode pesquisar usuários em locatários externos | Sim<sup>2</sup> | Não |
| O usuário pode compartilhar arquivos | Não | Sim |
| O usuário pode acessar os recursos do Teams | Não | Sim |
| O usuário pode ser adicionado a um chat de grupo | Não | Sim |
| O usuário pode ser adicionado para uma reunião | Sim | Sim |
| É possível adicionar outros usuários a um chat com um usuário externo | Não<sup>3</sup> | N/D |
| O usuário é identificado como um participante externo | Sim | Sim |
| A presença é exibida | Sim | Sim |
| A mensagem de ausência temporária é exibida | Não | Sim |
| É possível bloquear um usuário individual | Não | Sim |
| Há suporte para @menções | Sim<sup>4</sup> | Sim |
| Fazer chamadas privadas | Sim | Sim |
| Exibir o número de telefone dos participantes da reunião discada | Não<sup>5</sup> | Sim |
| Permitir vídeo IP | Sim | Sim |
| Modo de compartilhamento de tela | Sim<sup>4</sup> | Sim |
| Permitir Reunir Agora
 | Não | Sim |
| Editar mensagens enviadas | Sim<sup>4</sup> | Sim |
| É possível excluir mensagens enviadas | Sim<sup>4</sup> | Sim |
| Usar Giphy em conversas | Sim<sup>4</sup> | Sim |
| Usar memes em conversas | Sim<sup>4</sup> | Sim |
| Usar figurinhas em conversas | Sim<sup>4</sup> | Sim |
||||

<sup>1</sup> Desde que o usuário tenha sido adicionado como um convidado e esteja conectado também como convidado ao locatário de convidado.<br>
<sup>2</sup> Apenas por endereço de email ou de protocolo SIP.<br>
<sup>3</sup> O chat externo (federado) funciona apenas no modo 1:1.<br>
<sup>4</sup> Com suporte para chat individual de usuários do Apenas Teams para Apenas Teams de duas organizações diferentes. <br>
<sup>5</sup> Por padrão, os participantes externos não podem visualizar os números de telefone dos participantes discados. Se você quiser manter a privacidade desses números de telefone, selecione **Tons** para **Tipo de anúncio de entrada/saída** (isso impede que os números sejam lidos pelo Teams). Para obter mais informações, leia [Ativar ou desativar anúncios de entrada e saída de reuniões no Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).

## <a name="related-topics"></a>Tópicos relacionados

[Acesso externo ao Teams](manage-external-access.md)

[Acesso de convidados ao Teams](guest-access.md)

