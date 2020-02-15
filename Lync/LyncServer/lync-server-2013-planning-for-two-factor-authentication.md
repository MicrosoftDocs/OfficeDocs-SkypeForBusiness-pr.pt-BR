---
title: 'Lync Server 2013: planejando a autenticação de dois fatores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba76bbc896c1da2929a584611af0607a51d5afcc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>Planejando a autenticação de dois fatores no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-04-06_

Veja a seguir uma lista de considerações de implantação ao configurar um ambiente do Microsoft Lync Server 2013 para suportar a autenticação de dois fatores.

<div>

## <a name="client-support"></a>Suporte ao cliente

As atualizações cumulativas do Lync 2013 para o Lync Server 2013:2013 julho de atendimento desktop cliente e todos os clientes móveis suportam a autenticação de dois fatores no momento.

</div>

<div>

## <a name="topology-requirements"></a>Requisitos de topologia

É altamente recomendável que os clientes implantem a autenticação de dois fatores usando o Lync Server 2013 dedicado com atualizações cumulativas para o Lync Server 2013: julho de 2013, diretor e pools de usuários. Para habilitar a autenticação passiva para usuários do Lync, outros métodos de autenticação devem ser desabilitados para outras funções e serviços, incluindo o seguinte:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de configuração</th>
<th>Tipo de serviço</th>
<th>Função de servidor</th>
<th>Tipo de autenticação a ser desabilitada</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serviço Web</p></td>
<td><p>WebServer</p></td>
<td><p>Be</p></td>
<td><p>Kerberos, NTLM e certificado</p></td>
</tr>
<tr class="even">
<td><p>Serviço Web</p></td>
<td><p>WebServer</p></td>
<td><p>Front-end</p></td>
<td><p>Kerberos, NTLM e certificado</p></td>
</tr>
<tr class="odd">
<td><p>Acionista</p></td>
<td><p>EdgeServer</p></td>
<td><p>Borda</p></td>
<td><p>Kerberos e NTLM</p></td>
</tr>
<tr class="even">
<td><p>Acionista</p></td>
<td><p>Registrador</p></td>
<td><p>Front-end</p></td>
<td><p>Kerberos e NTLM</p></td>
</tr>
</tbody>
</table>


A menos que esses tipos de autenticação sejam desabilitados no nível de serviço, todas as outras versões do cliente Lync não poderão entrar com êxito quando a autenticação de dois fatores estiver habilitada em sua implantação.

</div>

<div>

## <a name="lync-service-discovery"></a>Descoberta de serviço do Lync

Os registros DNS usados por clientes internos e/ou externos para descobrir os serviços do Lync devem ser configurados para resolver para um Lync Server que não está habilitado para a autenticação de dois fatores. Com essa configuração, os usuários dos pools do Lync que não estão habilitados para a autenticação de dois fatores não serão solicitados a inserir um PIN para autenticar, enquanto os usuários dos pools do Lync habilitados para a autenticação de dois fatores serão solicitados a inserir seu PIN para fornecer.

</div>

<div>

## <a name="exchange-authentication"></a>Autenticação do Exchange

Os clientes que implantaram a autenticação de dois fatores para o Microsoft Exchange podem achar que determinados recursos no cliente do Lync não estão disponíveis. No momento, esse é o design, já que o cliente do Lync não oferece suporte à autenticação de dois fatores para recursos que dependem da integração do Exchange.

</div>

<div>

## <a name="lync-contacts"></a>Contatos do Lync

Os usuários do Lync que estão configurados para aproveitar o recurso de repositório unificado de contatos descobrirão que seus contatos não estão mais disponíveis após entrar com a autenticação de dois fatores.

Você deve usar o cmdlet **Invoke-CsUcsRollback** para remover os contatos de usuário existentes do repositório unificado de contatos e armazená-los no Lync Server 2013 antes de habilitar a autenticação de dois fatores.

</div>

<div>

## <a name="skill-search"></a>Pesquisa de habilidades

Os clientes que tiverem configurado o recurso de pesquisa de habilidades em seus ambientes do Lync acharão que esse recurso não funciona quando o Lync estiver habilitado para a autenticação de dois fatores. Isso ocorre por design, já que o Microsoft SharePoint não oferece suporte à autenticação de dois fatores no momento.

</div>

<div>

## <a name="lync-credentials"></a>Credenciais do Lync

Há várias considerações de implantação envolvendo as credenciais salvas do Lync que podem afetar os usuários configurados para usar a autenticação de dois fatores.

<div>

## <a name="deleting-saved-credentials"></a>Excluir credenciais salvas

Os usuários do cliente da área de trabalho devem usar a opção **excluir minhas informações de entrada** no cliente do Lync e excluir a pasta de perfil\\SIP\\de\\%\\LocalAppData% Microsoft Office 15,0 Lync antes de tentar assinar pela primeira vez usando a autenticação de dois fatores.

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

Com o método de autenticação Kerberos ou NTLM, as credenciais do Windows do usuário são usadas automaticamente para autenticação. Em uma implantação típica do Lync Server 2013, onde Kerberos e/ou NTLM está habilitado para autenticação, os usuários não devem inserir suas credenciais toda vez que entrarem.

Se os usuários forem solicitados involuntariamente por credenciais antes de serem solicitadas a inserir o PIN, a chave do registro **DisableNTCredentials** poderá ser configurada acidentalmente nos computadores cliente, possivelmente por meio da política de grupo.

Para impedir o prompt adicional para credenciais, crie a seguinte entrada de registro na estação de trabalho local ou use o modelo administrativo do Lync para aplicar a todos os usuários de um determinado pool usando a política de Grupo:

HKEY\_local\_Machine\\software\\\\Policies\\Microsoft\\Office\\15,0 Lync

REG\_DWORD: DisableNTCredentials

Valor: 0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

Quando um usuário entra no Lync pela primeira vez, o usuário é solicitado a salvar sua senha. Se for selecionada, esta opção permitirá que o certificado de cliente do usuário seja armazenado no repositório de certificados pessoais e as credenciais do Windows do usuário sejam armazenadas no Gerenciador de credenciais do computador local.

A configuração do registro **SavePassword** deve ser desabilitada quando o Lync estiver configurado para oferecer suporte à autenticação de dois fatores. Para impedir que os usuários salvem suas senhas, altere a entrada de registro a seguir na estação de trabalho local ou use o modelo administrativo do Lync para aplicar a todos os usuários de um determinado pool usando a política de Grupo:

HKEY\_Current\_USER\\software\\Microsoft\\Office\\15,0\\Lync

REG\_DWORD: SavePassword

Valor: 0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>Repetição de token do AD FS 2,0

O AD FS 2,0 fornece um recurso referido como detecção de repetição de token, pelo qual várias solicitações de token que usam o mesmo token podem ser detectadas e descartadas. Quando esse recurso está habilitado, a detecção de repetição de token protege a integridade das solicitações de autenticação no perfil passivo do WS-Federation e no perfil de webs do SAML, garantindo que o mesmo token nunca seja usado mais de uma vez.

Esse recurso deve ser habilitado em situações em que a segurança é uma preocupação muito alta, como ao usar quiosques. Para obter mais informações sobre a detecção de repetição de token, consulte práticas recomendadas para o planejamento e a implantação [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)seguros do AD FS 2,0 em.

</div>

<div>

## <a name="external-user-access"></a>Acesso de usuário externo

A configuração de um proxy do AD FS ou do proxy reverso para dar suporte à autenticação de dois fatores do Lync de redes externas não é abordada nesses tópicos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

