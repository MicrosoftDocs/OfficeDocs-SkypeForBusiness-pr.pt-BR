---
title: Testar permissões de administrador no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Como testar permissões de administrador no Skype for Business Server
ms.openlocfilehash: 80971dab292252775f9a58cbf822d746326c8abf
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760689"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Testar permissões de administrador no Skype for Business Server

|&nbsp; |&nbsp; |
|--|--|
|Agendamento de verificação|Após a implantação Skype for Business Server inicial. Conforme necessário se surgirem problemas relacionados à permissão.|
|Ferramenta de teste|Windows PowerShell|
|Permissões obrigatórias|Quando executado localmente usando o Shell de Gerenciamento Skype for Business Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.<br><br/>Quando executado usando uma instância remota de Windows PowerShell, os usuários devem ter uma função RBAC com permissão para executar o cmdlet Test-CsOUPermission. Para ver uma lista de todas as funções do RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt Windows PowerShell:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Descrição

Quando você instala o Skype for Business Server, uma das tarefas executadas pelo programa de Instalação fornece ao grupo RTCUniversalUserAdmins as permissões do Active Directory necessárias para gerenciar usuários, computadores, contatos, contatos de aplicativo e pessoas InetOrg. Se você tiver desabilitado a herança de permissão no Active Directory, a instalação não poderá atribuir essas permissões. Como resultado, os membros do grupo RTCUniversalUserAdmins não poderão gerenciar Skype for Business Server entidades. Esses privilégios de gerenciamento estarão disponíveis apenas para administradores de domínio. 

O Test-CsOUPermission cmdlet verifica se as permissões necessárias para gerenciar usuários, computadores e outros objetos são definidas em um contêiner do Active Directory. Se essas permissões não estão definidas, você pode resolver esse problema executando o [cmdlet Grant-CsOUPermission](/powershell/module/skype/Grant-CsOUPermission). 

Observe que Grant-CsOUPermission só pode atribuir permissões a membros do grupo RTCUniversalUserAdmins. Não é possível usar esse cmdlet para conceder permissões a um usuário ou grupo arbitrário. Se você quiser que um usuário ou grupo diferente tenha permissões de gerenciamento de usuário, adicione esse usuário (ou grupo) ao grupo RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Executando o teste

Para verificar se as permissões de gerenciamento estão definidas em um contêiner, execute o cmdlet Test-CsOUPermission seguido pelo nome diferenciado do contêiner e pelo tipo de permissões que você está verificando. Por exemplo, este comando verifica se as permissões do usuário estão definidas em ou=Redmond,dc=litwareinc,dc=com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Para verificar várias permissões usando um único comando, coloque cada tipo de permissão entre aspas e separe esses tipos usando vírgulas. Por exemplo, este comando verifica permissões de usuário, computador e contato:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Para obter mais informações, consulte [o tópico de ajuda para o cmdlet Test-CsOUPermission](/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se as permissões necessárias já foram definidas, Test-CsOUPermission retornará uma resposta de uma palavra:

Verdadeiro

Se as permissões necessárias não estão definidas, Test-CsOUPermission retornará o valor False. Talvez seja preciso pesquisar por um momento para encontrar esse valor. Normalmente, ele será inserido dentro de vários avisos que acompanham. Por exemplo:

AVISO: ace (entrada de controle de acesso) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendentes; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

AVISO: As entradas de controle de acesso (ACEs) no objeto "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" não estão prontas. 

Falso 

AVISO: o processamento "Test-CsOUPermission" foi concluído com avisos. Avisos "2" foram gravados durante essa executar. 

AVISO: Os resultados detalhados podem ser encontrados em "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Se Test-CsOUPermission falha, geralmente significa que a permissão especificada não foi atribuída ao grupo RTCUniversalUserAdmins. Você pode resolver esse problema e atribuir as permissões necessárias usando o cmdlet Grant-CsOUPermission. Por exemplo, este comando fornece permissões de UO para usuários, contatos e inetOrgPersons para o grupo RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Para obter mais informações, consulte [o tópico de ajuda para o cmdlet Test-CsOUPermission](/powershell/module/skype/test-csoupermission).