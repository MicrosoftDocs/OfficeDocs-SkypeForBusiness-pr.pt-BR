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
description: Saiba como mover usuários do Skype for Business online para o local.
ms.openlocfilehash: 64a5561fda35669be6ce7718c3ec037dcb8b9264
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221331"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Mover usuários da nuvem para o local 

Se necessário, você pode mover um usuário que foi migrado anteriormente do local para a nuvem (seja usando o Skype for Business online ou apenas o Microsoft Teams) de volta para o local. Para mover os usuários do Skype for Business online ou o modo TeamsOnly de volta para uma implantação local do Skype for Business Server, use o cmdlet Move-CsUser ou o painel de controle do Skype for Business Server, ambos são ferramentas locais. Ao mover um usuário de volta para uma implantação local, você deve decidir para qual pool mover o usuário.

> [!Important]
> Se o usuário estava anteriormente no modo TeamsOnly e você está usando uma versão anterior do que o Skype for Business Server 2015 com o CU8, você também deve remover a atribuição de modo TeamsOnly de TeamsUpgradePolicy para esse usuário. Os usuários locais não devem ter o modo = TeamsOnly.  As versões subsequentes do Skype for Business Server removem automaticamente essa atribuição. Para obter mais detalhes, consulte [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Pré-requisitos

- A organização deve ter o Azure AD Connect configurado corretamente e sincronizar todos os atributos relevantes para o usuário, conforme descrito em [Configure Azure ad Connect](configure-azure-ad-connect.md).
- O usuário que está sendo movido online de volta para o local deve já existir no Active Directory local.
- O Skype for Business híbrido deve ser configurado, conforme descrito em [Configure Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md).

## <a name="moving-users-back-to-on-premises"></a>Movendo usuários de volta para o local

Depois de mover um usuário da nuvem de volta para o local:

- O usuário interage com sua implantação do Skype for Business Server para sua funcionalidade. 
- Todos os contatos que existiam no Skype for Business online ou no Teams são migrados para o Skype for Business Server. Os dois conjuntos de contatos são mesclados e migrados de volta para o local.  Além disso, os contatos que estão previamente existentes no Teams permanecem no Teams.
- Se o usuário também usa o Microsoft Teams, eles não terão a capacidade de interoperar com os usuários do Skype for Business, nem poderão se comunicar com os usuários em organizações federadas.
- As reuniões no Skype for Business Online *não* são migradas automaticamente de volta para o local. Os usuários devem reagendar suas reuniões ou, se desejado, usar a [ferramenta de migração da reunião](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).

### <a name="move-users-with-move-csuser"></a>Mover usuários com o move-CsUser

O move-CsUser está disponível em uma janela do PowerShell do Shell de gerenciamento do Skype for Business local. Você deve ter privilégios suficientes no ambiente local, bem como na organização do serviço de nuvem (Microsoft 365 ou Office 365), conforme descrito em [credenciais administrativas necessárias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela local do Shell de gerenciamento do Skype for Business Server com credenciais locais e usar o `-Credential` parâmetro para especificar credenciais para uma conta do Microsoft 365 ou do Office 365 com a função administrativa necessária.

Para mover um usuário para o local usando o move-CsUser:

- Especifique o usuário a ser movido usando o parâmetro Identity.
- Especifique o parâmetro-Target com o nome de domínio totalmente qualificado do pool local desejado que hospedará o usuário.
- Se você não tiver uma conta com permissões suficientes no local e no serviço de nuvem (Microsoft 365 ou Office 365), use o parâmetro-Credential para fornecer uma conta com permissões suficientes no Microsoft 365 ou no Office 365.
- Se a conta com permissões no Microsoft 365 ou no Office 365 não terminar em "on.microsoft.com", você deverá especificar o parâmetro-HostedMigrationOverrideUrl, com o valor correto, conforme descrito em [credenciais administrativas necessárias](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

A sequência de cmdlet a seguir pode ser usada para mover um usuário para o Skype for Business Server e pressupõe que a credencial do Microsoft 365 ou do Office 365 seja uma conta separada e fornecida como entrada para o prompt Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Mover usuários com o painel de controle do Skype for Business Server

1. Abra o aplicativo painel de controle do Skype for Business Server.
2. Na navegação à esquerda, escolha **usuários**.
3. Use **Localizar** para localizar o (s) usuário (s) que você deseja mover de volta para o local.
4. Selecione o (s) usuário (s) e, em seguida, na lista suspensa **ação** acima da lista, escolha **mover usuários selecionados para o local**.
5. No assistente, selecione o pool de usuários que hospedará o usuário e clique em **Avançar**.
6. Se solicitado, entre no Microsoft 365 ou no Office 365 com uma conta que termine no. onmicrosoft.com e tenha permissões suficientes.
7. Clique em **Avançar**e, em seguida, **mais uma vez** para mover o usuário.
8. Observe que as mensagens de status referentes a sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, e não no assistente.

### <a name="removing-teamsonly-mode"></a>Removendo o modo TeamsOnly

Se você estiver usando uma versão anterior ao Skype for Business 2015 com o CU8 e o usuário estiver sendo movido de volta para o local no modo TeamsOnly, você deverá remover a instância do UpgradeToTeams de `TeamsUpgradePolicy` antes de mover o usuário local. Você pode conceder explicitamente uma política com um modo diferente ou simplesmente remover a atribuição de política existente para que esse usuário use a política global (desde que a política global do seu locatário não seja UpgradeToTeams).

Para remover a atribuição do usuário do TeamsUpgradePolicy, execute o seguinte cmdlet em uma janela do PowerShell do Skype for Business Online:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Como alternativa, para atribuir outra instância de TeamsUpgradePolicy que não tenha o modo = TeamsOnly, você pode especificar o nome da instância desejada como o valor do parâmetro PolicyName no cmdlet. Para ver uma lista de instâncias disponíveis do TeamsUpgradePolicy, execute Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Confira também

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
