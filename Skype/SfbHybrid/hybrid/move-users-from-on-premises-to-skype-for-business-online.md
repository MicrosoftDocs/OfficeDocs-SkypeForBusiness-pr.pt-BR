---
title: Mover usuários do local para o Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
description: Saiba como mover usuários para o Skype for Business online.
ms.openlocfilehash: 74816ae4c67f62cabad018a344b4b1800bd84444
ms.sourcegitcommit: 3c40bdd228ef88967cdf689100f2030f6997d9d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2019
ms.locfileid: "36715889"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Mover usuários do local para o Skype for Business Online

Após mover um usuário do local para o Skype for Business Online, o usuário interage com o Skype for Business online por sua funcionalidade. Todos os contatos que existiam no local estarão disponíveis no Skype for Business Online, e todas as reuniões existentes que o usuário organizou para o futuro serão atualizadas para que eles apontem para o Skype for Business online. Se o usuário estiver habilitado para audioconferência, as reuniões também incluirão as coordenadas de discagem.  Para mover os usuários de um ambiente local para o Skype for Business Online, use o cmdlet Move-CsUser ou o painel de controle do Skype for Business Server, ambos são ferramentas locais. 

Antes de mover qualquer usuário, leia os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem.
 
## <a name="move-users-with-move-csuser"></a>Mover usuários com o move-CsUser 

O move-CsUser está disponível em uma janela do PowerShell do Shell de gerenciamento do Skype for Business local. Você deve ter privilégios suficientes no ambiente local, bem como no locatário do Office 365, conforme descrito em [credenciais administrativas necessárias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela local do Shell de gerenciamento do Skype for Business Server com credenciais locais e usar o `-Credential` parâmetro para especificar credenciais para um Office 365 conta com a função administrativa necessária do Office 365.

Para mover um usuário para o modo online usando o move-CsUser:

- Especifique o usuário a ser movido usando o parâmetro Identity.
- Especifique o parâmetro-Target com o valor "sipfed. online. Lync. <span>com ".
- Se você não tiver uma conta com permissões suficientes no local e no Office 365, use o parâmetro-Credential para fornecer uma conta com permissões suficientes no Office 365.
- Se a conta com permissões no Office 365 não termina em "on. Microsoft. <span>com ", em seguida, você deve especificar o parâmetro-HostedMigrationOverrideUrl com o valor correto, conforme descrito em [credenciais administrativas necessárias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

 > [!NOTE]
 > Você deve determinar o valor correto do HostedMigrationOverrideUrl para o seu locatário. Isso pode ser feito facilmente navegando até o centro de administração do Skype for Business herdado. determinar o prefixo-XXXXXXX.online.lync.com e anexar/HostedMigration/hostedmigrationservice.svc. por exemplo: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc depois de identificar o valor, use-o para a variável $URL conforme mostrado abaixo.

A sequência de cmdlet a seguir pode ser usada para mover um usuário para o Skype for Business Online e supõe que a credencial do Office 365 é uma conta separada e fornecida como entrada para o prompt Get-Credential.

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Se a conta de administrador for a MFA (autenticação multifator) habilitada, não especifique o parâmetro-Credential. As credenciais do administrador serão solicitadas.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Mover usuários com o painel de controle do Skype for Business Server 

1. Abra o aplicativo painel de controle do Skype for Business Server.
2. Na navegação à esquerda, escolha **usuários**.
3. Use **Localizar** para localizar os usuários que você gostaria de mudar para o Skype for Business online.
4. Selecione o (s) usuário (s) e, no menu suspenso **ação** acima da lista, escolha **mover usuários selecionados para o Skype for Business online**.
5. No assistente, clique em **Avançar**.
6. Se solicitado, entre no Office 365, com uma conta que termina em. onmicrosoft.com e tem permissões suficientes.
7. Clique em **Avançar**e, **** em seguida, mais uma vez para mover o usuário.
8. Observe que as mensagens de status referentes a sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, e não no assistente.

## <a name="see-also"></a>Confira também

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
