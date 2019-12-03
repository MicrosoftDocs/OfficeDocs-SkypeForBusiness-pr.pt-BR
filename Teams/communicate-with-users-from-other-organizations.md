---
title: Comunique-se com usuários de outras organizações no Microsoft Teams
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
description: Aprenda a se comunicar com usuários de outras organizações no Microsoft Teams usando o acesso externo (federação) e o acesso de convidado.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 39fa50868b60ce78da360d97a2fad5dff9fee09b
ms.sourcegitcommit: 486eaa85042670edec2231efaf7dae8fa329e852
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2019
ms.locfileid: "39665444"
---
<a name="communicate-with-users-from-other-organizations-in-microsoft-teams"></a>Comunique-se com usuários de outras organizações no Microsoft Teams
======================================================

Quando você precisa se comunicar e colaborar com pessoas de fora da sua organização, o Microsoft Teams oferece duas maneiras diferentes de fazer isso acontecer. O primeiro - **acesso externo** (federação) - permite que você encontre, ligue e converse com usuários em outros domínios (por exemplo, contoso.com). O segundo - **acesso de convidados** - permite que você adicione indivíduos às suas equipes, como convidados, usando o endereço de email deles. Você pode colaborar com os convidados como faria com outros usuários da sua organização.

Você pode usar o acesso externo e o acesso para convidados, se desejar - isso não impede a outra pessoa.

Em um nível alto, veja aqui como escolher (para uma comparação detalhada, vá para [Comparar acesso externo e de convidados](#compare-external-and-guest-access)):

## <a name="external-access"></a>Acesso externo

Use o **acesso externo** (federação) quando você precisar de uma solução que permita que os usuários externos em outros domínios localizem, liguem, conversem e agendem reuniões com você. Os usuários externos não têm acesso às equipes ou aos recursos da equipe da sua organização. Escolha o acesso externo quando quiser se comunicar com usuários externos que ainda estão no Skype for Business (online ou local) ou no Skype (que chega no início de 2020). 

O acesso externo é ativado por padrão no Teams, o que significa que sua organização pode se comunicar com todos os domínios externos. O administrador do Teams pode desativá-lo ou especificar quais domínios devem ser incluídos (ou excluídos). Para saber mais, leia [Gerenciar acesso externo](manage-external-access.md). 

Se você desejar que usuários externos tenham acesso a equipes e canais, o [acesso de convidados](#guest-access) poderá ser a melhor opção. 


## <a name="guest-access"></a>Acesso de convidados

Use o **acesso de convidados** para adicionar um usuário individual (independentemente do domínio) a uma equipe, onde eles podem conversar, ligar, reunir e colaborar em arquivos da organização (armazenados no SharePoint ou no OneDrive for Business), usando os aplicativos do Office 365, como Word, Excel ou PowerPoint. Um usuário convidado pode ter quase todos os mesmos recursos de equipes que um membro nativo da equipe. Para saber mais, leia [Acesso de convidados no Teams](guest-access.md).

- Os convidados são adicionados ao Active Directory da sua organização.
- Para se comunicar com um convidado, ele deve estar conectado ao Teams usando sua conta de convidado. Isso significa que um convidado pode ter que sair de sua própria conta do Teams para entrar em sua conta do Teams.
- Os usuários convidados têm acesso a mais recursos no Teams - como arquivos, equipes e canais - do que os usuários de acesso externo (federado).
- O administrador do Teams controla tudo o que um convidado pode (ou não) fazer no centro de administração do Teams. Para saber mais, leia [Gerenciar acesso de convidados](manage-guests.md).

Se você estiver pronto para ativar o acesso de convidados em sua organização, comece com a [Lista de verificação de acesso de convidados](guest-access-checklist.md).


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
<sup>4</sup> Com suporte para chat individual de usuários do Apenas Teams para Apenas Teams de duas organizações diferentes. *Este é um recurso de versão prévia ou lançamento antecipado*

## <a name="related-topics"></a>Tópicos relacionados

[Acesso externo ao Teams](manage-external-access.md)

[Acesso de convidados ao Teams](guest-access.md)

