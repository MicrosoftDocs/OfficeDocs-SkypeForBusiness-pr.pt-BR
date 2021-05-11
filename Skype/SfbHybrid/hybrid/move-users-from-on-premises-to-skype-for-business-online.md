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
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Saiba como mover os usuários para Skype for Business Online.
ms.openlocfilehash: e4536b13b6a9c05757bfcbf629fcc8301f94ed86
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305975"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Mover usuários do ambiente local para o Skype for Business Online

Depois de mover um usuário do local para o Skype for Business Online, o usuário interage com o Skype for Business Online para sua funcionalidade. Todos os contatos existentes no local estarão disponíveis no Skype for Business Online e quaisquer reuniões existentes que o usuário organizou para o futuro serão atualizadas para que os links apontem para o Skype for Business Online. Se o usuário estiver habilitado para Audioconferência, as reuniões também incluirão coordenadas discada.  Para mover usuários de um ambiente local para o Skype for Business Online, use o cmdlet Move-CsUser ou o painel de controle Skype for Business Server, ambos são ferramentas locais. 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

Antes de mover qualquer usuário, revise os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem.

> [!NOTE]
> Em preparação para a próxima reforma do Skype for Business Online, a Microsoft estará simplificando como as organizações se movem para o Teams em um futuro próximo e não será mais possível mover para o Skype for Business Online.  Quando essas alterações são disponibilizadas, ao mover um usuário do local para a nuvem, os usuários serão atribuídos automaticamente ao modo TeamsOnly e suas reuniões no local serão convertidas automaticamente em reuniões Teams, como se a opção tivesse sido especificada, independentemente de a opção ser realmente `-MoveToTeams` especificada. Esperamos lançar essa funcionalidade antes da aposentadoria real de 31 de julho de 2021.   No momento, se essa opção não for especificada, os usuários migram de uma residência no Skype for Business Server local para o Skype for Business Online e seu modo permanece inalterado, que é a funcionalidade documentada neste artigo.

 
## <a name="move-users-with-move-csuser"></a>Mover usuários com Move-CsUser 

Move-CsUser está disponível em uma janela local Skype for Business Shell de Gerenciamento do PowerShell. Você deve ter privilégios suficientes no ambiente local, bem como na organização Microsoft 365, conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela local do Shell de Gerenciamento do Skype for Business Server com credenciais locais e usar o parâmetro para especificar credenciais para uma conta Microsoft 365 com a função administrativa `-Credential` necessária.

Para mover um usuário para online usando Move-CsUser:

- Especifique o usuário para mover usando o parâmetro Identity.
- Especifique o parâmetro -Target com o valor "sipfed.online.lync. <span> com".
- Se você não tiver uma conta com permissões suficientes no local e Microsoft 365, use o parâmetro -credential para fornecer uma conta com permissões suficientes Microsoft 365.
- Se a conta com permissões no Microsoft 365 não terminar em ".onmicrosoft. <span> com", em seguida, você deve especificar o parâmetro -HostedMigrationOverrideUrl, com o valor correto conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

A sequência de cmdlets a seguir pode ser usada para mover um usuário para Skype for Business Online. Presume que a credencial Microsoft 365 é uma conta separada e fornecida como entrada para o prompt Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Se a conta de administrador estiver habilitada para MFA (Autenticação Multifa factor), não especifique o parâmetro -Credential. O administrador será solicitado a solicitar credenciais.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Mover usuários com Skype for Business Server Painel de Controle 

1. Abra o aplicativo Skype for Business Server Painel de Controle.
2. Na navegação à esquerda, escolha **Usuários**.
3. Use **Localizar** para localizar os usuários que você gostaria de mover para Skype for Business Online.
4. Selecione o(s) usuário(s) e, em seguida, no menu suspenso **Ação** acima da lista, escolha Mover usuários selecionados para Skype for Business **Online**.
5. No assistente, clique em **Próximo**.
6. Se solicitado, entre no Microsoft 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.
7. Clique **em** Avançar e **em Avançar mais** uma vez para mover o usuário.
8. Observe que as mensagens de status relacionadas ao sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, não no assistente.

## <a name="see-also"></a>Também consulte

[Move-CsUser](/powershell/module/skype/move-csuser)
