---
title: 'Lync Server 2013: exibir configurações do servidor de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e978e28ea2c9d64a842c40237f1e5943c30d0a41
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a>Exibir configurações do servidor de borda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-20_

As configurações de servidor de borda geral devem ser analisadas em relação aos dados do banco de dados de gerenciamento de configuração para ajudar a garantir que todas as alterações tenham sido documentadas de acordo com os procedimentos definidos de controle de alterações.

As verificações adicionais podem incluir as descritas nas seguintes seções:

<div>

## <a name="verify-the-allow-and-block-lists"></a>Verificar as listas de permissões e bloqueios

Verifique o URI SIP "permitir" e "bloquear" listas para domínios federados, para determinar se os namespaces listados ainda são válidos.

Você pode usar o Windows PowerShell para exibir as listas permitidas e bloqueadas. Para revisar os domínios na lista de domínios permitidos, execute o seguinte comando do Windows PowerShell:

`Get-CsAllowedDomain`

Esse comando retorna informações semelhantes a estas para os domínios na lista de domínios permitidos:

Identidade: contoso.com

Domínio: contoso.com

ProxyFqdn

Retire

MarkForMonitoring: falso

Retire

Para revisar os domínios na lista de domínios bloqueados, use este comando:

`Get-CsBlockedDomain`

Por sua vez, você receberá informações como esta para cada domínio bloqueado:

Identidade: tailspintoys.com

Domínio: tailspintoys.com

O Windows PowerShell também permite verificar se você pode se conectar aos domínios da sua lista de domínios permitidos. Por exemplo, este comando verifica a conexão entre o servidor de borda (o TargetFqdn) e o domínio federado contoso.com:

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

E este comando verifica a conexão entre o servidor de borda e todos os domínios encontrados na sua lista de domínios permitidos:

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>Verificar se vários servidores de borda são idênticos

Se vários servidores de borda forem implantados em uma matriz com balanceamento de carga, recomendamos verificar se todos os servidores de borda na matriz estão configurados da mesma maneira.

Você pode exibir configurações para servidores de borda no painel de detalhes da extensão do Lync Server 2013 para o snap-in Gerenciamento do computador.

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

