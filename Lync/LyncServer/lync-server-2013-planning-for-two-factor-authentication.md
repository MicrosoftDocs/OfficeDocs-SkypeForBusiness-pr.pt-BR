---
title: 'Lync Server 2013: planejando a autenticação de dois fatores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 299d2328ee11ffb893974e48b86922123145ed72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>Planejando a autenticação de dois fatores no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-04-06_

Veja a seguir uma lista de considerações de implantação ao configurar um ambiente do Microsoft Lync Server 2013 para dar suporte à autenticação de dois fatores.

<div>

## <a name="client-support"></a>Suporte de Cliente

As atualizações cumulativas do Lync 2013 para o Lync Server 2013: julho de 2013 do cliente de área de trabalho e todos os clientes móveis atualmente dão suporte à autenticação de dois fatores.

</div>

<div>

## <a name="topology-requirements"></a>Requisitos de topologia

Os clientes são altamente incentivados a implantar a autenticação de dois fatores usando o Lync Server dedicado 2013 com atualizações cumulativas para o Lync Server 2013:2013 de julho a Edge, director e grupos de usuários. Para habilitar a autenticação passiva para usuários do Lync, outros métodos de autenticação devem ser desabilitados para outras funções e serviços, incluindo o seguinte:


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
<th>Função do servidor</th>
<th>Tipo de autenticação a ser desabilitada</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serviço Web</p></td>
<td><p>WebServer</p></td>
<td><p>Diretor</p></td>
<td><p>Kerberos, NTLM e Certificado</p></td>
</tr>
<tr class="even">
<td><p>Serviço Web</p></td>
<td><p>WebServer</p></td>
<td><p>Front-End</p></td>
<td><p>Kerberos, NTLM e Certificado</p></td>
</tr>
<tr class="odd">
<td><p>Proxy</p></td>
<td><p>EdgeServer</p></td>
<td><p>Borda</p></td>
<td><p>Kerberos e NTLM</p></td>
</tr>
<tr class="even">
<td><p>Proxy</p></td>
<td><p>Registrador</p></td>
<td><p>Front-End</p></td>
<td><p>Kerberos e NTLM</p></td>
</tr>
</tbody>
</table>


A menos que esses tipos de autenticação sejam desabilitados no nível de serviço, todas as outras versões do cliente do Lync não poderão entrar com êxito após a habilitação da autenticação de dois fatores na sua implantação.

</div>

<div>

## <a name="lync-service-discovery"></a>Descoberta de serviço do Lync

Os registros DNS usados por clientes internos e/ou externos para descobrir serviços do Lync devem ser configurados para resolver para um Lync Server que não está habilitado para autenticação de dois fatores. Com essa configuração, os usuários de pools do Lync que não estão habilitados para autenticação de dois fatores não serão necessários para inserir um PIN para autenticação, enquanto os usuários de pools do Lync habilitados para a autenticação de dois fatores serão solicitados a digitar o PIN para faz.

</div>

<div>

## <a name="exchange-authentication"></a>Autenticação do Exchange

Os clientes que implantaram a autenticação de dois fatores para o Microsoft Exchange podem descobrir que determinados recursos no cliente do Lync não estão disponíveis. Isso, no momento, é design, pois o cliente do Lync não dá suporte à autenticação de dois fatores para recursos que dependem da integração do Exchange.

</div>

<div>

## <a name="lync-contacts"></a>Contatos do Lync

Os usuários do Lync que estiverem configurados para aproveitar o recurso de repositório de contatos unificado verão que seus contatos não estarão mais disponíveis depois de entrar com a autenticação de dois fatores.

Você deve usar o cmdlet **Invoke-CsUcsRollback** para remover os contatos do usuário existentes do repositório de contatos unificado e armazená-los no Lync Server 2013 antes de habilitar a autenticação de dois fatores.

</div>

<div>

## <a name="skill-search"></a>Pesquisa de Habilidades

Os clientes que tiverem configurado o recurso de pesquisa de habilidades no ambiente do Lync perceberão que esse recurso não funciona quando o Lync estiver habilitado para autenticação de dois fatores. Isso ocorre devido ao projeto, já que o Microsoft SharePoint não é compatível com a autenticação de dois fatores.

</div>

<div>

## <a name="lync-credentials"></a>Credenciais do Lync

Há várias considerações de implantação envolvendo as credenciais do Lync salvas, que podem afetar os usuários configurados para usar a autenticação de dois fatores.

<div>

## <a name="deleting-saved-credentials"></a>Exclusão de Credenciais Salvas

Os usuários do cliente de desktop devem usar a opção **excluir minhas informações de entrada** no cliente do Lync e excluir a pasta do perfil SIP de\\%\\LocalAppData\\%\\Microsoft Office 15,0 Lync antes de tentar se conectar pela primeira vez usando a autenticação de dois fatores.

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

Com o método de autenticação Kerberos ou NTLM, as credenciais do Windows do usuário são usadas automaticamente para fins de autenticação. Em uma implantação típica do Lync Server 2013 na qual Kerberos e/ou NTLM está habilitado para autenticação, os usuários não devem inserir suas credenciais toda vez que entrarem.

Se as credenciais dos usuários forem inadvertidamente solicitadas antes de ser necessário informar o PIN, a chave de registro **DisableNTCredentials** pode estar configurada por engano nos computadores clientes, possivelmente através de uma Política de Grupo.

Para impedir o prompt adicional de credenciais, crie a seguinte entrada do registro na estação de trabalho local ou use o modelo administrativo do Lync para aplicar a todos os usuários de um determinado pool usando a política de Grupo:

HKEY\_local\_Machine\\software\\\\Policies\\Microsoft\\Office\\15,0 Lync

REG\_DWORD: DisableNTCredentials

Value: 0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

Quando um usuário entrar no Lync pela primeira vez, o usuário será solicitado a salvar sua senha. Em caso positivo, o certificado de cliente do usuário fica armazenado no armazenamento de certificado pessoal e as credenciais do Windows do usuário ficam armazenadas no Gerenciador de Credenciais do computador local.

A configuração do registro **SavePassword** deve ser desabilitada quando o Lync estiver configurado para dar suporte à autenticação de dois fatores. Para impedir que os usuários salvem suas senhas, altere a seguinte entrada do registro na estação de trabalho local ou use o modelo administrativo do Lync para aplicar a todos os usuários de um determinado pool usando a política de Grupo:

HKEY\_software\_\\user\\atual Microsoft\\Office\\15,0\\Lync

REG\_DWORD: SavePassword

Value: 0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 Token Replay

O AD FS 2.0 oferece um recurso chamado detecção de repetição de token, pelo qual é possível detectar várias solicitações de token que usam o mesmo token a fim de descartá-las. Quanto este recurso está habilitado, a detecção de repetição de token protege a integridade das solicitações de autenticação tanto no perfil passivo do WS-Federation quanto no perfil de SAML WebSSO, certificando-se de que o mesmo token nunca é usado mais de uma vez.

Esse recurso deve ser habilitado em situações em que há grandes preocupações com a segurança, como quando se usa quiosques. Para obter mais informações sobre a detecção de repetição de token, consulte práticas recomendadas para o planejamento seguro e a [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)implantação do AD FS 2,0 em.

</div>

<div>

## <a name="external-user-access"></a>Acesso de usuários externos

A configuração de um proxy do AD FS ou do proxy reverso para dar suporte à autenticação de dois fatores do Lync de redes externas não é abordada nestes tópicos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

