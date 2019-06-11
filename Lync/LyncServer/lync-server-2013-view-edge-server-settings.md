---
title: 'Lync Server 2013: exibir configurações do servidor de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972a5861af803dbaf66843883595c446345ac29a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a>Exibir as configurações do servidor de borda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-20_

As configurações gerais do servidor de borda devem ser analisadas nos dados do banco de dados de gerenciamento de configuração, para ajudar a garantir que todas as alterações tenham sido documentadas de acordo com os procedimentos definidos de controle de alterações.

Verificações adicionais podem incluir aquelas descritas nas seguintes seções:

<div>

## <a name="verify-the-allow-and-block-lists"></a>Verificar as listas permitir e bloquear

Verifique as listas "permitir" e "bloquear" do URI SIP para domínios federados – para determinar se os namespaces listados ainda são válidos.

Você pode usar o Windows PowerShell para ver as listas autorizadas e bloqueadas. Para examinar os domínios na lista de domínios permitidos, execute o seguinte comando do Windows PowerShell:

`Get-CsAllowedDomain`

Esse comando retorna informações semelhantes a esta para os domínios na lista de domínios permitidos:

Identidade: contoso.com

Domínio: contoso.com

ProxyFqdn :

Come

MarkForMonitoring: false

Come

Para revisar os domínios na lista de domínios bloqueados, use este comando:

`Get-CsBlockedDomain`

Por sua vez, você receberá informações como essa para cada domínio bloqueado:

Identidade: tailspintoys.com

Domínio: tailspintoys.com

O Windows PowerShell também permite que você verifique se você pode se conectar a domínios na lista de domínios permitidos. Por exemplo, esse comando verifica a conexão entre o servidor de borda (o TargetFqdn) e o domínio federado contoso.com:

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

E esse comando verifica a conexão entre o servidor de borda e todos os domínios encontrados na lista de domínios permitidos:

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>Verificar se vários servidores de borda são idênticos

Se vários servidores de borda forem implantados em uma matriz de carga balanceada, recomendamos verificar se todos os servidores de borda na matriz estão configurados da mesma maneira.

Você pode visualizar as configurações dos servidores de borda no painel de detalhes da extensão 2013 do Lync Server para o snap-in Gerenciamento do computador.

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[Get-CsBlockedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

