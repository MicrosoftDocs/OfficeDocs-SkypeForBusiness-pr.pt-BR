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
description: Saiba como mover usuários para o Skype for Business Online.
ms.openlocfilehash: 4d74cdebc5477d0204f69b64c2c05a4435212b3f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110617"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Mover usuários do ambiente local para o Skype for Business Online

Depois de mover um usuário do local para o Skype for Business Online, o usuário interage com o Skype for Business Online para sua funcionalidade. Todos os contatos existentes no local estarão disponíveis no Skype for Business Online e quaisquer reuniões existentes que o usuário organizou para o futuro serão atualizadas para que os links apontem para o Skype for Business Online. Se o usuário estiver habilitado para Audioconferência, as reuniões também incluirão coordenadas discada.  Para mover usuários de um ambiente local para o Skype for Business Online, use o cmdlet Move-CsUser ou o Painel de Controle do Skype for Business Server, ambos ferramentas locais. 

Antes de mover qualquer usuário, revise os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem.
 
## <a name="move-users-with-move-csuser"></a>Mover usuários com Move-CsUser 

Move-CsUser está disponível em uma janela local do Shell de Gerenciamento do Skype for Business PowerShell. Você deve ter privilégios suficientes no ambiente local, bem como na organização do Microsoft 365/Office 365, conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela do Shell de Gerenciamento do Skype for Business Server local com credenciais locais e usar o parâmetro para especificar credenciais para uma conta do `-Credential` Microsoft 365 ou office 365 com a função administrativa necessária.

Para mover um usuário para online usando Move-CsUser:

- Especifique o usuário para mover usando o parâmetro Identity.
- Especifique o parâmetro -Target com o valor "sipfed.online.lync. <span> com".
- Se você não tiver uma conta com permissões suficientes no local e no Office 365, use o parâmetro -credential para fornecer uma conta com permissões suficientes no Office 365.
- Se a conta com permissões no Office 365 não terminar em ".onmicrosoft. <span> com", em seguida, você deve especificar o parâmetro -HostedMigrationOverrideUrl, com o valor correto conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

A sequência de cmdlets a seguir pode ser usada para mover um usuário para o Skype for Business Online. Ele supõe que a credencial do Microsoft 365 ou Office 365 seja uma conta separada e fornecida como entrada para o prompt Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Se a conta de administrador estiver habilitada para MFA (Autenticação Multifa factor), não especifique o parâmetro -Credential. O administrador será solicitado a solicitar credenciais.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Mover usuários com o Painel de Controle do Skype for Business Server 

1. Abra o aplicativo Painel de Controle do Skype for Business Server.
2. Na navegação à esquerda, escolha **Usuários**.
3. Use **Localizar** para localizar os usuários que você gostaria de mover para o Skype for Business Online.
4. Selecione os usuários e, em seguida, no menu suspenso **Ação** acima da lista, escolha Mover usuários selecionados **para o Skype for Business Online**.
5. No assistente, clique em **Próximo**.
6. Se solicitado, entre no Microsoft 365 ou Office 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.
7. Clique **em** Avançar e **em Avançar mais** uma vez para mover o usuário.
8. Observe que as mensagens de status relacionadas ao sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, não no assistente.

## <a name="see-also"></a>Confira também

[Move-CsUser](/powershell/module/skype/move-csuser)