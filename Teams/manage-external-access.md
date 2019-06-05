---
title: Gerenciar o acesso externo (federação) no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: Seu administrador de ti pode configurar o acesso externo para outros domínios (Federação) para permitir que os usuários desses domínios participem da equipe.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6a3dc6016eb52d58e82e9e9022d1bb8575404b
ms.sourcegitcommit: b9e7a11d8332a029a4f1cd4e396787f5a74f0a44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2019
ms.locfileid: "34702716"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a>Gerenciar o acesso externo (federação) no Microsoft Teams
======================================================

Com o acesso externo ao Microsoft Teams, os usuários de outros domínios podem participar de chats e chamadas. Você também pode permitir que usuários externos que ainda estejam usando o Skype for Business online ou o Skype for Business no local para participar. 

O acesso externo (Federação) e o acesso de convidado são diferentes:

- O acesso de convidado concede permissão de acesso a um indivíduo. O acesso externo oferece permissão de acesso a um domínio inteiro.

- O acesso de convidado, uma vez concedido por um proprietário de equipe, permite que um convidado [acesse recursos](guest-experience.md), como discussões e arquivos de canal, para uma equipe específica e converse com outros usuários na equipe em que foram convidados. Com o acesso externo (chat federado), os participantes do chat externo não têm acesso às equipes ou aos recursos da equipe que convida a organização. Eles podem participar apenas de um chat federado único. Os administradores de locatários podem escolher entre as duas opções de comunicação, dependendo do nível de colaboração que é desejável na parte externa. Os administradores podem escolher abordagens ou ambos, dependendo de suas necessidades organizacionais, mas recomendamos habilitar o acesso de convidado para obter uma experiência de equipes mais abrangente e colaborativa. 

Consulte a tabela a seguir para obter uma comparação de recursos de acesso externo e de convidado.

| Recurso | Usuários de acesso externo | Usuários de acesso de convidado |
|---------|-----------------------|--------------------|
| O usuário pode conversar com alguém em outra empresa | Sim |Sim |
| O usuário pode fazer uma chamada para alguém em outra empresa | Sim | Sim |
| O usuário pode ver se alguém de outra empresa está disponível para chamada ou chat | Sim | Sim<sup>1</sup> |
| O usuário pode pesquisar usuários em locatários externos | Sim<sup>2</sup> | Não |
| O usuário pode compartilhar arquivos | Não | Sim |
| O usuário pode acessar os recursos da equipe | Não | Sim |
| O usuário pode ser adicionado a um chat em grupo | Não | Sim |
| O usuário pode ser adicionado a uma reunião | Sim | Sim |
| Outros usuários podem ser adicionados a um chat com um usuário externo | Não<sup>3</sup> | N/D |
| O usuário é identificado como uma festa externa | Sim | Sim |
| A presença será exibida | Sim | Sim |
| Mensagem de ausência temporária é mostrada | Não | Sim |
| O usuário individual pode ser bloqueado | Não | Sim |
| @mentions têm suporte | Não | Sim |
| Fazer chamadas privadas | Sim | Sim |
| Permitir vídeo IP | Sim | Sim |
| Modo de compartilhamento de tela | Sim | Sim |
| Permitir reunião agora | Não | Sim |
| Editar mensagens enviadas | Sim | Sim |
| Pode excluir mensagens enviadas | Sim | Sim |
| Usar o Giphy em conversa | Sim | Sim |
| Usar o memes em conversa | Sim | Sim |
| Usar adesivos em conversa | Sim | Sim |
||||

<sup>1</sup> desde que o usuário tenha sido adicionado como um convidado e esteja conectado como convidado ao locatário de convidado.<br>
<sup>2</sup> somente por endereço de email ou protocolo de iniciação de sessão (SIP).<br>
<sup>3</sup> o chat externo (federado) só é o 1:1.

> [!NOTE]
> Para obter mais informações sobre os recursos convidados e sobre a experiência de convidado, consulte [Ativar ou desativar o acesso de convidado ao Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) e o [que a experiência de convidado é curtir](https://docs.microsoft.com/microsoftteams/guest-experience).

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a>Ativar ou desativar o acesso externo (os usuários podem se comunicar com os usuários do Skype for Business e do Teams)

Você pode usar o centro de administração do Microsoft Teams & o Skype for Business para gerenciar o acesso externo.

1. No centro de administração do Microsoft Teams & o centro de administração do Skype for Business, selecione >  **configurações de toda a organização****acesso externo**.

     ![Captura de tela de acesso externo às configurações de toda a organização](media/manage-external-access-1.png).

2. Alternar os **usuários podem se comunicar com o Skype for Business e os usuários** do teams alternar para **ativado** ou **desativado**.

     ![Captura de tela da opção de acesso externo ativada](media/manage-external-access-2.png).

3. Clique em **Salvar**. 

## <a name="add-or-block-a-domain"></a>Adicionar ou bloquear um domínio

Siga estas etapas para adicionar um domínio ou desativar o acesso externo para um domínio.

1. No centro de administração do Microsoft Teams & o centro de administração do Skype for Business, selecione >  **configurações de toda a organização****acesso externo**.

2. Selecione **Adicionar um domínio**. 
 
    ![Captura de tela da página de acesso externo com o link adicionar um domínio](media/manage-external-access-3.png).

   O painel **Adicionar um domínio** é exibido.

    ![Captura de tela do painel Adicionar um domínio](media/manage-external-access-4.png).


3. Em **Adicionar um domínio**, digite o nome do domínio; por exemplo, digite Contoso.com.

4. Selecione **Permitido** ou **Bloqueado**. Você pode alterar essa configuração a qualquer momento.

2. Selecione **concluído**.

Depois de adicionar um domínio, você verá o nome de domínio e o status adicionados à lista de domínios na página de acesso externo.

## <a name="more-information"></a>Mais informações

Para obter informações sobre o acesso de convidado no Microsoft Teams, consulte [gerenciar o acesso de convidados no Microsoft Teams](manage-guests.md).
