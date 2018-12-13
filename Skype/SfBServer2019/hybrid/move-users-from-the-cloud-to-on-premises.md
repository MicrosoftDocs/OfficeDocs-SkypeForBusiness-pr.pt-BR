---
title: Mover usuários de nuvem para local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Saiba como mover os usuários do Skype para Business Online no local.
ms.openlocfilehash: fadb3a485cac691a97f0786aea78000b6b48c344
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247599"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Mover usuários de nuvem para local 

Se necessário, você pode mover um usuário que tiver sido migrado de no local para a nuvem (se estiver usando o Skype para Business Online ou equipes somente) volta para no local. Para mover usuários de um dos Skype para o modo Online de negócios ou TeamsOnly volta para uma implantação local do Skype para Business Server, use o cmdlet Move-CsUser ou o Skype para painel de controle do Business Server, ambos os quais são as ferramentas de local. Quando você move um usuário de volta para uma implantação local, você deve decidir qual pool para mover o usuário.

> [!Important]
> Se o usuário estava anteriormente no modo de TeamsOnly e você estiver usando uma versão anterior Skype para 2015 do servidor de negócios com CU8, em seguida, você também deve remover a atribuição de modo de TeamsOnly de TeamsUpgradePolicy para esse usuário. Os usuários não devem ter o modo local = TeamsOnly.  Versões subsequentes do Skype para Business Server removerem automaticamente essa atribuição. Para obter mais detalhes, consulte [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Pré-requisitos

- A organização deve ter o Azure Connect da AD configurado corretamente e ser sincronizando todos os atributos relevantes para o usuário, conforme descrito em [Configurar o Azure AD Connect](configure-azure-ad-connect.md).
- O usuário sendo movido de volta on-line para no local já deve existir no Active Directory local.
- Skype para o híbrido de negócios deve ser configurado conforme descrito em [Configurar Skype para o híbrido de negócios](configure-federation-with-skype-for-business-online.md).

## <a name="moving-users-back-to-on-premises"></a>Migração de usuários de volta para no local

Depois que você mover um usuário da nuvem volta para local:

- O usuário interage com seu Skype para implantação de servidor de negócios para sua funcionalidade. 
- Todos os contatos que existiam no Skype para Business Online são migrados voltar ao Skype para Business Server. Atualmente, os contatos que estão em equipes não são migrados voltar ao local.
- Se o usuário também usa equipes, eles não terão a capacidade de interoperar com Skype para usuários comerciais, nem eles serão capazes de se comunicarem com usuários em organizações federadas.
- Reuniões no Skype para Business Online são *não* automaticamente migrada de volta para no local. Os usuários devem tanto reagende suas reuniões ou, se desejado, usam a [Ferramenta de migração de reunião](https://support.office.com/en-us/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).

### <a name="move-users-with-move-csuser"></a>Mover os usuários com Move-CsUser

Move-CsUser está disponível no Skype local para a janela do PowerShell de Shell de gerenciamento de negócios. Você deve ter privilégios suficientes no ambiente do local, bem como o locatário do Office 365, conforme descrito em [necessárias credenciais administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Você pode usar uma única conta que possua privilégios nos dois ambientes, ou você pode iniciar uma Skype no local para a janela do Shell de gerenciamento do servidor de negócios com credenciais no local e usar o `-Credential` parâmetro para especificar as credenciais para um Office 365 conta com a função administrativa do Office 365 necessária.

Para mover um usuário no local usando o Move-CsUser:

- Especifique o usuário mover usando o parâmetro Identity.
- Especificar o - parâmetro de destino com o nome de domínio totalmente qualificado do pool local desejado que irá hospedar o usuário.
- Se você não tiver uma conta com permissões suficientes em ambos no local e o Office 365, use o parâmetro - credential para fornecer uma conta com permissões suficientes no Office 365.
- Se a conta com permissões no Office 365 não termina em "on.microsoft.com", você deve especificar o parâmetro - HostedMigrationOverrideUrl, com o valor correto, conforme descrito em [necessárias credenciais administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

A seguinte sequência de cmdlet pode ser usada para mover um usuário para Skype para Business Server e assume a credencial do Office 365 é uma conta separada e fornecidos como entrada para o prompt de Get-Credential.

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Mover os usuários com o Skype para painel de controle do servidor de negócios

1. Abra o Skype para controle de servidor de negócios app do painel.
2. No painel de navegação esquerdo, escolha **usuários**.
3. Use o comando **Localizar** para localizar o (s) que você deseja mover de volta para no local.
4. Selecione o (s) e no menu suspenso de **ação** acima da lista, selecione **mover usuários selecionados para o local**.
5. No assistente, selecione o pool de usuário que hospedará o usuário e clique em **Avançar**.
6. Se solicitado, faça logon no Office 365, com uma conta que termina em. onmicrosoft.com e tem permissões suficientes.
7. Clique em **Avançar**e, em seguida, **Avançar** mais uma vez para mover o usuário.
8. Observe que as mensagens de status sobre o sucesso ou falha são fornecidas na parte superior do aplicativo principal do painel de controle, não no assistente.

### <a name="removing-teamsonly-mode"></a>Removendo o modo de TeamsOnly

Se você estiver usando uma versão anterior ao Skype para 2015 corporativos com CU8 e o usuário está sendo transferido volta para no local no modo de TeamsOnly, você deve remover a instância de UpgradeToTeams do `TeamsUpgradePolicy` antes de mover o usuário no local. Você pode conceder explicitamente uma política com um modo diferente ou simplesmente remova a atribuição de política existente para que o usuário usar a política global (desde que política global do seu locatário não é UpgradeToTeams).

Para remover a atribuição do usuário do TeamsUpgradePolicy, execute o seguinte cmdlet de um Skype para a janela de negócios Online PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Como alternativa, para atribuir a outra instância do TeamsUpgradePolicy que não tem o modo = TeamsOnly, você pode especificar o nome da instância desejada como o valor do parâmetro PolicyName no cmdlet. Para ver uma lista de instâncias de disponibilidade de TeamsUpgradePolicy, execute Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Consulte também

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)