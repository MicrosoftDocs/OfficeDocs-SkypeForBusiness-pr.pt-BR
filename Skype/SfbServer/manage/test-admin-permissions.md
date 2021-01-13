---
title: Testando permissões de administrador no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Como testar permissões de administrador no Skype for Business Server
ms.openlocfilehash: 27ae50cca0018985ad59dbc4487dd3630cb5cf87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800086"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Testando permissões de administrador no Skype for Business Server

| | |
|--|--|
|Agenda de verificação|Após a implantação inicial do Skype for Business Server. Conforme necessário, se surgirem problemas relacionados à permissão.|
|Ferramenta de teste|Windows PowerShell|
|Permissões obrigatórias|Quando executados localmente usando o Shell de Gerenciamento do Skype for Business Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.<br><br/>Ao executar usando uma instância remota do Windows PowerShell, os usuários devem ter uma função RBAC com permissão para executar o cmdlet Test-CsOUPermission usuário. Para ver uma lista de todas as funções do RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Descrição

Quando você instala o Skype for Business Server, uma das tarefas realizadas pelo programa de Instalação fornece ao grupo RTCUniversalUserAdmins as permissões do Active Directory necessárias para gerenciar usuários, computadores, contatos, contatos de aplicativo e pessoas InetOrg. Se você tiver desabilitado a herança de permissão no Active Directory, a instalação não poderá atribuir essas permissões. Como resultado, os membros do grupo RTCUniversalUserAdmins não poderão gerenciar entidades do Skype for Business Server. Esses privilégios de gerenciamento só estarão disponíveis para administradores de domínio. 

O Test-CsOUPermission cmdlet verifica se as permissões necessárias necessárias para gerenciar usuários, computadores e outros objetos estão definidas em um contêiner do Active Directory. Se essas permissões não estão definidas, você pode resolver esse problema executando [o cmdlet Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission). 

Observe que Grant-CsOUPermission só pode atribuir permissões a membros do grupo RTCUniversalUserAdmins. Não é possível usar esse cmdlet para conceder permissões a um usuário ou grupo arbitrário. Se você quiser que um usuário ou grupo diferente tenha permissões de gerenciamento de usuário, adicione esse usuário (ou grupo) ao grupo RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Executando o teste

Para verificar se as permissões de gerenciamento estão definidas em um contêiner, execute o cmdlet Test-CsOUPermission seguido pelo nome diferenciado do contêiner e pelo tipo de permissões que você está verificando. Por exemplo, este comando verifica se as permissões de usuário estão definidas na ou=Redmond,dc=litwareinc,dc=com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Para verificar várias permissões usando um único comando, coloque cada tipo de permissão entre aspas e separe-os usando vírgulas. Por exemplo, este comando verifica as permissões de usuário, computador e contato:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Para obter mais informações, consulte [o tópico de ajuda para Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se as permissões necessárias já foram definidas, Test-CsOUPermission retornará uma resposta de uma palavra:

Verdadeiro.

Se as permissões necessárias não estão definidas, Test-CsOUPermission retornará o valor False. Talvez seja preciso pesquisar por um momento para encontrar esse valor. Normalmente, ele será incorporado dentro de vários avisos que o acompanham. Por exemplo:

AVISO: ace (entrada de controle de acesso) atl-cs-001\RTCUniversalUserReadOnlyGroup; permitir; ReadProperty; ContainerInherit; Descendentes; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

AVISO: As acEs (entradas de controle de acesso) no objeto "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" não estão prontas. 

Falso 

AVISO: o processamento "Test-CsOUPermission" foi concluído com avisos. Os avisos "2" foram gravados durante essa operação. 

AVISO: Resultados detalhados podem ser encontrados em "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Se Test-CsOUPermission falhar, geralmente significa que a permissão especificada não foi atribuída ao grupo RTCUniversalUserAdmins. Você pode resolver esse problema e atribuir as permissões necessárias usando o Grant-CsOUPermission cmdlet. Por exemplo, este comando concede permissões de UO para usuários, contatos e inetOrgPersons ao grupo RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Para obter mais informações, consulte [o tópico de ajuda para Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).
