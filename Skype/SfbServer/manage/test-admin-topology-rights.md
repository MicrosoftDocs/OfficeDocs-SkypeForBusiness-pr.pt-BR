---
title: Testar direitos de topologia de administrador em Skype for Business Server
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
description: Como testar direitos de topologia em Skype for Business Server
ms.openlocfilehash: 2da77957baaa510ef7669fb6a980de2aacf428a4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759713"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Testar direitos de topologia de administrador em Skype for Business Server

|&nbsp; |&nbsp; |
|--|--|
|Agendamento de verificação|Após a implantação Skype for Business Server inicial. Conforme necessário se surgirem problemas relacionados à permissão.|
|Ferramenta de teste|Windows PowerShell|
|Permissões obrigatórias|Quando executado localmente usando o Shell de Gerenciamento Skype for Business Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.<br/><br/>Quando executado usando uma instância remota de Windows PowerShell, os usuários devem ter uma função RBAC com permissão para executar o cmdlet Test-CsSetupPermission. Para ver uma lista de todas as funções do RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt Windows PowerShell:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Descrição

Por padrão, somente os administradores de domínio podem habilitar uma topologia Skype for Business Server e fazer grandes alterações na infraestrutura Skype for Business Server de segurança. Isso não será um problema, desde que seus administradores de domínio e seus Skype for Business Server administradores de Skype for Business Server sejam um e o mesmo. Em muitas organizações, Skype for Business Server administradores não têm direitos administrativos para todo o domínio. Por padrão, isso significa que esses administradores (definidos como membros do grupo RTCUniversalServerAdmins) não podem fazer Skype for Business Server de topologia. Para conceder aos membros do grupo RTCUniversalServerAdmins o direito de fazer alterações de topologia, você deve atribuir as permissões necessárias do Active Directory usando o cmdlet [Grant-CsSetupPermission.](/powershell/module/skype/Grant-CsSetupPermission)
 
O Test-CsSetupPermission cmdlet verifica se as permissões necessárias para instalar o Skype for Business Server ou um de seus componentes estão configuradas no contêiner do Active Directory especificado. Se as permissões não são atribuídas, você pode executar o cmdlet Grant-CsSetupPermission para dar aos membros do grupo RTCUniversalServerAdmins o direito de instalar e habilitar Skype for Business Server.

## <a name="running-the-test"></a>Executando o teste

Para determinar se as permissões de instalação são atribuídas a um contêiner do Active Directory, chame o cmdlet Test-CsSetupPermission de configuração. Especifique o nome diferenciado do contêiner a ser verificado. Por exemplo, este comando verifica as permissões de instalação no contêiner ou=CsServers,dc=litwareinc,dc=com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Para obter mais informações, consulte o tópico de ajuda do cmdlet [Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se Test-CsSetupPermission determinar que as permissões necessárias já foram definidas em um contêiner do Active Directory, o cmdlet retornará o valor True:

Verdadeiro 

Se as permissões não estão definidas, Test-CsSetupPermission retornará o valor False. Observe que esse valor normalmente será incluído em muitas mensagens de aviso. Por exemplo:

AVISO: Ace (Entrada de controle de acesso) atl-cs-001\RTCUniversalServerAdmins; Permitir; ExtendedRight; Nenhum; Nenhum; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

AVISO: As entradas de controle de acesso (ACEs) no objeto "CN=Computers,DC=litwareinc,DC=com" não estão prontas. 

Falso 

AVISO: o processamento "Test-CsSetupPermission" foi concluído com avisos. Avisos "2" foram gravados durante essa executar. 

AVISO: Os resultados detalhados podem ser encontrados em "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Embora existam raras exceções, se Test-CsSetupPermission isso normalmente significa que as permissões de instalação não são atribuídas ao contêiner especificado do Active Directory. Essas permissões podem ser atribuídas usando o cmdlet Grant-CsSetupPermission. Por exemplo, este comando concede permissões de instalação ao contêiner Computers no domínio litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Para obter mais informações, consulte o tópico de ajuda do cmdlet [Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)