---
title: Mover usuários do ambiente local para o Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Saiba como mover os usuários para Skype for Business Online.
ms.openlocfilehash: a865b5ece2802f11bbbd103b10e52ff82f1ef804
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614975"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Mover usuários do ambiente local para o Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Depois de mover um usuário do local para o Skype for Business Online, o usuário interage com o Skype for Business Online para sua funcionalidade. Todos os contatos existentes no local estarão disponíveis no Skype for Business Online e quaisquer reuniões existentes que o usuário organizou para o futuro serão atualizadas para que os links apontem para o Skype for Business Online. Se o usuário estiver habilitado para Audioconferência, as reuniões também incluirão coordenadas discada.  Para mover usuários de um ambiente local para o Skype for Business Online, use o cmdlet Move-CsUser ou o painel de controle Skype for Business Server, ambos são ferramentas locais. 

Antes de mover qualquer usuário, revise os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem.

> [!NOTE]
> Em preparação para a próxima reforma do Skype for Business Online, a Microsoft simplificou a forma como as organizações se movem para Teams. Ao mover os usuários do local para a nuvem, os usuários agora são atribuídos automaticamente ao modo TeamsOnly e suas reuniões no local são convertidas automaticamente em reuniões de Teams, como se a opção tivesse sido especificada, independentemente de a opção ter sido `-MoveToTeams` realmente especificada.  Antes de se aposentar do Skype for Business Online, as organizações que exigem a mudança de usuários do local para o Skype for Business Online podem fazer isso em duas etapas atualizando o modo do usuário depois que o usuário for movido para o *TeamsOnly*. No entanto, em um futuro próximo, não será mais possível atribuir um modo diferente do TeamsOnly aos usuários que estão na nuvem.  
 
## <a name="move-users-with-move-csuser"></a>Mover usuários com Move-CsUser 

Move-CsUser está disponível em uma janela local Skype for Business Shell de Gerenciamento do PowerShell. Você deve ter privilégios suficientes no ambiente local, bem como na organização Microsoft 365, conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela local do Shell de Gerenciamento do Skype for Business Server com credenciais locais e usar o parâmetro para especificar credenciais para uma conta Microsoft 365 com a função administrativa `-Credential` necessária.

Para mover um usuário para online usando Move-CsUser:

- Especifique o usuário para mover usando o parâmetro Identity.
- Especifique o parâmetro -Target com o valor "sipfed.online.lync. <span> com".
- Se você não tiver uma conta com permissões suficientes no local e Microsoft 365, use o parâmetro -credential para fornecer uma conta com permissões suficientes Microsoft 365.
- Se a conta com permissões no Microsoft 365 não terminar em ".onmicrosoft. <span> com", em seguida, você deve especificar o parâmetro -HostedMigrationOverrideUrl, com o valor correto conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

A sequência de cmdlets a seguir pode ser usada para mover um usuário para o Skype for Business Online e atribui o modo padrão do locatário ao usuário. Presume que a credencial Microsoft 365 é uma conta separada e fornecida como entrada para o prompt Get-Credential.

```PowerShell
# From an on-premises Skype for Business Server or Lync Server 2013 management shell window, run:
 
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
 
# And then from a Teams PowerShell window, remove TeamsOnly mode by running: 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName $null
```

Se a conta de administrador estiver habilitada para MFA (Autenticação Multifa factor), não especifique o parâmetro -Credential. O administrador será solicitado a solicitar credenciais.

## <a name="move-users-with-skype-for-business-server-control-panel-and-teams-admin-center"></a>Mover usuários com Skype for Business Server Painel de Controle e Teams Admin Center

1. Abra o aplicativo Skype for Business Server Painel de Controle.
2. Na navegação à esquerda, escolha **Usuários**.
3. Use **Localizar** para localizar os usuários que você gostaria de mover para Skype for Business Online.
4. Selecione o(s) usuário(s)  e, em seguida, na lista suspenso Ação acima da lista, escolha Mover usuários selecionados para Skype for Business **Online** ou **Mover** usuários selecionados para Teams . Ambas as opções moverão inicialmente o usuário para o modo TeamsOnly, mas após a movimentação, você pode atribuir outro modo. 
5. No assistente, clique em **Próximo**.
6. Se solicitado, entre no Microsoft 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.
7. Clique **em** Avançar e **em Avançar mais** uma vez para mover o usuário.
8. Observe que as mensagens de status relacionadas ao sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, não no assistente.
9. Abra o Teams Admin Center e selecione "Usuários" na navegação à esquerda. 
10. Clique no usuário desejado na listview. 
11. Clique na **seção Editar** na seção que diz Teams **atualização**.
12. No sublinhado à direita, selecione o modo de coexistência desejado e clique em **Aplicar**.
 

## <a name="see-also"></a>Confira também

[Move-CsUser](/powershell/module/skype/move-csuser)
