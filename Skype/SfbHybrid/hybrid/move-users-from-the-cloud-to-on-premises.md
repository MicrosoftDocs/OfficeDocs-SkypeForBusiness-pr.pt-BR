---
title: Mover usuários da nuvem para o local
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
description: Saiba como mover usuários do Skype for Business Online para o local.
ms.openlocfilehash: 64a5561fda35669be6ce7718c3ec037dcb8b9264
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221331"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Mover usuários da nuvem para o local 

Se necessário, você pode mover um usuário que foi migrado anteriormente do local para a nuvem (usando o Skype for Business Online ou Apenas Teams) de volta para o local. Para mover os usuários do modo Skype for Business Online ou TeamsOnly de volta para uma implantação local do Skype for Business Server, use o cmdlet Move-CsUser ou o Painel de Controle do Skype for Business Server, que são ferramentas locais. Ao mover um usuário de volta para uma implantação local, você deve decidir para qual pool mover o usuário.

> [!Important]
> Se o usuário estava anteriormente no modo TeamsOnly e você estiver usando uma versão anterior ao Skype for Business Server 2015 com CU8, você também deve remover a atribuição do modo TeamsOnly do TeamsUpgradePolicy para esse usuário. Os usuários locais não devem ter o modo= TeamsOnly.  As versões subsequentes do Skype for Business Server removem automaticamente essa atribuição. Para obter mais detalhes, [consulte Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Pré-requisitos

- A organização deve ter o Azure AD Connect configurado corretamente e sincronizar todos os atributos relevantes para o usuário, conforme descrito em Configurar o [Azure AD Connect.](configure-azure-ad-connect.md)
- O usuário que está sendo movido de volta online para o local já deve existir no Active Directory local.
- O Skype for Business híbrido deve ser configurado, conforme descrito em [Configurar o Skype for Business híbrido.](configure-federation-with-skype-for-business-online.md)

## <a name="moving-users-back-to-on-premises"></a>Movendo usuários de volta para o local

Depois de mover um usuário da nuvem de volta para o local:

- O usuário interage com sua implantação do Skype for Business Server para sua funcionalidade. 
- Todos os contatos existentes no Skype for Business Online ou no Teams são migrados para o Skype for Business Server. Os dois conjuntos de contatos são mesclados e, em seguida, migrados de volta para o local.  Além disso, os contatos pré-existentes no Teams permanecem no Teams.
- Se o usuário também usar o Teams, ele não poderá interoperar com os usuários do Skype for Business nem poderá se comunicar com usuários em organizações federadas.
- As reuniões no Skype for Business Online *não são* migradas automaticamente de volta para o local. Os usuários devem reagendar suas reuniões ou, se desejar, usar a Ferramenta [de Migração de Reunião.](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)

### <a name="move-users-with-move-csuser"></a>Mover usuários com Move-CsUser

Move-CsUser está disponível em uma janela do PowerShell do Shell de Gerenciamento do Skype for Business local. Você deve ter privilégios suficientes no ambiente local, bem como na organização do serviço de nuvem (Microsoft 365 ou Office 365), conforme descrito em Credenciais [administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)necessárias. Você pode usar uma única conta com privilégios em ambos os ambientes ou iniciar uma janela local do Shell de Gerenciamento do Skype for Business Server com credenciais locais e usar o parâmetro para especificar credenciais para uma conta do `-Credential` Microsoft 365 ou office 365 com a função administrativa necessária.

Para mover um usuário para o local usando Move-CsUser:

- Especifique o usuário para mover usando o parâmetro Identity.
- Especifique o parâmetro -Target com o nome de domínio totalmente qualificado do pool local desejado que hospedará o usuário.
- Se você não tiver uma conta com permissões suficientes no serviço local e na nuvem (Microsoft 365 ou Office 365), use o parâmetro -credential para fornecer uma conta com permissões suficientes no Microsoft 365 ou no Office 365.
- Se a conta com permissões no Microsoft 365 ou no Office 365 não terminar em "on.microsoft.com", você deverá especificar o parâmetro -HostedMigrationOverrideUrl, com o valor correto conforme descrito em Credenciais [administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)necessárias.

A sequência de cmdlets a seguir pode ser usada para mover um usuário para o Skype for Business Server, e supõe que a credencial do Microsoft 365 ou Office 365 seja uma conta separada e fornecida como entrada para o prompt de Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Mover usuários com o Painel de Controle do Skype for Business Server

1. Abra o aplicativo Painel de Controle do Skype for Business Server.
2. No painel de navegação esquerdo, escolha **Usuários**.
3. Use **Localizar** para localizar os usuários que você gostaria de mover de volta para o local.
4. Selecione o(s) usuário(s) e, no **menu** suspenso Ação acima da lista, escolha Mover usuários selecionados para **o local.**
5. No assistente, selecione o pool de usuários que hospedará o usuário e clique em **Próximo.**
6. Se solicitado, entre no Microsoft 365 ou no Office 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.
7. Clique **em Avançar** e em **Avançar** mais uma vez para mover o usuário.
8. Observe que as mensagens de status relacionadas ao sucesso ou falha são fornecidas na parte superior do aplicativo do Painel de Controle principal, não no assistente.

### <a name="removing-teamsonly-mode"></a>Removendo o modo TeamsOnly

Se você estiver usando uma versão anterior ao Skype for Business 2015 com CU8 e o usuário estiver sendo movido de volta para o local no modo TeamsOnly, deverá remover a instância UpgradeToTeams antes de mover o usuário no `TeamsUpgradePolicy` local. Você pode conceder explicitamente uma política com um modo diferente ou simplesmente remover a atribuição de política existente para que o usuário use a política global (desde que a política global do locatário não seja UpgradeToTeams).

Para remover a atribuição do usuário do TeamsUpgradePolicy, execute o seguinte cmdlet em uma janela do PowerShell do Skype for Business Online:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Como alternativa, para atribuir outra instância de TeamsUpgradePolicy que não tenha mode=TeamsOnly, você pode especificar o nome da instância desejada como o valor do parâmetro PolicyName no cmdlet. Para ver uma lista de instâncias disponíveis do TeamsUpgradePolicy, execute Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Confira também

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
