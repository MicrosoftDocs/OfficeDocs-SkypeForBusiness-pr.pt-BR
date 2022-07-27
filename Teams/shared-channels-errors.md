---
title: Erros de canais compartilhados no Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jasonlewis
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: normal
search.appverid: MET150
description: Saiba como usar corrigir erros em canais compartilhados no Microsoft Teams.
ms.openlocfilehash: ecd05f1593817ed03d6e516e8915cd15694b6315
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024126"
---
# <a name="shared-channels-errors-in-microsoft-teams"></a>Erros de canais compartilhados no Microsoft Teams

Se os usuários veem mensagens de erro ao tentar adicionar pessoas de fora da sua organização a canais compartilhados, verifique as configurações neste artigo. 

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel-for-more-info-talk-to-your-admin"></a>Devido à política de administrador, você não pode adicionar pessoas externas ao canal. Para obter mais informações, fale com seu administrador.

O Teams usa Grupos do Microsoft 365 para associação à equipe. As Grupos do Microsoft 365 de convidado devem ser ativadas para que pessoas fora da organização sejam adicionadas a um canal compartilhado. Se os usuários visualizarem esse erro, verifique as Grupos do Microsoft 365 configurações para pessoas de fora da organização.

Para definir Grupos do Microsoft 365 configurações para pessoas fora da organização
1. No painel Centro de administração do Microsoft 365, no painel de navegação esquerdo, expanda **Configurações**.
1. Clique **em Configurações da Organização**.
1. Na lista, clique em **Grupos do Microsoft 365**.
1. Verifique se os proprietários **do** grupo Permitir que os proprietários adicionem pessoas de fora da  sua organização Grupos do Microsoft 365 como convidados e deixe que os membros do grupo de convidados acessem as caixas de seleção de conteúdo do grupo.
1. Se você tiver feito alterações, clique **em Salvar alterações**.

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel"></a>Devido à política de administrador, você não pode adicionar pessoas externas ao canal

As políticas de canal do Teams determinam como os usuários podem interagir com canais compartilhados. Se os usuários visualizarem essa mensagem de erro, verifique a política de canal desse usuário.

Para definir a política para convidar pessoas de fora da organização para canais compartilhados
1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, acesse Teams > Teams.
1. Selecione a política à qual o usuário está atribuído.
1. Certifique-se **de que Convidar usuários externos para canais compartilhados** esteja **Ativado**.
1. Se você tiver feito alterações, selecione **Aplicar**.

Para obter mais informações sobre políticas de canal do Teams, consulte [Gerenciar políticas de canal no Microsoft Teams](teams-policies.md).

## <a name="you-cant-share-this-channel-with-people-from-this-org"></a>Você não pode compartilhar este canal com pessoas desta organização

Se os usuários visualizarem esse erro, eles serão impedidos de compartilhar o canal com pessoas em outra organização pelas configurações de acesso entre locatários do Azure Active Directory. Isso pode ocorrer devido às configurações de entrada em sua organização ou às configurações de saída na outra organização.

Para verificar as configurações de entrada para sua organização
1. No [Azure Active Directory](https://aad.portal.azure.com), selecione Identidades **Externas** e, em seguida, selecione **configurações de acesso entre locatários**.
1. Selecione o link de acesso de entrada para a organização que você deseja verificar.
1. Na guia **conexão direta B2B** , escolha **Personalizar configurações**.
1. Na guia Usuários e grupos externos, verifique se  Permitir acesso e  Todos os usuários e grupos externos estão selecionados ou, se você escolheu Selecionar usuários e grupos externos **, verifique** se o usuário que está sendo convidado é um membro dos grupos selecionados.
1. Se você tiver feito alterações, selecione **Salvar** e fechar a **folha configurações de acesso de** entrada.

Se os usuários continuarem a ver o erro, verifique com a organização com a qual eles estão colaborando. As configurações de saída dessa organização podem não permitir o compartilhamento com sua organização. Para obter informações sobre como configurar canais compartilhados entre organizações, consulte [Colaborar com participantes externos em um canal compartilhado](/microsoft-365/solutions/collaborate-teams-direct-connect).

## <a name="we-couldnt-find-any-matches-make-sure-the-email-address-is-correct-or-talk-to-your-admin"></a>Não encontramos nenhum fósforo. Verifique se o endereço de email está correto ou fale com o administrador

Se os usuários veem esse erro, o Microsoft 365 não consegue localizar o endereço de email especificado na organização externa. Você precisará confirmar o endereço com a organização externa.

