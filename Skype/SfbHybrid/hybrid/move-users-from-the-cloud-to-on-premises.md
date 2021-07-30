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
description: Saiba como mover usuários do Teams para o local.
ms.openlocfilehash: 782fd16fb4ad5c8567600ffcf781410a4532c213
ms.sourcegitcommit: d0fb9035903d9e1ce184417250913db10608b1a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2021
ms.locfileid: "53660709"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Mover usuários da nuvem para o local 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Se necessário, você pode mover um usuário que foi migrado anteriormente do local para Teams voltar para o local. Para mover os usuários do modo TeamsOnly de volta para uma implantação local do Skype for Business Server, use o cmdlet Move-CsUser ou o Painel de Controle Skype for Business Server, ambos são ferramentas locais. Ao mover um usuário de volta para uma implantação local, você deve decidir para qual pool mover o usuário.

> [!Important]
> Se o usuário estava anteriormente no modo TeamsOnly e você está usando uma versão anterior do Skype for Business Server 2015 com CU8, você também deve remover a atribuição do modo TeamsOnly do TeamsUpgradePolicy para esse usuário. Os usuários locais não devem ter mode= TeamsOnly.  As versões subsequentes Skype for Business Server remover automaticamente essa atribuição. Para obter mais detalhes, [consulte Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Pré-requisitos

- A organização deve ter o Azure AD Conexão configurado corretamente e estar sincronizando todos os atributos relevantes para o usuário, conforme descrito em [Configure Azure AD Conexão](configure-azure-ad-connect.md).
- O usuário que está sendo movido de volta online para o local já deve existir no Active Directory local.
- Skype for Business híbrido deve ser configurado, conforme descrito em [Configure Skype for Business híbrido](configure-federation-with-skype-for-business-online.md).

## <a name="moving-users-back-to-on-premises"></a>Mover os usuários de volta para o local

Depois de mover um usuário da nuvem de volta para o local:

- O usuário interage com sua implantação Skype for Business Server para sua funcionalidade. 
- Todos os contatos existentes no Teams são migrados para Skype for Business Server. Os dois conjuntos de contatos são mesclados e migrados de volta para o local.  Além disso, os contatos que estão pré-existentes no Teams permanecem em Teams.
- Se o usuário também usa Teams, ele não terá a capacidade de interoperar com Skype for Business usuários, nem poderá se comunicar com usuários em organizações federadas.

### <a name="move-users-with-move-csuser"></a>Mover usuários com Move-CsUser

Move-CsUser está disponível em uma janela local Skype for Business Shell de Gerenciamento do PowerShell. Você deve ter privilégios suficientes no ambiente local, bem como na organização do serviço de nuvem (Microsoft 365), conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela local do Shell de Gerenciamento do Skype for Business Server com credenciais locais e usar o parâmetro para especificar credenciais para uma conta Microsoft 365 com a função administrativa `-Credential` necessária.

Para mover um usuário para o local usando Move-CsUser:

- Especifique o usuário para mover usando o parâmetro Identity.
- Especifique o parâmetro -Target com o nome de domínio totalmente qualificado do pool local desejado que hospedará o usuário.
- Se você não tiver uma conta com permissões suficientes no local e no serviço de nuvem (Microsoft 365), use o parâmetro -credential para fornecer uma conta com permissões suficientes no Microsoft 365.
- Se a conta com permissões no Microsoft 365 não terminar em "on.microsoft.com", você deverá especificar o parâmetro -HostedMigrationOverrideUrl, com o valor correto conforme descrito em Credenciais [administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)necessárias.

A sequência de cmdlets a seguir pode ser usada para mover um usuário para Skype for Business Server e supõe que a credencial Microsoft 365 é uma conta separada e fornecida como entrada para o prompt Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Mover usuários com o painel de Skype for Business Server de controle

1. Abra o aplicativo Skype for Business Server Painel de Controle.
2. Na navegação à esquerda, escolha **Usuários**.
3. Use **Localizar** para localizar os usuários que você gostaria de mover de volta para o local.
4. Selecione os usuários e, em seguida, na lista suspenso **Ação** acima da lista, escolha Mover usuários **selecionados** para o local .
5. No assistente, selecione o pool de usuários que hospedará o usuário e clique em **Próximo**.
6. Se solicitado, entre no Microsoft 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.
7. Clique **em** Avançar e **em Avançar mais** uma vez para mover o usuário.
8. Observe que as mensagens de status relacionadas ao sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, não no assistente.

### <a name="removing-teamsonly-mode"></a>Removendo o modo TeamsOnly

Se você estiver usando uma versão anterior ao Skype for Business 2015 com CU8 e o usuário estiver sendo movido de volta para o modo local no teamsOnly, remova a instância UpgradeToTeams antes de mover o usuário `TeamsUpgradePolicy` no local. Você pode conceder explicitamente uma política com um modo diferente ou simplesmente remover a atribuição de política existente para que esse usuário use a política global (desde que a política global do locatário não seja UpgradeToTeams).

Para remover a atribuição do usuário do TeamsUpgradePolicy, execute o seguinte cmdlet de uma janela Teams PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Como alternativa, para atribuir outra instância do TeamsUpgradePolicy que não tenha mode=TeamsOnly, você pode especificar o nome da instância desejada como o valor do parâmetro PolicyName no cmdlet. Para ver uma lista de instâncias disponíveis do TeamsUpgradePolicy, execute Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Confira também

[Move-CsUser](/powershell/module/skype/move-csuser)