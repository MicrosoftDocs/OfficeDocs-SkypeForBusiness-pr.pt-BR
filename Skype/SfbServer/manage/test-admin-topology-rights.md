---
title: Testando direitos de topologia de administrador no Skype for Business Server
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
description: Como testar direitos de topologia no Skype for Business Server
ms.openlocfilehash: a6bbebd44387911fdb69679a16ab052c673f0b10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832841"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Testando direitos de topologia de administrador no Skype for Business Server

| | |
|--|--|
|Agenda de verificação|Após a implantação inicial do Skype for Business Server. Conforme necessário, se surgirem problemas relacionados à permissão.|
|Ferramenta de teste|Windows PowerShell|
|Permissões obrigatórias|Quando executados localmente usando o Shell de Gerenciamento do Skype for Business Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.<br/><br/>Ao executar usando uma instância remota do Windows PowerShell, os usuários devem ter uma função RBAC com permissão para executar o Test-CsSetupPermission cmdlet. Para ver uma lista de todas as funções do RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Descrição

Por padrão, somente administradores de domínio podem habilitar uma topologia do Skype for Business Server e fazer grandes alterações na infraestrutura do Skype for Business Server. Isso não será um problema, desde que seus administradores de domínio e seus administradores do Skype for Business Server sejam os mesmos. Em muitas organizações, os administradores do Skype for Business Server não têm direitos administrativos para todo o domínio. Por padrão, isso significa que esses administradores (definidos como membros do grupo RTCUniversalServerAdmins) não podem fazer alterações na topologia do Skype for Business Server. Para conceder aos membros do grupo RTCUniversalServerAdmins o direito de fazer alterações na topologia, você deve atribuir as permissões necessárias do Active Directory usando o cmdlet [Grant-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)
 
O Test-CsSetupPermission cmdlet verifica se as permissões necessárias para instalar o Skype for Business Server ou um de seus componentes estão configuradas no contêiner do Active Directory especificado. Se as permissões não são atribuídas, você pode executar o cmdlet Grant-CsSetupPermission para dar aos membros do grupo RTCUniversalServerAdmins o direito de instalar e habilitar o Skype for Business Server.

## <a name="running-the-test"></a>Executando o teste

Para determinar se as permissões de instalação são atribuídas a um contêiner do Active Directory, chame o Test-CsSetupPermission cmdlet. Especifique o nome diferenciado do contêiner a ser verificado. Por exemplo, este comando verifica as permissões de instalação no contêiner ou=CsServers,dc=litwareinc,dc=com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se Test-CsSetupPermission determinar que as permissões necessárias já foram definidas em um contêiner do Active Directory, o cmdlet retornará o valor True:

Verdadeiro 

Se as permissões não estão definidas, Test-CsSetupPermission retornará o valor False. Observe que esse valor normalmente será incluído em muitas mensagens de aviso. Por exemplo:

AVISO: Entrada de controle de acesso (ACE) atl-cs-001\RTCUniversalServerAdmins; Permitir; ExtendedRight; Nenhum; Nenhum; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

AVISO: as ACEs (entradas de controle de acesso) no objeto "CN=Computers,DC=litwareinc,DC=com" não estão prontas. 

Falso 

AVISO: o processamento "Test-CsSetupPermission" foi concluído com avisos. Os avisos "2" foram gravados durante essa operação. 

AVISO: Resultados detalhados podem ser encontrados em "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Embora existam raras exceções, se Test-CsSetupPermission falhar, isso geralmente significa que as permissões de configuração não são atribuídas para o contêiner do Active Directory especificado. Essas permissões podem ser atribuídas usando o Grant-CsSetupPermission cmdlet. Por exemplo, este comando concede permissões de configuração para o contêiner Computadores no domínio litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)
